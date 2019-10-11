---
title: gx64krb5 kullanarak SAP BW’da çoklu oturum açma (SSO) için Kerberos'u kullanma
description: gx64krb5 kullanarak SAP BW sunucunuzu Power BI hizmetinden SSO etkinleştirecek şekilde yapılandırma
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/01/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 4932f00fa7585c6b4f9186c29b65700d7a14fbea
ms.sourcegitcommit: 9bf3cdcf5d8b8dd12aa1339b8910fcbc40f4cbe4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2019
ms.locfileid: "71968692"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-bw-using-gx64krb5"></a>gx64krb5 kullanarak SAP BW’da çoklu oturum açma (SSO) için Kerberos'u kullanma

Bu makalede, gx64krb5 kullanılarak Power BI hizmetinden SSO'yu etkinleştirmek için SAP BW veri kaynağınızın nasıl yapılandırılacağı açıklanmaktadır.

> [!NOTE]
> Power BI hizmetinde SAP BW Uygulama Sunucusu tabanlı raporlar için SSO tabanlı yenilemeyi etkinleştirmek üzere [Kerberos SSO yapılandırma](service-gateway-sso-kerberos.md) adımlarına ek olarak bu makaledeki adımları tamamlayabilirsiniz. Ancak Microsoft, SNC kitaplığı olarak gx64krb5 değil CommonCryptoLib kullanılmasını önerir. SAP artık gx64krb5 desteği sağlamamaktadır ve ağ geçidi ile kullanılmak üzere yapılandırmak için gereken adımlar CommonCryptoLib ile karşılaştırıldığında çok daha karmaşıktır. CommonCryptoLib kullanarak SSO yapılandırma hakkında bilgi için bkz. [CommonCryptoLib kullanarak SAP BW’yu SSO için yapılandırma](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md). CommonCryptoLib _veya_ gx64krb5 yapılandırmasını tamamlamanız gerekir. Her iki kitaplık için yapılandırma adımlarını tamamlamayın.

### <a name="set-up-gx64krb5-on-gateway-machine-and-the-sap-bw-server"></a>Ağ geçidi makinesinde ve SAP BW sunucusunda gx64krb5 ayarlama
Bu kılavuz mümkün olduğunca kapsamlı olmaya çalışır. Bu adımlardan bazılarını önceden tamamladıysanız atlayabilirsiniz. Örneğin gx64krb5 kullanarak SSO için zaten SAP BW sunucunuzu ayarlamış olabilirsiniz.

### <a name="set-up-gx64krb5-on-the-gateway-machine-and-the-sap-bw-server"></a>Ağ geçidi makinesinde ve SAP BW sunucusunda gx64krb5 ayarlama

