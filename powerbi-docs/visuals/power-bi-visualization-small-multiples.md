---
title: Power BI küçük katlar oluşturma (Önizleme)
description: Küçük katlar veya trellising, görselin yan yana sunulan ve verileri, seçilen bir boyut tarafından bu sürümler genelinde bölümlenen birden çok sürümüne böler.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: pbi-visuals
ms.topic: how-to
ms.date: 02/05/2021
LocalizationGroup: Visualizations
ms.openlocfilehash: bc1f890e588227f9d0dc30202474a8f77f93fc38
ms.sourcegitcommit: f17acb16018752c234db6bff1f51f5130be12c58
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99617447"
---
# <a name="create-small-multiples-in-power-bi-preview"></a>Power BI küçük katlar oluşturma (Önizleme)

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Küçük katlar veya trellising, görselin birden çok sürümüne böler. Sürümler yan yana sunulur. veriler, seçilen bir boyut tarafından bu sürümler arasında bölünür. Örneğin, küçük bir çoklu bir "satış ölçütü" sütun grafiğini ürün hatları veya bölgeler genelinde bölebilir. Bu önizlemede, küçük katların daha sonraki sürümlerde daha fazla sunulan küçük bir özellik kümesi vardır.

:::image type="content" source="media/power-bi-visualization-small-multiples/small-mulitple-sales-category-region.png" alt-text="Kategori ve bölge için küçük katların ekran görüntüsü.":::

## <a name="enable-the-preview-feature"></a>Önizleme özelliğini etkinleştirme

**Dosya** menüsünde **Seçenekler ve ayarlar**  >  **Seçenekler**  >  **Önizleme özellikleri**' ni seçin ve **küçük katlar** onay kutusunu seçin.

:::image type="content" source="media/power-bi-visualization-small-multiples/small-multiple-enable-preview.png" alt-text="Küçük katların önizlemesini etkinleştirin.":::

Power BI Desktop yeniden başlatın ve küçük katları denemeye hazırsınız.

## <a name="create-small-multiples"></a>Küçük katlar oluştur

Şu anda çubuk, sütun, çizgi ve alan grafiklerde küçük katlar oluşturabilirsiniz. 

Başlamak için yukarıdaki görsellerden birini oluşturun ve verilerini bölümlemek istediğiniz bir alan seçin. Bu alanı görsel öğeler bölmesinin alanlar bölümünde **küçük katlara** sürükleyin. Grafiğiniz, verileri seçtiğiniz boyuta göre bölünen 2 × 2 kılavuza ayırır. Izgara, küçük katlar grafik ile doldurulur. Bunlar, soldan sağa ve yukarıdan aşağıya kadar seçtiğiniz sıralama sıralamasına göre sıralanır.

:::image type="content" source="media/power-bi-visualization-small-multiples/small-multiple-two-by-two-grid.png" alt-text="İki-iki kılavuzda küçük katlar.":::

Eksenlerin eşitlendiğini görürsünüz. Her satırın solunda bir Y ekseni ve her sütunun altında bir X ekseni vardır.

