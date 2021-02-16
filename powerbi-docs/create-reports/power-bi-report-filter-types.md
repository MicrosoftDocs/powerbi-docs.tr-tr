---
title: Power BI raporlarındaki filtre türleri
description: Sayfa filtresi, görselleştirme filtresi ve rapor filtresi gibi Power BI'daki raporlara uygulanabilecek filtre türleri hakkında bilgi edinin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: conceptual
ms.date: 02/12/2021
LocalizationGroup: Reports
ms.openlocfilehash: c9092ae8e64b2dde94d66a658c37dca5f83721a6
ms.sourcegitcommit: 00e3eb2ec4f18d48a73cfd020bb42d08e859ad06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2021
ms.locfileid: "100531551"
---
# <a name="types-of-filters-in-power-bi-reports"></a>Power BI raporlarındaki filtre türleri

Filtreler birbiriyle aynı davranışları göstermez çünkü aynı şekilde oluşturulmamışlardır. Bunları nasıl oluşturacağınız, düzen modundaki filtre bölmesinde nasıl davrandığını etkiler. Bu makalede farklı filtre türlerini açıklayacağız: bunları farklı oluşturma yollarınız ve bunların yararlı olduğu farklı kullanımlar. [Raporlara filtre ekleme](power-bi-report-add-filter.md) konusunda bilgi edinin. 

![Filtre bölmesi](media/power-bi-report-filter-types/power-bi-filter-pane.png)

En yaygın iki filtre türüyle başlayalım: otomatik ve el ile.

## <a name="automatic-filters"></a>Otomatik filtreler 

Otomatik filtreler, siz görsel oluştururken filtre bölmesinin görsel düzeyine otomatik olarak eklenen filtrelerdir. Bu filtreler görselinizi oluşturan alanları temel alır. Raporda düzenleme izni olan kullanıcılar, bölmedeki bu filtreyi düzenleyebilir, temizleyebilir, gizleyebilir, kilitleyebilir, yeniden adlandırabilir veya sıralayabilir. Otomatik filtreleri silemezler çünkü görselde bu alanlara başvurulur.

## <a name="manual-filters"></a>El ile çalıştırılan filtreler 

El ile filtreler, bir raporu düzenlediğinizde Filtre bölmesinin herhangi bir bölümünde sürüklediğiniz ve sürüklediğiniz filtrelerdir. Raporda düzenleme izniniz varsa, bölmesinde bu filtreyi düzenleyebilir, silebilir, temizleyebilir, gizleyebilir, kilitleyebilir, yeniden adlandırabilir veya sıralayabilirsiniz.

[Bir rapora filtre ekleme](power-bi-report-add-filter.md)hakkında bilgi edinin.

## <a name="more-advanced-filters"></a>Daha gelişmiş filtreler

Bundan sonra açıklanan filtre türleri o kadar yaygın değildir ama bunlar raporunuzda görüntüleniyorsa bunları anlamanız yine de önemlidir. Ayrıca raporunuz için en doğru filtreyi oluşturmanıza yardımcı olabilirler.

## <a name="include-and-exclude-filters"></a>Dahil etme ve hariç tutma filtreleri

Görselde dahil etme veya hariç tutma işlevselliğini kullandığınızda filtre bölmesine dahil etme ve hariç tutma filtreleri otomatik olarak eklenir. Bir raporu düzenleyebiliyorsanız, bölmedeki bu filtreyi silebilir, kilitleyebilir, gizleyebilir veya sıralayabilirsiniz. Görsellerin dahil etme ve hariç tutma işlevselliğiyle ilişkili olduğundan ekleme veya dışlama filtresini düzenleyemez, temizleyemez veya yeniden adlandıramazsınız.

![Hariç tutma filtresi](media/power-bi-report-filter-types/power-bi-filters-exclude.png)

## <a name="drill-down-filters"></a>Detaya gitme filtreleri

Raporunuzda görsel için detaya gitme işlevselliğini kullandığınızda filtre bölmesine detaya gitme filtreleri otomatik olarak eklenir. Bir raporu düzenleyebiliyorsanız, bölmedeki filtreyi düzenleyebilir veya temizleyebilirsiniz. Görsellerin detaya gitme işlevselliğiyle ilişkili olduğundan, bu filtreyi silemez, gizleyemez, kilitleyebilir, yeniden adlandırabilir veya sıralayamazsınız. Ayrıntıya gitme filtresini kaldırmak için görselin detaya gitme düğmesini seçin.

![Detaya gitme filtresi](media/power-bi-report-filter-types/power-bi-filters-drill-down.png)

## <a name="cross-drill-filters"></a>Çapraz detaylandırma filtreleri

