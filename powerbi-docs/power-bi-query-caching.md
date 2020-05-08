---
title: Power BI Premium’da sorgu önbelleğe alma
description: Power BI Premium’da sorgu önbelleğe alma
author: KesemSharabi
ms.author: kesharab
ms.reviewer: bhmerc
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/04/2019
LocalizationGroup: ''
ms.openlocfilehash: bf9248b29c71f42de9fed53ee0148847a8f60d30
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "79488649"
---
# <a name="query-caching-in-power-bi-premiumembedded"></a>Power BI Premium/Embedded’de sorguları önbelleğe alma

Power BI Premium veya Power BI Embedded ile kuruluşlar bir veri kümesiyle ilişkili raporları hızlandırmak için *sorguları önbelleğe alma* özelliğinden yararlanabilir. Sorgu önbelleğe alma, sorgu sonuçlarını korumak için Premium/Embedded kapasiteden kendi yerel önbelleğe alma hizmetini kullanmasını ister ve temel alınan veri kaynağının o sonuçları işlemesini önler.

> [!IMPORTANT]
> Sorgu önbelleğe alma, yalnızca Power BI Premium veya Power BI Embedded'de kullanılabilir. Azure Analysis Services veya SQL Server Analysis Services kullanan LiveConnect veri kümeleri için geçerli değildir.

Önbelleğe alınmış sorgu sonuçları kullanıcıya ve veri kümesi içeriğine özgüdür ve güvenlik kurallarını her zaman dikkate alır. Hizmet şu anda yalnızca açtığınız ilk sayfa için sorgu önbelleğe alma yapmaktadır. Başka bir deyişle, raporla etkileşim kurduğunuzda sorgular önbelleğe alınmaz. Sorgu önbelleği [kişisel yer işaretlerini](consumer/end-user-bookmarks.md#personal-bookmarks) ve [kalıcı filtreleri](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) gözetir. Bu nedenle, kişiselleştirilmiş rapor tarafından oluşturulan sorgular önbelleğe alınır. Aynı sorgularla desteklenen [pano kutucukları](service-dashboard-tiles.md) da sorgunun önbelleğe alınmasından yararlanır. Performans özellikle, bir veri kümesine sık erişildiğinde ve sık sık yenilenmesi gerekmediğinde yarar sağlar. Sorgu önbelleğe alma, genel sorgu sayısını azaltarak Premium/Embedded kapasitenizin yükünü de azaltabilir.

Power BI hizmetindeki veri kümesi için sorgu önbelleğe alma davranışını **Ayarlar** sayfasında denetlersiniz. Üç olası ayar şunlardır:

- **Kapasite varsayılanı**: Sorgu önbelleğe alma kapalı
- **Kapalı**: Bu veri kümesi için sorgu önbelleğe alma kullanmayın.
- **Açık**: Bu veri kümesi için sorgu önbelleğe alma kullanın.

    ![Sorgu önbelleğe alma iletişim kutusu](media/power-bi-query-caching/power-bi-query-3-options.png)

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

- Önbelleğe alma ayarlarını **Açık**’tan **Kapalı**’ya getirdiğinizde, veri kümesinin önceden kaydedilmiş tüm sorgu sonuçları kapasite önbelleğinden kaldırılır. Önbelleğe almayı açıkça veya bir yöneticinin **Kapalı** olarak ayarladığı kapasite varsayılanı ayarına geri alarak kapatabilirsiniz. Kapatılması, herhangi bir rapor bu veri kümesine karşı sorgular çalıştırdığında küçük bir gecikmeye neden olabilir. Gecikmeye, isteğe bağlı çalışan ve kaydedilmiş sonuçları kullanmayan o rapor sorguları neden olur. Ayrıca, zorunlu veri kümesinin sorgulara hizmet edebilmesi için belleğe yüklenmesi gerekebilir.
- Sorgu önbelleği yenilendiğinde, en güncel sonuçları almak için Power BI’ın temel alınan veri modellerinde sorgu çalıştırması gerekir. Çok sayıda veri kümesinde sorgu önbelleği etkinse ve Premium/Embedded kapasite çok yüklüyse, önbellek yenilemesi esnasında performans düşüşü yaşanabilir. Performans düşüşü, yürütülen sorguların sayısındaki artıştan kaynaklanır.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI Premium nedir?](service-premium-what-is.md)
* [Azure'da Power BI Embedded nedir?](developer/embedded/azure-pbie-what-is-power-bi-embedded.md)