Küçük katlara [sahip olduğunuza göre, Power BI (Önizleme) ' de küçük katlarla nasıl etkileşim kurdığınıza](power-bi-visualization-small-multiples-interact.md)bakın.

## <a name="format-a-small-multiples-visual"></a>Küçük bir katgörseli biçimlendirme

Biçimlendirme bölmesindeki bazı yeni seçenekler kılavuzun görünüm ve kullanımını denetlemenize olanak tanır.

### <a name="change-the-grid-dimensions"></a>Kılavuz boyutlarını değiştirme

Kılavuz düzen kartındaki kılavuzun boyutlarını değiştirebilirsiniz:

:::image type="content" source="media/power-bi-visualization-small-multiples/small-multiple-grid-layout-card.png" alt-text="Küçük birden çok kılavuz düzen kartı.":::

Varsayılan değer 2 × 2 küçük katları ızgaradır, ancak satır ve sütun sayısını 6 × 6 ' ya kadar ayarlayabilirsiniz. Aşağı kaydırırken bu kılavuza sığmayan katların her türlü katları.


### <a name="adjust-the-small-multiples-titles"></a>Küçük katların başlıklarını ayarla

Diğer görsel başlıklarda olduğu gibi, küçük bir çok **başlık** kartındaki küçük birden çok başlığın stilini ve konumunu ayarlayabilirsiniz.

## <a name="preview-limitations"></a>Önizleme sınırlamaları

Özellik önizlemedeyken sürekli olarak çalışmaya devam ediyoruz ve özelliklerimizin geri kalanı ile sorunsuz bir şekilde çalışıyoruz. Bazı geçerli sınırlamalar aşağıda verilmiştir.

### <a name="fields-pane"></a>Alanlar bölmesi

- Tarih ve diğer sürekli hiyerarşiler: X ekseninde bir tarih hiyerarşisi olan çizgi grafik gibi bir görselin olduğunu varsayalım. Sıfırdan küçük katdığınızda, Power BI bu ekseni sürekli kategorik bir eksene dönüştürür.
- Veri içermeyen öğeleri göster: seçenek hala var, ancak davranış beklentilerinizle hizalanmayabilir.

### <a name="visual-interactions"></a>Görsel etkileşimler

- Kategorik ekseninde daha fazla yükle: eksen sonuna gittiğinizde, eksenin sonuna kadar kaydırdığınızda, görsel daha fazla kategori yükler. Şu anda küçük katbir görsel daha fazla kategori yüklemez.
- Ölçüyü ölçüyle Sırala: küçük katların sıralanması yeni işlevsellikdir. Küçük katlarınızı bir ölçüye göre sıralamayı bekliyor olabilirsiniz. Şu anda, alanın doğal sıralama düzeni ile yalnızca katlarınızı sıralayabilirsiniz.
- Sağ tıklama/bağlam menüsü-> çözümle: şimdilik devre dışı bırakıldı.
- Sağ tıklama/bağlam menüsü-> özetleme: şimdilik devre dışı bırakıldı.
- Dikdörtgen seçim ile birden çok veri noktası seçme: şimdilik devre dışı bırakıldı.
- Eksen önizlemesi: şimdilik devre dışı.
- Erişilebilirlik: küçük katların görsellere gelmesini sağlayan yeni "kılavuz" katmanını daha iyi destekleyebilmeniz için klavye gezintisi ve ekran geçici ayarlarını yapabilirsiniz. Kategorik eksen kaydırma çubuğu aracılığıyla klavye gezintisi gibi bazı davranışlar eksik olur.

### <a name="formatting-options"></a>Biçimlendirme seçenekleri

**Genel**

- Yanıt veren geçiş: seçenek hala var, ancak davranış beklentilerinizle hizalanmayabilir. Birçok mobil konaklama bu geçiş ile bağlı olduğundan, mobil deneyim, Power BI Desktop ve Power BI hizmeti bulduğunuz deneyimi de yakından yansıtır.
- Yüksek yoğunluklu örnekleme: çizgi grafikler için, yüksek yoğunluklu örnekleme değiştirme hala mevcuttur, ancak şu anda küçük katlarla desteklenmez.

**Eksen**

- Etiketleri birleştir: şimdilik devre dışı.

**Toplam etiketleri**

- Yığılmış grafikler için toplam Etiketler: şimdilik devre dışı bırakıldı.

**Yakınlaştırma kaydırıcısı**

- Yakınlaştırma sürgüleri: şimdilik devre dışı.

**Analiz bölmesi** 

- Eğilim çizgileri: şimdilik devre dışı.
- Tahmin: şimdilik devre dışı bırakıldı.

Açıkton etiketleri için Dinamik biçimlendirme: Şu anda desteklenmiyor.
Hizmet kullanılabilirliği

## <a name="authoring-in-the-power-bi-service"></a>Power BI hizmeti yazma

Özellik önizlemedeyken Web üzerinde küçük katların yazılması desteklenmez. Bir raporu küçük katbir Görselle görüntüleyebilir ve hatta görseli biçimlendirebilirsiniz. Ancak standart görseli Power BI hizmeti küçük bir görsele dönüştüremezsiniz. Bir görselin küçük katlar alanındaki bir alana zaten sahip olması veya bu görselde küçük katların gösterilmesi gerekir.

## <a name="share-your-feedback"></a>Geri bildiriminizi paylaşın

Küçük katların görselinizi öğrenmemizi sağlayın:

- [Power BI Topluluğu](https://community.powerbi.com/)
- [Power BI fikirler sayfası](https://ideas.powerbi.com/ideas/) 

## <a name="next-steps"></a>Sonraki adımlar

[Power BI küçük katlarla etkileşim kurma (Önizleme)](power-bi-visualization-small-multiples-interact.md)
