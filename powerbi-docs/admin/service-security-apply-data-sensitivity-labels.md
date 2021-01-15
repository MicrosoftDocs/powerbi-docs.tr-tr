---
title: Power BI'da duyarlılık etiketlerini uygulama
description: Power BI'da duyarlılık etiketlerini uygulamayı öğrenin
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 12/09/2020
LocalizationGroup: Data from files
ms.openlocfilehash: 09188b3b03fd5bfb720b98045ee9d895d337d677
ms.sourcegitcommit: a5e98bc86915f7bea6a0ab5df282683840e63d2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97969179"
---
# <a name="how-to-apply-sensitivity-labels-in-power-bi"></a>Power BI'da duyarlılık etiketlerini uygulama

Rapor, pano, veri kümesi, veri akışı ve .pbix dosyalarınıza uygulanan Microsoft Bilgi Koruması duyarlılık etiketleri, hassas içeriklerinizi yetkisiz veri erişimi ve sızıntılara karşı koruyabilir. Verilerinize duyarlılık etiketlerinin doğru şekilde uygulanması, verilerinize yalnızca yetkili kişilerin erişebilmesini sağlar. Bu makalede Power BI hizmetinde ve Power BI Desktop'ta duyarlılık etiketlerinin nasıl uygulanacağı gösterilir.

