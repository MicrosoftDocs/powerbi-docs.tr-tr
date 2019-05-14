---
title: Power BI Premium’da sorgu önbelleğe alma
description: Power BI Premium’da sorgu önbelleğe alma
author: maggiesMSFT
manager: kfile
ms.reviewer: bhmerc
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/03/2019
ms.author: maggies
LocalizationGroup: ''
ms.openlocfilehash: fbfd8c98743144e0c9604aca4174d6ef32916e77
ms.sourcegitcommit: de0b72915183a8a784d3227838bd704c1c209422
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58914288"
---
# <a name="query-caching-in-power-bi-premium"></a>Power BI Premium’da sorgu önbelleğe alma

Power BI Premium ile kuruluşlar bir veri kümesiyle ilişkili raporları hızlandırmak için *sorgu önbelleğe alma* özelliğinden yararlanabilir. Sorgu önbelleğe alma, sorgu sonuçlarını korumak için Premium kapasiteden kendi yerel önbelleğe alma hizmetini kullanmasını ister ve temel alınan veri kaynağının o sonuçları işlemesini önler.

> [!IMPORTANT]
> Sorgu önbelleğe alma, yalnızca Power BI Premium'da kullanılabilir. Azure Analysis Services veya SQL Server Analysis Services kullanan LiveConnect veri kümeleri için geçerli değildir.

Önbelleğe alınmış sorgu sonuçları kullanıcıya ve veri kümesi içeriğine özgüdür ve güvenlik kurallarını her zaman dikkate alır. Hizmet şu anda yalnızca açtığınız ilk sayfa için sorgu önbelleğe alma yapmaktadır. Başka bir deyişle, raporla etkileşim kurduğunuzda sorgular önbelleğe alınmaz. Önbellek kişisel yer işaretlerini ve kalıcı filtreleri yansıtır. Aynı sorgularla desteklenen [pano kutucukları](service-dashboard-tiles.md) da sorgunun önbelleğe alınmasından yararlanır. Performans özellikle, bir veri kümesine sık erişildiğinde ve sık sık yenilenmesi gerekmediğinde yarar sağlar. Sorgu önbelleğe alma, genel sorgu sayısını azaltarak Premium kapasitenizin yükünü de azaltabilir.

Power BI hizmetindeki veri kümesi için sorgu önbelleğe alma davranışını **Ayarlar** sayfasında denetlersiniz. Üç olası ayar şunlardır:

- **Kapasite Varsayılanı**: Veri kümesi, ayarı Premium kapasiteden devralır. Kapasite varsayılanı, Power BI Premium kapasite yöneticisi tarafından denetlenir.

- **Kapalı**: Bu veri kümesi için sorgu önbelleğe alma kullanmayın.

- **Açık**: Bu veri kümesi için sorgu önbelleğe alma kullanın.

![Sorgu önbelleğe alma iletişim kutusu](media/power-bi-query-caching/power-bi-query-caching.png)

> [!NOTE]
> Önbelleğe alma ayarlarını **Açık**’tan **Kapalı**’ya getirdiğinizde, veri kümesinin önceden kaydedilmiş tüm sorgu sonuçları kapasite önbelleğinden kaldırılır. Önbelleğe almayı açıkça veya bir yöneticinin **Kapalı** olarak ayarladığı kapasite varsayılanı ayarına geri alarak kapatabilirsiniz. Kapatılması, herhangi bir rapor bu veri kümesine karşı sorgular çalıştırdığında küçük bir gecikmeye neden olabilir. Gecikmeye, isteğe bağlı çalışan ve kaydedilmiş sonuçları kullanmayan o rapor sorguları neden olur. Ayrıca, zorunlu veri kümesinin sorgulara hizmet edebilmesi için belleğe yüklenmesi gerekebilir.

