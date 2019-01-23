---
title: Raporlarda grafiklerin sıralanma biçimini değiştirme
description: Power BI raporlarında grafiklerin sıralanma biçimini değiştirme
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: Conceptual
ms.date: 01/17/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: e648257ecd657b07d02fbff69a3424159b636059
ms.sourcegitcommit: ccbe76a0a43c5c5e87354a33e617bf3cb291608e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2019
ms.locfileid: "54394678"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI raporlarında grafiklerin sıralanma biçimini değiştirme
Power BI raporunda çoğu görselleştirmeyi kategori adlarına göre alfabetik şekilde veya kategorilerin sayısal değerlerine göre sıralayabilirsiniz. Örneğin, bu grafik, **mağaza adı** kategorisine göre sıralanmıştır.

![X eksenine göre alfa sıralaması olan çubuk grafik](media/end-user-change-sort/pbi_chartsortcategory.png)

Sıralama ölçütünü kategoriden (store name) değere (sales per square feet) dönüştürebilirsiniz.

1. Üç nokta (...) simgesini seçin ve ardından **Sıralama ölçütü: Sales Per Sq Ft** seçeneğini belirleyin.
2. Gerekirse, üç nokta simgesini yeniden seçin ve **Azalan düzene göre sırala** seçeneğini belirleyin.

   ![sıralamanın ve ardından artan, azalan ayarının seçilmesini gösteren video](media/end-user-change-sort/sort.gif)

   **NOT**: Her görsel sıralanamaz.  Örneğin, aşağıdaki görseller sıralanamaz: Ağaç Haritası, Harita, Kartogram, Dağılım, Gösterge, Kart, Çok Satırlı Kart, Şelale.

## <a name="saving-changes-you-make-to-sort-order"></a>Sıralama düzeninde yaptığınız değişiklikleri kaydetme
Power BI raporları, yaptığınız filtre, dilimleyici, sıralama ve diğer veri görünümü değişikliklerini korur. Bu nedenle, bir rapordan çıkış yapıp daha sonra geri dönerseniz değişiklikleriniz kaydedilir.  Değişikliklerinizi rapor tasarımcısının ayarlarına geri almak isterseniz üstteki menü çubuğundan **Varsayılana sıfırla**’yı seçin. 

![kalıcı sıralama](media/end-user-change-sort/power-bi-reset-to-default.png)

Ancak, **Varsayılana sıfırla** düğmesi griyse, bu durum rapor tasarımcısının değişikliklerinizi kaydetme (kalıcı hale getirme) özelliğini devre dışı bıraktığı anlamına gelir.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Diğer ölçütleri kullanarak sıralama
Bazı durumlarda görselinizi farklı bir alana veya ölçüte göre sıralamak isteyebilirsiniz.  Örneğin, aya göre (alfabetik sırada değil) veya tek basamak yerine sayının tamamına göre (ör. 0, 1, 20, 9 değil 0, 1, 9, 20 şeklinde) sıralama yapmak isteyebilirsiniz.  

Bazı durumlarda görseli istediğiniz şekilde (örneğin, aya göre) sıralayabilirsiniz.  Aksi halde, raporun temel aldığı veri kümesinde değişiklik yapmanız gerekebilir. Rapor tasarımcısından veri kümesini güncelleştirmesini isteyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki görselleştirmeler](end-user-visualizations.md) hakkında daha fazla bilgi.

[Power BI - Temel Kavramlar](end-user-basic-concepts.md)