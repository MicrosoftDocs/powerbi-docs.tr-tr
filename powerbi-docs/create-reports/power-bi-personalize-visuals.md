---
title: Kullanıcıların rapordaki görselleri kişiselleştirmesine olanak tanıma
description: Rapor okuyucularının raporu düzenlemeden kendi rapor görünümlerini oluşturmasına olanak tanıyın.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/21/2020
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 27f71da8a8396de30254c1a02307aa48281db5a8
ms.sourcegitcommit: 5e5a7e15cdd55f71b0806016ff91256a398704c1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83793615"
---
# <a name="let-users-personalize-visuals-in-a-report"></a>Kullanıcıların rapordaki görselleri kişiselleştirmesine olanak tanıma

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Raporu geniş bir hedef kitleyle paylaşırken, kullanıcılarınızdan bir bölümü belirli görsellerin biraz farklı görünümlerini görmek isteyebilir. Eksendeki öğeleri değiştirmek, görsel türünü değiştirmek veya araç ipucuna bir şeyler eklemek isteyebilirler. Tek görselle herkesin gereksinimlerini karşılamak kolay değildir. Bu yeni özellikle tüketicilerinize tümüyle rapor okuma görünümünde görselleri inceleme ve kişiselleştirme gücü verebilirsiniz. Görseli istedikleri gibi ayarlayabilir ve görsele geri dönmek üzere onu bir yer işareti olarak kaydedebilirler. Rapor üzerinde düzenleme iznine sahip olmaları veya değişiklik istemek için rapor yazarına dönmeleri gerekmez.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-visual.png" alt-text="Görseli kişiselleştirme":::
 
## <a name="what-report-consumers-can-change"></a>Rapor tüketicilerinin değiştirebileceği öğeler

Bu özellik tüketicilerin Power BI raporunda görselleri rastgele inceleyerek daha fazla içgörü kazanmasına olanak tanır. Bir tüketici olarak bu özelliği nasıl kullanacağınızı öğrenmek için bkz. [Raporlarınızdaki görselleri kişiselleştirme](../consumer/end-user-personalize-visuals.md). Rapor okuyucularına temel inceleme senaryoları sağlamak isteyen rapor oluşturucuları için ideal bir özelliktir. Rapor okuyucuları şu değişiklikleri yapabilir:

- Görselleştirme türünü değiştirme
- Ölçü veya boyutu değiştirme
- Göstergeyi ekleme veya kaldırma
- İki veya daha fazla ölçüyü karşılaştırma
- Toplamaları vb. değiştirme

Bu özellik yeni inceleme olanakları sağlamakla kalmaz. Ayrıca tüketicilerin değişikliklerini yakalaması ve paylaşması için de yollar sağlar:

- Yaptıkları değişiklikleri yakalama
- Yaptıkları değişiklikleri paylaşma
- Bir raporda yaptıkları tüm değişiklikleri sıfırlama
- Bir görselde yaptıkları tüm değişiklikleri sıfırlama
- Son değişikliklerini temizleme

## <a name="turn-on-the-preview-feature"></a>Önizleme özelliğini açma

Bu özellik önizleme aşamasında olduğundan önce özellik anahtarını açmanız gerekir. **Dosya** > **Seçenekler ve Ayarlar** > **Seçenekler** yolunu izleyin. **Genel** ayarlar > **Önizleme özellikleri**’nin altında **Görselleri kişiselleştir**’in seçili olduğundan emin olun.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-preview-personalize-visual.png" alt-text="Görselleri kişiselleştirme seçeneğini açma":::

Bunu geçerli dosyanın ayarlarında görmek için Power BI Desktop’ı yeniden başlatmanız gerekebilir.

## <a name="enable-personalization-in-a-report"></a>Raporda kişiselleştirmeyi etkinleştirme

Önizleme anahtarını açtıktan sonra, tüketicilerin görsellerini kişiselleştirmesine izin vermek istediğiniz raporlar için bunu özel olarak etkinleştirmeniz gerekir.

Bu özelliği Power BI Desktop'ta veya Power BI hizmetinde etkinleştirebilirsiniz.