> [!NOTE]
> `gx64krb5` artık SAP tarafından etkin olarak desteklenmiyor. Daha fazla bilgi için bkz. [SAP Notu 352295](https://launchpad.support.sap.com/#/notes/352295). `gx64krb5`'in veri ağ geçidinden SAP BW İleti Sunucularına yönelik SSO bağlantılarına izin vermediğine de dikkat edin. Yalnızca SAP BW Application Server’larla bağlantı kurulabilir. SNC kitaplığı olarak [CommonCryptoLib](service-gateway-sso-kerberos-sap-bw-commoncryptolib.md) kullanıyorsanız sadece Uygulama Sunucusu kısıtlaması yoktur. Diğer SNC kitaplıkları BW SSO için de çalışabilir ancak Microsoft tarafından resmi olarak desteklenmemektedir.

Ağ geçidi üzerinden bir SSO bağlantısını tamamlamak için `gx64krb5` hem istemci hem de sunucu tarafından kullanımda olmalıdır; diğer bir deyişle, hem istemci hem de sunucu aynı SNC kitaplığını kullanıyor olmalıdır.

1. [SAP Notu 2115486](https://launchpad.support.sap.com/) sayfasından `gx64krb5` indirin (SAP s-user gereklidir). En az 1.0.11.x sürümüne sahip olduğunuzdan emin olun. Ayrıca, ağ geçidi aracılığıyla SSO bağlantısını denemeden önce SSO bağlantısını SAP GUI’sinde test etmek istiyorsanız (önerilir) `gsskrb5` (kitaplığın 32 bit sürümü) indirin. SAP GUI yalnızca 32 bit sürümünde kullanılabildiği için SAP GUI ile test ederken 32 bit sürümü gerekir.

1. Ağ geçidi makinenizde `gx64krb5` kitaplığını ağ geçidi hizmetinizin kullanıcısı tarafından erişilebilir bir konuma yerleştirin. SAP GUI kullanarak SSO bağlantısını test etmek istiyorsanız ayrıca makineye bir `gsskrb5` kopyası yerleştirin ve **SNC_LIB** ortam değişkenini ona işaret edecek şekilde ayarlayın. Hem ağ geçidi Hizmeti Kullanıcısı hem de Hizmet Kullanıcısının kimliğine bürüneceği Active Directory (AD) kullanıcıları `gx64krb5` kopyası için okuma ve yürütme izinlerine ihtiyaç duyar. Kimliği Doğrulanmış Kullanıcılar grubuna .dll dosyalarında izin vermenizi öneririz. Test amacıyla, bu izinleri hem ağ geçidi Hizmeti Kullanıcısına hem de test edeceğiniz Active Directory kullanıcısına açıkça verebilirsiniz.

1. BW sunucunuz gx64krb5 kullanılarak SSO için yapılandırılmadıysa, SAP BW sunucu makinenizde SAP BW sunucusu tarafından erişilebilen bir konuma başka bir .dll kopyası yerleştirin. SAP BW sunucusuyla kullanmak üzere gx64krb5'i yapılandırma hakkında daha fazla bilgi için [SAP belgelerine](https://launchpad.support.sap.com/#/notes/2115486) bakın (s-kullanıcısı gereklidir).

1. İstemci ve sunucu makinelerinde `SNC_LIB` ve/veya `SNC_LIB_64` ortam değişkenlerini ayarlayın. gsskrb5 kullanıyorsanız `SNC_LIB` değişkenini gsskrb5.dll dosyasının mutlak yoluna ayarlayın. gx64krb5 kullanıyorsanız `SNC_LIB_64` değişkenini gx64krb5.dll dosyasının mutlak yoluna ayarlayın.

### <a name="configure-an-sap-bw-service-user-and-enable-snc-communication-on-the-bw-server"></a>SAP BW hizmeti kullanıcısı yapılandırma ve BW sunucusunda SNC iletişimini etkinleştirme

gx64krb5 kullanarak SAP BW sunucunuzu SNC iletişimi (örneğin SSO) için henüz yapılandırmadıysanız bu bölümü tamamlayın.

> [!NOTE]
> Bu bölümde, BW için bir Hizmet Kullanıcısı oluşturduğunuz ve bu kullanıcıya uygun bir SPN bağladığınız (örn. `SAP/` ile başlayan bir şey) varsayılır.

1. Hizmet kullanıcısına, SAP BW Application Server’ınıza yönelik erişim verin:

    1. SAP BW sunucu makinesinde, Hizmet Kullanıcısını Local Admin grubuna ekleyin. Bilgisayar Yönetimi programını açın ve sunucunuzun Local Admin grubunu belirleyin. Örneğin:

        ![Bilgisayar Yönetimi programı ekran görüntüsü](media/service-gateway-sso-kerberos/computer-management.png)

    1. Local Admin grubuna çift tıklayın ve **Ekle**'yi seçerek hizmet kullanıcınızı gruba ekleyin. Adı doğru girdiğinizden emin olmak için **Adları Denetle**’yi seçin. **Tamam**'ı seçin.

1. SAP BW sunucusunun Hizmet Kullanıcısını, SAP BW sunucusu makinesinde SAP BW sunucusu hizmetini başlatan kullanıcı olarak ayarlayın.

    1. **Çalıştır**’ı açın ve **Services.msc** girin. SAP BW Application Server örneğinize karşılık gelen hizmeti bulun. Sağ tıklayıp **Özellikler**'i seçin.

        ![Özellikler seçeneği vurgulanmış halde hizmetler ekran görüntüsü](media/service-gateway-sso-kerberos/server-properties.png)

    1. **Oturum açma** sekmesine geçin ve kullanıcıyı, SAP BW hizmet kullanıcınız olarak değiştirin. Kullanıcı parolasını girin ve **Tamam**'ı seçin.

1. SAP Logon uygulamasında, sunucunuzda oturum açın ve RZ10 işlemini kullanarak aşağıdaki profil parametrelerini ayarlayın:

    1. **snc/identity/as** profil parametresini *p:&lt;oluşturduğunuz SAP BW hizmeti kullanıcısı&gt;* olarak ayarlayın, örneğin: *p:BWServiceUser\@MYDOMAIN.COM*. Hizmet kullanıcısının UPN bilgisinin önündeki p: ifadesine dikkat edin. SNC Kitaplığı olarak Genel Şifreleme Kitaplığının kullanıldığı durumdaki gibi P:CN= değildir.

    1. **snc/gssapi\_lib** profil parametresini *&lt;BW sunucu makinesindeki gx64krb5.dll yoluna&gt;* ayarlayın. Kitaplığı SAP BW Application Server’ın erişebileceği bir konuma yerleştirmeyi unutmayın.

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

    1. **snc/enable** özelliğini 1 olarak ayarlayın.

1. Bu profil parametrelerini ayarladıktan sonra sunucu makinesinde SAP Management Console uygulamasını açın ve SAP BW örneğini yeniden başlatın. Sunucu başlatılmazsa profil parametrelerini doğru ayarladığınızı doğrulayın. Profil parametresi ayarları hakkında daha fazla bilgi için [SAP belgelerine](https://help.sap.com/saphelp_nw70ehp1/helpdata/en/e6/56f466e99a11d1a5b00000e835363f/frameset.htm) bakın. Sorunla karşılaşmanız halinde bu bölümün sonraki kısımlarında yer alan sorun giderme bilgilerine de başvurabilirsiniz.

### <a name="map-a-sap-bw-user-to-an-active-directory-user"></a>SAP BW kullanıcısını Active Directory kullanıcısına eşleme

Henüz yapmadıysanız, bir Active Directory kullanıcısını bir SAP BW Application Server kullanıcısına eşleyin ve SAP Logon ile SSO bağlantısını test edin.

1. SAP Logon uygulamasını kullanarak SAP BW sunucunuzda oturum açın. SU01 işlemini çalıştırın.

1. **User** (Kullanıcı) alanına SSO bağlantılarını etkinleştirmek istediğiniz SAP BW kullanıcısını girin (aşağıdaki ekran görüntüsünde BIUSER kullanıcısının izinlerini ayarlamaya hazırlanıyoruz). SAP Logon penceresinin sol üst köşesindeki **Edit** (Düzenle) simgesini (kalem görüntüsü) seçin.

    ![SAP BW User maintenance (Kullanıcı yönetimi) ekranı ekran görüntüsü](media/service-gateway-sso-kerberos/user-maintenance.png)

1. **SNC** sekmesini seçin. SNC name (SNC adı) giriş kutusuna *p:&lt;Active Directory kullanıcınız&gt;@&lt;etki alanınız&gt;* girin. Active Directory kullanıcısının UPN değerinden önce p: ifadesinin kullanılması gerektiğini unutmayın. Belirttiğiniz Active Directory kullanıcısının SAP BW Application Server için SSO erişimini etkinleştirmek istediğiniz kişiye veya kuruluşa ait olması gerekir. Örneğin *testuser\@TESTDOMAIN.COM* adlı kullanıcı için SSO erişimini etkinleştirmek istiyorsanız *p:testuser\@TESTDOMAIN.COM* girin.

    ![SAP BW Maintain users (Kullanıcıları yönet) ekranı ekran görüntüsü](media/service-gateway-sso-kerberos/maintain-users.png)

1. Ekranın Sol üst köşesindeki **Save** (Kaydet) simgesini (disket görseli) seçin.

### <a name="test-sign-in-via-sso"></a>SSO yoluyla oturum açmayı test etme

SSO erişimini etkinleştirmiş olduğunuz Active Directory kullanıcısı olarak SAP Logon kullanarak SSO aracılığıyla sunucuda oturum açabildiğinizi doğrulayın.

1. SSO erişimini etkinleştirmiş olduğunuz Active Directory kullanıcısı olarak etki alanınızda SAP Logon’un yüklü olduğu bir makinede oturum açın. SAP Logon’u başlatın ve yeni bir bağlantı oluşturun.

1. Daha önce indirdiğiniz `gsskrb5`.dll dosyasını yeni oturum açtığınız makinedeki bir konuma indirin. `SNC_LIB` ortam değişkenini bu konumun mutlak yoluna ayarlayın.

1. SAP Logon’u başlatın ve yeni bir bağlantı oluşturun.

1. **Create New System Entry** (Yeni Sistem Girdisi Oluştur) ekranından **User Specified System**'i (Kullanıcı Tarafından Belirtilen Sistem) ve **Next**'i (İleri) seçin.

    ![Create New System Entry (Yeni Sistem Girdisi Oluştur) ekranı ekran görüntüsü](media/service-gateway-sso-kerberos/new-system-entry.png)

1. Sonraki ekranda, uygulama sunucusu, örnek sayısı ve sistem kimliği gibi gerekli bilgileri girin. Ardından **Finish**'i (Son) seçin.

1. Yeni bağlantıya sağ tıklayın ve **Özellikler**'i seçin. **Ağ** sekmesini seçin. **SNC Name** (SNC Adı) metin kutusunda *p:&lt;SAP BW hizmet kullanıcısı UPN'si&gt;* girin, örneğin: *p:BWServiceUser\@MYDOMAIN.COM*. Ardından **Tamam**'ı seçin.

    ![System Entry Properties (Sistem Girdisi Özellikleri) ekranı ekran görüntüsü](media/service-gateway-sso-kerberos/system-entry-properties.png)

1. Yeni oluşturduğunuz bağlantıya çift tıklayarak SAP BW sunucunuzla bir SSO bağlantısı kurmayı deneyin. Bu bağlantı başarılı olursa bir sonraki adıma geçin. Aksi takdirde belgenin önceki adımlarını gözden geçirerek doğru şekilde tamamlandığından emin olun veya aşağıdaki sorun giderme bölümünü inceleyin. Bu bağlamda SSO ile SAP BW sunucusuna bağlanamıyorsanız ağ geçidi bağlamında da SSO ile SAP BW sunucusuna bağlanamayacağınıza dikkat edin.

### <a name="add-registry-entries-to-the-gateway-machine"></a>Ağ geçidi makinesine kayıt defteri girişleri ekleme

Hem ağ geçidinin yüklendiği makinenin hem de Power BI Desktop’tan bağlanılması amaçlanan makinelerin kayıt defterine gerekli kayıt defteri girdilerini ekleyin. Çalıştırılacak komutlar şunlardır:

1. ```REG ADD HKLM\SOFTWARE\Wow6432Node\SAP\gsskrb5 /v ForceIniCredOK /t REG_DWORD /d 1 /f```

1. ```REG ADD HKLM\SOFTWARE\SAP\gsskrb5 /v ForceIniCredOK /t REG_DWORD /d 1 /f```

### <a name="add-a-new-sap-bw-application-server-data-source-to-the-power-bi-service-or-edit-an-existing-one"></a>Power BI hizmetine yeni bir SAP BW Application Server veri kaynağı ekleyin veya var olanı düzenleyin

1. Veri kaynağı yapılandırma penceresinde Application Server’ın **Ana bilgisayar adı**, **Sistem Numarası** ve **İstemci Kimliği** bilgilerini Power BI Desktop'tan SAP BW sunucusunda oturum açar gibi girin.

1. **SNC İş Ortağı Adı** alanına *p:&lt;SAP BW hizmet kullanıcınıza eşlediğiniz SPN'yi girin&gt;* . Örneğin SPN **SAP/BWServiceUser\@MYDOMAIN.COM** ise **SNC İş Ortağı Adı** alanına *p:SAP/BWServiceUser\@MYDOMAIN.COM* girmelisiniz.

1. SNC Kitaplığı alanında **SNC\_LIB** veya **SNC\_LIB\_64** değerini seçin. Ağ geçidi makinesindeki **SNC\_LIB\_64**’ün gx64krb5.dll dosyasını işaret ettiğinden emin olun. Alternatif olarak, "Özel" seçeneğini belirleyebilir ve gx64krb5.dll dosyasının mutlak yolunu belirtin (ağ geçidi makinesinde).

1. **DirectQuery sorguları için Kerberos üzerinden SSO kullanın** kutusunu ve **Uygula**'yı seçin. Bağlantı testi başarılı olmazsa önceki kurulum ve yapılandırma adımlarının doğru şekilde tamamlandığından emin olun.

1. [Power BI raporu çalıştırma](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="troubleshooting"></a>Sorun giderme

### <a name="troubleshoot-gx64krb5-configuration"></a>gx64krb5 yapılandırma sorunlarını giderme

Herhangi bir sorunla karşılaşırsanız gx64krb5 yüklemesinin ve SSO bağlantılarının sorunlarını gidermek için bu adımları izleyin.

* Sunucu günlüklerinin (sunucu makinesinde …work\dev\_w0) görüntülenmesi, gx64krb5 kurulum adımlarını tamamlarken karşılaştığınız hataları giderme konusunda yardımcı olabilir. Bu, özellikle profil parametreleri değiştirildikten sonra SAP BW sunucusu başlamazsa geçerlidir.

* Oturum açma hatası nedeniyle SAP BW hizmetini başlatamıyorsanız SAP BW "başlatma" kullanıcısı ayarlarında yanlış parola girmiş olabilirsiniz. Active Directory ortamınızdaki bir makinede SAP BW hizmet kullanıcısı olarak oturum açarak parolayı doğrulayın.

* Sunucunun başlatılmasını önleyen temel veri kaynağı kimlik bilgileriyle (örneğin, SQL Server) ilgili hata alıyorsanız hizmet kullanıcısına SAP BW veritabanına erişim izni verdiğinizi doğrulayın.

* Aşağıdaki iletiyi alabilirsiniz: *(GSS-API) Belirtilen hedef bilinmiyor veya erişilebilir değil.* Bu genellikle yanlış SNC adını belirttiğiniz anlamına gelir. İstemci uygulamasında "p:CN=" değil yalnızca "p:" ve hizmet kullanıcısının UPN bilgisini kullandığınızdan emin olun.

* Aşağıdaki iletiyi alabilirsiniz: *(GSS-API) Geçersiz bir ad sağlandı.* Sunucunun SNC kimlik profili parametresindeki değerde "p:" ifadesinin bulunduğundan emin olun.

* Aşağıdaki iletiyi alabilirsiniz: *(SNC hatası) Belirtilen modül bulunamadı.* Bu durum, genellikle `gx64krb5.dll` erişim için yükseltilmiş ayrıcalıklar (yönetici hakları) gerektiren bir konuma yerleştirildiğinde oluşur.

### <a name="troubleshoot-gateway-connectivity-issues"></a>Ağ geçidi bağlantı sorunlarını giderme

1. Ağ geçidi günlüklerini kontrol edin. Ağ geçidi yapılandırması uygulamasını açın, **Tanılama Günlükleri**'ni ve **Günlükleri dışarı aktar**'ı seçin. En son hatalar, incelediğiniz günlük dosyalarının en altında bulunur.

    ![Tanılama vurgulanmış olarak Şirket içi veri ağ geçidi uygulaması ekran görüntüsü](media/service-gateway-sso-kerberos/gateway-diagnostics.png)

1. SAP BW izlemeyi açın ve oluşturulan günlük dosyalarını inceleyin. Birçok farklı SAP BW izleme türü vardır (örneğin, CPIC izlemesi). Daha fazla bilgi için SAP belgelerine başvurun.

## <a name="next-steps"></a>Sonraki adımlar

**Şirket içi veri ağ geçidi** ve **DirectQuery** hakkında daha fazla bilgi için aşağıdaki kaynaklara göz atın:

* [Şirket içi veri ağ geçidi nedir?](/data-integration/gateway/service-gateway-onprem)
* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
