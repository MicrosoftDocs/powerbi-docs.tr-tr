---
title: Power BI Premium’da sorgu önbelleğe alma
description: Power BI Premium’da sorgu önbelleğe alma
author: maggiesMSFT
manager: kfile
ms.reviewer: bhmerc
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/16/2019
ms.author: maggies
LocalizationGroup: ''
ms.openlocfilehash: e45773784fbe97f8521ad071c03e86dcbddddbeb
ms.sourcegitcommit: 4689766f08f5285deac50bec595d57c3a398fff5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68329121"
---
# <a name="query-caching-in-power-bi-premium"></a>Power BI Premium’da sorgu önbelleğe alma

Power BI Premium ile kuruluşlar bir veri kümesiyle ilişkili raporları hızlandırmak için *sorgu önbelleğe alma* özelliğinden yararlanabilir. Sorgu önbelleğe alma, sorgu sonuçlarını korumak için Premium kapasiteden kendi yerel önbelleğe alma hizmetini kullanmasını ister ve temel alınan veri kaynağının o sonuçları işlemesini önler.

> [!IMPORTANT]
> Sorgu önbelleğe alma, yalnızca Power BI Premium'da kullanılabilir. Azure Analysis Services veya SQL Server Analysis Services kullanan LiveConnect veri kümeleri için geçerli değildir.

Önbelleğe alınmış sorgu sonuçları kullanıcıya ve veri kümesi içeriğine özgüdür ve güvenlik kurallarını her zaman dikkate alır. Hizmet şu anda yalnızca açtığınız ilk sayfa için sorgu önbelleğe alma yapmaktadır. Başka bir deyişle, raporla etkileşim kurduğunuzda sorgular önbelleğe alınmaz. Sorgu önbelleği [kişisel yer işaretlerini](consumer/end-user-bookmarks.md#personal-bookmarks) ve [kalıcı filtreleri](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) gözetir. Bu nedenle, kişiselleştirilmiş rapor tarafından oluşturulan sorgular önbelleğe alınır. Aynı sorgularla desteklenen [pano kutucukları](service-dashboard-tiles.md) da sorgunun önbelleğe alınmasından yararlanır. Performans özellikle, bir veri kümesine sık erişildiğinde ve sık sık yenilenmesi gerekmediğinde yarar sağlar. Sorgu önbelleğe alma, genel sorgu sayısını azaltarak Premium kapasitenizin yükünü de azaltabilir.

Power BI hizmetindeki veri kümesi için sorgu önbelleğe alma davranışını **Ayarlar** sayfasında denetlersiniz. İki olası ayar şunlardır:

- **Kapalı**: Bu veri kümesi için sorgu önbelleğe alma kullanmayın.

- **Açık**: Bu veri kümesi için sorgu önbelleğe alma kullanın.

![Sorgu önbelleğe alma iletişim kutusu](media/power-bi-query-caching/power-bi-query-caching.png)

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

- Önbelleğe alma ayarlarını **Açık**’tan **Kapalı**’ya getirdiğinizde, veri kümesinin önceden kaydedilmiş tüm sorgu sonuçları kapasite önbelleğinden kaldırılır. Önbelleğe almayı açıkça veya bir yöneticinin **Kapalı** olarak ayarladığı kapasite varsayılanı ayarına geri alarak kapatabilirsiniz. Kapatılması, herhangi bir rapor bu veri kümesine karşı sorgular çalıştırdığında küçük bir gecikmeye neden olabilir. Gecikmeye, isteğe bağlı çalışan ve kaydedilmiş sonuçları kullanmayan o rapor sorguları neden olur. Ayrıca, zorunlu veri kümesinin sorgulara hizmet edebilmesi için belleğe yüklenmesi gerekebilir.
- Sorgu önbelleği yenilendiğinde, en güncel sonuçları almak için Power BI’ın temel alınan veri modellerinde sorgu çalıştırması gerekir. Çok sayıda veri kümesinde sorgu önbelleği etkinse ve Premium kapasite çok yüklüyse, önbellek yenilemesi esnasında performans düşüşü yaşanabilir. Performans düşüşü, yürütülen sorguların sayısındaki artıştan kaynaklanır.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium nedir?](service-premium-what-is.md)