### <a name="in-power-bi-desktop"></a>Power BI Desktop'ta

Özelliği Power BI Desktop’ta etkinleştirmek için **Dosya** > **Seçenekler ve Ayarlar** > **Seçenekler** > **Geçerli dosya** > **Rapor ayarları**’na gidin. **Görselleri kişiselleştir (önizleme)** seçeneğinin açıldığından emin olun.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-settings-personalize-visual.png" alt-text="Raporda kişiselleştirmeyi etkinleştirme":::

### <a name="in-the-power-bi-service"></a>Power BI hizmetinde

Özelliği bunun yerine Power BI hizmetinde etkinleştirmek için raporunuzun **Ayarlar** bölümüne gidin.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-service-settings-personalize-visual.png" alt-text="Power BI hizmetinde rapor ayarları":::

**Görselleri kişiselleştir (önizleme)**  > **Kaydet**’i açın.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-service-personalize-visual.png" alt-text="Hizmette görselleri kişiselleştirme seçeneğini açma":::

## <a name="select-visuals-that-can-be-personalized"></a>Kişiselleştirilebilecek görselleri seçme

Belirli rapor için bu ayarı etkinleştirdiğinizde, varsayılan olarak rapordaki tüm görseller kişiselleştirilebilir. Tüm görsellerin kişiselleştirilmesini istemiyorsanız bu ayarı her görsel için açabilir veya kapatabilirsiniz.

Görseli seçin > **Görselleştirmeler** bölmesinde **Biçim**’i seçin > **Görsel üst bilgisi**’ni genişletin.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-format-visual-header-personalize.png" alt-text="Görsel üst bilgisi’ni seçme":::
 
**Görseli kişiselleştir** >  kaydırıcısını **Açık** veya **Kapalı** konuma getirin.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-format-visual-personalize-on-off.png" alt-text="Görseli kişiselleştir kaydırıcısı açık veya kapalı":::


## <a name="limitations-and-known-issues"></a>Sınırlamalar ve bilinen sorunlar

Şu anda özelliğin bilinmesi gereken birkaç sınırlaması vardır.

- Bu özellik web’de yayımlama gibi ekleme senaryolarında desteklenmez.
- Kullanıcının incelemeleri otomatik olarak kalıcı olmaz. Değişikliklerinizi yakalamak için görünümünüzü kişisel bir yer işareti olarak kaydetmeniz gerekir.
- Bu özellik, iOS ve Android tabletler için Power BI mobil uygulamalarında ve Power BI Windows uygulamasında desteklenir; telefonlar için Power BI mobil uygulamalarında desteklenmez. Bununla birlikte, Power BI hizmetindeyken kişisel yer işaretine kayıtlı bir görselde yapılan değişiklikler, tüm Power BI mobil uygulamalarında dikkate alınır.

Ayrıca ilgilendiğimiz bazı bilinen sorunlar da vardır:

- Hiyerarşi ekleme desteklenmez; alt öğeleri tek tek eklemeniz gerekir.
- Tarih hiyerarşisini bir tarihe (veya tersine) dönüştüremezsiniz. 
- Kişisel yer işaretleriyle, seçtiğiniz sıraya bağlı olarak biraz farklı sonuçlar elde edebilirsiniz. Tutarsızlıklar olması mümkündür çünkü raporun tam durumunu değil yalnızca yapılan değişiklikleri yakalarız. Geçici çözüm olarak **Varsayılana sıfırla**’yı ve sonra da görüntülemek istediğiniz yer işaretini seçmektir. 

## <a name="next-steps"></a>Sonraki adımlar

[Raporlarınızdaki görselleri kişiselleştirme](../consumer/end-user-personalize-visuals.md)     

Yeni görsel kişiselleştirme deneyimini bir kez deneyin. [Power BI Ideas sitesinde](https://ideas.powerbi.com/forums/265200-power-bi) bu özellikle ilgili geri bildirimlerinizi sağlayın ve bu deneyimi geliştirmeye nasıl devam edebileceğimiz konusunda görüşlerinizi bildirin. 

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
