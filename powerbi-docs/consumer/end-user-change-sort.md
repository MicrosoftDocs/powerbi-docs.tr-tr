---
title: Raporlarda grafiklerin sıralanma biçimini değiştirme
description: Power BI raporlarında grafiklerin sıralanma biçimini değiştirme
author: mihart
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 08/25/2020
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 6147bc0ee725eb7adc7e1edb637a22bb7dc66558
ms.sourcegitcommit: 1aaa742c239a3119cdaad698be5a7553b68801fa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2020
ms.locfileid: "89040356"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI raporlarında grafiklerin sıralanma biçimini değiştirme

[!INCLUDE[consumer-appliesto-ynnn](../includes/consumer-appliesto-ynnn.md)]


> [!IMPORTANT]
> **Bu makale rapor veya veri kümesi üzerinde düzenleme izinleri olmayan ve Power BI’ın yalnızca çevrimiçi sürümünde (Power BI hizmeti) çalışan Power BI kullanıcılarına yöneliktir. Rapor *tasarımcısı*, *yöneticisi* veya *sahibiyseniz*, bu makale ihtiyacınız olan tüm bilgileri içermiyor olabilir. Bunun yerine lütfen [Power BI Desktop'ta sütuna göre sıralama](../create-reports/desktop-sort-by-column.md)** konusunu okuyun.

Power BI hizmetinde farklı veri alanlarına göre sıralayarak bir görselin görüntülenme şeklini değiştirebilirsiniz. Görseli sıralama ölçütünü değiştirerek iletmek istediğiniz bilgileri vurgulayabilirsiniz. İster sayısal veriler (satış rakamları gibi) ister metin verileri (eyalet adları gibi) kullanıyor olun, görsellerinizi istediğiniz gibi sıralayabilirsiniz. Power BI, sıralama için kullanabileceğiniz birçok seçenek ve hızlı menüler sunmaktadır. 

Panodaki görseller sıralanamaz. Ancak bir Power BI raporundaki çoğu görseli tek seferde bazen bir, bazen iki alana göre sınıflandırabilirsiniz. Belirli görsel türlerinde sıralama kullanılamaz: ağaç haritaları, ölçüler, haritalar vb. 

## <a name="get-started"></a>Kullanmaya başlayın

Başlamak için kendi oluşturduğunuz veya sizinle paylaşılmış olan herhangi bir raporu açın. Bir görsel (sıralayabileceğiniz) seçtikten sonra **Diğer eylemler** (...) öğesini seçin.  Üç sıralama seçeneği vardır: **Azalan düzende sırala**, **Artan düzende sırala** ve **Sıralama ölçütü**. 
    

![Y eksenine göre alfa sıralaması olan çubuk grafik](media/end-user-change-sort/power-bi-actions.png)

### <a name="sort-alphabetically-or-numerically"></a>Alfabetik veya sayısal olarak sıralama

Görseller, görseldeki kategorilerin adlarına göre alfabetik şekilde veya kategorilerin sayısal değerlerine göre sıralanabilir. Örneğin, bu grafik X ekseni mağaza **Adı** kategorisine göre alfabetik olarak sıralanmıştır.

![X eksenine göre alfa sıralaması olan çubuk grafik](media/end-user-change-sort/powerbi-sort-category.png)

Sıralama ölçütünü kategoriden (store name) değere (sales per square feet) dönüştürmek için **Diğer eylemler** (...) ve **Sıralama ölçütü**'nü seçin. Görselde kullanılan bir sayısal değeri seçin.  Bu örnekte biz **Sales Per Sq Ft** değerini seçtik.

![Sıralama ölçütü'nün ve ardından değerin seçilmesini gösteren ekran görüntüsü](media/end-user-change-sort/power-bi-sort-value.png)

Gerekirse artan ve azalan sıralama düzenleri arasında geçiş yapın.  **Diğer eylemler**’i (...) tekrar seçip **Azalan düzende sırala**’yı veya **Artan düzende sırala**'yı seçin. Sıralamak için kullanılan alan kalın yazı tipindedir ve sarı bir çubuğa sahiptir.

   ![sıralamanın ve ardından artan, azalan ayarının seçilmesini gösteren video](media/end-user-change-sort/sort.gif)

> [!NOTE]
> Her görsel sıralanamaz. Örneğin, şu görselleri sıralamak mümkün değildir: ağaç haritası, harita, kartogram, dağılım, ölçer, kart, şelale.

## <a name="sorting-by-multiple-columns"></a>Birden fazla sütuna göre sıralama
Bu tablodaki veriler **Müşterilerin sayısına** göre sıralanmıştır.  Bunu, *Sayı* sözcüğünün altındaki küçük oktan anlıyoruz. Ok aşağıyı işaret ediyor, bu da sütunun *azalan* düzende sıralandığı anlamına geliyor.

![sıralama için kullanılan ilk sütunu gösteren ekran görüntüsü](media/end-user-change-sort/power-bi-sort-column.png)


Sıralama düzenine daha fazla sütun eklemek için Shift tuşunu basılı tutarak, sonraki sıralama düzenine eklemek istediğiniz sütun üst bilgisine tıklayın. Örneğin **Müşteri sayısına** tıklayıp daha sonra Shift tuşunu basılı tutarak **Toplam gelir**’e tıklarsanız tablo ilk önce müşterilere, daha sonra gelire göre sıralanır. Kırmızı ana hat, sıralama düzeninin değiştiği alanları gösterir.

![sıralama için kullanılan ikinci sütunu gösteren ekran görüntüsü](media/end-user-change-sort/power-bi-sort-second.png)

Aynı sütunda Shift tuşunu basılı tutarak ikinci kez tıklarsanız bu, ilgili sütunun sıralama yönünü (artan, azalan) değiştirir. Dahası, Shift tuşunu basılı tutup daha önce sıralama düzenine eklediğiniz bir sütuna tıklarsanız bu, sütunu sıralama düzenine geri taşır.


## <a name="saving-changes-you-make-to-sort-order"></a>Sıralama düzeninde yaptığınız değişiklikleri kaydetme
[Okuma görünümünde](end-user-reading-view.md) çalışıyor olsanız bile, Power BI raporları yaptığınız filtre, dilimleyici, sıralama ve diğer veri görünümü değişikliklerini korur. Bu nedenle, bir rapordan çıkıp daha sonra geri dönerseniz sıralama değişiklikleriniz kaydedilir.  Değişikliklerinizi rapor *tasarımcısının* ayarlarına geri döndürmek isterseniz üst menü çubuğundan **Varsayılana sıfırla**’yı seçin. 

![kalıcı sıralama](media/end-user-change-sort/power-bi-reset.png)

Ancak, **Varsayılana sıfırla** düğmesi griyse, bu durum rapor *tasarımcısının* değişikliklerinizi kaydetme (kalıcı hale getirme) özelliğini devre dışı bıraktığı anlamına gelir.

<a name="other"></a>
## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

### <a name="sorting-using-other-criteria"></a>Diğer ölçütleri kullanarak sıralama
Bazı durumlarda görselinizi farklı bir alana (görsele dahil olmayan) veya ölçüte göre sıralamak isteyebilirsiniz.  Örneğin, sıralı bir şekilde aya göre (alfabetik sırada değil) veya tek basamak yerine sayının tamamına göre (ör. 0, 1, 20, 9 değil 0, 1, 9, 20 şeklinde) sıralama yapmak isteyebilirsiniz.  

Yalnızca raporu tasarlayan kişi sizin için bu değişiklikleri yapabilir. *Tasarımcının* iletişim bilgileri başlık çubuğundan rapor adı seçilerek bulunabilir.

![İletişim bilgilerini gösteren açılır menü](media/end-user-change-sort/power-bi-header.png)

*Tasarımcıysanız* ve içerik üzerinde düzenleme izinleriniz varsa, veri kümesini güncelleştirmeyi ve bu tür bir sıralamayı etkinleştirmeyi öğrenmek için [Power BI Desktop’ta sütuna göre sıralama](../create-reports/desktop-sort-by-column.md) konusunu okuyun.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki görselleştirmeler](end-user-visualizations.md) hakkında daha fazla bilgi.

[Power BI - Temel Kavramlar](end-user-basic-concepts.md)
