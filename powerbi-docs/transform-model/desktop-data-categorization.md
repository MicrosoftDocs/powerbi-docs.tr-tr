---
title: Power BI Desktop'ta verileri kategorilere ayırma
description: Power BI Desktop'ta verileri kategorilere ayırma
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-transform-model
ms.topic: how-to
ms.date: 01/15/2020
LocalizationGroup: Model your data
ms.openlocfilehash: d99eb0355d414a9e1627da0b5629eaf45cbaf18d
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96415807"
---
# <a name="specify-data-categories-in-power-bi-desktop"></a>Power BI Desktop’ta veri kategorilerini belirtme
Power BI Desktop'ta bir sütun için *veri kategorisi* seçerek Power BI Desktop'ın bu değerleri görselleştirme içinde nasıl işleyeceğini belirleyebilirsiniz.

Power BI Desktop verileri içeri aktarırken, verilerin kendileri dışında başka bilgiler de alır (örneğin tablo ve sütun adları ve verilerin birincil anahtar olup olmadığı). Power BI Desktop bu bilgileri kullanarak görselleştirme oluştururken iyi bir varsayılan deneyim sağlamak amacıyla bazı varsayımlarda bulunur.
Örneğin bir sütunda sayısal değer bulunduğunda büyük olasılıkla bunu herhangi bir yolla toplamak istersiniz, bu nedenle Power BI Desktop bu değeri **Görselleştirmeler** bölmesinin **Değerler** alanına yerleştirir. Öte yandan çizgi grafikte tarih-saat değerleri içeren bir sütun için, Power BI Desktop bunu büyük olasılıkla bir zaman hiyerarşisi ekseni olarak kullanacağınızı varsayar.

Ancak coğrafya gibi daha zorlayıcı alanlar da vardır. Aşağıdaki tablonun bulunduğu bir Excel çalışma sayfasını düşünün:

![Power BI Desktop’a içeri aktarılacak tablosal verileri gösteren Excel’in ekran görüntüsü.](media/desktop-data-categorization/datacategorizationtable.png)

Power BI Desktop, **GeoCode** sütunundaki kodları Ülkelerin mi yoksa ABD Eyaletlerinin mi kısaltması olarak kabul etmelidir?  Böyle bir kod her ikisi de olabileceğinden kesin ayrım yapmak mümkün değildir. Örneğin AL, Alabama veya Arnavutluk; AR, Arkansas veya Arjantin; CA ise Kaliforniya veya Kanada anlamına gelebilir. Bu fark özellikle GeoCode alanını bir haritaya yerleştirdiğimizde ortaya çıkar. 

Power BI Desktop ülkelerin vurgulandığı bir dünya resmi mi göstermelidir? Yoksa eyaletlerin vurgulandığı bir Birleşik Devletler resmi mi göstermelidir?  Bunun gibi veriler için veri kategorisi belirtebilirsiniz. Verileri kategorilere ayırma, Power BI Desktop'ın en iyi görselleştirmeleri sunmak için kullanabileceği verileri detaylandırır.  

**Veri kategorisi belirtmek için**

1. **Rapor** Görünümündeki veya **Veri** Görünümündeki **Alanlar** listesinde farklı bir kategoride sıralanmasını istediğiniz alanı seçin.
2. Şeritteki **Modelleme** sekmesinin **Özellikler** alanında, **Veri Kategorisi**'nin yanındaki aşağı açılan oku seçin.  Bu liste sütununuz için seçebileceğiniz veri kategorilerini gösterir. Sütununuzun geçerli veri türüyle kullanılamayacak olan bazı seçenekler devre dışı bırakılmış olabilir.  Örneğin, sütun tarih veya saat değer türündeyse Power BI Desktop coğrafi veri kategorilerini seçmenize izin vermez. 
3. İstediğiniz kategoriyi seçin.

   ![Veri Kategorisi filtresini gösteren Power BI Desktop’ın ekran görüntüsü.](media/desktop-data-categorization/desktop-data-categorization.png)

Ayrıca, [Power BI mobil uygulamaları için coğrafi filtreleme](desktop-mobile-geofiltering.md) hakkında da bilgi edinmek isteyebilirsiniz.