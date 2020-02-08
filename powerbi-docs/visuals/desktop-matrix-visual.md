---
title: Power BI’da matris görselini kullanma
description: Matris görselinin Power BI’da basamaklı düzenlere ve ayrıntılı vurgulamaya nasıl olanak sağladığını öğrenin.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/30/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 2e4ab92d5d1adce8659cdb971c5061a0f133b38f
ms.sourcegitcommit: 64a270362c60581a385af7fbc31394e3ebcaca41
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/31/2020
ms.locfileid: "76895546"
---
# <a name="create-matrix-visualizations-in-power-bi"></a>Power BI'da matris görselleştirmesi oluşturma

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Matris görseli tabloya benzer.  Tablo iki boyutu destekler ve verileri düzdür; başka bir deyişle yinelenen değerler gösterilir ve toplanmaz. Matris, çok boyutlu verileri daha anlamlı bir şekilde görüntülemeyi kolaylaştırır; basamaklı düzeni destekler. Matris verileri otomatik olarak toplar ve detaya gitmeye olanak tanır. 

**Power BI Desktop** raporlarınızda matris görselleri oluşturabilir ve matristeki öğeleri bu rapor sayfasındaki diğer görsellerle çapraz vurgulayabilirsiniz. Örneğin satırları, sütunları ve hatta tek tek hücreleri seçip çapraz vurgulama uygulayabilirsiniz. Ayrıca, tek veya birden fazla hücre seçimi kopyalanıp diğer uygulamalara yapıştırılabilir. 

![çapraz vurgulanan matris ve halka grafik](media/desktop-matrix-visual/matrix-visual_2a.png)

Matrisle ilişkili birçok özellik vardır ve bu özellikler, makalenin ilerleyen bölümlerinde ele alınacaktır.


## <a name="understanding-how-power-bi-calculates-totals"></a>Power BI tarafından toplamların nasıl hesaplandığını anlama

Matris görselinin nasıl kullanılacağı konusuna geçmeden önce, tablo ve matrislerdeki toplam ve alt toplam değerlerinin Power BI tarafından nasıl hesaplandığının öğrenilmesi önemlidir. Toplam ve alt toplam satırları için Power BI ölçümü temel verilerdeki tüm satırlarda hesaplanır; yalnızca görünen veya görüntülenen satırlardaki değerlerin toplanmasından ibaret değildir. Bu, toplam satırında beklediğinizden farklı değerler görebileceğiniz anlamına gelir.

Aşağıdaki matris görsellerini gözden geçirin. 

![tablo ile matrisi karşılaştırır](media/desktop-matrix-visual/matrix-visual_3.png)

Bu örnekte, en sağdaki matris görselinin her satırında her satıcı/tarih bileşimi için *Tutar* gösterilmektedir. Ancak, bir satıcının birden çok tarihte göründüğünden, sayılar birden çok kez yer görünebilir. Bu nedenle, temel verilerden elde edilen doğru toplam ile görünen değerlerin basitçe toplanmasından elde edilen değer eşit değildir. Bu, toplanan değer bir bire çok ilişkinin ‘bir’ tarafı olduğunda yaygın olarak kullanılan bir düzendir.

Toplamlara ve alt toplamlara baktığınızda, bu değerlerin temel alınan değerlere dayandığını unutmayın. Yalnızca görünen değerlere dayanmazlar.


## <a name="expanding-and-collapsing-row-headers"></a>Satır üst bilgilerini genişletme ve daraltma
Satır üst bilgilerini iki yolla genişletebilirsiniz. Bunların ilki sağ tıklatma menüsüdür. Seçtiğiniz belirli bir satır üst bilgisini, düzeyin tamamını veya hiyerarşinin en alt düzeyine kadar olan her şeyi genişletme seçenekleri görürsünüz. Satır üst bilgilerini daraltmanız için de benzer seçenekler sağlanır.

![](media/desktop-matrix-visual/power-bi-expand1.png)

Ayrıca biçimlendirme bölmesi aracılığıyla **Satır üst bilgileri** kartının altında satır üst bilgilerine +/- düğmeleri de ekleyebilirsiniz. Varsayılan olarak simgelerin satır üst bilgisi biçimlendirmesiyle eşleşmesi gerekir ama isterseniz simgelerin renklerini ve boyutlarını ayrıca özelleştirebilirsiniz.

