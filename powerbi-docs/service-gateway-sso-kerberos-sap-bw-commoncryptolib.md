---
title: CommonCryptoLib (sapcrypto.dll) kullanarak SSO için SAP BW’de Kerberos çoklu oturum açma kullanma
description: CommonCryptoLib (sapcrypto.dll) kullanarak SAP BW sunucunuzu Power BI hizmetinden SSO etkinleştirecek şekilde yapılandırma
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/01/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 6c4f2b0d8856d5e68e02b9b33cf393ca85ecb580
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71106297"
---
# <a name="use-kerberos-single-sign-on-for-sso-to-sap-bw-using-commoncryptolib-sapcryptodll"></a>CommonCryptoLib (sapcrypto.dll) kullanarak SSO için SAP BW’de Kerberos çoklu oturum açma kullanma

Bu makalede, CommonCryptoLib (sapcrypto.dll) kullanılarak Power BI hizmetinden SSO'yu etkinleştirmek için SAP BW sunucunuzun nasıl yapılandırılacağı açıklanmaktadır.

> [!NOTE]
> Kerberos SSO’su kullanan SAP BW tabanlı bir raporu yenilemeyi denemeden önce [Kerberos SSO’yu Yapılandırma](service-gateway-sso-kerberos.md) bölümündeki adımlara ek olarak bu makaledeki adımları tamamlayın. SNC kitaplığı olarak CommonCryptoLib kullanmak, hem SAP BW Uygulama Sunucuları hem de SAP BW İleti Sunucuları ile SSO bağlantıları kurmayı sağlar.

## <a name="configure-sap-bw-server-to-enable-sso-using-commoncryptolib"></a>CommonCryptoLib kullanarak SSO’yu etkinleştirmek için SAP BW yapılandırma

> [!NOTE]
> Şirket içi veri ağ geçidi 64 bit yazılımdır ve bu nedenle CommonCryptoLib’in (sapcrypto.dll) 64 bit sürümünü gerektirir. Ağ geçidi aracılığıyla bir SSO bağlantısı denemeden önce SAP GUI’de SAP BW sunucunuzla SSO bağlantısını test etmeyi planlıyorsanız (önerilir), SAP GUI bir 32 bit yazılım olduğu için CommonCryptoLib’in 32 bit sürümü de gerekli olacaktır.

