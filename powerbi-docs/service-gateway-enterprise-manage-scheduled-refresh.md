---
title: Veri kaynağınızı yönetme - İçeri Aktarma/Zamanlanmış Yenileme
description: Şirket içi veri ağ geçidini ve bu ağ geçidine ait veri kaynaklarını yönetme. Bu makale, içeri aktarma/zamanlanmış yenileme ile kullanılabilen veri kaynaklarına yöneliktir.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 2a3cdc3e6c4fc4f18613994a919f8ab733df5e14
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271692"
---
# <a name="manage-your-data-source---importscheduled-refresh"></a>Veri kaynağınızı yönetme - İçeri Aktarma/Zamanlanmış Yenileme

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

[Şirket içi veri ağ geçidini yükledikten](/data-integration/gateway/service-gateway-install) sonra, ilgili ağ geçidi ile kullanılabilecek [veri kaynaklarını](service-gateway-data-sources.md#add-a-data-source) eklemeniz gerekir. Bu makale, DirectQuery veya canlı bağlantılardan farklı olarak, zamanlanmış yenileme için kullanılan veri kaynakları ve ağ geçitleri ile nasıl çalışılacağını inceler.

## <a name="add-a-data-source"></a>Veri kaynağı ekleme

Veri kaynağı ekleme hakkında bilgi edinmek için bkz. [Veri kaynağı ekleme](service-gateway-data-sources.md#add-a-data-source).

Listelenen tüm veri kaynağı türleri, şirket içi veri ağ geçidi ile zamanlanmış yenileme için kullanılabilir. Analysis Services, SQL Server ve SAP HANA zamanlanmış yenileme veya DirectQuery/canlı bağlantılar için kullanılabilir.

![Veri kaynağını seçin](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings2.png)

Ardından, kaynak bilgilerini ve veri kaynağına erişmek için kullanılan kimlik bilgilerini içeren veri kaynağı bilgilerini doldurmanız gerekir.

> [!NOTE]
> Veri kaynağına yönelik tüm sorgular bu kimlik bilgileri kullanılarak çalıştırılır. Kimlik bilgilerinin nasıl depolandığı hakkında daha fazla bilgi almak için bkz. [Şifrelenmiş kimlik bilgilerini bulutta depolama](service-gateway-data-sources.md#storing-encrypted-credentials-in-the-cloud).

![Veri kaynağı ayarlarını doldurma](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings3-oracle.png)

Zamanlanmış yenileme ile kullanabilir olan veri kaynağı türlerinin listesi için [Kullanılabilir veri kaynağı türlerinin listesine](service-gateway-data-sources.md#list-of-available-data-source-types) bakın.

Tüm bilgileri doldurduktan sonra **Ekle**'yi seçin. Artık bu veri kaynağını şirket içi verilerinizle zamanlanmış yenileme için kullanabilirsiniz. İşlem başarılı olursa *Bağlantı Başarılı* iletisini göreceksiniz.

![Bağlantı durumunu görüntüleme](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings4.png)

### <a name="advanced-settings"></a>Gelişmiş ayarlar

İsteğe bağlı olarak, veri kaynağınızın gizlilik düzeyini yapılandırabilirsiniz. Bu işlem, verilerin nasıl birleştirilebileceğini denetler. Bu işlem yalnızca zamanlanmış yenileme için kullanılır. Veri kaynağınıza ilişkin gizlilik düzeyleri hakkında daha fazla bilgi edinmek için bkz. [Gizlilik düzeyleri (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Gizlilik düzeyini ayarlama](media/service-gateway-enterprise-manage-scheduled-refresh/datasourcesettings9.png)

## <a name="using-the-data-source-for-scheduled-refresh"></a>Veri kaynağını zamanlanmış yenileme için kullanma

Oluşturduğunuz veri kaynağı, DirectQuery bağlantıları veya zamanlanmış yenileme ile kullanılabilir.

> [!NOTE]
> Şirket içi veri ağ geçidinde bulunan veri kaynağındaki ve Power BI Desktop’taki sunucu ve veritabanı adı eşleşmelidir.

Ağ geçidindeki veri kaynağı ve veri kümeniz arasındaki bağlantı, sunucu ve veritabanı adınızı temel alır. Bunlar eşleşmelidir. Örneğin, Power BI Desktop'ta sunucu adı için bir IP Adresi sağlarsanız ağ geçidi yapılandırmasındaki veri kaynağında da bu IP Adresini kullanmanız gerekir. Power BI Desktop'ta *SUNUCU\ÖRNEK* yapılandırmasını kullanırsanız ağ geçidi için yapılandırılan veri kaynağında da aynısını kullanmanız gerekir.

Ağ geçidinde yapılandırılan veri kaynağının **Kullanıcılar** sekmesinde yer alıyorsanız ve sunucu ile veritabanı adı eşleşiyorsa ağ geçidini zamanlanmış yenileme ile kullanılabilen bir seçenek olarak görürsünüz.

![Kullanıcıları görüntüleme](media/service-gateway-enterprise-manage-scheduled-refresh/powerbi-gateway-enterprise-schedule-refresh.png)

> [!WARNING]
> Veri kümeniz birden çok veri kaynağı içeriyorsa her bir veri kaynağı, ağ geçidine eklenmelidir. Ağ geçidine bir veya daha fazla veri kaynağı eklenmezse ağ geçidini zamanlanmış yenileme için kullanılabilir olarak göremezsiniz.

## <a name="limitations"></a>Sınırlamalar

OAuth, şirket içi veri ağ geçidi için desteklenen bir kimlik doğrulama düzeni değildir. OAuth kimlik doğrulamasını gerekli kılan veri kaynakları ekleyemezsiniz. Veri kümeniz OAuth kimlik doğrulamasını gerekli kılan bir veri kaynağı içeriyorsa ağ geçidini zamanlanmış yenileme için kullanamazsınız.

## <a name="next-steps"></a>Sonraki adımlar

* [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](/data-integration/gateway/service-gateway-tshoot)
* [Ağ geçidiyle ilgili sorunları giderme - Power BI](service-gateway-onprem-tshoot.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