Simgeler açılınca, Excel’deki PivotTable simgelerine benzer şekilde çalışır.

![](media/desktop-matrix-visual/power-bi-expand2.png)

Matrisin genişletme durumu raporunuzla birlikte kaydedilir. Matris, genişletilmiş veya daraltılmış olarak panoya sabitlenebilir. Pano kutucuğu seçildiğinde ve rapor açıldığında, genişletme durumu raporda yine değiştirilebilir. 

![](media/desktop-matrix-visual/power-bi-expand3.png)



## <a name="using-drill-down-with-the-matrix-visual"></a>Matris görseliyle detaya gitme özelliğini kullanma
Matris görseli ile daha önce kullanılabilir olmayan her türlü ilgi çekici detaya gitme etkinliğini gerçekleştirebilirsiniz. Detaya gitme özelliği satırlar, sütunlar ve hatta tek tek bölümler ve hücreler için kullanılabilir. Şimdi bunlardan her birinin nasıl çalıştığına göz atalım.

### <a name="drill-down-on-row-headers"></a>Satır başlıklarında detaya gitme

Görselleştirme bölmesinde, **Alanlar** kutusunun **Satırlar** bölümüne birden çok alan eklediğinizde matris görselinin satırlarında detaya gitme özelliğini etkinleştirmiş olursunuz. Bu, detayına inmenize (ve ardından detaydan çıkmanıza) olanak sağlayacak bir hiyerarşi oluşturup her bir düzeydeki verileri çözümlemeye benzer.

Aşağıdaki görüntüde, **Satırlar** bölümü *Sales stage* ve *Opportunity size* alanlarını içerir ve satırlarda detaylandırabileceğimiz bir gruplandırma (veya hiyerarşi) oluşturur.

![Hangi satırların seçildiğini gösteren Filtreler kartı](media/desktop-matrix-visual/power-bi-rows-matrix.png)

Görsel, **Satırlar** bölümünde oluşturulmuş bir gruplama içeriyorsa sol üst köşesinde *detaya git* ve *genişlet* simgelerini görüntüler.

![detaylandırma denetimlerinin vurgulandığı matris](media/desktop-matrix-visual/power-bi-matrix-drilldown.png)

Tıpkı diğer görsellerdeki detaya gitme ve genişletme davranışında olduğu gibi bu düğmeler seçildiğinde de hiyerarşide detaya gidebilir veya detaydan çıkabilirsiniz. Bu örnekte, aşağıdaki görüntüde gösterilen şekilde bir düzey detaya git simgesini (yaba) seçerek *Sales stage*'den *Opportunity size*'a gidebiliriz.

![yaba simgesinin vurgulandığı matris](media/desktop-matrix-visual/power-bi-matrix-drill3.png)

Bu simgeleri kullanmanın yanı sıra ilgili satır başlıklarını seçip açılan menüden seçiminizi yaparak detaya gitmeyi de tercih edebilirsiniz.

![matristeki satırlar için menü seçenekleri](media/desktop-matrix-visual/power-bi-matrix-menu.png)

Açılan menüde farklı sonuçlar elde etmenizi sağlayan birkaç seçenek bulunmaktadır:

**Detaya Git** seçeneğini belirlediğinizde *ilgili* satır düzeyine yönelik matris genişletilir ve seçilen satır başlığı dışındaki tüm diğer satır başlıkları *dışlanır*. Aşağıdaki resimde **Proposal** > **Detaya Git** seçilmiştir. En üst düzeydeki diğer satırların matriste artık görünmediğine dikkat edin. Bu detaya gitme yöntemi faydalı bir özelliktir ve çapraz vurgulama bölümüne gittiğimizde özellikle kullanışlı hale gelir.

![bir düzey detaya gitmiş matris](media/desktop-matrix-visual/power-bi-drill-down-matrix.png)

**Detaydan çık** simgesini seçerek önceki en üst düzey görünümüne dönün. Ardından **Proposal** > **Sonraki Düzeyi Göster**'i seçtiğinizde, daha üst düzey hiyerarşi kategorileri olmaksızın tüm sonraki düzey öğelerinin (bu örnekteki *Opportunity size* alanı) artan sırada bir listesini görürsünüz.