Çapraz detaya gitme filtreleri, rapor sayfasındaki çapraz filtre veya çapraz vurgulama özelliği aracılığıyla başka bir görsele geçirildiğinde, bölmeye otomatik olarak eklenir. Bir raporu düzenleyebilse bile, görsellerin detaya gitme işlevselliğiyle ilişkili olduğundan, bu filtreyi silemez, temizleyebilir, gizleyemez, yeniden adlandırabilir veya sıralayabilirsiniz. Ayrıca, başka bir görselde detaya gitmeyi sağladığından bu filtreyi düzenleyemezsiniz. Ayrıntıya gitme filtresini kaldırmak için, filtreyi geçiren görsele ilişkin detaya gitme düğmesini seçin.

## <a name="drill-through-filters"></a>Detaylandırma filtreleri

Detaylandırma filtreleri, detaylandırma özelliği aracılığıyla bir sayfadan diğerine geçirilir. Bunlar detaya gitme bölmesinde görünür. İki tür detaylandırma filtresi vardır. İlk tür detaya gitmeyi çağıran bir türüdür. Bir raporu düzenleyebiliyorsanız, bu tür bir filtreyi düzenleyebilir, silebilir, temizleyebilir, gizleyebilir veya Kilitle ' yi seçebilirsiniz. İkinci tür, kaynak sayfanın sayfa düzeyi filtrelerine bağlı olarak hedefe geçirilen detaya gitme filtresidir. Bu geçici detaylandırma filtresi türünü düzenleyebilir, silebilir veya temizleyebilirsiniz. Son kullanıcılar için bu filtreyi kilitleyemez veya gizleyemezsiniz.

[Detaylandırma filtreleri oluşturma](desktop-drillthrough.md)hakkında bilgi edinin.

## <a name="url-filters"></a>URL filtreleri

URL filtreleri, bir URL sorgu parametresi eklenerek bölmesine eklenir. Bir raporu düzenleyebiliyorsanız, bölmedeki filtreyi düzenleyebilir, silebilir veya temizleyebilirsiniz. URL parametresiyle ilişkili olduğundan, bu filtreyi gizleyemez, kilitleyebilir, yeniden adlandıramaz veya sıralayamazsınız. Filtreyi kaldırmak için URL'den URL parametresini kaldırırsınız. Parametre içeren bir URL örneği:

app.powerbi.com/groups/me/apps/*app-id*/reports/*report-id*/ReportSection?filter=Stores~2FStatus%20eq%20'Off'

![URL filtresi](media/power-bi-report-filter-types/power-bi-filter-url.png)

[URL filtrelerini ayarlama](../collaborate-share/service-url-filters.md)hakkında bilgi edinin.

## <a name="pass-through-filters"></a>Geçiş filtreleri

Geçiş filtreleri Soru-Cevap aracılığıyla oluşturulan görsel düzeyi filtrelerdir. Bir raporu düzenleyebiliyorsanız, bölmedeki bu filtreleri silebilir, gizleyebilir veya sıralayabilirsiniz. Ancak, bu filtreleri yeniden adlandıramaz, düzenleyemez, temizleyebilir veya kilitleyemezsiniz.

![Soru-Cevap özelliğiyle geçiş filtresi](media/power-bi-report-filter-types/power-bi-filters-qna.png)

## <a name="comparing-filter-types"></a>Filtre türlerini karşılaştırma

Bu tabloda yazarların farklı filtre türleriyle neler yapabilecekleri karşılaştırılır.

| Filtre türü | Düzenle | Temizle | Sil | Gizle | Kilitle | Sırala | Yeniden adlandır |
|----|----|----|----|----|----|----|----|
| El ile çalıştırılan filtreler | E | E | E | E | E | E | E |
| Otomatik filtreler | E | E | N | E | E | E | E |
| Ekleme/Dışlama filtreleri | N | N | E | E | E | E | N |
| Detaya gitme filtreleri | E | E | N | N | N | N | N |
| Çapraz Detaylandırma filtreleri | N | N | N | N | N | N | N |
| Detaylandırma filtreleri (detaya gitmeyi çağırır) | E | E | E | E | E | N | N |
| Detaylandırma filtreleri (geçici) | E | E | E | N | N | N | N |
| URL filtreleri - geçici | E | E | E | N | N | N | N |
| Geçiş filtreleri | N | N | E | E | N | E | N |


## <a name="next-steps"></a>Sonraki adımlar

[Raporlara filtre ekleme](power-bi-report-add-filter.md)

[Power BI Filtreler bölmesine ilişkin tura katılın](../consumer/end-user-report-filter.md)

[Raporlarda filtreleme ve vurgulama](power-bi-reports-filters-and-highlighting.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
