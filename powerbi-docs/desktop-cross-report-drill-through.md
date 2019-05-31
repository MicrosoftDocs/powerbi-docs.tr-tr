---
title: Power BI Desktop'ta rapor arası detaylandırma kullanın
description: Bir rapordan başka bir Power BI Desktop'ta detaylandırma öğrenin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 45a7cdd3c7b5324f3d618eaba4bdb3968a9549a5
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375206"
---
# <a name="use-cross-report-drillthrough-in-power-bi-desktop"></a>Power BI Desktop'ta rapor arası detaylandırma kullanın

Power BI Desktop'ta rapor arası detaylandırma özelliği ile bir rapordan başka bir rapora bağlamsal atlayabilirsiniz. Bu, aynı çalışma alanı veya uygulama Microsoft Power BI hizmetindeki raporları olduğu sürece geçerlidir. Çapraz-rapor detaylandırma içeriğiyle ilgili iki veya daha fazla rapor bağlamak ve filtre bağlamı rapor çapraz bağlantısı ile birlikte geçirmek için kullanın. Bu makalede, Power BI raporları için bir rapor arası detaylandırma kurma ve kendileri için çapraz rapor detaylandırma kullandığınızda, hangi kullanıcıların deneyimi öğrenin.

![Power BI Desktop ekran detaylandırma seçeneği](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Aşağıdaki tanımları anlamak önemlidir, başlamadan önce ayarlama ve kullanma arası detaylandırma raporu:

* **Kaynak görsel:** Görsel visual bağlam menüsünü kullanarak detaylandırma eylemi çağırır.
* **Kaynak Rapor:** Detaylandırma rapor arası için kaynak görseli içeren rapor.
* **Hedef sayfası:** Bir detaylandırma eylemi başlatıldıktan sonra bir kullanıcı şirket gölünüzdeki sayfası.
* **Hedef raporu:** Çapraz-rapor detaylandırma hedef sayfayı içeren rapor.

## <a name="enable-cross-report-drillthrough"></a>Çapraz-rapor detaylandırma etkinleştir

Çapraz-rapor detaylandırma hedefi için bir rapor etkinleştirmek için bu rapor için özelliği etkinleştirmeniz gerekir **seçenekleri** penceresi. Git **dosya** > **seçenekler ve ayarlar** > **seçenekleri**ve ardından **rapor ayarlarını** neredeyse Sayfanın sol taraftaki.

Seçin **diğer raporları için detaylandırma hedeflerden kullanmak için bu rapordaki görseller izin** onay kutusunu, aşağıdaki görüntüde gösterildiği gibi.

![Ekran seçeneklerin penceresiyle vurgulandığı rapor ayarları](media/desktop-cross-report-drill-through/cross-report-drill-through-02.png)

Çapraz-rapor detaylandırma şimdi etkinleştirildi.

## <a name="set-up-cross-report-drillthrough"></a>Çapraz-rapor detaylandırmayı ayarlama

Çapraz-rapor detaylandırmayı ayarlama, detaylandırma rapor içinde ayarlamak benzerdir. Detaylandırma etkin sayfada detaylandırma hedeflemek diğer görsellerin izin vererek hedef sayfasında etkinleştirilir. Detaylandırma tek bir rapor içinde oluşturma adımları için bkz: [Power BI Desktop'ta detaylandırma özelliğini kullanma](desktop-drillthrough.md).

Kurulum işlemini başlatmak için birkaç ilk adımlar gerekir:

* Çalışma alanı veya uygulamada başka raporlardan erişilebilir bir detaylandırma hedef sayfası ayarlayın.
* Detaylandırma sayfaları dışında kendi raporu görmek bir rapor sağlar.

Detaylandırma seçeneklerinde Bul **alanları** bölümünü **görselleştirmeler** bölmesinde, aşağıdaki görüntüde gösterildiği gibi.

![Detaylandırma seçenekleri vurgulanmış ekran görüntüsü, görselleştirmeler bölmesi](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Detaylandırma sayfası için etkinleştirmenin ilk adımı, kaynak ve hedef raporlar için veri modellerini doğrulamaktır. Emin olun: 

* Geçirmek istediğiniz alanları her iki veri modelleri var.
* Alanların adlarını ve ait oldukları, tabloların adlarının aynı olduğundan (dizeleri da ayrıca eşleşmelidir ve büyük küçük harfe duyarlıdır).

Örneğin, bir filtre alanına geçirmek istiyorsanız *Ülke* tablo içindeki *Coğrafya*, iki modeli de sahip olmalıdır bir *Coğrafya* tablosunu ve *Ülke* Bu tablo içindeki alan. Aksi durumda, alan adı veya tablo adı temel alınan modelinde güncelleştirmeniz gerekir. Görünen ad alanları güncelleştirerek kolayca Çapraz rapor detaylandırma için düzgün şekilde çalışmaz. (Not her raporda şemaları tam olarak aynı olması gerekmez.)

Kurulum ile çalışmaya başlamak için hedef sayfayı hazır hale getirmek gerekir. Power BI Desktop'ta sayfasına gidin ve emin **arası rapor** detaylandırma geçiş ayarlandığında **üzerinde**. 

![Ekran görüntüsü açık olarak ayarlayın ve Çapraz rapor Aç/Kapat](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Ardından, tuvale detaylandırma hedefi olarak kullanmak istediğiniz alanları sürükleyip bırakın. Bir kategori olarak kullanılan veya bir ölçü gibi özetlenen alanın isteyip istemediğinizi seçin. Bu noktada, devre dışı bırakmak isteyip istemediğinizi seçebilirsiniz **tüm filtreleri tut** görsel geçiş. Diğer uygulanan filtreler kaynaktan visual, hedef detaylandırma visual geçirmek istemiyorsanız seçin **kapalı**.

> [!NOTE]
> Yalnızca arası rapor detaylandırma sayfası kullanıyorsanız, silmelisiniz **geri** düğme otomatik olarak eklenir. **Geri** düğmesi nagivation içinde tek bir rapor için yalnızca çalışır. 

Görsel yapılandırdıktan sonra Power BI hizmetinde değilseniz raporu kaydedin veya kaydedin ve Power BI Desktop'ı kullanıyorsanız, raporu yayımlayın emin olun.

Power BI Desktop için rapor arası detaylandırma etkinleştirme önceki bölümde açıklanan (içinde **seçenekleri** pencere). Çapraz-rapor detaylandırma etkinleştirmek için Power BI hizmetinde bir rapor arası detaylandırma hedefi oluşturmak için kullanıyorsanız, şunları yapmalısınız: 

1. Hedef rapor ve kaynak raporda bulunduğu çalışma alanını seçin.
2. Seçin **raporları**.
3. Seçin **ayarları** kaynak rapor simgesi.
4. Detaylandırma rapor çapraz geçiş olduğundan emin olun **üzerinde**.
5. Raporunuzu kaydedin.

İşte bu kadar. Raporunuzu rapor arası detaylandırma deneyimi için hazırdır. 

Sonraki bölümde, biz deneyimi kullanıcının açısından göz atın.

## <a name="cross-report-drillthrough-experience"></a>Çapraz-rapor detaylandırma deneyimi

Bir rapor için rapor arası detaylandırma deneyimi yapılandırdığınızda kullanma özelliğini koyabilirsiniz.

Power BI hizmetinde kaynak raporunu seçin ve sonra alanın veya alanların hedef page up belirttiğiniz şekilde kullanan bir görsel seçin. Ardından, görsel içerik menüsünü açın ve bir veri noktasına sağ **detaylandırma**.

![Kaynak raporu Power BI hizmetinde detaylandırma vurgulanmış ekran görüntüsü](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Gibi bunları hedef oluştururken yukarı ayarlamanız yeterlidir, ardından hedef arası rapor detaylandırma sayfasında, sonuçları görürsünüz. Sonuçları detaylandırma ayarlarına göre filtrelenir.

> [!IMPORTANT]
> Power BI rapor arası detaylandırma hedefleri önbelleğe alır. Değişiklik yaparsanız, beklendiği gibi detaylandırma hedefleri görmüyorsanız tarayıcınızı yenileyin emin olun. 

Çapraz-rapor hedefleri şu şekilde biçimlendirilir: 

`Target Page Name [Target Report Name]`

Detaylandırma istediğiniz hedef sayfayı seçtikten sonra Power BI, söz konusu sayfaya gider. Hedef sayfasının ayarlara göre filtre bağlamı boyunca geçirir. 

Kaynak görsel filtre bağlamı şunları içerebilir: 

* Rapor, sayfa ve görsel düzeyi filtreleri kaynak görseli etkileyen. 
* Çapraz filtreleme ve çapraz vurgulama, kaynak görseli etkiler. 
* Dilimleyicileri eşitleme ve sayfasında dilimleyicileri.
* URL parametreleri.

Power BI, yalnızca hedef rapor için detaylandırma geldiğinde filtreleri için tam bir dizeyle eşleşir alan adı ve tablo adı için bulduğu alanlar için geçerlidir. Power BI, hedef raporu Yapışkan filtreleri geçerli değildir. Varsa, ancak varsayılan kişisel işaretinizi geçerlidir. Örneğin, bir rapor düzeyi filtresi için varsayılan kişisel yer işareti içeriyorsa, *ülke = US*, Power BI geçerli filtre ilk olarak, filtre bağlamı kaynak uygulamadan önce. 

Power BI rapor arası detaylandırma için filtre bağlamı hedef rapordaki tüm standart sayfaları geçirir. Araç İpucu çağıran kaynağında visual araç ipucu sayfaları bağlı olarak filtrelenir olduğundan, power BI araç ipucu sayfaları için filtre bağlamı geçmiyor.

Çapraz-rapor detaylandırma eylemi sonra kaynak rapora geri dönmek istiyorsanız, tarayıcının kullanın **geri** düğmesi. 

## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki makaleler de ilginizi çekebilir:

* [Power BI Desktop’ta dilimleyicileri kullanma](visuals/power-bi-visualization-slicers.md)
* [Power BI Desktop'ta detaylandırma özelliğini kullanma](desktop-drillthrough.md)

