---
title: Power BI hizmeti kullanıcıları için pano neyi ifade eder?
description: Panolar, Power BI hizmetinin temel özelliklerinden biridir.
author: maggieMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 09/02/2018
ms.author: maggie
LocalizationGroup: Dashboards
ms.openlocfilehash: 2e71f3a1efe60094b9a714e1d03b891aa9da99a6
ms.sourcegitcommit: 07beb155ec0ea1cdcc741085251ed06d7bc8581c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48875431"
---
# <a name="dashboards-in-power-bi-service"></a>Power BI hizmetindeki panolar

Power BI ***panosu***, görselleştirmeler kullanarak bir hikaye anlatan ve genellikle tuval olarak adlandırılan tek bir sayfadır. Tek sayfayla sınırlı olduğundan, iyi tasarlanmış bir panoda yalnızca hikayenin en önemli parçaları yer alır.

![pano](media/service-dashboards/power-bi-dashboard2.png)

Panolar Power BI hizmetinin özelliklerinden biridir ve Power BI Desktop ile kullanılamaz. Panolar mobil cihazlarda oluşturulamaz ancak [görüntülenebilir ve paylaşılabilir](mobile-apps-view-dashboard.md).

## <a name="dashboard-creators-and-dashboard-consumers"></a>Pano oluşturucuları ve kullanıcıları
İş rolünüze bağlı olarak, kendi kullanımınız veya iş arkadaşlarınızla paylaşmak için pano oluşturan biri olabilirsiniz. Size yönelik bilgiler **İçerik oluşturanlar için panolar** bölümünde verilmiştir. Başkalarının panolar gönderdiği biriyseniz. Bu durumda panoları nasıl anlayacağınızı ve raporlarla nasıl etkileşim kuracağınızı öğrenmek istersiniz. Bu makale sizin için!


### <a name="if-you-will-be-receiving-and-consuming-dashboards"></a>Pano alacak ve kullanacaksanız

Panoda gördüğünüz görselleştirmeler, *kutucuk* olarak adlandırılır ve *içerik oluşturanlar* tarafından panolara raporlardan *sabitlenir*. Power BI'ı kullanmaya yeni başladıysanız [Power BI temel kavramlarını](service-basic-concepts.md) okuyarak sağlam bir temel oluşturabilirsiniz.

> [!IMPORTANT]
> Paylaşılan bir panoyu görüntülemek için [Power BI Pro](service-free-vs-pro.md) gerekir.

Panodaki görselleştirmeler raporlardan gelir ve her rapor bir veri kümesini temel alır. Panoları, bağlantılı raporlara ve temel alınan veri kümelerine giriş noktası olarak düşünebilirsiniz. Görselleştirmelerden birini seçtiğinizde bunu oluşturmak için kullanılan rapor (ve veri kümesi) açılır.

![panolar, raporlar, veri kümeleri arasındaki ilişkiyi gösteren diyagram](media/service-dashboards/power-bi-diagram.png)



## <a name="advantages-of-dashboards"></a>Panoların avantajları
Panolar işlerinizi izlemek, yanıtlar aramak ve en önemli ölçümlerinizi bir bakışta görmek için harikadır. Panolardaki görselleştirmeler, bir veya daha fazla temel alınan veri kümesinden ve bağlantılı rapordan oluşabilir. Bir panoda şirket içi ve bulut kaynaklı veriler bir arada kullanılarak verilerin konumundan bağımsız tümleşik bir görünüm oluşturulabilir.

Panolar yalnızca güzel görünen resimlerden ibaret değildir. Bu nesneler büyük ölçüde etkileşimlidir. Ayrıca temel alınan veriler değiştikçe kutucuklar da güncelleştirilir.

## <a name="dashboards-versus-reports"></a>Panolarla raporları karşılaştırma
[Raporlar](service-reports.md) da görselleştirmelerle dolu tuvaller olduklarından genellikle panolarla karıştırılır. Ancak Power BI kullanıcıları için bazı önemli farklılıklar bulunur.

| **Özellik** | **Panolar** | **Raporlar** |
| --- | --- | --- |
| Sayfalar |Bir sayfa |Bir veya daha fazla sayfa |
| Veri kaynakları |Pano başına bir veya daha fazla rapor ve bir veya daha fazla veri kümesi |Rapor başına tek bir veri kümesi |
| Power BI Desktop'ta kullanılabilirlik |Hayır |Evet, ***içerik oluşturanlar*** Desktop uygulamasında rapor oluşturabilir ve görüntüleyebilir |
| Abonelik |Bir panoya abone olabilirsiniz |Rapor sayfalarına abone olabilirsiniz |
| Filtreleme |Filtreleme veya dilimleme yapamazsınız |Filtreleme, vurgulama ve dilimleme için birçok farklı yol vardır |
| Öne çıkanlar |Bir panoyu "öne çıkan" panonuz olarak ayarlayabilirsiniz |Öne çıkan bir rapor oluşturamazsınız |
| Sık Kullanılan | Panoları *sık kullanılanlara* ekleyebilirsiniz | Raporları *sık kullanılanlara* ekleyebilirsiniz
| Uyarı ayarlama |Bazı durumlarda pano kutucukları için kullanılabilir |Raporlardan kullanılamaz |
| Doğal dil sorguları |Panodan kullanılabilir |Raporlardan kullanılamaz |
| Temel alınan veri kümesi tablolarını ve alanlarını görme |Hayır. Verileri dışarı aktarabilir ancak tabloları ve alanları panonun kendisinde göremezsiniz. |Evet. Veri kümesi tablolarını, alanlarını ve değerlerini görebilirsiniz. |
| Özelleştirme |Hayır |Okuma görünümü'nde yayımlama, ekleme, filtreleme, dışarı aktarma, .pbix olarak indirme, ilişkili içeriği görüntüleme, QR kodları oluşturma, Excel'de çözümleme ve daha fazla işlemi yapabilirsiniz.  |

## <a name="next-steps"></a>Sonraki adımlar
* Panoları daha rahat kullanmak için [örnek panolarımızdan](sample-tutorial-connect-to-the-samples.md) birine ilişkin tura katılın.
* [Pano kutucukları](service-dashboard-tiles.md) ve bunlardan birini seçtiğinizde gerçekleşecekler hakkında bilgi edinin.
* Tek bir pano kutucuğunu izlemek ve belirli bir eşiğe ulaştığında e-posta almak mı istiyorsunuz? [Kutucuklar için uyarılar oluşturun](service-set-data-alerts.md).
* Panolarınıza sorular sormanın keyfini çıkarın. Verileriniz hakkında soru sormak ve görselleştirme şeklinde yanıt almak için [Power BI Soru-Cevap](power-bi-tutorial-q-and-a.md) özelliğini kullanmayı öğrenin.
