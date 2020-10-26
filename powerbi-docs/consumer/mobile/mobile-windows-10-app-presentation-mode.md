---
title: Surface Hub ve Windows 10 ’da sunu modunda görüntüleme - Power BI
description: Power BI raporlarını Surface Hub'da görüntüleme ve Power BI panolarını, raporlarını ve kutucuklarını Windows 10 cihazlarda tam ekran modunda görüntüleme hakkında bilgi edinin.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 08/12/2020
ms.author: painbar
ms.openlocfilehash: a47af4b96e80508a6ea21de2d8d3e0b40f907d8d
ms.sourcegitcommit: 383d87841d2509131fac7cc02c5c37c6a868144f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92025945"
---
# <a name="view-reports-and-dashboards-in-presentation-mode-on-surface-hub-and-windows-10-devices"></a>Raporları ve panoları Surface Hub'da ve Windows 10 cihazlarında sunu modunda görüntüleme
Windows 10 cihazlarında ve Surface Hub'da raporları ve panoları tam ekran modunda görüntülemek için sunu modunu kullanabilirsiniz. Sunu modu Power BI içeriğini toplantılarda, konferanslarda ya da ofisteki projektörde görüntülemek veya küçük ekranlarda daha fazla alan kullanmak için kullanışlıdır.

![Tam ekran modundaki rapor](./media/mobile-windows-10-app-presentation-mode/power-bi-presentation-mode-2.png)

Sunu modunda:
* Raporunuzdaki verilere daha kolay bir şekilde odaklanmanız için tüm “grafik öğeleri” (gezinti ve menü çubukları gibi) kaybolur.
* Verilerinizle etkileşim kurmanızı ve sunuyu yönetmenizi sağlamak amacıyla bir eylem araç çubuğu kullanılabilir hale gelir.
* Sayfalar, yer işaretleri veya ikisi arasında otomatik olarak geçiş yapan bir slayt gösterisi oynatabilirsiniz.

>[!NOTE]
>**Windows 10 Mobile kullanan telefonlar** için Power BI mobil uygulama desteği, 16 Mart 2021’de sona erecektir. [Daha fazla bilgi](/legal/powerbi/powerbi-mobile/power-bi-mobile-app-end-of-support-for-windows-phones)

## <a name="use-presentation-mode"></a>Sunu modunu kullanma
Power BI mobil uygulamasında, **Tam ekran** simgesine dokunarak tam ekran moduna geçin.
![Tam ekran simgesi](././media/mobile-windows-10-app-presentation-mode/power-bi-full-screen-icon.png) Uygulamanın grafik öğeleri görüntüden kaldırılır ve ekranın alt kısmında veya sağ ve sol kenarlarında (ekranınızın boyutuna bağlı olarak) bir eylem araç çubuğu gösterilir.

