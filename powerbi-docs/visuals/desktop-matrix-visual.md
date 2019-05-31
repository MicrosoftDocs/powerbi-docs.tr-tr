---
title: Power BI’da matris görselini kullanma
description: Matris görselinin Power BI’da basamaklı düzenlere ve ayrıntılı vurgulamaya nasıl olanak sağladığını öğrenin
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 6ad8900e5a95148b3f8333aa1953cc939d56f0e6
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375348"
---
# <a name="use-the-matrix-visual-in-power-bi"></a>Power BI’da Matris görselini kullanma
**Matris** visual benzer bir **tablo**.  2 boyutlu bir tablo destekler ve veri düz, anlamı yinelenen değerler görüntülenir ve değil bir araya getirilir. Matris verileri atayamayacağına arasında birden çok boyutta görüntülemek kolaylaştırır--basamaklı Düzen destekler. Matris otomatik olarak veri toplar ve aşağı ayrıntıya sağlar. 

Matris görselleri oluşturabilirsiniz **Power BI Desktop** ve **Power BI hizmetinde** raporlar ve Matristeki, rapor sayfasındaki diğer görsellerle çapraz vurgulama öğeleri. Örneğin, satırlar, sütunlar ve hatta tek tek hücreleri seçebilir ve çapraz vurgulama. Ayrıca, tek tek hücrelere birden çok hücre seçimleri kopyalanır ve diğer uygulamalara yapıştırıldı. 

![Çapraz vurgulanan matris ve halka grafik](media/desktop-matrix-visual/matrix-visual_2a.png)

Matrisle ilişkili birçok özellik vardır ve bu özellikler, makalenin ilerleyen bölümlerinde ele alınacaktır.


## <a name="understanding-how-power-bi-calculates-totals"></a>Power BI tarafından toplamların nasıl hesaplandığını anlama

**Matris** görselinin nasıl kullanılacağı konusuna geçmeden önce Power BI tarafından tablo ve matrislerdeki toplam ve alt toplam değerlerinin nasıl hesaplandığının anlaşılması önemlidir. Toplam ve alt toplam satırları için yapılan ölçüm, temel verilerdeki tüm satırlarda değerlendirilir; yalnızca görünen veya görüntülenen satırlardaki değerlerin toplanmasından ibaret *değildir*. Bu, toplam satırında beklediğinizden farklı değerler görebileceğiniz anlamına gelir. 

Aşağıdaki matris görselleri göz atın. 

![Tablo ve matris karşılaştırır](media/desktop-matrix-visual/matrix-visual_3.png)

Bu örnekte, matris görselinin sağa görselinin her satırında gösteren *tutarı* her bir satıcı/tarih bileşimi için. Ancak, bir satıcının birden çok tarihte göründüğünden, sayılar birden çok kez yer görünebilir. Bu nedenle, temel verilerden elde edilen doğru toplam ile görünen değerlerin basitçe toplanmasından elde edilen değer eşit değildir. Bu, toplanan değer bir bire çok ilişkinin ‘bir’ tarafı olduğunda yaygın olarak kullanılan bir düzendir.

Toplam ve alt toplam değerlerine bakarken bunların yalnızca görünen değerleri değil temel verileri temel aldığını unutmayın. 

<!-- use Nov blog post video

## Expanding and collapsing row headers
There are two ways you can expand row headers. The first is through the right-click menu. You’ll see options to expand the specific row header you clicked on, the entire level or everything down to the very last level of the hierarchy. You have similar options for collapsing row headers as well.

![](media/desktop-matrix-visual/power-bi-expand1.png)

You can also add +/- buttons to the row headers through the formatting pane under the row headers card. By default, the icons will match the formatting of the row header, but you can customize the icons’ color and size separately if you want. 
Once the icons are turned on, they work similarly to the icons from PivotTables in Excel.

![](media/desktop-matrix-visual/power-bi-expand2.png)

The expansion state of the matrix will save with your report. It can be pinned to dashboards as well, but consumers will need to open up the report to change the state. Conditional formatting will only apply to the inner most visible level of the hierarchy. Note that this expand/collapse experience is not currently supported when connecting to AS servers older than 2016 or MD servers.

![](media/desktop-matrix-visual/power-bi-expand3.png)

Watch the following video to learn more about expand/collapse in the matrix:

