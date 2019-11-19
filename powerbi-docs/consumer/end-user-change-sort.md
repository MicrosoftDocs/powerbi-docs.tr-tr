---
title: Raporlarda grafiklerin sıralanma biçimini değiştirme
description: Power BI raporlarında grafiklerin sıralanma biçimini değiştirme
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/28/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: e325d13dd8001e8da41dc5602bf3f7dbba2f371f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73852381"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI raporlarında grafiklerin sıralanma biçimini değiştirme

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Power BI hizmetinde farklı veri alanlarına göre sıralayarak bir görselin görüntülenme şeklini değiştirebilirsiniz. Görseli sıralama ölçütünü değiştirerek iletmek istediğiniz bilgileri vurgulayabilir ve görselin bu eğilimi yansıtmasını (veya vurgulamasını) sağlayabilirsiniz.

İster sayısal veriler (satış rakamları gibi) ister metin verileri (eyalet adları gibi) kullanıyor olun, görselleştirmelerinizi istediğiniz şekilde sıralayabilir ve istediğiniz gibi görünmelerini sağlayabilirsiniz. Power BI, sıralama için kullanabileceğiniz birçok seçenek ve hızlı menüler sunmaktadır. Herhangi bir görselde **Diğer eylemler** (...) öğesini seçin ve ardından sıralamayı istediğiniz alanı seçin.

![X eksenine göre alfa sıralaması olan çubuk grafik](media/end-user-change-sort/power-bi-more-actions.png)

Bir panodaki görseller sıralanamaz ancak Power BI raporunda çoğu görselleştirmeyi kategori adlarına göre alfabetik şekilde veya kategorilerin sayısal değerlerine göre sıralayabilirsiniz. Örneğin, bu grafik, **mağaza adı** kategorisine göre alfabetik olarak sıralanmıştır.

![X eksenine göre alfa sıralaması olan çubuk grafik](media/end-user-change-sort/pbi-chartsortcategory.png)

Sıralama ölçütünü kategoriden (store name) değere (sales per square feet) dönüştürebilirsiniz.

1. **Diğer eylemler** (...) ve **Sıralama ölçütü > Fit Kare Başına Satış**’ı seçin.
2. Gerekirse, **Diğer eylemler**’i (...) tekrar seçip **Azalan düzende sırala**’yı seçin. Sıralamak için kullanılan alan kalın yazı tipindedir ve sarı bir çubuğa sahiptir.

   ![sıralamanın ve ardından artan, azalan ayarının seçilmesini gösteren video](media/end-user-change-sort/sort.gif)

> [!NOTE]
> Her görsel sıralanamaz. Örneğin, şu görselleri sıralamak mümkün değildir: ağaç haritası, harita, kartogram, dağılım, ölçer, kart, şelale.

## <a name="saving-changes-you-make-to-sort-order"></a>Sıralama düzeninde yaptığınız değişiklikleri kaydetme
Power BI raporları, yaptığınız filtre, dilimleyici, sıralama ve diğer veri görünümü değişikliklerini korur. Bu nedenle, bir rapordan çıkış yapıp daha sonra geri dönerseniz değişiklikleriniz kaydedilir.  Değişikliklerinizi rapor tasarımcısının ayarlarına geri döndürmek isterseniz üst menü çubuğundan **Varsayılana sıfırla**’yı seçin. 

![kalıcı sıralama](media/end-user-change-sort/power-bi-reset.png)

Ancak, **Varsayılana sıfırla** düğmesi griyse, bu durum rapor tasarımcısının değişikliklerinizi kaydetme (kalıcı hale getirme) özelliğini devre dışı bıraktığı anlamına gelir.

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>Diğer ölçütleri kullanarak sıralama
Bazı durumlarda görselinizi farklı bir alana (görsele dahil olmayan) veya ölçüte göre sıralamak isteyebilirsiniz.  Örneğin, aya göre (alfabetik sırada değil) veya tek basamak yerine sayının tamamına göre (ör. 0, 1, 20, 9 değil 0, 1, 9, 20 şeklinde) sıralama yapmak isteyebilirsiniz.  Rapor tasarımcısı bu sıralama türünü etkinleştirmek için veri kümesini güncelleştirebilir. Tasarımcının iletişim bilgileri başlık çubuğundan rapor adı seçilerek bulunabilir.

![İletişim bilgilerini gösteren açılır menü](media/end-user-change-sort/power-bi-contact.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki görselleştirmeler](end-user-visualizations.md) hakkında daha fazla bilgi.

[Power BI - Temel Kavramlar](end-user-basic-concepts.md)