Power BI’daki duyarlılık etiketleri hakkında daha fazla bilgi için bkz. [Power BI'daki duyarlılık etiketleri](service-security-sensitivity-label-overview.md).

## <a name="apply-sensitivity-labels-in-the-power-bi-service"></a>Power BI hizmetinde duyarlılık etiketlerini uygulama

Power BI hizmetinde raporlara, panolara, veri kümelerine ve veri akışlarına duyarlılık etiketi uygulayabilirsiniz.

Power BI hizmetinde duyarlılık etiketlerini uygulayabilmek için:
* Bir [Power BI Pro lisansına](./service-admin-purchasing-power-bi-pro.md) ve etiketlemek istediğiniz içerik üzerinde Düzenleme izinlerine sahip olmanız gerekir.
* Kuruluşunuz için duyarlılık etiketlerinin etkinleştirilmesi gerekir. Bundan emin değilseniz Power BI yöneticinize danışın.
* [Power BI’da duyarlılık etiketlerini etkinleştirme](./service-security-enable-data-sensitivity-labels.md) makalesinde açıklandığı gibi, duyarlılık etiketlerini uygulama izinleri olan bir güvenlik grubuna dahil olmanız gerekir.
* Tüm [lisanslama gereksinimleri ve diğer gereksinimler](./service-security-enable-data-sensitivity-labels.md#licensing-and-requirements) karşılanmış olmalıdır.

Kiracınızda veri koruma etkin olduğunda panolar, raporlar, veri kümeleri ve veri akışlarının liste görünümünün duyarlılık sütununda duyarlılık etiketleri görünür.

![Duyarlılık etiketlerini etkinleştirme](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-01.png)

**Rapor veya panodaki bir duyarlılık etiketini uygulama veya değiştirme**
1. **Daha fazla (...)** seçeneğine tıklayın.
1. **Ayarlar**'ı seçin.
1. Ayarlar kenar bölmesinde uygun duyarlılık etiketini seçin.
1. Ayarları kaydedin.

Aşağıdaki görüntüde rapordaki bu adımlar gösterilmektedir

![Duyarlılık etiketlerini ayarlama](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-02.png)

**Veri kümesi veya veri akışındaki bir duyarlılık etiketini uygulama veya değiştirme**

1. **Diğer seçenekler (...)** öğesine tıklayın.
1. **Ayarlar**'ı seçin.
1. Veri kümeleri veya veri akışları sekmesini (hangisi uygunsa) seçin.
1. Duyarlılık etiketleri bölümünü genişletin ve uygun duyarlılık etiketini seçin.
1. Ayarları uygulayın.

Aşağıdaki iki görüntüde, veri kümesindeki bu adımlar gösterilmektedir.

**Diğer seçenekler (...)** öğesini ve sonra **Ayarlar**’ı seçin.

![Veri kümesi ayarlarını açma](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-05.png)

Ayarlar veri kümeleri sekmesinde duyarlılık etiketi bölümünü açın, istediğiniz duyarlılık etiketini seçin ve **Uygula**'ya tıklayın.

![Duyarlılık etiketi seçme](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-06.png)

## <a name="apply-sensitivity-labels-in-power-bi-desktop-preview"></a>Power BI Desktop'ta duyarlılık etiketlerini uygulama (önizleme)

Power BI Desktop'ta duyarlılık etiketlerini kullanmak için:
* [Power BI Pro lisansınızın](./service-admin-purchasing-power-bi-pro.md) olması gerekir.
* Kuruluşunuz için duyarlılık etiketlerinin etkinleştirilmesi gerekir. Bundan emin değilseniz Power BI yöneticinize danışın.
* [Power BI’da duyarlılık etiketlerini etkinleştirme](./service-security-enable-data-sensitivity-labels.md) makalesinde açıklandığı gibi, duyarlılık etiketlerini uygulama izinleri olan bir güvenlik grubuna dahil olmanız gerekir.
* Tüm [lisanslama gereksinimleri ve diğer gereksinimler](./service-security-enable-data-sensitivity-labels.md#licensing-and-requirements) karşılanmış olmalıdır.
* Power BI Desktop'ta bilgi koruması önizleme özelliğinin anahtarı açık olmalıdır. Giriş sekmesinde duyarlılık düğmesini görüyorsanız, önizleme özelliği açık demektir. Düğmeyi görmüyorsanız, **Dosya > Seçenekler ve ayarlar > Seçenekler > Önizleme özellikleri**'ne gidin ve **Bilgi koruması**'nın yanındaki kutuyu işaretleyin.

    ![Desktop önizleme özellikleri sayfasının ekran görüntüsü.](media/service-security-apply-data-sensitivity-labels/desktop-preview-features-page.png)

    >[!Important]
    >Bilgi koruması önizleme özelliğini açtıktan sonra duyarlılık etiketlerini kullanmaya başlamak için Desktop'ı yeniden başlatmalısınız.
    >
    >Desktop yeniden başlatıldıktan sonra kilitlenirse makinenizde gerekli Visual C++ yeniden dağıtılabilir çalışma zamanı kitaplığı sürümü eksik olabilir. Kilitlenmeyle karşılaşmanız halinde [Microsoft Visual C++ 2015 Yeniden Dağıtılabilir Güncelleştirmesi 3 indirme sayfasını](https://www.microsoft.com/download/details.aspx?id=53587) ziyaret edip yönergeleri izleyerek güncelleştirmeyi indirin ve yükleyin. Güncelleştirmeyi yükledikten sonra Desktop'ı başlatmayı yeniden deneyin.

    Bilgi koruması önizleme seçeneğini görmüyorsanız, bilgi koruması önizleme özelliği kuruluşunuz için engellenmiş olabilir. Bu durumda Power BI yöneticinizle iletişime geçin.

* Oturum açmış olmanız gerekir.

Üzerinde çalıştığınız dosyaya duyarlılık etiketi uygulamak için giriş sekmesinde duyarlılık düğmesine tıklayın ve görüntülenen menüden istediğiniz etiketi seçin.

![Desktop'ta duyarlılık etiketi menüsünün ekran görüntüsü.](media/service-security-apply-data-sensitivity-labels/sensitivity-label-menu-desktop.png)

>[!NOTE]
> Önizleme özelliklerinde duyarlılık etiketleri özelliğini açtıysanız ama hala duyarlılık düğmesini görmüyorsanız, bu durum [Power BI'da duyarlılık etiketlerini etkinleştirme](./service-security-enable-data-sensitivity-labels.md) konusunda açıklandığı gibi uygun lisansınızın olmadığını veya duyarlılık etiketi uygulama izinleri olan güvenlik grubunda yer almadığınızı gösteriyor olabilir.

Siz etiketi uyguladıktan sonra etiket durum çubuğunda görünür.

![Desktop durum çubuğundaki duyarlılık etiketinin ekran görüntüsü.](media/service-security-apply-data-sensitivity-labels/sensitivity-label-in-desktop-status-bar.png)

### <a name="sensitivity-labels-when-uploading-or-downloading-pbix-files-tofrom-the-service"></a>Hizmete veya hizmetten .pbix dosyalarını yükler veya indirirken duyarlılık etiketleri
* Desktop'tan Power BI hizmetine bir .pbix dosyası yayımladığınızda veya .pbix dosyasını doğrudan **Veri al**'ı kullanarak Power BI hizmetine yüklediğinizde, .pbix dosyasının etiketi hizmette oluşturulan hem rapora hem de veri kümesine uygulanır. Yayımladığınız veya karşıya yüklediğiniz .pbix dosyası mevcut varlıkların (.pbix dosyasıyla aynı adı taşıyan varlıkların) yerini alıyorsa, .pbix dosyasının etiketi söz konusu varlıklardaki etiketlerin üzerine yazılır.
* Power BI hizmetinde ".pbix dosyasına indir" özelliği kullanılırken, indirilen hem raporun hem de veri kümesinin etiketleri varsa ve bu etiketler birbirinden farklıysa, .pbix dosyasına bu iki etiketten daha kısıtlayıcı olan uygulanır.

## <a name="remove-sensitivity-labels"></a>Duyarlılık etiketlerini kaldırma

### <a name="service"></a>Hizmet
Rapor, pano, veri kümesi veya veri akışından duyarlılık etiketini kaldırmak için, [Power BI hizmetinde etiketleri uygulama işlemiyle aynı yordamı](#apply-sensitivity-labels-in-the-power-bi-service) izleyin ama verilerin duyarlılığını sınıflandırmanız istendiğinde **(Hiçbiri)** öğesini seçin.

### <a name="desktop"></a>Masaüstü
Bir .pbix dosyası duyarlılık etiketiyle kaydedildikten sonra dosyadan etiketi kaldırmak şu anda Desktop'ta desteklenmemektedir. Böyle durumlarda dosyanın Power BI hizmetine yayımlanması ve ardından hizmette izleyen rapor ve veri kümesinden etiketin kaldırılması önerilir.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Power BI'daki duyarlılık etiketi sınırlamaları için bkz. [Power BI'daki duyarlılık etiketleri](service-security-sensitivity-label-overview.md#limitations).

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, Power BI'da duyarlılık etiketlerini uygulama işlemi açıklanmıştır. Aşağıdaki makalelerde Power BI’da veri koruma hakkında daha fazla bilgi verilmektedir. 

* [Power BI'daki duyarlılık etiketlerine genel bakış](./service-security-sensitivity-label-overview.md)
* [Power BI’da duyarlılık etiketlerini etkinleştirme](./service-security-enable-data-sensitivity-labels.md)
* [Power BI’da Microsoft Cloud App Security denetimlerini kullanma](./service-security-using-microsoft-cloud-app-security-controls.md)