-->
## <a name="using-drill-down-with-the-matrix-visual"></a>Matris görseliyle detaya tuşunu kullanarak
Matris görselinin önce kullanılabilir olmayan etkinlikler ilgi çekici detaya her türlü yapabilirsiniz. Detaya gitme özelliği satırlar, sütunlar ve hatta tek tek bölümler ve hücreler için kullanılabilir. Şimdi bunlardan her birinin nasıl çalıştığına göz atalım.

### <a name="drill-down-on-row-headers"></a>Satır başlıklarında detaya gitme
**Görsel Öğeler** bölmesinde, **Alanlar** kutusunun **Satırlar** bölümüne birden çok alan eklediğinizde matris görselinin satırlarında detaya gitme özelliğini etkinleştirmiş olursunuz. Bu, detayına inmenize (ve ardından detaydan çıkmanıza) olanak sağlayacak bir hiyerarşi oluşturup her bir düzeydeki verileri çözümlemeye benzer.

Aşağıdaki görüntüde, **satırları** bölüm içeren *satış aşamasına* ve *fırsat boyutu*, satırlarda detaylandırabileceğimiz bir gruplama (veya hiyerarşi) oluşturma.

![Hangi satır seçildi göstererek filtreleri kartı](media/desktop-matrix-visual/power-bi-rows-matrix.png)

Görsel, **Satırlar** bölümünde oluşturulmuş bir gruplama içeriyorsa sol üst köşesinde *detaya git* ve *genişlet* simgelerini görüntüler.

![özetlenen ayrıntıya denetimlerle Matrisi](media/desktop-matrix-visual/power-bi-matrix-drilldown.png)

Tıpkı diğer görsellerdeki detaya gitme ve genişletme davranışında olduğu gibi bu düğmeler seçildiğinde de hiyerarşide detaya gidebilir veya detaydan çıkabilirsiniz. Bu durumda, biz gelen detaya gidebilirsiniz *satış aşamasına* için *fırsat boyutu*burada bir düzey simgesini (yaba seçerek) detaya seçilmiş aşağıdaki görüntüde gösterildiği gibi.

![özetlenen yaba seçerek Matrisi](media/desktop-matrix-visual/power-bi-matrix-drill3.png)

Bu simgeleri kullanmanın yanı sıra ilgili satır başlıklarına birini seçin ve görünen menüden seçim yaparak detaya.

![Matris satır için menü seçenekleri](media/desktop-matrix-visual/power-bi-matrix-menu.png)

Açılan menüde farklı sonuçlar elde etmenizi sağlayan birkaç seçenek bulunmaktadır:

Seçme **detaya** yönelik matris genişletilir *,* satır düzeyine *hariç* tüm diğer satır başlıkları hariç seçili satır üst bilgisi. Aşağıdaki görüntüde, **teklif** > **detaya** seçilmedi. En üst düzeydeki diğer satırların matriste artık görünmediğine dikkat edin. Bu detaya gitme yöntemi faydalı bir özelliktir ve **çapraz vurgulama** bölümüne gittiğimizde özellikle kullanışlı hale gelir.

![bir düzey aşağıya sıralandığında Matrisi](media/desktop-matrix-visual/power-bi-drill-down-matrix.png)

Seçin **Detaydan** simgesine tıklayarak önceki en üst düzey görünümüne dönebilirsiniz. Ardından seçerseniz **teklif** > **sonraki düzeyi Göster**, tüm sonraki düzey öğelerinin artan bir listesini alın (Bu durumda, *fırsat boyutu* alan), üst düzey hiyerarşi kategori.

![sonraki düzeyi Göster kullanarak Matrisi](media/desktop-matrix-visual/power-bi-next-level-matrix.png)

Seçin **Detaydan** matrisin tüm en üst düzey kategorilerini ardından select göstermek için sol üst köşedeki simgeyi **teklif** > **sonraki düzeye Genişlet**, Her iki - hiyerarşi düzeyleri için tüm değerleri görmek *satış aşamasına* ve *fırsat boyutu*.

![sonraki düzeyi Genişlet kullanarak Matrisi](media/desktop-matrix-visual/power-bi-matrix-expand-next.png)

Ayrıca **genişletme** görüntüyü daha fazla denetlemek için menü öğesi.  Örneğin, **teklif** > **genişletme** > **seçimi**. Power BI için her bir toplam satır görüntüler *satış aşamasına* ve tüm *fırsat boyutu* seçenekleri *teklif*.

![Matris sonra teklifine uygulanan Genişlet](media/desktop-matrix-visual/power-bi-matrix-expand.png)