![Sonraki düzeyi göster'in kullanıldığı matris](media/desktop-matrix-visual/power-bi-next-level-matrix.png)

Matrisin tüm üst düzey kategorileri göstermesi için sol üst köşedeki **Detaydan çık** simgesini seçin, sonra **Proposal** > **Bir sonraki düzeye genişlet**'i seçerek hiyerarşinin her iki düzeyi (*Sales stage* ve *Opportunity size*) için de tüm değerleri görün.

![Bir sonraki düzeye genişlet seçeneğinin kullanıldığı matris](media/desktop-matrix-visual/power-bi-matrix-expand-next.png)

Görüntüde daha fazla denetim sağlamak için **Genişlet** menü öğesini de kullanabilirsiniz.  Örneğin **Proposal** > **Genişlet** > **Seçim**'i seçin. Power BI *Proposal* öğesinin her *Sales stage* alanı ve tüm *Opportunity size* seçenekleri için bir toplam satırı görüntüler.

![Proposal öğesine Genişlet seçeneği uygulandıktan sonra matris](media/desktop-matrix-visual/power-bi-matrix-expand.png)

### <a name="drill-down-on-column-headers"></a>Sütun başlıklarında detaya gitme
Satırlarda detaya gitme özelliğine benzer şekilde sütunlarda da detaya gidebilirsiniz. Aşağıdaki görüntüde, **Sütunlar** alan kutusunda iki alan vardır ve bunlar yukarıda bahsedilen satırlar için kullandığımıza benzer bir hiyerarşi oluşturur. **Sütunlar** alan kutusunda *Region* ve *Segment* alanları bulunuyor. **Sütunlar**'a ikinci alan eklendiği anda görselde yeni bir açılan menü görüntülenir; şu anda **Satırlar** gösterilmektedir.

![İkinci sütun değeri eklendikten sonra matris](media/desktop-matrix-visual/power-bi-matrix-row.png)

Sütunlarda detaya gitmek için, matrisin sol üst köşesinde yer alan **Detaylandır** menüsünden *Sütunlar*'ı seçin. *East* bölgesini seçin ve **Detaya Git**'i seçin.

![sütunlarda detaya gitme menüsü](media/desktop-matrix-visual/power-bi-matrix-column.png)

**Detaya Git**’i seçtiğinizde *Region > East* için sütun hiyerarşisinin sonraki düzeyi (bu örnekte *Opportunity count*) görüntülenir. Diğer bölge gizlidir.

![sütunda tek düzey detaya gidilmiş matris](media/desktop-matrix-visual/power-bi-matrix-column-drill.png)

Menünün diğer öğeleri, sütunlarda da satırlarda olduğu gibi işlev görür. (**Satır başlıklarında detaya gitme** adlı önceki bölüme bakın). Satırlarda yaptığınız gibi sütunlarda da **Sonraki Düzeyi Göster** ve **Bir sonraki düzeye genişlet** seçeneklerini kullanabilirsiniz.

> [!NOTE]
> Matris görselinin sol üstündeki detaya git ve detaydan çık simgeleri, yalnızca satırlar için kullanılabilir. Sütunlarda detaya gitmek için sağ tıklama menüsünü kullanmanız gerekir.

## <a name="stepped-layout-with-matrix-visuals"></a>Matris görselleriyle basamaklı düzen

Matris görseli, bir hiyerarşide her üst öğenin altındaki alt kategorileri otomatik olarak girintiler. Bu işleme basamaklı düzen adı verilir.

Matris görselinin özgün halinde alt kategoriler tamamen farklı bir sütunda gösterilir ve bu durum, görselde daha fazla alan kullanılmasına neden olur. Aşağıdaki görüntüde, özgün matris görselindeki tablo gösterilir. Görüntüde, alt kategorilerin ayrı bir sütunda bulunduğunu görebilirsiniz.

![Alt kategorilerin ayrı sütunda gösterildiği eski Matris görselinin ekran görüntüsü.](media/desktop-matrix-visual/matrix-visual_14.png)

Aşağıdaki görüntü, basamaklı düzen kullanılan bir matris görseli içerir. *Computers* kategorisinin alt kategorilerinin (Computers Accessories, Desktops, Laptops, Monitors vb.) hafif girintili olduğunu ve böylece daha net ve yoğun bir görselin ortaya çıktığını görebilirsiniz.

![matrisin verileri biçimlendirmek için kullandığı geçerli yöntem](media/desktop-matrix-visual/matrix-visual_13.png)

Basamaklı düzen ayarlarını kolayca yapabilirsiniz. Matris görseli seçiliyken, **Görsel Öğeler** bölmesinin **Biçim** bölümünde (boya rulosu simgesi) satır başlıkları bölümünü genişletin. Basamaklı düzen iki durumlu denetimi (bu özelliği etkinleştirir veya devre dışı bırakır) ve basamaklı düzen girintisi (piksel cinsinden girinti miktarını belirler) olmak üzere iki seçeneğiniz bulunur.

![Basamaklı düzen denetiminin görüntülendiği satır üst bilgileri kartı](media/desktop-matrix-visual/power-bi-stepped-matrix.png)

Basamaklı düzen devre dışı bırakılırsa, Power BI alt kategorileri, üst kategori altında girintilemek yerine başka bir sütunda gösterir.

## <a name="subtotals-with-matrix-visuals"></a>Matris görselleri ile alt toplamlar

Hem satırlar hem de sütunlar için matris görsellerindeki alt toplamları etkinleştirebilir veya devre dışı bırakabilirsiniz. Aşağıdaki görüntüde, satır alt toplamlarının **Açık** olarak ayarlandığını görebilirsiniz.

![toplamları ve alt toplamları gösteren matris](media/desktop-matrix-visual/matrix-visual_20.png)

Görsel öğeler bölmesinin biçim bölümündeki **Alt toplamlar** kartını genişletin ve satır alt toplamları kaydırıcısını **Kapalı** olarak ayarlayın. Bunu yaptığınızda alt toplamlar gösterilmez.

![alt toplamların devre dışı bırakıldığı matris](media/desktop-matrix-visual/matrix-visual_21.png)

Aynı işlem sütun alt toplamları için de geçerlidir.

## <a name="cross-highlighting-with-matrix-visuals"></a>Matris görselleri ile çapraz vurgulama

Matris görseliyle matristeki herhangi bir öğeyi, çapraz vurgulamada temel alınacak şekilde seçebilirsiniz. Matriste bir sütun seçtiğinizde, rapor sayfasındaki diğer görsellerde yapıldığı gibi Power BI bu sütunu da vurgular. Bu çapraz vurgulama türü, diğer görseller ve bir veri noktası seçimleri için ortak bir özellik olduğundan artık matris görseli de aynı işlevi sunar.

Ayrıca, çapraz vurgulama için Ctrl+Tıklama seçeneği de kullanılabilir. Örneğin, aşağıdaki görüntüde matris görselindeki bir alt kategori koleksiyonu seçilmiştir. Görseldeki seçili olmayan öğelerin gri renkte göründüğünü ve sayfadaki diğer görsellerin matris görselinde yapılan seçimleri yansıttığını görebilirsiniz.

![Çapraz vurgulama için Ctrl+Tıklama işlevinin gösterildiği matris görseliyle diğer iki görselin ekran görüntüsü.](media/desktop-matrix-visual/matrix-visual_16.png)

## <a name="copying-values-from-power-bi-for-use-in-other-applications"></a>Power BI’daki değerleri diğer uygulamalarda kullanmak üzere kopyalama

Matrisinizde veya tablonuzdaki içeriği başka uygulamalarda kullanmak isteyebilirsiniz: Dynamics CRM, Excel ve diğer Power BI raporları. Power BI’da sağ tıkladığınızda tek bir hücreyi veya birden fazla hücreyi panonuza kopyalayabilirsiniz. Ardından bunları başka bir uygulamaya yapıştırırsınız.


* Tek bir hücrenin değerini kopyalamak için hücreyi seçin, sağ tıklayın ve **Değeri kopyala**’yı seçin. Panonuza kaydedilen biçimlendirilmemiş hücre değerini başka bir uygulamaya yapıştırabilirsiniz.

    ![Bir değere işaret eden bir ok bulunan Matris görselinin yer aldığı ve sağ tıklama menüsünün genişletilip Değer kopyala ve Seçimi kopyala seçeneklerinin öne çıkarıldığı ekran görüntüsü.](media/desktop-matrix-visual/power-bi-cell-copy.png)



* Birden fazla hücreyi kopyalamak için bir hücre aralığını veya CTRL tuşunu basılı tutarak birden fazla hücreyi seçin. 

    ![Öne çıkarılan üç değerden çıkan bir ok bulunan Matris görselinin yer aldığı ve sağ tıklama menüsünün genişletilip Değer kopyala ve Seçimi kopyala seçeneklerinin öne çıkarıldığı ekran görüntüsü.](media/desktop-matrix-visual/power-bi-copy.png)

* Kopyalanan veriler sütun ve satır üst bilgilerini içerecektir.

    ![İçlerine değerler yapıştırılmış Excel satırlarını ve sütunlarını gösteren ekran görüntüsü.](media/desktop-matrix-visual/power-bi-copy-selection.png)

* Görselin yalnızca seçili hücrelerinizi içeren bir kopyasını oluşturmak için CTRL ve sağ tıklamayı kullanarak bir veya daha fazla hücreyi seçip **Görseli kopyala** seçeneğini belirleyin

    ![Görseli kopyala seçeneğini gösteren ekran görüntüsü](media/desktop-matrix-visual/power-bi-copy-visual.png)

* Kopya başka bir matris görselleştirmesi olur, ancak yalnızca sizin kopyalanmış verilerinizi içerir.

    ![Görseli kopyala örneğini gösteren ekran görüntüsü](media/desktop-matrix-visual/power-bi-copy-visual-example.png)

## <a name="setting-a-matrix-value-as-a-custom-url"></a>Matris değerini özel URL olarak ayarlama

Web sitesi URL'leri içeren bir sütununuz veya ölçünüz varsa koşullu biçimlendirmeyi kullanarak bu URL'leri alanlara etkin bağlantılar olarak uygulayabilirsiniz. Bu seçeneği biçimlendirme bölmesindeki **Koşullu biçimlendirme** kartı altında bulabilirsiniz.

![Hangi satırların seçildiğini gösteren Filtreler kartı](media/desktop-matrix-visual/power-bi-web-url.png)

**Web URL’si** ayarını Açık konuma getirin ve sütun için URL olarak kullanılacak alanı seçin. Uygulandığında, bu alanda (sütun) yer alan değerler etkin bağlantılara dönüşür. Bağlantıyı görmek için üzerine gelin ve söz konusu sayfaya atlamak için seçin. 

Daha fazla bilgi için bkz. [Koşullu tablo biçimlendirme](../desktop-conditional-table-formatting.md)

## <a name="shading-and-font-colors-with-matrix-visuals"></a>Matris görselleriyle gölgelendirme ve yazı tipi renkleri
Matris görseliyle, matris içindeki hücrelerin arka planına koşullu biçimlendirme (renkler, gölgelendirme ve veri çubukları) uygulayabilir ve metin ve değerlerde koşullu biçimlendirme gerçekleştirebilirsiniz.

Koşullu biçimlendirme uygulamak için matris görselini seçin ve **Biçim** bölmesini açın. **Koşullu biçimlendirme** kartını genişletin ve **Arka plan rengi**, **Yazı tipi rengi** veya **Veri çubukları** için kaydırıcıyı **Açık** konumuna getirin. Bu seçeneklerden biri etkinleştirildiğinde, koşullu biçimlendirme için renkleri ve değerleri özelleştirmenize olanak sağlayan bir *Gelişmiş denetimler* bağlantısı görüntülenir.
  
  ![Veri çubukları denetiminin gösterildiği Biçim bölmesi](media/desktop-matrix-visual/power-bi-matrix-data-bars.png)

Ayar yapmanızı sağlayan bir iletişim kutusu görüntülemek için *Gelişmiş denetimler*'i seçin. Bu örnekte **Veri çubukları**'nın iletişim kutusu gösterilir.

![Veri çubukları bölmesi](media/desktop-matrix-visual/power-bi-data-bars.png)

## <a name="next-steps"></a>Sonraki adımlar

[Power BI için Power Apps görseli](power-bi-visualization-powerapp.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)