[![Kenar araç çubuklarıyla tam ekran modunda rapor](./media/mobile-windows-10-app-presentation-mode/power-bi-presentation-mode-toolbar.png)](./media/mobile-windows-10-app-presentation-mode/power-bi-presentation-mode-toolbar-expanded.png#lightbox)

Araç çubuğunda dokunarak aşağıdaki eylemleri gerçekleştirebilirsiniz:

| Simge | Eylem |
|------|--------|
|![geri simgesi](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-back-icon.png)|Önceki sayfaya **geri dönün**. Simgeye uzun süre dokunduğunuzda içerik haritası pencereleri açılır. Bu, raporunuzu veya panonuzu içeren klasöre gitmenize olanak tanır.|
|![Sayfalandırma simgesi](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-pages-icon.png)|Sunumunuzdaki raporun farklı bir sayfasına **geçiş yapın**.|
|![Yer işaretleri simgesi](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-bookmarks-icon.png)|Verilerinizin, yer işareti tarafından yakalanan belirli bir görünümünü sunmak için **yer işareti uygulayın**. Hem kişisel hem de rapor yer işaretlerini uygulayabilirsiniz.|
|![Mürekkep simgesi](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-ink-icon.png)|Rapor sayfanıza çizmek veya açıklama eklemek için Surface kaleminizi kullanırken **bir mürekkep rengi seçin**.|
|![Silgi simgesi](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-eraser-icon.png)|Rapor sayfanızda çizim yapmak ve buna açıklama eklemek için Surface kaleminizi kullanırken oluşabilen **mürekkep izlerini silin**.          |
|![Sıfırlama simgesi](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-reset-icon.png)|**Varsayılan görünüme sıfırlayın** ve sunu sırasında uygulamış olabileceğiniz tüm filtreleri, dilimleyicileri veya diğer veri görünümü değişikliklerini temizleyin.|
|![Paylaş simgesi](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-share-icon.png)|Sunum görünümünün bir görüntüsü iş arkadaşlarınızla **paylaşın**. Görüntü, sunum esnasında Surface kaleminizle yaptığınız tüm ek açıklamaları içerir.|
|![Yenileme simgesi](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-refresh-icon.png)|Raporu **yenileyin**.|
|![Oynat simgesi](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-play-icon.png)|Eylem çubuğunu gizleyip slayt gösterisini başlatarak **slayt gösterisini oynatın**. Seçici sayfalar, yer işaretleri veya her ikisi arasında otomatik dönmeyi seçmenizi sağlar. Slayt gösterisi varsayılan olarak her 30 saniyede bir sayfalar arasında otomatik olarak döner. Bu ayarları [**Ayarlar > Seçenekler**](#slideshow-settings)’den değiştirebilirsiniz. Slayt gösterileri hakkında daha fazla bilgi için bkz. [Diğer ayrıntılar](#slideshows)|
|![Tam ekran modundan çık](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-exit-full-screen-icon.png)|Sunu modundan **çıkın**.|
|![Arama simgesi](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-search-icon.png)|Power BI’daki diğer yapıtları **arayın**.|

Araç çubuğunu yerinden çıkarabilir ve sürükleyip bırakarak ekranın herhangi bir yerine yerleştirebilirsiniz. Büyük ekranlarda, raporunuzun belirli bir alanına odaklanmayı tercih ettiğinizde ve araçları bu alanın yanında kullanabilmek istediğinizde bu yararlı olacaktır. Parmağınızı araç çubuğunun üzerine koyup rapor tuvaline doğru çekmeniz yeterlidir.

[![Sunu modunda rapor ve yerinden çıkarılmış araç çubuğu](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-drag-toolbar-2.png)](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-drag-toolbar-2-expanded.png#lightbox)

## <a name="slideshows"></a>Slayt gösterileri

Sununuzda otomatik olarak geçiş yapması için bir slayt gösterisi oynatabilirsiniz. Slayt gösterisini sayfalar, yer işaretleri veya her ikisinde geçiş yapacak şekilde ayarlayabilirsiniz. Slayt gösterisi sırasında [otomatik sayfa yenilemesi](../../create-reports/desktop-automatic-page-refresh.md) ayarına sahip olan rapor sayfaları otomatik olarak yapılandırılarak yenilenir ve bu sayede her zaman en güncel verilerin görüntülenmesi sağlanır.

Eylem araç çubuğunda **Oynat** düğmesini seçtiğinizde slayt gösterisi başlar. Slayt gösterisini durdurmanıza veya oynatılan öğeyi (sayfalar, yer işaretleri veya her ikisi) değiştirmenize olanak veren bir denetleyici karşınıza gelir.

![Slayt gösterisi seçicisinin ekran görüntüsü](././media/mobile-windows-10-app-presentation-mode//power-bi-windows-10-slideshow-selector.png)

 Denetleyici, görüntülenen geçerli görünümün (sayfa veya yer işareti ve sayfa) adını gösterir. Yukarıdaki resimde **Satış** adlı raporu görüyoruz ve şu anda **Satış Performansı** sayfasındaki **Asya Pasifik** yer işaretini görüntülüyoruz.

Bir slayt gösterisi varsayılan olarak yalnızca sayfalar arasında her 30 saniyede bir geçiş yapar. [Slayt gösterisi ayarlarındaki](#slideshow-settings) varsayılan davranışı değiştirebilirsiniz.


### <a name="auto-play-a-slideshow-on-startup"></a>Başlangıçta bir slayt gösterisini otomatik oynatma

Power BI mobil uygulamasını, uygulama başlatıldığında otomatik olarak bir slayt gösterisini oynatmaya başlayacak şekilde ayarlayabilirsiniz. Bu seçenek, el ile müdahale olmaksızın herkese açık ekranlarda bir raporun çalıştırıldığı kiosk benzeri deneyimler oluşturmak için faydalıdır. Raporu otomatik oynatılacak şekilde ayarlama hakkında daha fazla bilgi için bkz. [Slayt gösterisi ayarları](#slideshow-settings).

### <a name="slideshow-settings"></a>Slayt gösterisi ayarları

Bir slayt gösterisi varsayılan olarak yalnızca sayfalar arasında her 30 saniyede bir geçiş yapar. Bu varsayılan davranışı aşağıda gösterildiği gibi **Ayarlar > Seçenekler**’e giderek değiştirebilirsiniz. Dilerseniz otomatik oynatmayı açabilir ve oynatılmak üzere bir rapor seçebilirsiniz.

1. Ayarlar simgesini seçin.

1. Seçenekler sekmesini açın.

1. Dilerseniz varsayılan ayarı slayt gösterisinin döngüye gireceği öğeye göre (sayfalar, yer işaretleri veya her ikisi) ve slaytların ne sıklıkta geçeceğine yönelik değiştirebilirsiniz.

1. Uygulama başlatıldığında raporunuzun otomatik olarak oynatılmaya başlamasını istiyorsanız ayarı açık duruma getirip **Rapor Seç**’e tıklayın. Erişiminiz olan raporları da arayabilirsiniz.

![Slayt gösterisi ayarlarının ekran görüntüsü](././media/mobile-windows-10-app-presentation-mode//power-bi-windows-10-slideshow-settings.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI hizmetindeki panoları ve raporları tam ekran modunda görüntüleme](../end-user-focus.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)