### <a name="drill-down-on-column-headers"></a>Sütun başlıklarında detaya gitme
Benzer şekilde satırlarda detaya gitme olanağı, siz de detaya gidebilirsiniz **sütunları**. Aşağıdaki görüntüde, iki alan vardır **sütunları** alan kutusunda, bu makalenin önceki kısımlarında satırlar için kullandığımız için benzer bir hiyerarşi oluşturma. İçinde **sütunları** alan, sahip olduğumuz *bölge* ve *Segment*. İkinci alan eklenmişse hemen sonra **sütunları**, şu anda bu görselde görüntülenen yeni bir açılan menü gösterir **satırları**.

![Eklenen ikinci sütun değeri sonra Matrisi](media/desktop-matrix-visual/power-bi-matrix-row.png)

Sütunlarda detaya gitmek için seçin **sütunları** gelen *detaylandır* matris sol alt köşesinde bulunan menü. Seçin *Doğu* bölge ve **detaya**.

![sütunlarda detaya gitmek için menü](media/desktop-matrix-visual/power-bi-matrix-column.png)

Seçtiğinizde, **detaya**, için sütun hiyerarşisinin sonraki düzeyi *bölge > Doğu* görüntülendiğinde, bu durumda *fırsat sayısı*. Başka bir bölgede görüntüler, ancak devre dışı.

![Sütu sunulmakta bir düzey detaya gidin](media/desktop-matrix-visual/power-bi-matrix-column-drill.png)

Menü öğeleri, sütunlarda satırlarda aynı şekilde (önceki bölüme bakın **satır başlıklarında detaya**). Yapabilecekleriniz **sonraki düzeyi Göster** ve **sonraki düzeye Genişlet** sütunlarla satırları ile yapabilecekleriniz gibi.

> [!NOTE]
> Matris görselinin sol üstündeki detaya git ve detaydan çık simgeleri, yalnızca satırlar için kullanılabilir. Sütunlarda detaya gitmek için sağ tıklama menüsünü kullanmanız gerekir.
> 
> 

## <a name="stepped-layout-with-matrix-visuals"></a>Matris görselleriyle basamaklı düzen
**Matris** görseli, bir hiyerarşide her bir üst öğenin altındaki alt kategorileri otomatik olarak girintiler ve bu işleme **Basamaklı düzen** adı verilir.

Matris görselinin *özgün* halinde alt kategoriler tamamen farklı bir sütunda gösterilir ve bu durum, görselde daha fazla alan kullanılmasına neden olur. Aşağıdaki görüntüde, özgün **Matris** görselindeki tablo gösterilmektedir; buradan alt kategorilerin ayrı bir sütunda bulunduğunu görebilirsiniz.

![matrisler için varsayılan biçimi eski yöntem](media/desktop-matrix-visual/matrix-visual_14.png)

Aşağıdaki görüntü, **Basamaklı düzen** kullanılan bir **Matris** görseli içermektedir. *Computers* kategorisinin alt kategorilerinin (Computers Accessories, Desktops, Laptops, Monitors vb.) hafif girintili olduğunu ve böylece daha net ve yoğun bir görselin ortaya çıktığını görebilirsiniz.

![Geçerli yolu, matris veri biçimleri](media/desktop-matrix-visual/matrix-visual_13.png)

Basamaklı düzen ayarlarını kolayca yapabilirsiniz. **Matris** görseli seçiliyken **Görsel Öğeler** bölmesinin **Biçim** bölümündeki (boya rulosu simgesi) **Satır başlıkları** bölümünü genişletin. İki seçeneğiniz vardır: **Basamaklı düzen** açma/kapatma kaydırıcısı (bu özelliği etkinleştirir veya devre dışı bırakır) ve **Basamaklı düzen girintisi** (piksel cinsinden girinti miktarını belirler).

![Satır üst bilgileri kartı basamaklı düzen denetimi görüntüleme](media/desktop-matrix-visual/power-bi-stepped-matrix.png)

**Basamaklı düzen**'i devre dışı bırakırsanız alt kategoriler, üst kategori altında girintilenmez ve bunun yerine başka bir sütunda gösterilir.

## <a name="subtotals-with-matrix-visuals"></a>Matris görselleri ile alt toplamlar
Hem satırlar hem de sütunlar için matris görsellerindeki alt toplamları etkinleştirebilir veya devre dışı bırakabilirsiniz. Aşağıdaki görüntüde, satır alt toplamlarının **açık** olarak belirlendiğini görebilirsiniz.

![Matris gösteren toplamlar ve alt toplamlar](media/desktop-matrix-visual/matrix-visual_20.png)

