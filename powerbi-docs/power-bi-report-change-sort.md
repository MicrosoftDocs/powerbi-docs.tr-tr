---
title: Power BI raporlarında grafiklerin sıralanma biçimini değiştirme
description: Power BI raporlarında grafiklerin sıralanma biçimini değiştirme
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3c32fc3cc9dc2b16384016ca624d4dd3a773aacb
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34561805"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI raporlarında grafiklerin sıralanma biçimini değiştirme
Power BI raporunda çoğu görselleştirmeyi kategori adlarına göre alfabetik şekilde veya kategorilerin sayısal değerlerine göre sıralayabilirsiniz. Örneğin, bu grafik mağaza adına göre sıralanmıştır.

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

Sıralama ölçütünü kategoriden (store name) değere (sales per square feet) dönüştürebilirsiniz.

1. Üç nokta (...) simgesini seçin ve ardından **Sıralama ölçütü: Sales Per Sq Ft** seçeneğini belirleyin.
2. Gerekirse sıralama simgesini ![](media/power-bi-report-change-sort/sorticon.png) seçerek **Azalan** düzene geçin.

   ![](media/power-bi-report-change-sort/sortby.gif)

   **NOT**: Her görsel sıralanamaz.  Örneğin, şu görselleri sıralamak mümkün değildir: Ağaç Haritası, Harita, Doldurulmuş Harita, Dağılım, Ölçek, Kart, Çok Satırlı Kart, Şelale.

## <a name="saving-changes-you-make-to-sort-order"></a>Sıralama düzeninde yaptığınız değişiklikleri kaydetme
Power BI raporları, yaptığınız filtre, dilimleyici, sıralama ve diğer veri görünümü değişikliklerini korur. Bu nedenle, bir rapordan çıkış yapıp daha sonra geri dönerseniz değişiklikleriniz kaydedilir.  Değişikliklerinizi rapor yazarı ayarlarına geri almak isterseniz üstteki menü çubuğundan **Varsayılana sıfırla**’yı seçin. 

![kalıcı sıralama](media/power-bi-report-change-sort/power-bi-reset-to-default.png)

Ancak, **Varsayılana sıfırla** düğmesi griyse, bu durum rapor yazarının değişikliklerinizi kaydetme (kalıcı hale getirme) özelliğini devre dışı bıraktığı anlamına gelir.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Diğer ölçütleri kullanarak sıralama
Bazı durumlarda görselinizi farklı bir alana veya ölçüte göre sıralamak isteyebilirsiniz.  Örneğin, aya göre (alfabetik sırada değil) veya tek basamak yerine sayının tamamına göre (ör. 0, 1, 20, 9 değil 0, 1, 9, 20 şeklinde) sıralama yapmak isteyebilirsiniz.  

Bazı durumlarda görseli istediğiniz şekilde (örneğin, aya göre) sıralayabilirsiniz.  Aksi halde, raporun temel aldığı veri kümesinde değişiklik yapmanız gerekebilir. Kullanabileceğiniz çeşitli çözümler aşağıda verilmiştir:

* Power BI Desktop'ta, [Veri Araçları Modelleme sekmesini kullanarak başka bir sütuna göre sıralama yapın](desktop-sort-by-column.md).
* Veri kümesinin sahibi sizseniz Excel'de ay adını ve sayıyı birleştiren yeni bir sütun oluşturun. Ardından veri kümesini yenilediğinizde veya yeniden içeri aktardığınızda yeni sütunu Alanlar listesinde görebilirsiniz.
* Excel'deki sayı içeren sütunlarınızın "metin" değil, "tam sayı" veya "ondalık" olarak etiketlendiğinden emin olun.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md) hakkında daha fazla bilgi.

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