1. BW sunucunuzun CommonCryptoLib kullanarak Kerberos SSO için doğru yapılandırıldığından emin olun. Doğru yapılandırılmışsa, CommonCryptoLib kullanacak şekilde yapılandırılmış SAP GUI’si gibi bir SAP aracı ile BW sunucunuza erişmek için (doğrudan veya bir SAP BW İleti Sunucusu üzerinden) SSO kullanabilmeniz gerekir. Kurulum adımları hakkında daha fazla bilgi için bkz. [Sap Çoklu Oturum Açma: Kerberos/SPNEGO ile kimlik doğrulama](https://blogs.sap.com/2017/07/27/sap-single-sign-on-authenticate-with-kerberosspnego/). BW sunucunuzun CommonCryptoLib’i SNC Kitaplığı olarak kullanması ve “CN=BW1” gibi “CN=” ile başlayan bir SNC adının olması gerekir. SNC ad gereksinimleri hakkında daha fazla bilgi için bkz [Kerberos Yapılandırması için SNC Parametreleri](https://help.sap.com/viewer/df185fd53bb645b1bd99284ee4e4a750/3.0/en-US/360534094511490d91b9589d20abb49a.html) (özellikle snc/kimlik/parametre olarak).

1. Daha önce yapmadıysanız, [SAP .NET Bağlayıcısının](https://support.sap.com/en/product/connectors/msnet.html) x64 sürümünü, ağ geçidinin yüklü olduğu bilgisayara yükleyin. Power BI Desktop’taki BW sunucunuza bağlanmayı deneyerek bileşenin yüklenip yüklenmediğini denetleyebilirsiniz. 2\.0 uygulamasını kullanarak bağlanamıyorsanız, .NET Connector yüklü değildir.

1. SAP Güvenli Oturum Açma İstemcisi’nin (SLC) ağ geçidinin yüklü olduğu bilgisayarda çalışmadığından emin olun. SLC, Kerberos biletlerini ağ geçidinin çoklu oturum açma için Kerberos’u kullanma özelliğini engelleyebilecek şekilde önbelleğe alır. SLC yüklüyse, SLC’yi kaldırın veya SAP Güvenli Oturum Açma İstemcisi’nden çıktığınızdan emin olun: ağ geçidini kullanarak çoklu oturum açma gerçekleştirmeyi denemeden önce sistem tepsisinden simgeye sağ tıklayıp Oturumu Kapat’ı belirleyin. SLC, Windows Server makinelerinde kullanım için desteklenmez. Daha fazla bilgi için bkz. [SAP Notu 2780475](https://launchpad.support.sap.com/#/notes/2780475) (s-user gerekir).

    ![SAP Güvenli Oturum Açma İstemcisi](media/service-gateway-sso-kerberos/sap-secure-login-client.png)

    SLC’yi kaldırırsanız veya **Oturumu Kapat** ve **Çıkış**’ı seçerseniz, ağ geçidi aracılığıyla bir çoklu oturum açma bağlantısı kurmayı denemeden önce önbellekteki tüm Kerberos biletlerini temizlemek için bir komut penceresi açıp pencereye şunu girin: `klist purge`.

1. SAP Launchpad’den 64 bit CommonCryptoLib’in (sapcrypto.dll) **8.5.25 veya daha yeni sürümünü** indirip bunu ağ geçidi makinenizdeki bir klasöre kopyalayın. sapcrypto.dll dosyasını kopyaladığınız dizinde sapcrypto.ini adlı bir dosya oluşturup aşağıdaki içeriklere sahip olmasını sağlayın:

    ```
    ccl/snc/enable_kerberos_in_client_role = 1
    ```

    .ini dosyası, CommonCryptoLib’in ağ geçidi senaryosunda çoklu oturum açmayı etkinleştirmek için gerek duyduğu yapılandırma bilgilerini içerir.

    > [!NOTE]
    > Bu dosyalar aynı konumda depolanmalıdır. Farklı bir deyişle, _/path/to/sapcrypto/_ dizini hem sapcrpyto.ini hem de sapcrypto.dll dosyasını içermelidir.

    Hem ağ geçidi Hizmeti Kullanıcısı hem de Hizmet Kullanıcısının kimliğine bürüneceği Active Directory (AD) kullanıcısı her iki dosya için okuma ve yürütme izinlerine ihtiyaç duyar. Kimliği Doğrulanmış Kullanıcılar grubuna hem .ini hem de .dll dosyalarında izin vermenizi öneririz. Test amacıyla, bu izinleri hem ağ geçidi Hizmeti Kullanıcısına hem de test edeceğiniz Active Directory kullanıcısına açıkça verebilirsiniz. Aşağıdaki ekran görüntüsünde, sapcrypto.dll dosyası için Kimliği Doğrulanmış Kullanıcılar grubuna **Okuma ve &amp;Yürütme** izinlerinin verilmiş olduğunu görebilirsiniz:

    ![Kimliği doğrulanmış kullanıcılar](media/service-gateway-sso-kerberos/authenticated-users.png)

1. Bir SAP BW veri kaynağınız yoksa, Power BI hizmetinin **Ağ geçitlerini yönet** sayfasından bir veri kaynağı ekleyin. Çoklu oturum açma bağlantısının akışına izin verilen, ağ geçidiyle ilişkilendirilmiş bir BW veri kaynağınız varsa bunu düzenlemeye hazırlanın. BW Uygulama Sunucusu ile SSO bağlantısı oluşturmak istiyorsanız **Veri Kaynağı Türü** olarak **SAP Business Warehouse**’u seçin. BW İleti Sunucusu ile SSO bağlantısı oluşturmak istiyorsanız **Sap Business Warehouse İleti Sunucusu**’nu seçin.

    **SNC Kitaplığı** için **SNC\_LIB veya SNC\_LIB\_64 ortam değişkeni** ya da **Özel**’i seçin. **SNC\_LIB** seçeneğini belirlerseniz, ağ geçidinde **SNC\_LIB\_64** ortam değişkenin değerini, ağ geçidindeki sapcrypto.dll dosyasının 64 bit kopyasının mutlak yoluna ayarlamanız gerekir (örneğin C:\Users\Test\Desktop\sapcrypto.dll). **Özel**’i seçerseniz, **Ağ geçitlerini yönet** sayfasında çıkan sapcrypto.dll için mutlak yolu Custom SNC Kitaplığı Yol alanına yapıştırın. **SNC İş Ortağı Adı** için BW sunucusunun SNC Adını girin. **Gelişmiş ayarlar** altından, **DirectQuery sorguları için Kerberos üzerinden SSO kullanın** kutusunun işaretlendiğinden emin olun. Diğer alanlar, PBI Desktop'tan bir Windows Kimlik Doğrulama bağlantısı kurarken olduğu gibi doldurulmalıdır.

1. Bir CCL\_PROFILE sistem ortamı değişkeni oluşturup bunun sapcrypto.ini dosyasına işaret etmesini sağlayın.

    ![CCL\_PROFILE sistem ortamı değişkeni](media/service-gateway-sso-kerberos/ccl-profile-variable.png)

    sapcrypto.dll ve .ini dosyalarının aynı konumda bulunması gerektiğini unutmayın. sapcrypto.ini dosyasının masaüstünde bulunduğu yukarıdaki örnekte, sapcrypto.dll dosyası da masaüstünde bulunmalıdır.

1. Ağ geçidi hizmetini yeniden başlatın:

    ![Ağ geçidi hizmetini yeniden başlatma](media/service-gateway-sso-kerberos/restart-gateway-service.png)

1. [Power BI raporu çalıştırma](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="troubleshooting"></a>Sorun giderme

Power BI hizmetindeki raporu yenileyemiyorsanız, bu sorunu tanılamanıza yardımcı olması için ağ geçidi izleme, CPIC izleme ve CommonCryptoLib izleme özelliklerini kullanabilirsiniz. CPIC izleme ve CommonCryptoLib, SAP ürünleridir. Bu nedenle, Microsoft bunlar için doğrudan destek sağlayamaz. Bazı Active Directory yapılandırmaları, BW’ye SSO erişimi verilecek Active Directory kullanıcıları için kullanıcıların ağ geçidinin kurulu olduğu makinede Yöneticiler grubunun üyesi olmasını gerektirebilir.

1. **Ağ geçidi günlükleri:** Sorunu yeniden oluşturun. [Ağ geçidi uygulamasını](https://docs.microsoft.com/data-integration/gateway/service-gateway-app) açın, **Tanılama** sekmesine gidin ve **Günlükleri dışarı aktar** seçeneğini belirleyin:

    ![Ağ geçidi günlüklerini dışarı aktarma](media/service-gateway-sso-kerberos/export-gateway-logs.png)

1. **CPIC İzleme:** CPIC izlemeyi etkinleştirmek için iki ortam değişkeni ayarlayın: CPIC\_TRACE ve CPIC\_TRACE\_DIR. İlk değişken izleme düzeyini, ikinci değişken de izleme dosyası dizinini ayarlar. Dizin, Kimliği Doğrulanmış Kullanıcılar grubunun yazma izninin bulunduğu bir konum olmalıdır. Set CPIC\_TRACE parametresini 3 olarak belirleyip CPIC\_TRACE\_ parametresini izleme dosyalarının yazılmasını istediğiniz dizine ayarlayın.

    ![CPIC izleme](media/service-gateway-sso-kerberos/cpic-tracing.png)

    Sorunları yeniden oluşturup CPIC\_TRACE\_DIR parametresinin izleme dosyalarını içerdiğinden emin olun.

1. **CommonCryptoLib İzleme:** Önceden oluşturduğunuz sapcrypto.ini dosyasına iki satır ekleyerek CommonCryptoLib izlemeyi açın:

    ```
    ccl/trace/level=5
    ccl/trace/directory=<drive>:\logs\sectrace
    ```

    _ccl/trace/directory_ seçeneğini Kimliği Doğrulanmış Kullanıcılar grubu üyelerinin yazma izninin olduğu bir konuma ayarladığınızdan emin olun. Alternatif olarak, bu davranışı değiştirmek için yeni bir .ini dosyası oluşturun. sapcrypto.ini ve sapcrypto.dll ile aynı dizinde sectrace.ini adlı bir dosya oluşturup aşağıdaki içeriklere sahip olmasını sağlayın. DİZİN seçeneğini, Kimliği Doğrulanmış Kullanıcının yazma izninin olduğu, makinenizde bulunan bir konumla değiştirin:

    ```
    LEVEL = 5

    DIRECTORY = <drive>:\logs\sectrace
    ```

    Şimdi, sorunu yeniden oluşturun ve DIZINE göre işaret eden konumun izleme dosyaları içerip içermediğini denetleyin. İşiniz bittiğinde CPIC ve CCL izlemeyi kapatmayı unutmayın.

    CommonCryptoLib izleme hakkında daha fazla bilgi için bkz. [SAP Notu 2491573](https://launchpad.support.sap.com/#/notes/2491573) (s-user gerekir).

## <a name="next-steps"></a>Sonraki adımlar

**Şirket içi veri ağ geçidi** ve **DirectQuery** hakkında daha fazla bilgi için aşağıdaki kaynaklara göz atın:

* [Şirket içi veri ağ geçidi nedir?](/data-integration/gateway/service-gateway-getting-started)
* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
