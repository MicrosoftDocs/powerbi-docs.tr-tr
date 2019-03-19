---
title: Şirket içi veri kaynaklarında çoklu oturum açma (SSO) için Kerberos’u kullanma
description: Power BI'dan şirket içi veri kaynaklarına bağlanmak için SSO'yu etkinleştirmek üzere ağ geçidinizi Kerberos ile yapılandırın
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2018
LocalizationGroup: Gateways
ms.openlocfilehash: eb50d8096c448e1a01533a7d8570e9dcc716ef23
ms.sourcegitcommit: 8fda7843a9f0e8193ced4a7a0e5c2dc5386059a6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/18/2019
ms.locfileid: "58174994"
---
# <a name="use-kerberos-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Power BI’dan şirket içi veri kaynaklarına kadar SSO (çoklu oturum açma) için Kerberos’u kullanma

[Kerberos kısıtlanmış temsili](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) kullanarak, sorunsuz çoklu oturum açma (SSO) bağlantısını etkinleştirin. SSO'yu etkinleştirmek, Power BI raporlarının ve panolarının şirket içi kaynaklardan alınan verileri yenilemesini kolaylaştırır.

## <a name="supported-data-sources"></a>Desteklenen veri kaynakları

Şu an için aşağıdaki veri kaynakları desteklenmektedir:

* SQL Server
* SAP HANA
* SAP BW
* Teradata
* Spark
* Impala

[Security Assertion Markup Language (SAML)](service-gateway-sso-saml.md) ile SAP HANA desteği de sunuyoruz.

### <a name="sap-hana"></a>SAP HANA

SAP HANA için SSO'yu etkinleştirmek için öncelikle şu adımları gerçekleştirin:

