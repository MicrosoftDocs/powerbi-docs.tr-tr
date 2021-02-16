---
title: Power BI raporlarıyla ilgili ayarları değiştirme
description: Power BI hizmetinde rapor ayarlarını değiştirme
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 10/14/2020
LocalizationGroup: Reports
ms.openlocfilehash: 996c4a1e7b2bdda0bfdfa0951afc7922b2996084
ms.sourcegitcommit: 00e3eb2ec4f18d48a73cfd020bb42d08e859ad06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2021
ms.locfileid: "100531574"
---
# <a name="change-settings-for-power-bi-reports"></a>Power BI raporlarıyla ilgili ayarları değiştirme

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Power BI Desktop ve Power BI hizmetindeki rapor ayarları sayesinde rapor okuyucularının raporunuzla etkileşim kurma şeklini denetleyebilirsiniz. Örneğin rapor için filtre kaydetmelerine, rapordaki görselleri kişiselleştirmelerine veya rapor sayfalarını yan taraf yerine alt tarafta bulunan sekmeler halinde görüntülemesine olanak tanıyabilirsiniz.

:::image type="content" source="media/power-bi-report-settings/service-report-settings-pane.png" alt-text="Power BI hizmetindeki rapor ayarları bölmesinin ekran görüntüsü.":::

Öncelikle aşağıdaki makaleleri okumanız faydalı olabilir:

- [Veri kümesini içeri aktararak Power BI hizmetinde rapor oluşturma](service-report-create-new.md) makalesi, rapor oluşturma deneyimi hakkında bilgi sahibi olmanızı sağlar.
- [Power BI'daki raporlar](../consumer/end-user-reports.md) makalesi, rapor okuyucularınızın yaşadığı deneyim hakkında bilgi sahibi olmanızı sağlar.

 Haydi başlayalım!

## <a name="prerequisites"></a>Önkoşullar

- Power BI Desktop kullanarak raporları oluşturmak için bkz. [Masaüstü rapor görünümü](desktop-report-view.md).
- [Power BI hizmetine kaydolma](../fundamentals/service-self-service-signup-for-power-bi.md). 
- Power BI hizmetindeki rapor için düzenleme iznine sahip olmanız gerekir. İzinle ilgili ayrıntılı bilgi için [Yeni çalışma alanlarındaki roller](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces) bölümüne bakın.
- Power BI hizmeti ortamınızda bir rapor yoksa içinde pano, rapor ve veri kümesi bulunan [örnek içerik paketini yükleyebilirsiniz](sample-datasets.md#install-built-in-content-packs).

## <a name="open-the-settings-pane-in-power-bi-desktop"></a>Power BI Desktop'ta Ayarlar bölmesini açın

1. **Dosya** > **Seçenekler ve ayarlar** > **Seçenekler**’i seçin.
1. **Geçerli dosya** bölümünde **Rapor ayarları**'nı seçin.

    :::image type="content" source="media/power-bi-report-settings/desktop-report-settings-pane.png" alt-text="Power BI Desktop'taki raporun Ayarlar bölmesinin ekran görüntüsü":::

    Bu makalenin devamında raporlarla ilgili bazı özel ayarlar ele alınmıştır.

## <a name="open-the-settings-pane-in-the-power-bi-service"></a>Power BI hizmetinde Ayarlar bölmesini açın

1. Raporun okuma görünümünde **Dosya** > **Ayarlar**'ı seçin.

    :::image type="content" source="media/power-bi-report-settings/service-report-file-settings.png" alt-text="Dosya menüsünün Ayarlar seçeneğinin ekran görüntüsü.":::

1. **Ayarlar** bölmesinde ilgili rapor için düzenleyebileceğiniz bir dizi ayar yer alır. Bu makalenin devamında bunların bazıları ele alınmıştır.

## <a name="set-featured-content"></a>Öne çıkan içerik ayarlama

Panoları, raporları ve uygulamaları öne çıkarabilirsiniz; böylece bu öğeler, iş arkadaşlarınızın Power BI Giriş sayfasının Öne Çıkanlar bölümünde görüntülenir. [İçerikleri öne çıkarma](../collaborate-share/service-featured-content.md) hakkında daha fazla bilgi edinin.

## <a name="set-the-pages-pane"></a>Sayfalar bölmesini ayarlama

Sayfalar bölmesi ayarını şu an için yalnızca Power BI hizmetinde değiştirebilirsiniz. **Sayfalar bölmesi** ayarını açık duruma getirdiğinize rapor okuyucuları Okuma görünümünde rapor sayfası sekmelerini yanda değil alt tarafta görür. Düzenleme görünümünde rapor sayfası sekmeleri zaten raporun altında yer alır.

:::image type="content" source="media/power-bi-report-settings/report-settings-pages-pane.png" alt-text="Sayfalar bölmesi ayarının ekran görüntüsü.":::

## <a name="control-filters"></a>Denetim filtreleri

Raporun **Ayarlar** bölmesinde okuyucuların raporunuzdaki filtrelerle etkileşim kurma şeklini denetlemeye yönelik üç ayar bulunur. Aşağıdaki bağlantılar, her bir ayar hakkında ayrıntılar için [Power BI raporlardaki filtreleri biçimlendirme](power-bi-report-filter.md) makalesine gider.

- **Kalıcı filtreler**, okuyucuların [filtreleri rapora kaydetmesini](power-bi-report-filter.md#allow-saving-filters) sağlar.
- **Filtreleme deneyiminde** iki ayar daha vardır:
    
    Rapor okuyucularının [filtre türlerini değiştirmesine](power-bi-report-filter.md#restrict-changes-to-filter-type) izin verebilirsiniz.

    [Filtre bölmesi için aramayı](power-bi-report-filter.md#filters-pane-search) etkinleştirebilirsiniz.

## <a name="export-data"></a>Verileri dışarı aktarma

Varsayılan olarak [rapor okuyucuları raporunuzdaki görseller için özetlenmiş veya temel alınan verileri dışarı aktarabilir](../consumer/end-user-export.md). **Verileri dışarı aktarma** seçeneği sayesinde yalnızca özetlenmiş verileri dışarı aktarmalarına izin verebilir veya raporunuzdaki verileri aktarmalarını engelleyebilirsiniz.

## <a name="personalize-visuals"></a>Görsel öğeleri kişiselleştirme

Okuyucularınızın raporunuzdaki görselleri değiştirmesine ve kişiselleştirmesine izin verin. [Rapor okuyucularının görselleri kişiselleştirmelerine olanak tanıma](power-bi-personalize-visuals.md) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar

* [Başkalarının Giriş sayfalarında içerikleri öne çıkarma](../collaborate-share/service-featured-content.md)
* [Rapor okuyucularının görselleri kişiselleştirmelerine olanak tanıma](power-bi-personalize-visuals.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
