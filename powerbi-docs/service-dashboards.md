---
title: Power BI tasarımcıları için panolara giriş
description: Panolar, Power BI hizmetinin temel özelliklerinden biridir. Bunlar çoğunlukla tuval olarak adlandırılan, görselleştirmeler aracılığıyla bir hikaye anlatan tek tek sayfalardır.
author: maggieMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/10/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 61d7bf9f9794545e963ca19c8f983d6d6cfefa54
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54286899"
---
# <a name="intro-to-dashboards-for-power-bi-designers"></a>Power BI tasarımcıları için panolara giriş

Power BI ***panosu***, görselleştirmeler kullanarak bir hikaye anlatan ve genellikle tuval olarak adlandırılan tek bir sayfadır. Tek sayfayla sınırlı olduğundan, iyi tasarlanmış bir panoda yalnızca hikayenin önemli parçaları yer alır. Okuyucular ayrıntılar için ilgili raporları görüntüleyebilir.

![pano](media/service-dashboards/power-bi-dashboard2.png)

Panolar Power BI hizmetinin bir özelliğidir. Power BI Desktop'ta kullanılamazlar. Mobil cihazlarda pano oluşturamazsınız ama bu cihazlarda onları [görüntüleyebilir ve paylaşabilirsiniz](mobile-apps-view-dashboard.md).

## <a name="dashboard-basics"></a>Pano temel bilgileri 

Panoda gördüğünüz görselleştirmelere *kutucuklar* denir. Kutucukları raporlardan panoya *sabitlersiniz*. Power BI'ı kullanmaya yeni başladıysanız [Power BI temel kavramlarını](service-basic-concepts.md) okuyarak sağlam bir temel oluşturabilirsiniz.

> [!IMPORTANT]
> Pano oluşturmak için [Power BI Pro](service-free-vs-pro.md) lisansı gerekir.

Panodaki görselleştirmeler raporlardan gelir ve her rapor bir veri kümesini temel alır. Panoları, bağlantılı raporlara ve temel alınan veri kümelerine giriş noktası olarak düşünebilirsiniz. Görselleştirmelerden birini seçtiğinizde temel aldığı rapor (ve veri kümesi) açılır.

![panolar, raporlar, veri kümeleri arasındaki ilişkiyi gösteren diyagram](media/service-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>Panoların avantajları
Panolar işlerinizi izlemek ve en önemli ölçümlerinizi bir bakışta görmek için harika bir yoldur. Panolardaki görselleştirmeler, bir veya daha fazla temel alınan veri kümesinden ve bağlantılı rapordan oluşabilir. Bir panoda şirket içi ve bulut verileri bir arada kullanılabilir ve verilerin konumundan bağımsız olarak tümleşik bir görünüm oluşturulabilir.

Panolar yalnızca güzel görünen resimlerden ibaret değildir. Bunlar son derece etkileşimli çalışır ve temel alınan veriler değiştikçe kutucuklar da güncelleştirilir.

## <a name="dashboards-versus-reports"></a>Panolarla raporları karşılaştırma
[Raporlar](service-reports.md) ve panoların ikisi de görselleştirmelerle dolu tuvaller olduğu için benzer görünebilir. Ancak önemli farklılıklar bulunur.

| **Özellik** | **Panolar** | **Raporlar** |
| --- | --- | --- |
| Sayfalar |Bir sayfa |Bir veya daha fazla sayfa |
| Veri kaynakları |Pano başına bir veya daha fazla rapor ve bir veya daha fazla veri kümesi |Rapor başına tek bir veri kümesi |
| Power BI Desktop'ta kullanılabilirlik |Hayır | Power BI Desktop'ta rapor oluşturabilir ve görüntüleyebilirsiniz |
| Abonelik |Bir panoya abone olabilirsiniz |Rapor sayfalarına abone olabilirsiniz |
| Filtreleme |Filtreleme veya dilimleme yapamazsınız |Filtreleme, vurgulama ve dilimleme için birçok farklı yol vardır |
| Öne çıkanlar |Bir panoyu "öne çıkan" panonuz olarak ayarlayabilirsiniz |Öne çıkan bir rapor oluşturamazsınız |
| Sık Kullanılan | Panoları *sık kullanılanlara* ekleyebilirsiniz | Raporları *sık kullanılanlara* ekleyebilirsiniz
| Uyarı ayarlama |Bazı durumlarda pano kutucukları için kullanılabilir |Raporlardan kullanılamaz |
| Doğal dil sorguları (Soru-Cevap) |Panolarda kullanılabilir | Raporlarda kullanılabilir |
| Temel alınan veri kümesi tablolarını ve alanlarını görme |Hayır. Verileri dışarı aktarabilir ancak tabloları ve alanları panonun kendisinde göremezsiniz. |Evet. Veri kümesi tablolarını, alanlarını ve değerlerini görebilirsiniz. |


## <a name="next-steps"></a>Sonraki adımlar
* Panoları daha rahat kullanmak için [örnek panolarımızdan](sample-tutorial-connect-to-the-samples.md) birine ilişkin tura katılın.
* [Pano kutucukları](service-dashboard-tiles.md) hakkında bilgi edinin.
* Tek bir pano kutucuğunu izlemek ve belirli bir eşiğe ulaştığında e-posta almak mı istiyorsunuz? [Kutucuklar için uyarılar oluşturun](service-set-data-alerts.md).
* Verileriniz hakkında soru sormak ve görselleştirme şeklinde yanıt almak için [Power BI Soru-Cevap](power-bi-tutorial-q-and-a.md) özelliğini kullanmayı öğrenin.
