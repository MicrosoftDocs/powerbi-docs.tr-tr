---
title: SSO yapılandırma - Kerberos
description: Power BI'dan şirket içi veri kaynaklarına bağlanmak için SSO'yu etkinleştirmek üzere ağ geçidinizi Kerberos ile yapılandırın
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 9958059fcf0d86323fc95f44f6fcfcb08fe7b52b
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71100496"
---
# <a name="configure-kerberos-based-sso-from-power-bi-service-to-on-premises-data-sources"></a>Power BI hizmetinden şirket içi veri kaynaklarına Kerberos tabanlı SSO yapılandırma

[Kerberos kısıtlanmış temsili](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) kullanarak, sorunsuz SSO bağlantısını etkinleştirin. SSO'yu etkinleştirmek, Power BI raporlarının ve panolarının şirket içi kaynaklardan alınan verileri yenilemesini kolaylaştırır.

Kerberos kısıtlanmış temsilinin düzgün bir şekilde çalışması için, hizmet hesaplarındaki _Hizmet Asıl Adlarının_ (SPN) ve temsilci seçme ayarlarının da dahil olduğu belirli öğelerin yapılandırılması gerekir.

### <a name="prerequisite-1-install-and-configure-the-microsoft-on-premises-data-gateway"></a>1\. Önkoşul: Microsoft şirket içi veri ağ geçidini yükleme ve yapılandırma

Şirket içi veri ağ geçidi, yerinde yükseltmeyi ve mevcut ağ geçitlerinin _ayarlarını devralma_ özelliğini destekler.

### <a name="prerequisite-2-run-the-gateway-windows-service-as-a-domain-account"></a>2\. Önkoşul: Ağ geçidi Windows hizmetini bir etki alanı hesabı olarak çalıştırma

Standart bir yüklemede, ağ geçidi, aşağıdaki görüntüde gösterildiği gibi bir makine yerel hizmet hesabı olarak (özel olarak belirtmek gerekirse, _NT Service\PBIEgwService_) çalıştırılır:

![Hizmet hesabı ekran görüntüsü](media/service-gateway-sso-kerberos/service-account.png)

Azure Active Directory (Azure AD) örneğiniz (Azure AD DirSync/Connect kullanılarak) yerel Active Directory örneğiniz ile eşitlenmediği sürece, Kerberos kısıtlanmış temsilinin etkinleştirilebilmesi için ağ geçidinin bir etki alanı hesabı olarak çalıştırılması gerekir. Bir etki alanı hesabına geçmek için bkz. [Ağ geçidi hizmeti hesabını değiştirme](/data-integration/gateway/service-gateway-service-account).

> [!NOTE]
> Azure AD Connect yapılandırıldıysa ve kullanıcı hesapları eşitlendiyse, ağ geçidi hizmetinin çalışma zamanında yerel Azure AD aramaları yapması gerekmez. Bunun yerine, Azure Active Directory'de gerekli olan tüm yapılandırmayı tamamlamak için ağ hizmetinin yerel hizmet SID’sini de kullanabilirsiniz. Bu belgede açıklanan Kerberos kısıtlanmış temsili yapılandırmasına ilişkin adımlar, Azure Active Directory bağlamında gereken yapılandırma adımlarıyla aynıdır. Bunlar, etki alanı hesabının yerine Azure AD’deki ağ geçidinin bilgisayar nesnesine (yerel hizmet SID’si ile tanımlanır) uygulanır.

### <a name="prerequisite-3-have-domain-admin-rights-to-configure-spns-setspn-and-kerberos-constrained-delegation-settings"></a>3\. Önkoşul: SPN'leri (SetSPN) ve Kerberos kısıtlanmış temsili ayarlarını yapılandırmak için etki alanı yöneticisi haklarını alma

Bir etki alanı yöneticisinin SPN'leri ve Kerberos temsili ayarlarını yapılandırma haklarını (etki alanı yöneticisi hakları gerektirmeden) etki alanı yönetici haklarına sahip olmayan başka bir kişiye geçici veya kalıcı olarak vermesini önermiyoruz. Aşağıdaki bölümde, önerilen yapılandırma adımlarını daha ayrıntılı bir biçimde inceleyeceğiz.

