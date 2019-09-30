---
title: Power BI Desktop'ta çapraz rapor detaylandırma özelliğini kullanma
description: Power BI Desktop'ta bir rapordan diğerindeki detaya gitme hakkında bilgi edinin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/18/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 6424180dde3dac0d6d2b66c8a9303810b6aa0dc6
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71100089"
---
# <a name="use-cross-report-drillthrough-in-power-bi-desktop"></a>Power BI Desktop'ta çapraz rapor detaylandırma özelliğini kullanma

Power BI Desktop’taki çapraz rapor detaylandırma özelliğini kullanarak bir rapordan başka bir rapora bağlamsal olarak atlayabilirsiniz. Raporlar Power BI hizmeti içinde aynı çalışma alanında veya uygulamada olduğu sürece bu durum geçerlidir. İlgili içeriğe sahip iki veya daha fazla raporu bağlamak ve çapraz rapor bağlantısıyla birlikte filtre bağlamını iletmek için çapraz rapor detaylandırma özelliğini kullanın. Bu makalede, Power BI raporları için çapraz rapor detaylandırma özelliğini ayarlamayı ve kullanıcıların kendileri için çapraz rapor detaylandırmayı kullandıklarında neyle karşılaştıklarını öğreneceksiniz.

![Power BI Desktop detaylandırma seçeneğinin ekran görüntüsü](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Çapraz rapor detaylandırma özelliğini ayarlamaya ve kullanmaya başlamadan önce aşağıdaki tanımların anlaşılması önemlidir:

* **Kaynak görseli:** Görsel bağlam menüsünü kullanarak detaylandırma eylemini çağıran görsel.
* **Kaynak raporu:** Çapraz rapor detaylandırma için kaynak görseli içeren rapor.
* **Hedef sayfa:** Bir detaylandırma eylemi başlatıldıktan sonra kullanıcının hangi yer aldığı sayfa.
* **Hedef rapor:** Çapraz rapor detaylandırma için hedef sayfayı içeren rapor.


> [!NOTE]
> Power BI Desktop’taki çapraz rapor detaylandırma özelliğini kullanarak bir rapordan başka bir rapora bağlamsal olarak atlayabilirsiniz. Raporlar Power BI hizmeti içinde aynı çalışma alanında veya uygulamada olduğu sürece bu durum geçerlidir. Bu özellik *Çalışma Alanım* ([Benimle paylaşılan raporlar](service-share-dashboards.md#share-a-dashboard-or-report)) içinden bireysel olarak paylaşılan raporlara erişilirken geçerli değildir; bunun yerine, ilk olarak paylaşıldığı çalışma alanından rapora erişmeniz gerekir.


## <a name="enable-cross-report-drillthrough"></a>Çapraz rapor detaylandırmayı etkinleştirme

Bir raporun çapraz rapor detaylandırma hedefi olması için, **Seçenekler** penceresinden bu rapor için özelliği etkinleştirmeniz gerekir. **Dosya** > **Seçenekler ve ayarlar** > **Seçenekler**’e gidin, sonra soldaki sayfanın alt kısmındaki **Rapor ayarları**’na gidin.

Aşağıdaki görüntüde gösterildiği gibi, **Bu rapordaki görsellerin diğer raporlardaki detaylandırma hedeflerini kullanmasına izin ver** onay kutusunu seçin.

![Rapor ayarları vurgulanmış Seçenekler penceresinin ekran görüntüsü](media/desktop-cross-report-drill-through/cross-report-drill-through-02.png)

Çapraz rapor detaylandırma artık etkindir.

## <a name="set-up-cross-report-drillthrough"></a>Çapraz rapor detaylandırmayı ayarlama

Çapraz rapor detaylandırmayı ayarlamak, bir rapor içinde detaylandırmayı ayarlama işlemine benzerdir. Detaylandırma hedef sayfada etkinleştirilerek diğer görsellerin detaylandırma için etkinleştirilen sayfayı hedef almasına olanak tanır. Tek bir rapor içinde detaylandırma oluşturma adımları için bkz. [Power BI Desktop’ta detaylandırma özelliğini kullanma](desktop-drillthrough.md).

Ayarlama işlemini başlatmak için birkaç başlangıç adımını uygulamanız gerekir:

* Daha sonra çalışma alanındaki veya uygulamadaki diğer raporlardan erişilebilen bir detaylandırma hedef sayfası ayarlayın.
* Raporun detaylandırma sayfalarını kendi raporunun dışından görmesine izin verin.

Aşağıdaki görüntüde gösterildiği gibi **Görsel Öğeler** bölmesinin **Alanlar** bölümünde detaylandırma seçeneklerini bulun.

![Detaylandırma seçeneklerinin vurgulandığı Görsel Öğeler bölmesinin ekran görüntüsü](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Bir sayfada detaylandırma özelliğini etkinleştirmenin ilk adımı, kaynak ve hedef raporların veri modellerini doğrulamaktır. Şunlardan emin olun: 

* Geçirmek istediğiniz alanlar her iki veri modelinde de mevcuttur.
* Alanların adları ve ait oldukları tabloların adları aynıdır (dizelerin de eşleşmesi gerekir ve büyük/küçük harfe duyarlıdır).

Örneğin, *Coğrafya* tablosundaki *Ülke* alanında bir filtreyi geçirmek istiyorsanız her iki modelin de *Coğrafya* tablosuna ve o tablo içinde bir *Ülke* alanına sahip olması gerekir. Aksi takdirde, temel alınan modeldeki alan adını veya tablo adını güncelleştirmeniz gerekir. Alanların sadece görünen adını güncelleştirmek, çapraz rapor detaylandırması için işe yaramaz. (Her rapordaki şemaların tam olarak aynı olması gerekmediğini unutmayın.)

Ayarlamaya başlamak için, hedef sayfayı hazır duruma getirmeniz gerekir. Power BI Desktop’ta sayfaya gidin ve **Çapraz rapor** detaylandırma düğmesinin **Açık** olarak ayarlandığından emin olun. 

![Açık olarak ayarlanmış Çapraz rapor düğmesinin ekran görüntüsü](media/desktop-cross-report-drill-through/cross-report-drill-through-03.png)

Sonra, detaylandırma hedefi olarak kullanmak istediğiniz alanları tuvale sürükleyin. Alanın kategori olarak kullanılmasına veya bir ölçü gibi özetlenmesine karar verin. Bu noktada, görsel için **Tüm filtreleri tut** seçeneğini devre dışı bırakmak isteyip istemediğinizi seçebilirsiniz. Kaynak görselden hedef detaylandırma görseline uygulanan diğer filtreleri geçirmek istemiyorsanız **Kapalı**'yı seçin.

> [!NOTE]
> Sayfayı yalnızca çapraz rapor detaylandırması için kullanıyorsanız, otomatik olarak eklenen **Geri** düğmesini silmeniz gerekir. **Geri** düğmesi yalnızca tek bir rapor içinde gezinmeye yarar. 

Görseli yapılandırdıktan sonra, Power BI hizmetindeyseniz raporu kaydettiğinizden emin olun veya Power BI Desktop kullanıyorsanız raporu kaydedip yayımlayın.

Bir önceki bölümde Power BI Desktop için çapraz rapor detaylandırmayı etkinleştirme işlemi açıklanmıştır (**Seçenekler** penceresinde). Çapraz rapor detaylandırma hedefi oluşturmak için Power BI hizmetini kullanıyorsanız, çapraz rapor detaylandırmayı etkinleştirmek için şunları yapmanız gerekir: 

1. Hedef raporunuzun ve kaynak raporunuzun bulunduğu çalışma alanını seçin.
2. **Raporlar**’ı seçin.
3. Kaynak raporun **Ayarlar** simgesini seçin.
4. Çapraz rapor detaylandırma düğmesinin **Açık** olduğundan emin olun.
5. Raporunuzu kaydedin.

İşte bu kadar. Raporunuz, çapraz rapor detaylandırma deneyimine hazırdır. 

Bir sonraki bölümde, bu deneyime kullanıcının perspektifinden bakacağız.

## <a name="cross-report-drillthrough-experience"></a>Çapraz rapor detaylandırma deneyimi

Bir rapor için çapraz rapor detaylandırma deneyimini yapılandırdığınızda, özelliği kullanıma alabilirsiniz.

Power BI hizmetinde kaynak raporunu seçin ve ardından hedef sayfayı ayarlarken belirttiğiniz şekilde alanı veya alanları kullanan bir görseli seçin. Sonra, bir veri noktasına sağ tıklayıp görsel bağlam menüsünü açın ve **Detaylandırma**'yı seçin.

![Detaylandırma seçeneği vurgulanmış Power BI hizmeti kaynak raporunun ekran görüntüsü](media/desktop-cross-report-drill-through/cross-report-drill-through-01.png)

Böylece sonuçları, hedefi oluştururken ayarladığınız gibi, hedef çapraz rapor detaylandırma sayfasında görürsünüz. Sonuçlar detaylandırma ayarlarına göre filtrelenir.

> [!IMPORTANT]
> Power BI, çapraz rapor detaylandırma hedeflerini önbelleğe kaydeder. Değişiklik yaparsanız, detaylandırma hedeflerini beklenen şekilde görmemeniz durumunda tarayıcınızı yenilediğinizden emin olun. 

Çapraz rapor hedefleri aşağıdaki biçimde biçimlendirilir: 

`Target Page Name [Target Report Name]`

Detaylandırmak istediğiniz hedef sayfayı seçtikten sonra Power BI bu sayfaya gider. Hedef sayfanın ayarlarına bağlı olarak filtre bağlamını geçirir. 

Kaynak görseldeki filtre bağlamı şunları içerebilir: 

* Kaynak görseli etkileyen rapor, sayfa ve görsel düzeyi filtreleri. 
* Kaynak görseli etkileyen çapraz filtre ve çapraz vurgulama. 
* Sayfa üzerindeki dilimleyiciler ve eşitleme dilimleyicileri.
* URL parametreleri.

Detaylandırma için hedef rapora girdiğinizde, Power BI alan adı ve tablo adı için yalnızca tam dize eşleşmeleri bulduğu alanlara filtre uygular. Power BI, hedef rapordaki yapışkan filtreler uygulamaz. Ancak, varsa varsayılan kişisel yer işaretinizi uygular. Örneğin, varsayılan kişisel yer işaretiniz *Ülke = ABD* için bir rapor düzeyi filtresi içeriyorsa, kaynak görselden filtre bağlamını uygulamadan önce Power BI ilk olarak bu filtreyi uygular. 

Çapraz rapor detaylandırma için Power BI, filtre bağlamını hedef rapordaki tüm standart sayfalara geçirir. Araç ipucu sayfaları araç ipucunu çağıran kaynak görsele göre filtreleneceği için, Power BI araç ipucu sayfaları için filtre bağlamını geçirmez.

Çapraz rapor detaylandırma eyleminden sonra kaynak rapora dönmek isterseniz tarayıcının **Geri** düğmesini kullanın. 

## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki makaleler de ilginizi çekebilir:

* [Power BI Desktop’ta dilimleyicileri kullanma](visuals/power-bi-visualization-slicers.md)
* [Power BI Desktop'ta detaylandırma özelliğini kullanma](desktop-drillthrough.md)

