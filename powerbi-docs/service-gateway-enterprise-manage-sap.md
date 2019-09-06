---
title: Veri kaynağınızı yönetme - SAP HANA
description: Şirket içi veri ağ geçidini ve bu ağ geçidine ait veri kaynaklarını yönetme. Bu makale SAP HANA'ya özeldir.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/16/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: b3e1ea53abeff39609515b0b615f9e000432e9c6
ms.sourcegitcommit: 09ee1b4697aad84d8f4c9421015d7e4dbd3cf25f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70303171"
---
# <a name="manage-your-data-source---sap-hana"></a>Veri kaynağınızı yönetme - SAP HANA

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

[Şirket içi veri ağ geçidini yükledikten](/data-integration/gateway/service-gateway-install) sonra ağ geçidi ile kullanılabilecek [veri kaynaklarını](service-gateway-data-sources.md#add-a-data-source) eklemeniz gerekir. Bu makalede, zamanlanmış yenileme veya DirectQuery için kullanılan ağ geçitleri ve SAP HANA veri kaynaklarıyla nasıl çalışılacağı açıklanır.

## <a name="add-a-data-source"></a>Veri kaynağı ekleme

Veri kaynağı ekleme hakkında daha fazla bilgi için bkz. [Veri kaynağı ekleme](service-gateway-data-sources.md#add-a-data-source). **Veri Kaynağı Türü**’nün altından **SAP HANA**’yı seçin.

![SAP HANA veri kaynağını ekleme](media/service-gateway-enterprise-manage-sap/datasourcesettings2-sap.png)

SAP HANA veri kaynağı türünü seçtikten sonra, **Sunucu**, **Kullanıcı adı** ve **Parola** gibi veri kaynağına ilişkin bilgileri doldurun.

> [!NOTE]
> Veri kaynağına yönelik tüm sorgular bu kimlik bilgileri kullanılarak çalıştırılır. Kimlik bilgilerinin nasıl depolandığı hakkında daha fazla bilgi edinmek için bkz. [Şifrelenmiş kimlik bilgilerini bulutta depolama](service-gateway-data-sources.md#store-encrypted-credentials-in-the-cloud).

![Veri kaynağı ayarlarını doldurma](media/service-gateway-enterprise-manage-sap/datasourcesettings3-sap.png)

Tüm bilgileri doldurduktan sonra **Ekle**'yi seçin. Artık bu veri kaynağını bir şirket içi SAP HANA sunucusunda zamanlanmış yenileme veya DirectQuery için kullanabilirsiniz. İşlem başarılı olursa *Bağlantı Başarılı* iletisini görürsünüz.

![Bağlantı durumunu görüntüleme](media/service-gateway-enterprise-manage-sap/datasourcesettings4.png)

### <a name="advanced-settings"></a>Gelişmiş ayarlar

İsteğe bağlı olarak, veri kaynağınızın gizlilik düzeyini yapılandırabilirsiniz. Bu ayar verilerin nasıl birleştirilebileceğini denetler. Bu ayar yalnızca zamanlanmış yenileme için kullanılır. Gizlilik düzeyi ayarı DirectQuery için geçerli değildir. Veri kaynağınıza ilişkin gizlilik düzeyleri hakkında daha fazla bilgi edinmek için bkz. [Gizlilik düzeyleri (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Gizlilik düzeyini ayarlama](media/service-gateway-enterprise-manage-sap/datasourcesettings9.png)

## <a name="use-the-data-source"></a>Veri kaynağını kullanma

Veri kaynağı, oluşturulduktan sonra DirectQuery bağlantılarıyla veya zamanlanmış yenileme yoluyla kullanılabilir.

> [!NOTE]
> Şirket içi veri ağ geçidinde bulunan veri kaynağındaki ve Power BI Desktop’taki sunucu ve veritabanı adları eşleşmelidir.

Ağ geçidindeki veri kaynağı ve veri kümeniz arasındaki bağlantı, sunucu ve veritabanı adınızı temel alır. Bu adların eşleşmesi gerekir. Örneğin, Power BI Desktop'ta sunucu adı için bir IP adresi sağlarsanız ağ geçidi yapılandırmasındaki veri kaynağında da bu IP adresini kullanmanız gerekir. Power BI Desktop'ta *SUNUCU\ÖRNEK* yapılandırmasını kullanırsanız ağ geçidi için yapılandırılan veri kaynağının içinde de bunu kullanmanız gerekir.

Bu gereksinim hem DirectQuery hem de zamanlanmış yenileme için geçerlidir.

### <a name="use-the-data-source-with-directquery-connections"></a>Veri kaynağını DirectQuery bağlantılarıyla kullanma

Sunucu ve veritabanı adlarının, Power BI Desktop'ta ve ağ geçidinin yapılandırılmış veri kaynağında eşleştiğinden emin olun. Ayrıca, DirectQuery veri kümelerini yayımlamak için kullanıcınızın, veri kaynağının **Kullanıcılar** sekmesinde listelendiğinden emin olmanız gerekir. DirectQuery'ye yönelik seçim, Power BI Desktop'ta verileri ilk kez içeri aktardığınız sırada gerçekleşir. DirectQuery’yi kullanma hakkında daha fazla bilgi için [Power BI Desktop'ta DirectQuery’yi kullanma](desktop-use-directquery.md) başlıklı makaleye bakın.

Power BI Desktop'tan veya **Veri Al** seçeneğini kullanarak yayımladığınız raporlarınızla hemen çalışmaya başlayabilirsiniz. Siz ağ geçidinde veri kaynağını oluşturduktan sonra bağlantının kullanılabilir duruma gelmesi için birkaç dakika beklemeniz gerekebilir.

### <a name="use-the-data-source-with-scheduled-refresh"></a>Zamanlanmış yenileme ile veri kaynağını kullanma

Ağ geçidinde yapılandırılan veri kaynağının **Kullanıcılar** sekmesinde yer alıyorsanız ve sunucu adı ile veritabanı adı eşleşiyorsa ağ geçidini zamanlanmış yenileme ile kullanılabilen bir seçenek olarak görürsünüz.

![Kullanıcıları görüntüleme](media/service-gateway-enterprise-manage-sap/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Sonraki adımlar

* [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](/data-integration/gateway/service-gateway-tshoot)
* [Ağ geçidiyle ilgili sorunları giderme - Power BI](service-gateway-onprem-tshoot.md) 

Başka bir sorunuz mu var? [Power BI Topluluğu](http://community.powerbi.com/)'na sorun.

