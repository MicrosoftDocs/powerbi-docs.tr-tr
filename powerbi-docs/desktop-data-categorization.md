---
title: "Power BI Desktop'ta verileri kategorilere ayırma"
description: "Power BI Desktop'ta verileri kategorilere ayırma"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 07/20/2017
ms.author: davidi
ms.openlocfilehash: a07e6020a18ab525c97069d5c635304e9b32d0d1
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="data-categorization-in-power-bi-desktop"></a>Power BI Desktop'ta verileri kategorilere ayırma
**Power BI Desktop**'ta bir sütun için Veri Kategorisi seçerek Power BI Desktop'ın bu değerleri görselleştirme içinde nasıl işleyeceğini belirleyebilirsiniz.

Power BI Desktop verileri içeri aktardığında verilerin kendisinin yanı sıra tablo ve sütun adları, birincil anahtar olup olmadığı gibi bilgileri de alır.  Power BI Desktop bu bilgileri kullanarak görselleştirme oluştururken iyi bir varsayılan deneyim sağlamak amacıyla bazı varsayımlarda bulunur. 

Örneğin: Power BI Desktop bir sütunda sayısal değer olduğunu algıladığında bu değerleri bir şekilde toplamak isteyebileceğinizi varsayarak Değerler alanına yerleştirir. Ya da tarih saat değerlerine sahip olan bir sütunu çizgi grafikte zaman hiyerarşisi ekseni olarak kullanacağınızı düşünür.

Ancak coğrafya gibi daha zorlayıcı alanlar da vardır. Aşağıdaki tablonun bulunduğu bir Excel çalışma sayfasını düşünün:

![](media/desktop-data-categorization/datacategorizationtable.png)

Power BI Desktop, GeoCode sütunundaki kodları Ülkelerin mi yoksa ABD Eyaletlerinin mi kısaltması olarak kabul etmelidir?  Böyle bir kod her ikisi de olabileceğinden kesin ayrım yapmak mümkün değildir.  Örneğin AL, Alabama veya Arnavutluk; AR, Arkansas veya Arjantin; CA ise Kaliforniya veya Kanada anlamına gelebilir. Bu fark özellikle GeoCode alanını bir haritaya yerleştirdiğimizde ortaya çıkar.  Power BI Desktop, ülkelerin vurgulanmış olduğu bir dünya haritası mı yoksa eyaletlerin vurgulanmış olduğu ABD haritası mı göstermelidir?  Bunun gibi veriler için Veri Kategorisi belirtebilirsiniz. Verileri kategorilere ayırma, Power BI Desktop'ın en iyi görselleştirmeleri sunmak için kullanabileceği verileri detaylandırır.  

**Bir Veri Kategorisi belirtmek için**

1. Rapor Görünümü veya Veri Görünümünde, **Alanlar** listesinde farklı bir kategoride sıralanmasını istediğiniz alanı seçin.
2. Şeritteki **Veri Araçları Modelleme** sekmesinde **Veri Kategorisi:** açılan listesine tıklayın.  Burada sütununuz için seçebileceğiniz veri kategorileri gösterilir.  Sütununuzun geçerli veri türüyle kullanılamayacak olan bazı seçenekler devre dışı bırakılmış olabilir.  Örneğin, sütun ikili değer türündeyse Power BI Desktop coğrafi veri kategorilerini seçmenize izin vermez. 

![](media/desktop-data-categorization/datacategorization.gif)

İşte bu kadar!  Normalde bir görsel oluşturan davranışlar artık otomatik olarak çalışır.  

Ayrıca, [Power BI mobil uygulamaları için coğrafi filtreleme](desktop-mobile-geofiltering.md) hakkında da bilgi edinmek isteyebilirsiniz.