**Görsel Öğeler** bölmesinin **Biçim** bölümündeki **Alt toplamlar** kartını genişletin ve **Satır alt toplamları** kaydırıcısını **Kapalı** olarak ayarlayın. Bunu yaptığınızda alt toplamlar gösterilmez.

![Kapalı toplamları Matrisi](media/desktop-matrix-visual/matrix-visual_21.png)

Aynı işlem sütun alt toplamları için de geçerlidir.

## <a name="cross-highlighting-with-matrix-visuals"></a>Matris görselleri ile çapraz vurgulama
**Matris** görseliyle matristeki herhangi bir öğeyi, çapraz vurgulamada temel alınacak şekilde seçebilirsiniz. **Matriste** bir sütun seçtiğinizde, rapor sayfasındaki diğer görsellerde olduğu gibi bu sütun da vurgulanır. Bu çapraz vurgulama türü, diğer görseller ve bir veri noktası seçimleri için ortak bir özellik olduğundan artık **Matris** görseli de aynı işlevi sunar.

Ayrıca, çapraz vurgulama için Ctrl+Tıklama seçeneği de kullanılabilir. Örneğin, aşağıdaki görüntüde **Matris** görselindeki bir alt kategori koleksiyonu seçilmiştir. Görseldeki seçili olmayan öğelerin gri renkte göründüğünü ve sayfadaki diğer görsellerin, **Matris** görselinde yapılan seçimleri yansıttığını görebilirsiniz.

![Rapor sayfasında bir matris tarafından highighted çapraz](media/desktop-matrix-visual/matrix-visual_16.png)

## <a name="copying-values-from-power-bi-for-use-in-other-applications"></a>Power BI’daki değerleri diğer uygulamalarda kullanmak üzere kopyalama

Matrisinizde veya tablonuzda Dynamics CRM ve Excel gibi farklı uygulamalarda ve hatta diğer Power BI raporlarında kullanmak istediğiniz içerik bulunabilir. Power BI’da sağ tıkladığınızda tek bir hücreyi veya birden fazla hücreyi panonuza kopyalayabilir, daha sonra diğer uygulamaya yapıştırabilirsiniz.

![kopyalama seçenekleri](media/desktop-matrix-visual/power-bi-cell-copy.png)

* Tek bir hücrenin değerini kopyalamak için hücreyi seçin, sağ tıklayın ve **Değeri kopyala**’yı seçin. Panonuza kaydedilen biçimlendirilmemiş hücre değerini başka bir uygulamaya yapıştırabilirsiniz.

    ![kopyalama seçenekleri](media/desktop-matrix-visual/power-bi-copy.png)

* Birden fazla hücreyi kopyalamak için bir hücre aralığını veya CTRL tuşunu basılı tutarak birden fazla hücreyi seçin. Kopyalanan veriler sütun ve satır üst bilgilerini içerecektir.

    ![Excel’e yapıştırma](media/desktop-matrix-visual/power-bi-copy-selection.png)

## <a name="shading-and-font-colors-with-matrix-visuals"></a>Matris görselleriyle gölgelendirme ve yazı tipi renkleri
Matris görselinin uyguladığınız **koşullu biçimlendirme** (renkler ve gölgelendirme ve veri çubukları) matris içindeki hücrelerin arka planına metin ve değerlerde de koşullu biçimlendirme uygulayabilirsiniz.

Koşullu biçimlendirme uygulamak için görsel ve açık matris seçin **biçimi** bölmesi. Genişletin **koşullu biçimlendirme** kart ve **arka plan rengi**, **yazı tipi rengi**, veya **veri çubukları**, içinkaydırıcıyı**Üzerinde**. Bu seçeneklerden birini açma bağlantısı görüntülenir *gelişmiş denetimler*, olanak sağlayan renkleri ve renk biçimlendirme için değerleri özelleştirin.
  
  ![Veri çubukları denetimi gösteren biçimi bölmesi](media/desktop-matrix-visual/power-bi-matrix-data-bars.png)

Seçin *gelişmiş denetimler* , ayar yapmanıza olanak sağlayan bir iletişim kutusunu görüntüleyin. Bu örnek, iletişim kutusu için gösterir **veri çubukları**.

![Veri çubukları bölmesi](media/desktop-matrix-visual/power-bi-data-bars.png)

## <a name="next-steps"></a>Sonraki adımlar

[Power BI'daki dağılım ve kabarcık grafikleri](power-bi-visualization-scatter.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)