## <a name="configure-kerberos-constrained-delegation-for-the-gateway-and-data-source"></a>Ağ geçidi ve veri kaynağı için Kerberos kısıtlanmış temsilini yapılandırma

Etki alanı yöneticisi olarak, ağ geçidi hizmeti etki alanı hesabı için bir SPN yapılandırın (gerekliyse) ve ağ geçidi hizmeti etki alanı hesabında temsilci seçme ayarlarını yapılandırın.

### <a name="configure-an-spn-for-the-gateway-service-account"></a>Ağ geçidi hizmet hesabı için SPN yapılandırma

Öncelikle, ağ geçidi hizmet hesabı olarak kullanılan etki alanı hesabı için bir SPN yapılandırılmış olup olmadığını belirleyin:

1. **Active Directory Kullanıcıları ve Bilgisayarları**'nı etki alanı yöneticisi olarak başlatın.

2. Etki alanına sağ tıklayın, **Bul** seçeneğini belirleyin ve ağ geçidi hizmet hesabına ilişkin hesap adını girin.

3. Arama sonucunda, ağ geçidi hizmet hesabına sağ tıklayıp **Özellikler**'i seçin.

4. **Özellikler** iletişim kutusunda **Temsilci Seçme** sekmesi görünüyorsa SPN zaten oluşturulmuştur ve [Kaynak temelli veya standart Kerberos kısıtlanmış temsiline karar verme](#decide-on-resource-based-or-standard-kerberos-constrained-delegation) bölümüne geçebilirsiniz.

    **Özellikler** iletişim kutusunda **Temsilci Seçme** sekmesi yoksa, bu hesapta elle SPN oluşturarak etkinleştirebilirsiniz. Windows ile birlikte gelen [setspn aracını](https://technet.microsoft.com/library/cc731241.aspx) kullanın. (SPN'yi oluşturmak için etki alanı yöneticisi haklarına sahip olmanız gerekir.)

    Örneğin, ağ geçidi hizmet hesabının **Contoso\GatewaySvc**), ağ geçidi hizmetinin çalıştığı makinenin adının ise **MyGatewayMachine** olduğunu varsayalım. Ağ geçidi hizmet hesabına yönelik SPN'yi ayarlamak için aşağıdaki komutu çalıştırırsınız:

    ![setspn komutu görüntüsü](media/service-gateway-sso-kerberos/set-spn.png)

    SPN’yi, Active Directory Kullanıcıları ve Bilgisayarları MMC (Microsoft Yönetim Konsolu) ek bileşenini kullanarak da ayarlayabilirsiniz.

### <a name="decide-on-resource-based-or-standard-kerberos-constrained-delegation"></a>Kaynak tabanlı veya standart Kerberos kısıtlanmış temsiline karar verme

Temsilci ayarları, kaynak temelli kısıtlanmış Kerberos temsili _veya_ standart Kerberos kısıtlanmış temsili için yapılandırılabilir. Veri kaynağınız ağ geçidinizden farklı bir etki alanına aitse kaynak temelli temsili kullanın, ancak bu yaklaşımın Windows Server 2012 veya sonraki bir sürümü gerektirdiğini unutmayın. Temsile yönelik iki yaklaşım arasındaki farklar hakkında daha fazla bilgi için [Kerberos kısıtlanmış temsiline genel bakış sayfasına](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) bakın.

 Kullanmak istediğiniz yaklaşıma karar verdikten sonra, [Ağ geçidi hizmet hesabını standart Kerberos kısıtlanmış temsili için yapılandırma](#configure-the-gateway-service-account-for-standard-kerberos-constrained-delegation) _veya_ [Ağ geçidi hizmet hesabını kaynak temelli Kerberos kısıtlanmış temsili için yapılandırma](#configure-the-gateway-service-account-for-resource-based-kerberos-constrained-delegation) bölümlerinden _birine_ ilerleyin. Her iki alt bölümü de tamamlamayın.

## <a name="configure-the-gateway-service-account-for-standard-kerberos-constrained-delegation"></a>Ağ geçidi hizmet hesabını standart Kerberos kısıtlanmış temsili için yapılandırma

> [!NOTE]
> Standart Kerberos kısıtlanmış temsilini etkinleştirmek istiyorsanız bu bölümdeki adımları tamamlayın. Kaynak temelli Kerberos kısıtlanmış temsilciyi etkinleştirmek istiyorsanız, [Ağ geçidi hizmet hesabını kaynak temelli Kerberos kısıtlanmış temsili için yapılandırma](#configure-the-gateway-service-account-for-resource-based-kerberos-constrained-delegation) alt bölümündeki adımları tamamlayın.

Şimdi ağ geçidi hizmet hesabı için temsilci ayarlarını belirleyeceğiz. Bu adımları uygulamak için kullanabileceğiniz birçok araç vardır. Burada, dizindeki bilgileri yönetmek ve yayımlamak için, bir Microsoft Yönetim Konsolu (MMC) ek bileşeni olan Active Directory Kullanıcıları ve Bilgisayarları'nı kullanacağız. Bu ayar etki alanı denetleyicilerinde varsayılan olarak mevcuttur, ancak diğer makinelerde Windows Özellik yapılandırması aracılığıyla da etkinleştirebilirsiniz.

Protokol geçişi ile Kerberos kısıtlanmış temsilini yapılandırmamız gerekir. Kısıtlanmış temsilde, ağ geçidinin temsilci kimlik bilgilerini sunmasına izin vereceğiniz hizmetleri açıkça belirtmeniz gerekir. Örneğin, ağ geçidi hizmet hesabından yapılan temsilci seçme çağrılarını yalnızca SQL Server veya SAP HANA sunucusu kabul eder.

Bu bölümde, temel alınan veri kaynaklarınız (SQL Server, SAP HANA, SAP BW, Teradata veya Spark vb.) için daha önce SPN yapılandırmış olduğunuz varsayılır. Söz konusu veri kaynağı sunucusu SPN'lerinin nasıl yapılandırılacağını öğrenmek için ilgili veritabanı sunucusuna yönelik teknik belgelere bakın. Başlığı da (*Uygulamanız hangi SPN’yi gerektiriyor*) [Kerberos Denetim Listem](https://techcommunity.microsoft.com/t5/SQL-Server-Support/My-Kerberos-Checklist-8230/ba-p/316160) blog gönderisinde görebilirsiniz.

Sıradaki adımlar için bir ağ geçidi makinesi ve daha önce Kerberos tabanlı SSO için yapılandırılmış SQL Server çalıştıran bir veritabanı olmak üzere iki makine içeren bir şirket içi ortamını kullanacağız. Bu adımlar, veri kaynağı Kerberos tabanlı çoklu oturum açma için zaten yapılandırılmışsa desteklenen diğer veri kaynaklarından biri için benimsenebilir. Bu örnek için ayrıca şu ayarların ve adların geçerli olduğunu varsayacağız:

* Active Directory Etki Alanı (Netbios): Contoso
* Ağ geçidi makine adı: **MyGatewayMachine**
* Ağ geçidi hizmeti hesabı: **Contoso\GatewaySvc**
* SQL Server veri kaynağı makine adı: **TestSQLServer**
* SQL Server veri kaynağı hizmet hesabı: **Contoso\SQLService**

Temsilci seçme ayarlarını yapılandırmak için şunları yapabilirsiniz:

1. **Active Directory Kullanıcıları ve Bilgisayarları**'nı etki alanı yöneticisi haklarıyla açın.

2. Ağ geçidi hizmet hesabına (**Contoso\GatewaySvc**) sağ tıklayın ve **Özellikler**'i seçin.

3. **Temsilci Seçme** sekmesini seçin.

4. **Bu bilgisayara yalnızca belirtilen hizmetlere temsilci seçmek için güven** > **Herhangi bir kimlik doğrulama protokolünü kullan** seçeneğini belirleyin.

5. **Bu hesabın temsilci seçilen kimlik bilgilerini sunacağı hizmetler** bölümünde **Ekle**'yi seçin.

6. Yeni iletişim kutusunda **Kullanıcı/Bilgisayar**'ı seçin.

7. Veri kaynağı için hizmet hesabını girin. Örneğin, bir SQL Server veri kaynağı **Contoso\SQLService** gibi bir hizmet hesabına sahip olabilir. Hesabınız eklendikten sonra **Tamam**’ı seçin.

8. Veritabanı sunucusu için oluşturduğunuz SPN'yi seçin. Örneğimizde SPN, **MSSQLSvc** ile başlar. Veritabanı hizmeti için hem FQDN hem de NetBIOS SPN'sini eklediyseniz her ikisini de seçin. Yalnızca birini görüyor olabilirsiniz.

9. **Tamam**'ı seçin. SPN'nin listede görünmesi gerekir.

    ![Ağ Geçidi Bağlayıcısı Özellikleri İletişim Kutusu Ekran Görüntüsü](media/service-gateway-sso-kerberos/gateway-connector-properties.png)

Şimdi kurulum işlemine devam etmek için [Ağ geçidi makinesinde ağ geçidi hizmet hesabına yerel ilke hakları verme](#grant-the-gateway-service-account-local-policy-rights-on-the-gateway-machine) bölümüne geçin.

## <a name="configure-the-gateway-service-account-for-resource-based-kerberos-constrained-delegation"></a>Ağ geçidi hizmet hesabını kaynak temelli Kerberos kısıtlanmış temsili için yapılandırma

> [!NOTE]
> Kaynak temelli Kerberos kısıtlanmış temsilini etkinleştirmek istiyorsanız bu bölümdeki adımları tamamlayın. Standart Kerberos kısıtlanmış temsilciyi etkinleştirmek istiyorsanız, [Ağ geçidi hizmet hesabını standart Kerberos kısıtlanmış temsili için yapılandırma](#configure-the-gateway-service-account-for-standard-kerberos-constrained-delegation) alt bölümündeki adımları tamamlayın.

Windows Server 2012 ve sonraki sürümlerinde çoklu oturum açma bağlantısına olanak sağlamak için, ön uç ile arka uç hizmetlerin farklı etki alanlarında bulunmasına izin veren [kaynak tabanlı Kerberos kısıtlanmış temsilini](/windows-server/security/kerberos/kerberos-constrained-delegation-overview) kullanın. Bu çalışma için, arka uç hizmeti etki alanın ön uç hizmeti etki alanına güvenmesi gerekir.

Sıradaki adımlar için bir ağ geçidi makinesi ve daha önce Kerberos tabanlı SSO için yapılandırılmış SQL Server çalıştıran bir veritabanı olmak üzere farklı etki alanlarında iki makine içeren bir şirket içi ortamını kullanacağız. Bu adımlar, veri kaynağı Kerberos tabanlı çoklu oturum açma için zaten yapılandırılmışsa desteklenen diğer veri kaynaklarından biri için benimsenebilir. Bu örnek için ayrıca şu ayarların ve adların geçerli olduğunu varsayıyoruz:

* Ağ geçidi makine adı: **MyGatewayMachine**
* Ağ geçidi hizmeti hesabı: **ContosoFrontEnd\GatewaySvc**
* SQL Server veri kaynağı makine adı: **TestSQLServer**
* SQL Server veri kaynağı hizmet hesabı: **ContosoBackEnd\SQLService**

Bu örnek adlar ve ayarlar doğrultusunda aşağıdaki yapılandırma adımlarını tamamlayın:

1. **ContosoFrontEnd** etki alanının etki alanı denetleyicisinde bir Microsoft Yönetim Konsolu (MMC) ek bileşeni olan **Active Directory Kullanıcıları ve Bilgisayarları**'nı kullanarak, ağ geçidi hizmet hesabına hiçbir temsil ayarı uygulanmadığından emin olun.

    ![Ağ geçidi bağlayıcısı özellikleri](media/service-gateway-sso-kerberos-resource/gateway-connector-properties.png)

2. **ContosoBackEnd** etki alanının etki alanı denetleyicisinde **Active Directory Kullanıcıları ve Bilgisayarları**'nı kullanarak, arka uç hizmet hesabına hiçbir temsil ayarı uygulanmadığından emin olun. Buna ek olarak, bu hesap için **msDS-AllowedToActOnBehalfOfOtherIdentity** özniteliğinin de ayarlanmadığından emin olun. Bu özniteliği, aşağıdaki resimde gösterildiği gibi **Öznitelik Düzenleyicisi**’nde bulabilirsiniz:

    ![SQL hizmeti özellikleri](media/service-gateway-sso-kerberos-resource/sql-service-properties.png)

3. **ContosoBackEnd** etki alanının etki alanı denetleyicisinde, **Active Directory Kullanıcıları ve Bilgisayarları**'nda bir grup oluşturun. Aşağıdaki görüntüde gösterildiği gibi ağ geçidi hizmet hesabını bu gruba ekleyin. Görüntüde _ResourceDelGroup_ adlı yeni bir grup ve bu gruba eklenen **GatewaySvc** ağ geçidi hizmet hesabı gösterilir.

    ![Grup özellikleri](media/service-gateway-sso-kerberos-resource/group-properties.png)

4. Bir komut istemi açın ve **ContosoBackEnd** etki alanının etki alanı denetleyicisinde aşağıdaki komutları çalıştırarak arka uç hizmet hesabının **msDS-AllowedToActOnBehalfOfOtherIdentity** özniteliğini güncelleştirin:

    ```powershell
    $c = Get-ADGroup ResourceDelGroup
    Set-ADUser SQLService -PrincipalsAllowedToDelegateToAccount $c
    ```

5. **Active Directory Kullanıcıları ve Bilgisayarları**'nda arka uç hizmet hesabının özelliklerindeki "Öznitelik Düzenleyicisi" sekmesinde güncelleştirmenin yansıtıldığını doğrulayabilirsiniz.

## <a name="grant-the-gateway-service-account-local-policy-rights-on-the-gateway-machine"></a>Ağ geçidi makinesinde ağ geçidi hizmet hesabına yerel ilke hakları verme

Son olarak, ağ geçidi hizmetinin çalıştırıldığı makinede (örneğimizde **MyGatewayMachine**), ağ geçidi hizmet hesabına **Kimlik doğrulamasından sonra istemcinin özelliklerini al** ve **İşletim sisteminin bir parçası olarak davran (SeTcbPrivilege)** yerel ilkesini uygulamanız gerekir. Bu yapılandırmayı gerçekleştirmek ve doğrulamak için Yerel Grup İlkesi Düzenleyicisi'ni (**gpedit**) kullanmanız gerekir.

1. Ağ geçidi makinesinde şunu çalıştırın: *gpedit.msc*.

2. **Yerel Bilgisayar İlkesi** > **Bilgisayar Yapılandırması** > **Windows Ayarları** > **Güvenlik Ayarları** > **Yerel İlkeler** > **Kullanıcı Hakları Ataması** seçeneğine gidin.

    ![Yerel Bilgisayar İlkesi klasör yapısı ekran görüntüsü](media/service-gateway-sso-kerberos/user-rights-assignment.png)

3. **Kullanıcı Hakları Ataması**’nın altındaki ilke listesinden **Kimlik doğrulamasından sonra istemcinin özelliklerini al** seçeneğini belirleyin.

    ![İstemci ilkesinin özelliklerini alma ekran görüntüsü](media/service-gateway-sso-kerberos/impersonate-client.png)

    Sağ tıklayın ve **Özellikler**’i açın. Hesap listesini kontrol edin. Ağ geçidi hizmet hesabını (**Contoso\GatewaySvc**) içermesi gerekir.

4. **Kullanıcı Hakları Ataması**’nın altındaki ilke listesinden **İşletim sisteminin parçası gibi davran (SeTcbPrivilege)** seçeneğini belirleyin. Ağ geçidi hizmet hesabının da hesap listesinde yer aldığından emin olun.

5. **Şirket içi veri ağ geçidi** hizmet işlemini yeniden başlatın.

### <a name="set-user-mapping-configuration-parameters-on-the-gateway-machine-if-required"></a>Gerekirse ağ geçidi makinesinde kullanıcı eşlemesi yapılandırma parametrelerini ayarlama

Azure AD Connect yapılandırılmamışsa, bir Power BI hizmeti kullanıcısını yerel bir Active Directory kullanıcısına eşlemek için bu adımları izleyin. Bu şekilde eşlenen her Active Directory kullanıcısının veri kaynağınıza ilişkin SSO izinlerine sahip olması gerekir. Daha fazla bilgi için bu [Küp içindeki adam videosuna](https://www.youtube.com/watch?v=NG05PG9aiRw) bakın.

1. Ana ağ geçidi yapılandırma dosyasını (`Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll`) açın. Bu dosya varsayılan olarak C:\Program Files\On-premises data gateway konumunda bulunur.

1. **ADUserNameLookupProperty** özelliğini kullanılmayan bir Active Directory özniteliğine ayarlayın. Bu öznitelik yalnızca Windows Server 2012 ve sonraki sürümlerde kullanılabilir olsa da, aşağıdaki adımlarda `msDS-cloudExtensionAttribute1` kullanıldığını varsayacağız. **ADUserNameReplacementProperty** özelliğini `SAMAccountName` olarak ayarlayın. Yapılandırma dosyasını kaydedin.

1. Görev Yöneticisi'nin **Hizmetler** sekmesinden ağ geçidi hizmetine sağ tıklayın ve **Yeniden Başlat**’ı seçin.

    ![Görev Yöneticisi Hizmetler sekmesi ekran görüntüsü](media/service-gateway-sso-kerberos/restart-gateway.png)

1. Kerberos SSO'yu etkinleştirmek istediğiniz her Power BI hizmeti kullanıcısı için yerel bir Active Directory kullanıcısına (veri kaynağınıza ilişkin SSO iznine sahip olmalıdır) ait `msDS-cloudExtensionAttribute1` özelliğini Power BI hizmeti kullanıcısının tam kullanıcı adına ayarlayın. Örneğin, Power BI hizmetinde `test@contoso.com` olarak oturum açıp bu kullanıcıyı `test@LOCALDOMAIN.COM` gibi SSO izinleri olan yerel bir Active Directory kullanıcısına eşlemek istiyorsanız, `test@LOCALDOMAIN.COM` adlı kullanıcının `msDS-cloudExtensionAttribute1` özniteliğini `test@contoso.com` olarak ayarlayın.

`msDS-cloudExtensionAttribute1` özelliğini, Active Directory Kullanıcıları ve Bilgisayarları Microsoft Yönetim Konsolu (MMC) ek bileşenini kullanarak ayarlayabilirsiniz.

1. Bir MMC ek bileşeni olan Active Directory Kullanıcıları ve Bilgisayarları'nı etki alanı yöneticisi olarak başlatın.

1. Etki alanına sağ tıklayın, Bul’u seçin ve eşlemek istediğiniz yerel Active Directory kullanıcısının hesap adını yazın.

1. **Öznitelik Düzenleyicisi** sekmesini seçin.

    `msDS-cloudExtensionAttribute1` özelliğini bulun ve çift tıklayın. Değeri, Power BI Hizmetinde oturum açmak için kullandığınız kullanıcının tam kullanıcı adı olarak ayarlayın.

1. **Tamam**'ı seçin.

    ![Dize Öznitelik Düzenleyicisi iletişim kutusu ekran görüntüsü](media/service-gateway-sso-kerberos/edit-attribute.png)

1. **Apply** (Uygula) seçeneğini belirleyin. **Değer** sütununda doğru değerin ayarlandığından emin olun.

## <a name="complete-data-source-specific-configuration-steps"></a>Veri kaynağına özgü yapılandırma adımlarını tamamlayın

SAP HANA ve SAP BW, ağ geçidi aracılığıyla bu veri kaynaklarına yönelik bir SSO bağlantısı kurmadan önce karşılanması veri kaynağına özgü ek yapılandırma gereksinimleri ve önkoşullara sahiptir. Ayrıntılı bilgi için [SAP HANA yapılandırma sayfasına](service-gateway-sso-kerberos-sap-hana.md) ve [SAP BW - CommonCryptoLib (sapcrypto.dll) yapılandırma sayfasına](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md) bakın. [SAP BW’yu gx64krb5 SNC kitaplığı ile kullanmak üzere yapılandırmak](service-gateway-sso-kerberos-sap-bw-gx64krb.md) da mümkündür ancak bu kitaplık artık SAP tarafından desteklenmediği için Microsoft tarafından önerilmemektedir. SNC kitaplığı olarak CommonCryptoLib _veya_ gx64krb5 kullanmanız gerekir. Her iki kitaplık için yapılandırma adımlarını tamamlamayın.

> [!NOTE]
> Diğer SNC kitaplıkları BW SSO için de çalışabilir ancak Microsoft tarafından resmi olarak desteklenmemektedir.

## <a name="run-a-power-bi-report"></a>Bir Power BI raporunu çalıştırma

Tüm yapılandırma adımları tamamlandıktan sonra, SSO için kullanacağınız veri kaynağını yapılandırmak üzere Power BI'daki **Ağ Geçidini Yönet** sayfasını kullanabilirsiniz. Birden fazla ağ geçidiniz varsa, Kerberos SSO için yapılandırdığınız ağ geçidini seçtiğinizden emin olun. Daha sonra **Gelişmiş Ayarlar** altından, "DirectQuery sorguları için Kerberos üzerinden SSO kullanın" kutusunun işaretlendiğinden emin olun.

![Gelişmiş ayarlar seçeneği ekran görüntüsü](media/service-gateway-sso-kerberos/advanced-settings.png)

 Power BI Desktop’tan **DirectQuery tabanlı** bir rapor yayımlayın. Bu rapor, Power BI hizmetinde oturum açan (Azure) Active Directory kullanıcısına eşlenmiş kullanıcı için erişilebilir olan verileri kullanmalıdır. Yenileme bu şekilde çalıştığı için içeri aktarma yerine DirectQuery kullanmanız gerekir. İçeri aktarma tabanlı raporlarının yenilenmesi esnasında, veri kaynağını oluştururken **Kullanıcı Adı** ve **Parola** alanlarına girdiğiniz kimlik bilgileri ağ geçidi tarafından kullanılır. Farklı bir deyişle, Kerberos SSO **kullanılmaz**. Ayrıca, birden fazla ağ geçidiniz varsa, yayımlarken SSO için yapılandırdığınız ağ geçidini seçtiğinizden emin olun. Power BI hizmetinde artık raporu yenileme veya yayımlanan veri kümesini temel alarak yeni bir rapor oluşturma imkanınızın gerekir.

Bu yapılandırma çoğu durumda çalışır. Ancak, ortamınıza bağlı olarak Kerberos ile farklı yapılandırmalar da söz konusu olabilir. Rapor hala yüklenmiyorsa sorunun daha ayrıntılı bir şekilde incelenmesi için etki alanı yöneticinizle iletişime geçin. Veri kaynağınız SAP BW ise [CommonCryptoLib](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md#troubleshooting) ve [gx64krb5/gsskrb5](service-gateway-sso-kerberos-sap-bw-gx64krb.md#troubleshooting) için veri kaynağına özgü yapılandırma sayfalarının sorun giderme bölümlerine de bakabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

**Şirket içi veri ağ geçidi** ve **DirectQuery** hakkında daha fazla bilgi için aşağıdaki kaynaklara göz atın:

* [Şirket içi veri ağ geçidi nedir?](/data-integration/gateway/service-gateway-getting-started)
* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
