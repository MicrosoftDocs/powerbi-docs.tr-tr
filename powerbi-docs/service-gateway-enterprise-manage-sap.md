---
title: Veri kaynağınızı yönetme - SAP HANA
description: Şirket içi veri ağ geçidini ve bu ağ geçidine ait veri kaynaklarını yönetme. Bu makale SAP HANA'ya özeldir.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: b61d794701d18fd25ab9acb5d5208ae289376eb6
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271768"
---
# <a name="manage-your-data-source---sap-hana"></a>Veri kaynağınızı yönetme - SAP HANA

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

[Şirket içi veri ağ geçidini yükledikten](/data-integration/gateway/service-gateway-install) sonra, ilgili ağ geçidi ile kullanılabilecek [veri kaynaklarını](service-gateway-data-sources.md#add-a-data-source) eklemeniz gerekir. Bu makalede, zamanlanmış yenileme veya DirectQuery için kullanılan ağ geçitleri ve SAP HANA veri kaynaklarıyla nasıl çalışılacağı açıklanır.

## <a name="add-a-data-source"></a>Veri kaynağı ekleme

Veri kaynağı ekleme hakkında bilgi edinmek için bkz. [Veri kaynağı ekleme](service-gateway-data-sources.md#add-a-data-source). **Veri Kaynağı Türü** içi SAP HANA’yı seçin.

![SAP HANA veri kaynağını ekleme](media/service-gateway-enterprise-manage-sap/datasourcesettings2-sap.png)

SAP HANA veri kaynağını seçtikten sonra, **Sunucu**, **Kullanıcı adı** ve **Parola** gibi veri kaynağına ilişkin bilgileri doldurmanız gerekir.

> [!NOTE]
> Veri kaynağına yönelik tüm sorgular bu kimlik bilgileri kullanılarak çalıştırılır. Kimlik bilgilerinin nasıl depolandığı hakkında daha fazla bilgi almak için bkz. [Şifrelenmiş kimlik bilgilerini bulutta depolama](service-gateway-data-sources.md#storing-encrypted-credentials-in-the-cloud).

![Veri kaynağı ayarlarını doldurma](media/service-gateway-enterprise-manage-sap/datasourcesettings3-sap.png)

Tüm bilgileri doldurduktan sonra **Ekle**'yi seçin. Artık bu veri kaynağını bir şirket içi SAP HANA sunucusunda zamanlanmış yenileme veya DirectQuery için kullanabilirsiniz. İşlem başarılı olduğunda *Bağlantı Başarılı* iletisini göreceksiniz.

![Bağlantı durumunu görüntüleme](media/service-gateway-enterprise-manage-sap/datasourcesettings4.png)

### <a name="advanced-settings"></a>Gelişmiş ayarlar

İsteğe bağlı olarak, veri kaynağınızın gizlilik düzeyini yapılandırabilirsiniz. Bu işlem, verilerin nasıl birleştirilebileceğini denetler. Bu işlem yalnızca zamanlanmış yenileme için kullanılır. DirectQuery için geçerli değildir. Veri kaynağınıza ilişkin gizlilik düzeyleri hakkında daha fazla bilgi edinmek için bkz. [Gizlilik düzeyleri (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Gizlilik düzeyini ayarlama](media/service-gateway-enterprise-manage-sap/datasourcesettings9.png)

## <a name="using-the-data-source"></a>Veri kaynağını kullanma

Oluşturduğunuz veri kaynağı, DirectQuery bağlantıları veya zamanlanmış yenileme ile kullanılabilir.

> [!NOTE]
> Şirket içi veri ağ geçidinde bulunan veri kaynağındaki ve Power BI Desktop’taki sunucu ve veritabanı adı eşleşmelidir.

Ağ geçidindeki veri kaynağı ve veri kümeniz arasındaki bağlantı, sunucu ve veritabanı adınızı temel alır. Bunlar eşleşmelidir. Örneğin, Power BI Desktop'ta sunucu adı için bir IP Adresi sağlarsanız ağ geçidi yapılandırmasındaki veri kaynağında da bu IP Adresini kullanmanız gerekir. Power BI Desktop'ta *SUNUCU\ÖRNEK* yapılandırmasını kullanırsanız ağ geçidi için yapılandırılan veri kaynağında da aynısını kullanmanız gerekir.

Bu durum hem DirectQuery hem de zamanlanmış yenileme için geçerlidir.

### <a name="using-the-data-source-with-directquery-connections"></a>Veri kaynağını DirectQuery bağlantılarıyla kullanma

Sunucu ve veritabanı adının, Power BI Desktop'ta ve ağ geçidinin yapılandırılmış veri kaynağında eşleştiğinden emin olmanız gerekir. Ayrıca, DirectQuery veri kümelerini yayımlamak için kullanıcınızın, veri kaynağının **Kullanıcılar** sekmesinde listelendiğinden emin olmanız gerekir. DirectQuery'ye yönelik seçim, Power BI Desktop'ta verileri ilk kez içeri aktardığınız sırada gerçekleşir. DirectQuery’yi kullanma hakkında daha fazla bilgi için [Power BI Desktop'ta DirectQuery’yi kullanma](desktop-use-directquery.md) başlıklı makaleye bakın.

Power BI Desktop'tan veya **Veri Al** seçeneğini kullanarak yayımladığınız raporlarınızla hemen çalışmaya başlayabilirsiniz. Ağ geçidinde veri kaynağı oluşturulduktan sonra bağlantının kullanılabilir hale gelmesi için birkaç dakika beklemeniz gerekebilir.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Zamanlanmış yenileme ile veri kaynağını kullanma

Ağ geçidinde yapılandırılan veri kaynağının **Kullanıcılar** sekmesinde yer alıyorsanız ve sunucu ile veritabanı adı eşleşiyorsa ağ geçidini zamanlanmış yenileme ile kullanılabilen bir seçenek olarak görürsünüz.

![Kullanıcıları görüntüleme](media/service-gateway-enterprise-manage-sap/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Sonraki adımlar

* [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](/data-integration/gateway/service-gateway-tshoot)
* [Ağ geçidiyle ilgili sorunları giderme - Power BI](service-gateway-onprem-tshoot.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

