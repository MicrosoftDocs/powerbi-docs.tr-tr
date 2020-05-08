---
title: Power BI mobil uygulamasında raporu coğrafi konuma göre filtreleme
description: Rapor sahibi coğrafi etiketleri ayarladıysa Microsoft Power BI mobil uygulamalarında bir raporu coğrafi konumunuza göre nasıl filtreleyebileceğinizi öğrenin.
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: painbar
ms.openlocfilehash: 4a9dcf14d1745087e2596507d4c7dbc7a03b5ab3
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "79435341"
---
# <a name="filter-a-report-by-geographic-location-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında bir raporu coğrafi konuma göre filtreleme
Aşağıdakiler için geçerlidir:

| ![iPhone](./media/mobile-apps-geographic-filtering/iphone-logo-50-px.png) | ![iPad](./media/mobile-apps-geographic-filtering/ipad-logo-50-px.png) | ![Android telefon](./media/mobile-apps-geographic-filtering/android-phone-logo-50-px.png) | ![Android tablet](./media/mobile-apps-view-dashboard/android-tablet-logo-50-px.png) | ![Windows telefon](./media/mobile-apps-geographic-filtering/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |Windows 10 telefonları |

Bir Power BI raporunu mobil cihazınızda görüntülediğinizde sağ üst köşede küçük bir raptiye simgesi görüyor musunuz? Görebiliyorsanız bu, coğrafi konumunuza göre raporu filtreleyebileceğiniz anlamına gelir.

> [!NOTE]
> Konuma göre filtreleme işlemini sadece, raporda geçen coğrafi adlar "New York City" ya da "Germany" gibi İngilizce yazılmışsa gerçekleştirebilirsiniz. Windows 10 tabletleri ve kişisel bilgisayarları coğrafi filtrelemeyi desteklemez. Ancak Windows 10 telefonlar bu özelliği destekler.

>[!NOTE]
>**Windows 10 Mobile kullanan telefonlar** için Power BI mobil uygulama desteği, 16 Mart 2021’de sona erecektir. [Daha fazla bilgi ](https://go.microsoft.com/fwlink/?linkid=2121400)

## <a name="filter-your-report-by-your-geographic-location"></a>Raporunuzu coğrafi konuma göre filtreleme
1. Mobil cihazınızda yüklü bulunan Power BI mobil uygulamasında bir rapor açın.
2. Rapor coğrafi veri içeriyorsa Power BI'ın bulunduğunuz konum bilgisine erişmesine izin vermenizi isteyen bir ileti görüntülenir. **İzin ver**’e tıklayın ve ardından yine **İzin ver**’e dokunun.
3. Raptiyeye dokunun ![Raptiye simgesi](./media/mobile-apps-geographic-filtering/power-bi-mobile-geo-icon.png)dokunun. Raporun kapsadığı veriye bağlı olarak şehir, eyalet/il veya ülke/bölge olarak filtreleme yapabilirsiniz. Filtre yalnızca mevcut konumunuzla eşleşen seçenekleri listeler.
   
    ![Raptiye filtresi](./media/mobile-apps-geographic-filtering/power-bi-mobile-geo-map-set-filter.png)

## <a name="why-dont-i-see-location-tags-on-a-report"></a>Rapor üzerinde neden konum etiketleri görmüyorum?
Konum etiketlerini görebilmeniz için aşağıdaki koşulların yerine getirilmesi gerekir. 

* Raporu Power BI Desktop’ta oluşturan kişi [coğrafi veriyi](../../desktop-mobile-geofiltering.md) Şehir, Eyalet ya da Ülke/Bölge olarak en az bir sütun için sınıflandırmış olmalıdır.
* Şu anda bu sütunda veri içeren konumlardan birinde olmanız gerekir.
* Şu mobil cihazlardan birini kullanmanız gerekir:
  * iOS (iPad, iPhone, iPod).
  * Android (telefon, tablet).
  * Windows 10 telefon (kişisel bilgisayarlar ve tabletler gibi diğer Windows 10 cihazları coğrafi filtrelemeyi desteklemez).

Power BI Desktop'ta [coğrafi filtrelemeyi ayarlama](../../desktop-mobile-geofiltering.md) hakkında daha fazla bilgi edinin.

### <a name="next-steps"></a>Sonraki adımlar
* Mobil uygulamalarla [gerçek dünyadan Power BI verilerine bağlanma](mobile-apps-data-in-real-world-context.md)
* [Power BI Desktop'ta verileri kategorilere ayırma](../../desktop-data-categorization.md) 
* Sorular? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

