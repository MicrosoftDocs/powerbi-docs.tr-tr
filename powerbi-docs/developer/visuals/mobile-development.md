---
title: Mobil geliştirme
description: Mobil cihazlarda kullanımı kolay Power BI görselleri oluşturma
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 03/12/2019
ms.openlocfilehash: 38e6ac3be143381304f1fdfc8e1427b91f398a9a
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82196641"
---
# <a name="how-to-create-mobile-friendly-power-bi-visuals"></a>Mobil cihazlarda kullanımı kolay Power BI görselleri oluşturma
Mobil kullanımın Power BI’da önemli bir rolü vardır. Güçlü yönlerinden biri, verilerinize her yerde ve her zaman bağlı kalmasıdır.

Bir geliştirici Power BI görselleri oluştururken, her mobil cihazın benzersiz kısıtlamaları, mümkün olduğunca çok kullanıcıya ulaşacak ve en iyi mobil deneyimi sunacak şekilde ele alınmalıdır.

Hareket halindeki iş kullanıcılarınıza verilerinin kapsamlı bir görünümünü en kolay şekilde sunmak amacıyla [Windows, iOS ve Android için Power BI uygulamasını kullanın](/power-bi/consumer/mobile/mobile-apps-for-mobile-devices).

## <a name="requirements"></a>Gereksinimler

Mobil cihazlarda kullanımı kolay görsel geliştirme için aşağıdakiler gereklidir:

- İşleme

  Desteklenen tarayıcı ve uygulamalar dahil olmak üzere tüm desteklenen mobil cihazlardaki Power BI görsellerinizin raporlarda, panolarda veya **Odak** modunda çalışırken hatasız bir şekilde işlenmesi gerekir. 

- Etkileşimli

  Etkileşim işlevselliğinin, masaüstü cihazlarda sağlandığı şekilde sağlanması gerekir. Masaüstü tarayıcılarda işlenen tüm olayların desteklenmesi veya mobil cihazlar için karşılaştırılabilir olay işleyicilerinin bulunması gerekir.
  
  Örneğin temel gezinti ve veri noktaları seçiminde, masaüstü tarayıcılardaki işlevselliğin aynısının bulunması gerekir. Bir görsel **Ctrl** kullanarak çoklu seçimi destekliyorsa geliştiricinin mobil cihazlar için benzer bir olay işleyicisi eklemeyi düşünmesi gerekir.

  Aşağıdaki tabloda, mobil cihazlarda karşılık gelen olayların bir listesi sunulur.

  | Fare olayı adı | Dokunma olayı adı |
  |:----------------:|:----------------:|
  | `click` | `click` |
  | `mousemove` | `touchmove` |
  | `mousedown` | `touchstart` |
  | `mouseup` | `touchend` |
  | `dblclick` | dış kitaplık kullanma |
  | `contextmenu` | dış kitaplık kullanma |
  | `mouseover` | `touchmove` |
  | `mouseout` | `touchmove` (veya dış kitaplık) |
  | `wheel` | `NaN` |

  > [!NOTE]
  > Her mobil veya dokunmatik ekranlı cihaz fare (veya *fare* önekli) olaylarını desteklemez. Böyle durumlarda, aynı anda hem *fare* hem de *dokunma* olaylarını işleyin.

## <a name="optional"></a>İsteğe bağlı
Aşağıdakiler isteğe bağlı olarak kabul edilir ve daha iyi son kullanıcı deneyimi oluşturmak için kullanılır.

- İşleme

  Daha küçük görsel boyutlarını desteklemek için, kullanıcının her öğenin boyutunu ayarlamak için değiştirebileceği biçimlendirme seçenekleri eklemeyi deneyin. Örneğin, rapor ve panolarda kullanılması için etiketlere biçimlendirme seçenekleri ekleyin. Bu, kullanıcıların bir görseli mobil cihazları için özelleştirebilmesine olanak verir.
  
  Aynı ayar, masaüstü tarayıcılardaki görsellere de uygulanabilir ve görseli daha küçük ekranlara sığdırmak için gerekirse geçersiz kılınabilir.

  > [!NOTE]
  > **Odak** modundaki bir görseli iyileştirmek için hem yatay hem de dikey ekran boyutunu ele almak gerekir; bkz. [Odak modunda içerik görüntüleme](/power-bi/consumer/end-user-focus).

- Etkileşimli

  Sürükleme ve kaydırma gibi mobil cihazlara özgü olay işleyicilerini eklemeyi düşünün.

- Yük devretme

  Mobil cihazda işlenemiyorsa görselin açıklayıcı bir hata iletisi göstermesi gerekir.

## <a name="supported-browsers-and-devices"></a>Desteklenen tarayıcılar ve cihazlar
Power BI görsellerinin Power BI Uygulamalarını destekleyen tüm cihazlarda işlenmesi gerekir, daha fazla bilgi için bkz. [Power BI için desteklenen tarayıcılar](/power-bi/power-bi-browsers) ve [Power BI mobil uygulamaları](/power-bi/consumer/mobile/mobile-apps-for-mobile-devices).

Windows, iOS ve Android cihazların en son modelleriyle test edilirken, geliştiricilerin bu kalite boyutlarından her birini ele alması gerekir.

## <a name="next-steps"></a>Sonraki adımlar
Kullanmaya başlamak için bkz. [Öğretici: Power BI görseli geliştirme](/power-bi/developer/visuals/custom-visual-develop-tutorial).