* SAP HANA sunucusunun, gerekli olan en düşük sürümü çalıştırdığından emin olun. Bu sürüm, SAP HANA sunucusu platform düzeyinize bağlıdır:
  * [HANA 2 SPS 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
  * [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
  * [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)
* Ağ geçidi makinesine SAP'nin en son HANA ODBC sürücüsünü yükleyin.  Yükleyebileceğiniz minimum sürüm Ağustos 2017'de kullanıma sunulan HANA ODBC 2.00.020.00 sürümüdür.

Kerberos kullanarak SAP HANA için SSO’yu ayarlama hakkında daha fazla bilgi almak için SAP HANA Security Guide’daki (SAP HANA Güvenlik Rehberi) [Single Sign-on Using Kerberos](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/1885fad82df943c2a1974f5da0eed66d.html) (Kerberos Kullanarak Çoklu Oturum Açma) konusuna bakın. Aynı sayfada bulunan bağlantılara da göz atın (özellikle SAP Note 1837331 – HOWTO HANA DBSSO Kerberos/Active Directory).

## <a name="prepare-for-kerberos-constrained-delegation"></a>Kerberos kısıtlanmış temsili için hazırlanın

Kerberos kısıtlanmış temsilinin düzgün bir şekilde çalışması için, hizmet hesaplarındaki *Hizmet Asıl Adlarının* (SPN) ve temsilci seçme ayarlarının da dahil olduğu belirli öğeleri yapılandırmanız gerekir.

### <a name="prerequisite-1-install-and-configure-the-microsoft-on-premises-data-gateway"></a>1. Önkoşul: Microsoft şirket içi veri ağ geçidini yükleme ve yapılandırma

Şirket içi veri ağ geçidinin bu sürümü, mevcut ağ geçitlerinin ayarlarını devralma özelliğinin yanı sıra yerinde yükseltmeyi destekler.

### <a name="prerequisite-2-run-the-gateway-windows-service-as-a-domain-account"></a>2. Önkoşul: Ağ geçidi Windows hizmetini bir etki alanı hesabı olarak çalıştırma

Standart bir yüklemede, ağ geçidi bir makine yerel hizmet hesabı (özel olarak belirtmek gerekirse, *NT Service\PBIEgwService*) olarak çalıştırılır.

![Hizmet hesabı ekran görüntüsü](media/service-gateway-sso-kerberos/service-account.png)

Azure Active Directory (Azure AD) örneğiniz (Azure AD DirSync/Connect kullanılarak) yerel Active Directory örneğiniz ile eşitlenmediği sürece, Kerberos kısıtlanmış temsilinin etkinleştirilebilmesi için ağ geçidinin bir etki alanı hesabı olarak çalıştırılması gerekir. Etki alanı hesabına geçmek için bu makalenin [Ağ geçidini bir etki alanı hesabına geçirme](#switch-the-gateway-to-a-domain-account) bölümüne bakın.

> [!NOTE]
> Azure AD Connect yapılandırıldıysa ve kullanıcı hesapları eşitlendiyse, ağ geçidi hizmetinin çalışma zamanında yerel Azure AD aramaları yapması gerekmez. Ağ geçidi hizmeti için yerel hizmet SID'sini kullanabilirsiniz (etki alanı hesabı gerektirmek yerine). Bu belgede açıklanan Kerberos kısıtlanmış temsili yapılandırmasına ilişkin adımlar, söz konusu yapılandırmaya yönelik olanlarla aynıdır. Bunlar, etki alanı hesabının yerine Azure AD’deki ağ geçidinin bilgisayar nesnesine uygulanır.

### <a name="prerequisite-3-have-domain-admin-rights-to-configure-spns-setspn-and-kerberos-constrained-delegation-settings"></a>3. Önkoşul: SPN'leri (SetSPN) ve Kerberos kısıtlanmış temsili ayarlarını yapılandırmak için etki alanı yöneticisi haklarını alma

Bir etki alanı yöneticisinin SPN'leri ve Kerberos temsili ayarlarını yapılandırma haklarını (etki alanı yöneticisi hakları gerektirmeden) geçici veya kalıcı olarak başka bir kişiye vermesi önerilmez. Aşağıdaki bölümde, önerilen yapılandırma adımlarını daha ayrıntılı bir biçimde inceleyeceğiz.

## <a name="configure-kerberos-constrained-delegation-for-the-gateway-and-data-source"></a>Ağ geçidi ve veri kaynağı için Kerberos kısıtlanmış temsilini yapılandırma

Etki alanı yöneticisi olarak, ağ geçidi hizmeti etki alanı hesabı için bir SPN yapılandırın ve ağ geçidi hizmeti etki alanı hesabında temsilci seçme ayarlarını yapılandırın.

### <a name="configure-an-spn-for-the-gateway-service-account"></a>Ağ geçidi hizmet hesabı için SPN yapılandırma

Öncelikle, ağ geçidi hizmet hesabı olarak kullanılan etki alanı hesabı için bir SPN yapılandırılmış olup olmadığını belirleyin:

1. **Active Directory Kullanıcıları ve Bilgisayarları**'nı etki alanı yöneticisi olarak açın.

2. Etki alanına sağ tıklayın, **Bul** seçeneğini belirleyin ve ağ geçidi hizmet hesabına ilişkin hesap adını girin.

3. Arama sonucunda, ağ geçidi hizmet hesabına sağ tıklayın ve **Özellikler**'i seçin.

4. **Özellikler** iletişim kutusunda **Temsilci Seçme** sekmesi görünüyorsa, önceden SPN oluşturulmuştur. Temsilci seçme ayarlarını yapılandırmaya geçebilirsiniz.

    **Özellikler** iletişim kutusunda **Temsilci Seçme** sekmesi yoksa, bu hesapta kendiniz bir SPN oluşturabilirsiniz. Bu işlem **Temsilci Seçme** sekmesini ekler. Windows ile birlikte gelen [setspn aracını](https://technet.microsoft.com/library/cc731241.aspx) kullanın. (SPN'yi oluşturmak için etki alanı yöneticisi haklarına sahip olmanız gerekir.)

    Örneğin, ağ geçidi hizmet hesabının "PBIEgwTest\GatewaySvc", ağ geçidi hizmetinin çalıştırıldığı makinenin adının ise **Machine1** olduğunu varsayalım. Bu örnekteki makineye ilişkin ağ geçidi hizmet hesabına yönelik SPN'yi ayarlamak için aşağıdaki komutu çalıştırın:

    ![setspn komutu görüntüsü](media/service-gateway-sso-kerberos/set-spn.png)

    Adım tamamlandığına göre, temsilci seçme ayarlarını yapılandırmaya geçebiliriz.

### <a name="configure-delegation-settings-on-the-gateway-service-account"></a>Ağ geçidi hizmet hesabında temsilci seçme ayarlarını yapılandırma

Ağ geçidi hizmet hesabındaki temsilci seçme ayarları ikinci yapılandırma gereksinimini oluşturur. Bu adımları uygulamak için kullanabileceğiniz birçok araç vardır. Burada, dizindeki bilgileri yönetmek ve yayımlamak için, bir Microsoft Yönetim Konsolu (MMC) ek bileşeni olan Active Directory Kullanıcıları ve Bilgisayarları'nı kullanacağız. Bu özellik etki alanı denetleyicilerinde varsayılan olarak bulunur. Bunu diğer makinelerdeki Windows Özellikleri yapılandırması aracılığıyla da etkinleştirebilirsiniz.

Protokol geçişi ile Kerberos kısıtlanmış temsilini yapılandırmamız gerekir. Kısıtlanmış temsilde, temsilci olarak seçeceğiniz hizmetleri açıkça belirtmeniz gerekir. Örneğin, ağ geçidi hizmet hesabından yapılan temsilci seçme çağrılarını yalnızca SQL Server veya SAP HANA sunucusu kabul eder.

Bu bölümde, temel alınan veri kaynaklarınız (SQL Server, SAP HANA, Teradata ve Spark vb.) için zaten SPN'ler yapılandırmış olduğunuz varsayılır. Söz konusu veri kaynağı sunucusu SPN'lerinin nasıl yapılandırılacağını öğrenmek için ilgili veritabanı sunucusuna yönelik teknik belgelere bakın. [What SPN does your app require?](https://blogs.msdn.microsoft.com/psssql/2010/06/23/my-kerberos-checklist/) (Uygulamanız hangi SPN’yi gerektiriyor?) blog gönderisine de göz atabilirsiniz.

Sıradaki adımlar için bir ağ geçidi makinesi ve SQL Server çalıştıran bir veritabanı olmak üzere iki makine içeren bir şirket içi ortamını kullanacağız. Bu örnek için ayrıca şu ayarların ve adların geçerli olduğunu varsayacağız:

* Ağ geçidi makine adı: **PBIEgwTestGW**
* Ağ geçidi hizmeti hesabı: **PBIEgwTest\GatewaySvc** (hesap görünen adı: Gateway Connector)
* SQL Server veri kaynağı makine adı: **PBIEgwTestSQL**
* SQL Server veri kaynağı hizmet hesabı: **PBIEgwTest\SQLService**

Temsilci seçme ayarlarını yapılandırmak için şunları yapabilirsiniz:

1. **Active Directory Kullanıcıları ve Bilgisayarları**'nı etki alanı yöneticisi haklarıyla açın.

2. Ağ geçidi hizmet hesabına (**PBIEgwTest\GatewaySvc**) sağ tıklayın ve **Özellikler**'i seçin.

3. **Temsilci Seçme** sekmesini seçin.

4. **Bu bilgisayara yalnızca belirtilen hizmetlere temsilci seçmek için güven** > **Herhangi bir kimlik doğrulama protokolünü kullan** seçeneğini belirleyin.

6. **Bu hesabın temsilci seçilen kimlik bilgilerini sunacağı hizmetler** bölümünde **Ekle**'yi seçin.

7. Yeni iletişim kutusunda **Kullanıcı/Bilgisayar**'ı seçin.

8. SQL Server veri kaynağı için hizmet hesabını (**PBIEgwTest\SQLService**) girin ve **Tamam**'ı seçin.

9. Veritabanı sunucusu için oluşturduğunuz SPN'yi seçin. Örneğimizde SPN, **MSSQLSvc** ile başlar. Veritabanı hizmeti için hem FQDN hem de NetBIOS SPN'sini eklediyseniz her ikisini de seçin. Yalnızca birini görüyor olabilirsiniz.

10. **Tamam**'ı seçin. SPN'nin listede görünmesi gerekir.

    İsterseniz **Genişletilmiş**'i seçerek hem FQDN hem de NetBIOS SPN'sini listede görebilirsiniz. **Genişletilmiş**'i seçtiyseniz iletişim kutusu aşağıdakine benzer şekilde görünür. **Tamam**'ı seçin.

    ![Ağ Geçidi Bağlayıcısı Özellikleri İletişim Kutusu Ekran Görüntüsü](media/service-gateway-sso-kerberos/gateway-connector-properties.png)

Son olarak, ağ geçidi hizmetinin çalıştırıldığı makinede (örneğimizde **PBIEgwTestGW**), ağ geçidi hizmet hesabına **Kimlik doğrulamasından sonra istemcinin özelliklerini al** yerel ilkesini uygulamanız gerekir. Bunu gerçekleştirmek ve doğrulamak için Yerel Grup İlkesi Düzenleyicisi'ni (**gpedit**) kullanmanız gerekir.

1. Ağ geçidi makinesinde şunu çalıştırın: *gpedit.msc*.

1. **Yerel Bilgisayar İlkesi** > **Bilgisayar Yapılandırması** > **Windows Ayarları** > **Güvenlik Ayarları** > **Yerel İlkeler** > **Kullanıcı Hakları Ataması** seçeneğine gidin.

    ![Yerel Bilgisayar İlkesi klasör yapısı ekran görüntüsü](media/service-gateway-sso-kerberos/user-rights-assignment.png)

1. **Kullanıcı Hakları Ataması**’nın altındaki ilke listesinden **Kimlik doğrulamasından sonra istemcinin özelliklerini al** seçeneğini belirleyin.

    ![İstemci ilkesinin özelliklerini alma ekran görüntüsü](media/service-gateway-sso-kerberos/impersonate-client.png)

    Sağ tıklayın ve **Özellikler**’i açın. Hesap listesini kontrol edin. Ağ geçidi hizmet hesabını (**PBIEgwTest\GatewaySvc**) içermesi gerekir.

1. **Kullanıcı Hakları Ataması**’nın altındaki ilke listesinden **İşletim sisteminin parçası gibi davran (SeTcbPrivilege)** seçeneğini belirleyin. Ağ geçidi hizmet hesabının da hesap listesinde yer aldığından emin olun.

1. **Şirket içi veri ağ geçidi** hizmet işlemini yeniden başlatın.

SAP HANA kullanıyorsanız az da olsa performans artışı sağlayabilecek aşağıdaki ek adımları gerçekleştirmenizi öneririz.

1. Ağ geçidi yükleme dizininde şu yapılandırma dosyasını bulun ve açın: *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*.

1. *FullDomainResolutionEnabled* özelliğini bulun ve değerini *True* olarak değiştirin.

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

## <a name="run-a-power-bi-report"></a>Bir Power BI raporunu çalıştırma

Tüm yapılandırma adımları tamamlandıktan sonra, veri kaynağını yapılandırmak için Power BI'daki **Ağ Geçidini Yönet** sayfasını kullanabilirsiniz. Ardından, **Gelişmiş Ayarlar** bölümünden SSO'yu etkinleştirin, söz konusu veri kaynağına bağlı raporlar ve veri kümeleri yayımlayın.

![Gelişmiş ayarlar seçeneği ekran görüntüsü](media/service-gateway-sso-kerberos/advanced-settings.png)

Bu yapılandırma çoğu durumda çalışır. Ancak, ortamınıza bağlı olarak Kerberos ile farklı yapılandırmalar da söz konusu olabilir. Rapor hala yüklenmiyorsa sorunun daha ayrıntılı bir şekilde incelenmesi için etki alanı yöneticinizle iletişime geçin.

## <a name="switch-the-gateway-to-a-domain-account"></a>Ağ geçidini bir etki alanı hesabına geçirme

Gerekirse, **Şirket içi veri ağ geçidi** kullanıcı arabirimini kullanarak ağ geçidini, yerel bir hizmet hesabı yerine etki alanı hesabı olarak çalıştırılacak şekilde değiştirebilirsiniz. Aşağıdaki adımları uygulayın:

1. **Şirket içi veri ağ geçidi** yapılandırma aracını açın.

   ![Ağ geçidi masaüstü uygulamasını çalıştırma seçeneği ekran görüntüsü](media/service-gateway-sso-kerberos/gateway-desktop-app.png)

2. Ana sayfadaki **Oturum aç** düğmesini seçin ve Power BI hesabınızla oturum açın.

3. Oturum açma işlemi tamamlandıktan sonra **Hizmet Ayarları** sekmesini seçin.

4. **Hesabı değiştir** seçeneğini belirleyerek destekli kılavuzu başlatın.

   ![Hesap değiştir seçeneği vurgulanmış olarak şirket içi veri ağ geçidi masaüstü uygulaması ekran görüntüsü](media/service-gateway-sso-kerberos/change-account.png)

## <a name="configure-sap-bw-for-sso"></a>SSO için SAP BW’yu Yapılandırma

Kerberos'un bir ağ geçidiyle nasıl çalıştığını anladığınıza göre artık SAP Business Warehouse (SAP BW) ortamınız için SSO yapılandırması gerçekleştirebilirsiniz. Aşağıdaki adımlarda bu makalenin önceki bölümlerinde anlatılan şekilde [Kerberos kısıtlanmış temsili için hazırlandığınız](#prepare-for-kerberos-constrained-delegation) kabul edilmektedir.

Bu kılavuz mümkün olduğunca kapsamlı olmaya çalışır. Bu adımlardan bazılarını önceden tamamladıysanız atlayabilirsiniz. Örneğin, SAP BW sunucunuz için zaten bir hizmet kullanıcısı oluşturmuş olabilir ve kullanıcıya bir SPN eşlemiş veya `gsskrb5` kitaplığını zaten yüklemiş olabilirsiniz.

### <a name="set-up-gsskrb5-on-client-machines-and-the-sap-bw-server"></a>İstemci makinelerinde ve SAP BW sunucusunda gsskrb5 kurulumu

> [!NOTE]
> `gsskrb5` artık SAP tarafından etkin olarak desteklenmiyor. Daha fazla bilgi için bkz. [SAP Notu 352295](https://launchpad.support.sap.com/#/notes/352295). `gsskrb5`'in veri ağ geçidinden SAP BW İleti Sunucularına yönelik SSO bağlantılarına izin vermediğine de dikkat edin. Yalnızca SAP BW Application Server’larla bağlantı kurulabilir.

Ağ geçidi üzerinden bir SSO bağlantısını tamamlamak için `gsskrb5`, hem istemci hem de sunucu tarafından kullanımda olmalıdır. Ortak Şifreleme Kitaplığı (sapcrypto) şu anda desteklenmemektedir.

1. `gsskrb5` - `gx64krb5`’i [SAP Note 2115486](https://launchpad.support.sap.com/) sayfasından indirin (SAP s-user gerekir). gsskrb5.dll ve gx64krb5.dll dosyalarının en az 1.0.11.x sürümüne sahip olduğunuzdan emin olun.

1. Kitaplığı ağ geçidi makinenizde ağ geçidi örneğinizin erişebileceği bir konuma yerleştirin (SAP Logon kullanarak SSO bağlantısını test etmek istiyorsanız SAP GUI tarafından da erişilebilir olması gerekir).

1. Bir kopyasını da SAP BW sunucusu makinenize, SAP BW sunucusu tarafından erişilebilecek bir konuma yerleştirin.

1. İstemci ve sunucu makinelerinde `SNC\_LIB` ve `SNC\_LIB\_64` ortam değişkenlerini sırasıyla gx64krb5.dll ve gx64krb5.dll dosyalarının konumlarını gösterecek şekilde ayarlayın.

### <a name="create-a-sap-bw-service-user-and-enable-snc-communication"></a>SAP BW hizmeti kullanıcısı oluşturma ve SNC iletişimini etkinleştirme

Tamamladığınız ağ geçidi yapılandırmasına ek olarak gerçekleştirmeniz gereken SAP BW hizmetine özgü birkaç adım vardır. Belgenin [Ağ geçidi hizmet hesabında temsilci seçme ayarlarını yapılandırma](#configure-delegation-settings-on-the-gateway-service-account) bölümünde bağlı veri kaynaklarınız için SPN’leri yapılandırmış olduğunuz kabul edilmektedir. Bu SAP BW yapılandırmasını tamamlamak için:

1. Active Directory Etki Alanı Denetleyicisi sunucusunda, Active Directory ortamınızdaki SAP BW Application Server için bir hizmet kullanıcısı (başlangıçta normal bir Active Directory kullanıcısı) oluşturun. Ardından bu kullanıcıya bir SPN atayın.

    SAP, SPN’nin `SAP/` ile başlatılmasını önerir ancak `HTTP/` gibi diğer ön eklerin kullanılması da mümkündür. `SAP/` ön ekinden sonra ne geldiğini istediğiniz şekilde belirleyebilirsiniz. Seçeneklerden biri, SAP BW sunucusunun hizmet kullanıcısına ait kullanıcı adını kullanmaktır. Örneğin, hizmet kullanıcınız olarak `BWServiceUser@\<DOMAIN\>` oluşturursanız, SPN olarak `SAP/BWServiceUser` kullanabilirsiniz. SPN eşlemesini ayarlama yöntemlerinden biri setspn komutudur. Örneğin, yeni oluşturduğunuz hizmet kullanıcısında SPN’yi ayarlamak için Etki Alanı Denetleyicisi makinesindeki bir komut penceresinden şu komutu çalıştırmanız gerekir: `setspn -s SAP/ BWServiceUser DOMAIN\ BWServiceUser`. Daha fazla bilgi için SAP BW belgelerine bakın.

1. Hizmet kullanıcısına, SAP BW Application Server’ınıza yönelik erişim verin:

    1. SAP BW sunucu makinesinde, hizmet kullanıcısını SAP BW sunucunuz için Local Admin grubuna ekleyin. Bilgisayar Yönetimi programını açın ve sunucunuzun Local Admin grubuna çift tıklayın.

        ![Bilgisayar Yönetimi programı ekran görüntüsü](media/service-gateway-sso-kerberos/computer-management.png)

    1. Local Admin grubuna çift tıklayın ve **Ekle**'yi seçerek hizmet kullanıcınızı gruba ekleyin. Adı doğru girdiğinizden emin olmak için **Adları Denetle**’yi seçin. **Tamam**'ı seçin.

1. SAP BW sunucusunun hizmet kullanıcısını, SAP BW sunucusu makinesinde SAP BW sunucusu hizmetini başlatan kullanıcı olarak ayarlayın.

    1. **Çalıştır**’ı açın ve “Services.msc” girin. SAP BW Application Server örneğinize karşılık gelen hizmeti bulun. Sağ tıklayıp **Özellikler**'i seçin.

        ![Özellikler seçeneği vurgulanmış halde hizmetler ekran görüntüsü](media/service-gateway-sso-kerberos/server-properties.png)

    1. **Oturum açma** sekmesine geçin ve kullanıcıyı, SAP BW hizmet kullanıcınız olarak değiştirin. Kullanıcı parolasını girin ve **Tamam**'ı seçin.

1. SAP Logon uygulamasında, sunucunuzda oturum açın ve RZ10 işlemini kullanarak aşağıdaki profil parametrelerini ayarlayın:

    1. snc/identity/as profil parametresini p:\<oluşturduğunuz SAP BW hizmeti kullanıcısı\> olarak ayarlayın, örneğin: p:BWServiceUser@MYDOMAIN.COM. Hizmet kullanıcısının UPN bilgisinin önündeki p: ifadesine dikkat edin. SNC Kitaplığı olarak Genel Şifreleme Kitaplığının kullanıldığı durumdaki gibi P:CN= değildir.

    1. snc/gssapi\_lib profil parametresini \<sunucu makinesindeki gsskrb5.dll/gx64krb5.dll dosyasının yolu (kullanacağınız kitaplık işletim sisteminin bit değerine göre değişir\> olarak ayarlayın. Kitaplığı SAP BW Application Server’ın erişebileceği bir konuma yerleştirmeyi unutmayın.

    1. Ayrıca aşağıdaki ek profil parametrelerini de ayarlayın ve değerleri ihtiyaçlarınıza uyacak şekilde değiştirin. Son beş seçeneğin, istemcilerin SNC yapılandırılmadan SAP Logon aracılığıyla SAP BW sunucusuna bağlanmasını sağlayacağına dikkat edin.

        | **Ayar** | **Değer** |
        | --- | --- |
        | snc/data\_protection/max | 3 |
        | snc/data\_protection/min | 1 |
        | snc/data\_protection/use | 9 |
        | snc/accept\_insecure\_cpic | 1 |
        | snc/accept\_insecure\_gui | 1 |
        | snc/accept\_insecure\_r3int\_rfc | 1 |
        | snc/accept\_insecure\_rfc | 1 |
        | snc/permit\_insecure\_start | 1 |

    1. snc/enable özelliğini 1 olarak ayarlayın.

1. Bu profil parametrelerini ayarladıktan sonra sunucu makinesinde SAP Management Console uygulamasını açın ve SAP BW örneğini yeniden başlatın. Sunucu başlatılmazsa profil parametrelerini doğru ayarladığınızı doğrulayın. Profil parametresi ayarları hakkında daha fazla bilgi için [SAP belgelerine](https://help.sap.com/saphelp_nw70ehp1/helpdata/en/e6/56f466e99a11d1a5b00000e835363f/frameset.htm) bakın. Sorunla karşılaşmanız halinde bu bölümün sonraki kısımlarında yer alan sorun giderme bilgilerine de başvurabilirsiniz.

### <a name="map-a-sap-bw-user-to-an-active-directory-user"></a>SAP BW kullanıcısını Active Directory kullanıcısına eşleme

Bir Active Directory kullanıcısını bir SAP BW Application Server kullanıcısına eşleyin ve SAP Logon ile SSO bağlantısını test edin.

1. SAP Logon uygulamasını kullanarak SAP BW sunucunuzda oturum açın. SU01 işlemini çalıştırın.

1. **User** (Kullanıcı) alanına SSO bağlantılarını etkinleştirmek istediğiniz SAP BW kullanıcısını girin (önceki ekran görüntüsünde BIUSER kullanıcısının izinleri ayarlanmaktadır). SAP Logon penceresinin sol üst köşesindeki **Edit** (Düzenle) simgesini (kalem görüntüsü) seçin.

    ![SAP BW User maintenance (Kullanıcı yönetimi) ekranı ekran görüntüsü](media/service-gateway-sso-kerberos/user-maintenance.png)

1. **SNC** sekmesini seçin. SNC name (SNC adı) giriş kutusuna p:\<Active Directory kullanıcınız\>@\<etki alanınız\> girin. Active Directory kullanıcısının UPN değerinden önce p: ifadesinin kullanılması gerektiğini unutmayın. Belirttiğiniz Active Directory kullanıcısının SAP BW Application Server için SSO erişimini etkinleştirmek istediğiniz kişiye veya kuruluşa ait olması gerekir. Örneğin [testuser@TESTDOMAIN.COM](mailto:testuser@TESTDOMAIN.COM) adlı kullanıcı için SSO erişimini etkinleştirmek istiyorsanız p:testuser@TESTDOMAIN.COM yazın.

    ![SAP BW Maintain users (Kullanıcıları yönet) ekranı ekran görüntüsü](media/service-gateway-sso-kerberos/maintain-users.png)

1. Ekranın Sol üst köşesindeki **Save** (Kaydet) simgesini (disket görseli) seçin.

### <a name="test-sign-in-by-using-sso"></a>SSO kullanarak oturum açmayı sınama

Sunucuda oturum açabildiğinizi doğrulayın. SSO aracılığıyla, SSO erişimini etkinleştirdiğiniz Active Directory kullanıcısı olarak SAP Logon’u kullanın.

1. SSO erişimini etkinleştirmiş olduğunuz Active Directory kullanıcısı olarak SAP Logon’un yüklü olduğu bir makinede oturum açın. SAP Logon’u başlatın ve yeni bir bağlantı oluşturun.

1. **Create New System Entry** (Yeni Sistem Girdisi Oluştur) ekranından **User Specified System** > **Next**'i (Kullanıcı Tarafından Belirtilen Sistem > İleri) seçin.

    ![Create New System Entry (Yeni Sistem Girdisi Oluştur) ekranı ekran görüntüsü](media/service-gateway-sso-kerberos/new-system-entry.png)

1. Sonraki ekranda, uygulama sunucusu, örnek sayısı ve sistem kimliği gibi gerekli bilgileri girin. Ardından **Finish**'i (Son) seçin.

1. Yeni bağlantıya sağ tıklayın ve **Özellikler**'i seçin. **Ağ** sekmesini seçin. **SNC Name** (SNC Adı) metin kutusunda p:\<SAP BW hizmet kullanıcısı UPN'si\> girin, örneğin: p:BWServiceUser@MYDOMAIN.COM. Ardından **Tamam**'ı seçin.

    ![System Entry Properties (Sistem Girdisi Özellikleri) ekranı ekran görüntüsü](media/service-gateway-sso-kerberos/system-entry-properties.png)

1. Yeni oluşturduğunuz bağlantıya çift tıklayarak SAP BW sunucunuzla bir SSO bağlantısı kurmayı deneyin. Bu bağlantı başarılı olursa bir sonraki adıma geçin. Aksi takdirde belgenin önceki adımlarını gözden geçirerek doğru şekilde tamamlandığından emin olun veya aşağıdaki sorun giderme bölümünü inceleyin. Bu bağlamda SSO ile SAP BW sunucusuna bağlanamıyorsanız ağ geçidi bağlamında da SSO ile SAP BW sunucusuna bağlanamayacağınıza dikkat edin.

### <a name="troubleshoot-installation-and-connections"></a>Yükleme ve bağlantı sorunlarını giderme

Herhangi bir sorunla karşılaşırsanız aşağıdaki gsskrb5 yüklemesinde ve SAP Logon’dan SSO bağlantılarında sorun giderme adımlarını izleyin.

- Sunucu günlüklerinin (sunucu makinesinde …work\dev\_w0) görüntülenmesi, gsskrb5 kurulum adımlarını tamamlarken karşılaştığınız hataları giderme konusunda yardımcı olabilir. Bu, özellikle profil parametreleri değiştirildikten sonra SAP BW sunucusu başlamazsa geçerlidir.

- Oturum açma hatası nedeniyle SAP BW hizmetini başlatamıyorsanız SAP BW "başlatma" kullanıcısı ayarlarında yanlış parola girmiş olabilirsiniz. Active Directory ortamınızdaki bir makinede SAP BW hizmet kullanıcısı olarak oturum açarak parolayı doğrulayın.

- Sunucunun başlatılmasını önleyen SQL kimlik bilgileriyle ilgili hata alıyorsanız hizmet kullanıcısına SAP BW veritabanına erişim izni verdiğinizi doğrulayın.

- Şu iletiyi alabilirsiniz: “(GSS-API) Belirtilen hedef bilinmiyor veya erişilemiyor.” Bu genellikle yanlış SNC adını belirttiğiniz anlamına gelir. İstemci uygulamasında "p:CN=" değil yalnızca "p:" ve hizmet kullanıcısının UPN bilgisini kullandığınızdan emin olun.

- Şu iletiyi alabilirsiniz: “(GSS-API) Geçersiz bir ad sağlandı.” Sunucunun SNC kimlik profili parametresindeki değerde "p:" ifadesinin bulunduğundan emin olun.

- Şu iletiyi alabilirsiniz: "(SNC hatası) Belirtilen modül bulunamadı." Bu durum, genellikle `gsskrb5.dll/gx64krb5.dll` erişim için yükseltilmiş ayrıcalıklar (yönetici hakları) gerektiren bir konuma yerleştirildiğinde oluşur.

### <a name="add-registry-entries-to-the-gateway-machine"></a>Ağ geçidi makinesine kayıt defteri girişleri ekleme

Ağ geçidinin yüklü olduğu makinenin kayıt defterine gerekli kayıt defteri girişlerini ekleyin. Çalıştırılacak komutlar şunlardır:

1. REG ADD HKLM\SOFTWARE\Wow6432Node\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

1. REG ADD HKLM\SOFTWARE\SAP\gsskrb5 /v ForceIniCredOK /t REG\_DWORD /d 1 /f

### <a name="set-configuration-parameters-on-the-gateway-machine"></a>Ağ geçidi makinesinde yapılandırma parametrelerini ayarlama

Kullanıcıların Power BI hizmetinde Azure AD kullanıcısı olarak oturum açabilmesi için yapılandırılmış bir Azure AD Connect olup olmadığına bağlı olarak, yapılandırma parametrelerini iki şekilde ayarlayabilirsiniz.

Azure AD Connect yapılandırılmışsa aşağıdaki adımları izleyin.

1. Ana ağ geçidi yapılandırma dosyasını (`Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll`) açın. Bu dosya varsayılan olarak C:\Program Files\On-premises data gateway konumunda bulunur.

1. **FullDomainResolutionEnabled** özelliğinin **True** ve **SapHanaSsoRemoveDomainEnabled** özelliğinin **False** olarak ayarlandığından emin olun.

1. Yapılandırma dosyasını kaydedin.

1. Görev Yöneticisi'nin **Hizmetler** sekmesinden ağ geçidi hizmetine sağ tıklayın ve **Yeniden Başlat**’ı seçin.

    ![Görev Yöneticisi Hizmetler sekmesi ekran görüntüsü](media/service-gateway-sso-kerberos/restart-gateway.png)

Azure AD Connect yapılandırılmamışsa, bir Azure AD kullanıcısına eşlemek istediğiniz her Power BI hizmeti kullanıcısı için bu adımları izleyin. Bu adımlar bir Power BI Hizmeti kullanıcısını, SAP BW’da oturum açma iznine sahip bir Active Directory kullanıcısına el ile bağlar.

1. Ana ağ geçidi yapılandırma dosyasını (`Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll`) açın. Bu dosya varsayılan olarak C:\Program Files\On-premises data gateway konumunda bulunur.

1. **ADUserNameLookupProperty** özelliğini `msDS-cloudExtensionAttribute1`, **ADUserNameReplacementProperty** özelliğini de `SAMAccountName` olarak ayarlayın. Yapılandırma dosyasını kaydedin.

1. Görev Yöneticisi'nin **Hizmetler** sekmesinden ağ geçidi hizmetine sağ tıklayın ve **Yeniden Başlat**’ı seçin.

    ![Görev Yöneticisi Hizmetler sekmesi ekran görüntüsü](media/service-gateway-sso-kerberos/restart-gateway.png)

1. Active Directory kullanıcısının `msDS-cloudExtensionAttribute1` özelliğini ayarlayın. Bu, SAP BW kullanıcısına eşlediğiniz kullanıcıdır. Özelliği, Kerberos SSO’yu etkinleştirmek istediğiniz Power BI hizmeti kullanıcısı olarak ayarlayın. `msDS-cloudExtensionAttribute1` özelliğini ayarlamak için, Active Directory Kullanıcıları ve Bilgisayarları MMC ek bileşeni kullanılabilir. (Farklı yöntemler de kullanabilirsiniz.)

    1. Etki Alanı Denetleyicisi makinesinde yönetici kullanıcı olarak oturum açın.

    1. Ek bileşen penceresinde **Kullanıcılar** klasörünü açın ve bir SAP BW kullanıcısına eşlediğiniz Active Directory kullanıcısına çift tıklayın.

    1. **Öznitelik Düzenleyicisi** sekmesini seçin.

        Bu sekmeyi görmüyorsanız etkinleştirme yönergelerini aramanız veya özelliği ayarlamak için başka bir yöntem kullanmanız gerekir. Özniteliklerden birini seçtikten sonra M tuşuna basarak 'm' harfiyle başlayan Active Directory özelliklerine gidin. `msDS-cloudExtensionAttribute1` özelliğini bulun ve çift tıklayın. Değeri, Power BI hizmetinde oturum açmak için kullandığınız YourUser@YourDomain biçimindeki kullanıcı adıyla değiştirin.

    1. **Tamam**'ı seçin.

        ![Dize Öznitelik Düzenleyicisi iletişim kutusu ekran görüntüsü](media/service-gateway-sso-kerberos/edit-attribute.png)

    1. **Apply** (Uygula) seçeneğini belirleyin. **Değer** sütununda doğru değerin ayarlandığından emin olun.

### <a name="add-a-new-sap-bw-application-server-data-source-to-the-power-bi-service"></a>Power BI hizmetine yeni bir SAP BW Application Server veri kaynağı ekleme

Bu makalenin önceki bölümlerinde yer alan [rapor çalıştırma](#run-a-power-bi-report) yönergelerini izleyerek SAP BW veri kaynağını ağ geçidinize ekleyin.

1. Veri kaynağı yapılandırma penceresinde Application Server’ın **Ana bilgisayar adı**, **Sistem Numarası** ve **İstemci Kimliği** bilgilerini Power BI Desktop'tan SAP BW sunucusunda oturum açar gibi girin. **Kimlik Doğrulaması Yöntemi** olarak **Windows**'u seçin.

1. **SNC İş Ortağı Adı** alanına p:\<SAP BW hizmet kullanıcınıza eşlediğiniz SPN\> girin. Örneğin, SPN SAP/BWServiceUser@MYDOMAIN.COM ise **SNC İş Ortağı Adı** alanına p:SAP/BWServiceUser@MYDOMAIN.COM girmeniz gerekir.

1. SNC Kitaplığı alanında **SNC\_LIB** veya **SNC\_LIB\_64** değerini seçin.

1. **Kullanıcı adı** ve **Parola**, SSO ile SAP BW sunucusunda oturum açma iznine sahip Active Directory kullanıcısının kullanıcı adı ve parolası olmalıdır. Başka bir deyişle bunlar, SU01 işlemi aracılığıyla SAP BW kullanıcısına eşlenen bir Active Directory kullanıcısına ait olmalıdır. Bu kimlik bilgileri yalnızca **DirectQuery sorguları için Kerberos üzerinden SSO kullanın** kutusu işaretli olmadığında kullanılır.

1. **DirectQuery sorguları için Kerberos üzerinden SSO kullanın** kutusunu ve **Uygula**'yı seçin. Bağlantı testi başarılı olmazsa önceki kurulum ve yapılandırma adımlarının doğru şekilde tamamlandığından emin olun.

    Ağ geçidi, sunucuyla bir test bağlantısı kurmak ve içeri aktarma temelli raporların zamanlanmış yenilemelerini yapmak için her zaman girilen kimlik bilgilerini kullanır. Ağ geçidi yalnızca **DirectQuery sorguları için Kerberos üzerinden SSO kullanın** seçeneği işaretliyse bir SSO bağlantısı kurmaya çalışır.

### <a name="test-your-setup"></a>Ayarları test etme

Ayarlarınızı test etmek için Power BI Desktop'tan Power BI hizmetine bir DirectQuery raporu yayımlayın. Power BI hizmetinde bir Azure AD kullanıcısı ya da bir Azure AD kullanıcısının `msDS-cloudExtensionAttribute1` özelliğine eşlediğiniz kullanıcı olarak oturum açtığınızdan emin olun. Ayarlar başarıyla tamamlandıysa Power BI hizmetinde yayımlanan veri kümesiyle bir rapor oluşturabilirsiniz. Rapordaki görseller aracılığıyla veri de çekebilirsiniz.

### <a name="troubleshoot-gateway-connectivity-issues"></a>Ağ geçidi bağlantı sorunlarını giderme

1. Ağ geçidi günlüklerini kontrol edin. Ağ Geçidi Yapılandırması uygulamasını açın, **Tanılama** > **Günlükleri dışarı aktar**'ı seçin. En son hatalar, incelediğiniz günlük dosyalarının en altında bulunur.

    ![Tanılama vurgulanmış olarak Şirket içi veri ağ geçidi uygulaması ekran görüntüsü](media/service-gateway-sso-kerberos/gateway-diagnostics.png)

1. SAP BW izlemeyi açın ve oluşturulan günlük dosyalarını inceleyin. Birçok farklı SAP BW izleme türü vardır. Daha fazla bilgi için SAP belgelerine başvurun.

## <a name="errors-from-an-insufficient-kerberos-configuration"></a>Yetersiz bir Kerberos yapılandırmasından kaynaklanan hatalar

Temel alınan veritabanı sunucusu ve ağ geçidi Kerberos kısıtlanmış temsili için düzgün bir şekilde yapılandırılmamışsa, şu veri yükleme hatası iletisini alabilirsiniz:

![Hata iletisi ekran görüntüsü](media/service-gateway-sso-kerberos/load-data-error.png)

Hata iletisiyle (DM_GWPipeline_Gateway_ServerUnreachable) ilişkili teknik ayrıntılar aşağıdaki gibi görünebilir:

![Hata mesajı teknik ayrıntılar ekran görüntüsü](media/service-gateway-sso-kerberos/server-unreachable.png)

Sonuç olarak, ağ geçidi kaynak kullanıcının kimliğine düzgün bir şekilde bürünemez ve veritabanı bağlantısı girişimi başarısız olur.

## <a name="next-steps"></a>Sonraki adımlar

**Şirket içi veri ağ geçidi** ve **DirectQuery** hakkında daha fazla bilgi için aşağıdaki kaynaklara göz atın:

* [Şirket içi veri ağ geçidi](service-gateway-onprem.md)
* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
