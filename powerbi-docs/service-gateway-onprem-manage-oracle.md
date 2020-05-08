---
title: Veri kaynağınızı yönetme - Oracle
description: Şirket içi veri ağ geçidini ve bu ağ geçidine ait veri kaynaklarını yönetme.
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: arthii
LocalizationGroup: Gateways
ms.openlocfilehash: 5641e42d380458bd1ddcdb316c56e17fafe2d71f
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "79207287"
---
# <a name="manage-your-data-source---oracle"></a>Veri kaynağınızı yönetme - Oracle

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

[Şirket içi veri ağ geçidini yükledikten](/data-integration/gateway/service-gateway-install) sonra ağ geçidi ile kullanılabilecek [veri kaynaklarını](service-gateway-data-sources.md#add-a-data-source) eklemeniz gerekir. Bu makalede, zamanlanmış yenileme veya DirectQuery için ağ geçitleri ve Oracle veri kaynaklarıyla nasıl çalışılacağı açıklanır.

## <a name="install-the-oracle-client"></a>Oracle istemcisini yükleme

Ağ geçidini Oracle sunucunuza bağlamak için .NET için Oracle Veri Sağlayıcısı’nın (ODP.NET) yüklenmesi ve yapılandırılması gerekir. ODP.NET, Oracle Data Access Components'ın (ODAC) bir parçasıdır.

Power BI Desktop'ın 32 bit sürümü için, 32 bit Oracle istemcisini indirip yüklemek amacıyla aşağıdaki bağlantıyı kullanın:

* [Oracle Developer Tools for Visual Studio (12.1.0.2.4) ile 32 bit Oracle Data Access Components (ODAC)](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

Power BI Desktop’ın 64 bit sürümü veya Şirket içi veri ağ geçidi için, 64 bit Oracle istemcisini indirip yüklemek üzere aşağıdaki bağlantıyı kullanın:

* [Windows x64 için 64 bit ODAC 12.2c Sürüm 1 (12.2.0.1.0)](https://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

İstemci yüklendikten sonra, tnsnames.ora dosyanızı veritabanınız için uygun bilgilerle yapılandırın. Power BI Desktop ve ağ geçidi, tnsnames.ora dosyasında tanımlanan net_service_name için farklı değerlere sahip olur. net_service_name yapılandırılmamışsa bağlanamazsınız. tnsnames.ora için varsayılan yol şudur: `[Oracle Home Directory]\Network\Admin\tnsnames.ora`. tnsnames.ora dosyalarının nasıl yapılandırılacağı hakkında daha fazla bilgi için bkz. [Oracle: Yerel adlandırma parametreleri (tnsnames.ora)](https://docs.oracle.com/cd/B28359_01/network.111/b28317/tnsnames.htm).

### <a name="example-tnsnamesora-file-entry"></a>Örnek tnsnames.ora dosya girişi

tnsname.ora dosyasındaki bir girişin temel biçimi şöyledir:

```
net_service_name=
 (DESCRIPTION=
   (ADDRESS=(protocol_address_information))
   (CONNECT_DATA=
     (SERVICE_NAME=service_name)))
```

Burada sunucu ve bağlantı noktası bilgileri doldurulmuş bir örnek verilmiştir:

```
CONTOSO =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = oracleserver.contoso.com)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = CONTOSO)
    )
  )
```

## <a name="add-a-data-source"></a>Veri kaynağı ekleme

Veri kaynağı ekleme hakkında daha fazla bilgi için bkz. [Veri kaynağı ekleme](service-gateway-data-sources.md#add-a-data-source). **Veri Kaynağı Türü**’nün altından **Oracle**’ı seçin.

![Oracle veri kaynağını ekleme](media/service-gateway-onprem-manage-oracle/data-source-oracle.png)

Oracle veri Kaynağı türünü seçtikten sonra, **Sunucu** ve **Veritabanı** da dahil olmak üzere veri kaynağına ilişkin bilgileri doldurun. 

**Kimlik Doğrulama Yöntemi** olarak **Windows** veya **Temel** seçeneklerinden birini belirleyebilirsiniz. Windows kimlik doğrulaması yerine Oracle'da oluşturulmuş bir hesabı kullanmayı planlıyorsanız **Temel**'i seçin. Ardından, bu veri kaynağı için kullanılacak kimlik bilgilerini girin.

> [!NOTE]
> Veri kaynağına yönelik tüm sorgular bu kimlik bilgileri kullanılarak çalıştırılır. Kimlik bilgilerinin nasıl depolandığı hakkında daha fazla bilgi edinmek için bkz. [Şifrelenmiş kimlik bilgilerini bulutta depolama](service-gateway-data-sources.md#store-encrypted-credentials-in-the-cloud).

![Veri kaynağı ayarlarını doldurma](media/service-gateway-onprem-manage-oracle/data-source-oracle2.png)

Tüm bilgileri doldurduktan sonra **Ekle**'yi seçin. Artık bu veri kaynağını bir şirket içi Oracle sunucusunda zamanlanmış yenileme veya DirectQuery için kullanabilirsiniz. İşlem başarılı olursa *Bağlantı Başarılı* iletisini görürsünüz.

![Bağlantı durumunu görüntüleme](media/service-gateway-onprem-manage-oracle/datasourcesettings4.png)

### <a name="advanced-settings"></a>Gelişmiş ayarlar

İsteğe bağlı olarak, veri kaynağınızın gizlilik düzeyini yapılandırabilirsiniz. Bu ayar verilerin nasıl birleştirilebileceğini denetler. Bu ayar yalnızca zamanlanmış yenileme için kullanılır. Gizlilik düzeyi ayarı DirectQuery için geçerli değildir. Veri kaynağınıza ilişkin gizlilik düzeyleri hakkında daha fazla bilgi edinmek için bkz. [Gizlilik düzeyleri (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Gizlilik düzeyini ayarlama](media/service-gateway-onprem-manage-oracle/datasourcesettings9.png)

## <a name="use-the-data-source"></a>Veri kaynağını kullanma

Veri kaynağı, oluşturulduktan sonra DirectQuery bağlantılarıyla veya zamanlanmış yenileme yoluyla kullanılabilir.

> [!WARNING]
> Şirket içi veri ağ geçidinde bulunan veri kaynağındaki ve Power BI Desktop’taki sunucu ve veritabanı adları eşleşmelidir.

Ağ geçidindeki veri kaynağı ve veri kümeniz arasındaki bağlantı, sunucu ve veritabanı adınızı temel alır. Bu adların eşleşmesi gerekir. Örneğin, Power BI Desktop'ta sunucu adı için bir IP adresi sağlarsanız ağ geçidi yapılandırmasındaki veri kaynağında da bu IP adresini kullanmanız gerekir. Bu adın, tnsnames.ora dosyasında tanımlanan bir diğer ad ile aynı olması gerekir. tnsnames.ora dosyası hakkında daha fazla bilgi için bkz. [Oracle İstemcisini Yükleme](#install-the-oracle-client).

Bu gereksinim hem DirectQuery hem de zamanlanmış yenileme için geçerlidir.

### <a name="use-the-data-source-with-directquery-connections"></a>Veri kaynağını DirectQuery bağlantılarıyla kullanma

Sunucu ve veritabanı adlarının, Power BI Desktop'ta ve ağ geçidinin yapılandırılmış veri kaynağında eşleştiğinden emin olun. Ayrıca, DirectQuery veri kümelerini yayımlamak için kullanıcınızın, veri kaynağının **Kullanıcılar** sekmesinde listelendiğinden emin olmanız gerekir. DirectQuery'ye yönelik seçim, Power BI Desktop'ta verileri ilk kez içeri aktardığınız sırada gerçekleşir. DirectQuery’yi kullanma hakkında daha fazla bilgi için [Power BI Desktop'ta DirectQuery’yi kullanma](desktop-use-directquery.md) başlıklı makaleye bakın.

Power BI Desktop'tan veya **Veri Al** seçeneğini kullanarak yayımladığınız raporlarınızla hemen çalışmaya başlayabilirsiniz. Siz ağ geçidinde veri kaynağını oluşturduktan sonra bağlantının kullanılabilir duruma gelmesi için birkaç dakika beklemeniz gerekebilir.

### <a name="use-the-data-source-with-scheduled-refresh"></a>Zamanlanmış yenileme ile veri kaynağını kullanma

Ağ geçidinde yapılandırılan veri kaynağının **Kullanıcılar** sekmesinde yer alıyorsanız ve sunucu adı ile veritabanı adı eşleşiyorsa ağ geçidini zamanlanmış yenileme ile kullanılabilen bir seçenek olarak görürsünüz.

![Kullanıcıları görüntüleme](media/service-gateway-onprem-manage-oracle/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="troubleshooting"></a>Sorun giderme

Adlandırma söz dizimi yanlış olduğunda veya doğru yapılandırılmadığında Oracle'da birkaç hata ile karşılaşabilirsiniz:

* ORA-12154: TNS: could not resolve the connect identifier specified (TNS: Belirtilen bağlantı tanımlayıcısı çözümlenemiyor).
* ORA-12514: TNS: listener does not currently know of service requested in connect descriptor (TNS: dinleyici, bağlantı tanımlayıcıda istenen hizmeti şu anda tanımıyor).
* ORA-12541: TNS: no listener (TNS: dinleyici yok).
* ORA-12170: TNS:Connect timeout occurred (TNS: Bağlantı zaman aşımı oluştu).
* ORA-12504: TNS: listener was not given the SERVICE_NAME in CONNECT_DATA (TNS: dinleyiciye CONNECT_DATA konumunda SERVICE_NAME verilmedi).

Oracle istemcisi yüklü olmadığında veya doğru yapılandırılmadığında bu hatalar oluşabilir. Yüklüyse tnsnames.ora dosyasının düzgün şekilde yapılandırıldığını ve uygun net_service_name kullandığınızı doğrulayın. Ayrıca, Power BI Desktop'ı kullanan makine ile ağ geçidini çalıştıran makine arasında aynı net_service_name değerinin kullanıldığından emin olmanız gerekir. Daha fazla bilgi için bkz. [Oracle istemcisini yükleme](#install-the-oracle-client).

> [!NOTE]
> Oracle sunucu sürümü ve Oracle istemci sürümü arasındaki uyumsuzluktan kaynaklanan bir sorunla karşılaşabilirsiniz. Genellikle bu sürümlerin eşleşmesi istenir.

Ağ geçidi ile ilgili daha fazla sorun giderme bilgisi için bkz. [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](/data-integration/gateway/service-gateway-tshoot).

## <a name="next-steps"></a>Sonraki adımlar

* [Ağ geçidiyle ilgili sorunları giderme - Power BI](service-gateway-onprem-tshoot.md)
* [Power BI Premium](service-premium.md)

Başka bir sorunuz mu var? [Power BI Topluluğu](https://community.powerbi.com/)'na sorun.

