---
title: Power BI'da ESRI tarafından sunulan ArcGIS haritalarını oluşturma
description: "Power BI'da ESRI tarafından sunulan ArcGIS haritalarını oluşturma "
author: mihart
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: EKVvOZmxg9s
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 02/28/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 85bf9630a8c272b513f27f38b24a5d8a77075444
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37599632"
---
# <a name="arcgis-maps-in-power-bi-service-and-power-bi-desktop-by-esri"></a>Power BI hizmetinde ve Power BI Desktop'ta Esri tarafından sunulan ArcGIS haritaları
Bu eğitim içeriği, ArcGIS haritası oluşturan bir kişinin bakış açısından yazılmıştır. ArcGIS haritasını oluşturan kişi haritayı bir iş arkadaşıyla paylaştıktan sonra, iş arkadaşı haritayı görüntüleyebilir ve haritayla etkileşim kurabilir, ancak değişiklikleri kaydedemez. ArcGIS haritalarını görüntüleme hakkında daha fazla bilgi için bkz. [ArcGIS haritaları ile etkileşim kurma](power-bi-visualizations-arcgis.md).

ArcGIS haritaları ile Power BI birlikte kullanıldığında eşleme deneyimi, haritada belirli noktaları göstermenin ötesinde yepyeni bir boyut kazanıyor. Harika, bilgilendirici harita görselleştirmeleri oluşturmak için altlık haritalar, konum türleri, temalar, sembol stilleri ve başvuru katmanları arasından seçiminizi yapın. Haritalarda yetkilendirmeli veri katmanlarıyla uzamsal çözümlemenin bir arada kullanılması, görselleştirmenizdeki verilerin daha kapsamlı şekilde anlaşılmasını sağlar.

 Mobil cihazlarda ArcGIS haritaları oluşturamazsınız ancak haritaları görüntüleyebilir ve bunlarla etkileşim kurabilirsiniz. Bkz. [ArcGIS haritaları ile etkileşim kurma](power-bi-visualizations-arcgis.md).

> [!TIP]
> GIS, Coğrafi Bilgi Bilimi anlamına gelir.


Aşağıdaki örnekte, 2016 yılına ait ortanca harcanabilir gelir demografik katmanındaki bölgesel satışların yoğunluk haritası yoluyla gösterilmesi için koyu gri bir tuval kullanılmıştır. Okumaya devam ettikçe fark edeceğiniz üzere, ArcGIS haritalarını kullandığınızda hikayenizi en iyi şekilde anlatabilmeniz için neredeyse sınırsız sayıda gelişmiş eşleme özelliği, demografik veriler ve çok daha ilgili çekici harita görselleştirmeleri elde edersiniz.

![](media/power-bi-visualization-arcgis/power-bi-intro-arcgis.png)

> [!TIP]
> Birçok örneğe göz atmak ve referansları okumak için [Esri'nin Power BI sayfasını](https://www.esri.com/powerbi) ziyaret edin. Ardından Esri'nin [ArcGIS Maps for Power BI ile Çalışmaya Başlama sayfasına](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm) bakın.

## <a name="user-consent"></a>Kullanıcı onayı
ArcGIS Maps for Power BI, Esri (www.esri.com) tarafından sağlanmaktadır. ArcGIS Maps for Power BI kullanımınız Esri'nin koşullarına ve gizlilik ilkesine tabidir. ArcGIS Maps for Power BI görsellerini kullanmak isteyen Power BI kullanıcılarının, onay iletişim kutusunu kabul etmesi gerekir.

**Kaynaklar**

[Koşullar](https://go.microsoft.com/fwlink/?LinkID=826322)

[Gizlilik İlkesi](https://go.microsoft.com/fwlink/?LinkID=826323)

[ArcGIS Maps for Power BI ürün sayfası](https://www.esri.com/powerbi)

<br/>

## <a name="enable-arcgis-map"></a>ArcGIS haritasını etkinleştirme
ArcGIS haritaları şu anda Power BI hizmetinde, Power BI Desktop'ta ve Power BI mobil uygulamalarında kullanılabilir. Bu makalede hizmet ve Desktop için yönergeler sunulmaktadır.

### <a name="enable-the-arcgis-map-in-power-bi-service-apppowerbicom"></a>***Power BI hizmetinde (app.powerbi.com)*** ArcGIS haritasını etkinleştirme
Bu eğitimde [Perakende Analizi örneği](sample-retail-analysis.md) kullanılmıştır. **ArcGIS Maps for Power BI**'ı etkinleştirmek için:

1. Menü çubuğunun sağ üst kısmındaki dişli simgesini seçin ve **Ayarlar**'ı açın
   
    ![](media/power-bi-visualization-arcgis/power-bi-settings.png)
2. **ArcGIS Maps for Power BI**  onay kutusunu seçin. Seçiminizi yaptıktan sonra Power BI'ı yeniden başlatmanız gerekir.
   
    ![](media/power-bi-visualization-arcgis/power-bi-use-arcgis-new.png)
3. Bir raporu [Düzenleme görünümü](service-reading-view-and-editing-view.md)'nde açın ve Görsel Öğeler bölmesinde ArcGIS Maps for Power BI simgesini seçin.
   
    ![](media/power-bi-visualization-arcgis/power-bi-viz-pane2.png)
4. Power BI, rapor tuvaline boş bir ArcGIS harita şablonu ekler.
   
   ![](media/power-bi-visualization-arcgis/power-bi-esri-placeholder2new.png)

<br/>

## <a name="create-an-arcgis-map-visual"></a>ArcGIS harita görseli oluşturma
Will'in birkaç ArcGIS harita görselleştirmesi oluşturduğu videoyu izledikten sonra [Perakende Analizi örneğini](sample-datasets.md) kullanarak kendiniz denemek için aşağıdaki adımları uygulayın.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EKVvOZmxg9s" frameborder="0" allowfullscreen></iframe>

1. **Alanlar** bölmesinden **Konum**, **Enlem** ve/veya **Boylam** demetlerine bir veri alanı sürükleyin. Biz bu örnekte **Store > City** seçeneğini kullanıyoruz.
   
   > [!NOTE]
   > ArcGIS Maps for Power BI, seçtiğiniz alanların haritada şekil mi yoksa nokta olarak mı en iyi şekilde görüntüleneceğini otomatik olarak algılar. Ayarlar bölümünde, varsayılan seçimi belirleyebilirsiniz. (Aşağıya bakın.)
   > 
   > 
   
    ![](media/power-bi-visualization-arcgis/power-bi-fields-pane3new.png)
2. Görsel Öğeler bölmesinde şablonu ![](media/power-bi-visualization-arcgis/power-bi-arcgis-template.png) seçerek görselleştirmeyi bir ArcGIS haritasına dönüştürün.
3. Verilerin gösterilme biçimini ayarlamak için **Alanlar** bölmesinden bir ölçüyü **Boyut** demetine sürükleyin. Biz bu örnekte **Sales > Last Year Sales** seçeneğini kullanıyoruz.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-point-map-size2new.png)

## <a name="settings-and-formatting-for-arcgis-maps"></a>ArcGIS haritaları için ayarlar ve biçimlendirme
**ArcGIS Maps for Power BI** biçimlendirme özelliklerine erişmek için:

1. Görselleştirmenin sağ üst köşesindeki üç nokta simgesini seçip **Düzenle** seçeneğini belirleyerek ek özelliklere erişin.
   
   ![](media/power-bi-visualization-arcgis/power-bi-edit2.png)
   
   Kullanılabilir özellikler, görselleştirmenin üst kısmında görüntülenir. Her bir özellik seçildiğinde, ayrıntılı seçeneklerin sunulduğu bir görev bölmesi açılır.<br/>
   
   ![](media/power-bi-visualization-arcgis/power-bi-esri-features-new.png)
   
   > [!NOTE]
   > Ayarlar ve özellikler hakkında daha fazla bilgi için aşağıdaki **Ayrıntılı belgeler** bölümüne bakın.
   > 
   > 
2. Rapora geri dönmek için rapor tuvalinizin sol üst köşesindeki **Rapora Geri Dön** seçeneğini belirleyin.

<br/>

## <a name="detailed-documentation"></a>Ayrıntılı belgeler
**Esri**, **ArcGIS Maps for Power BI**'ın özellikleri hakkında [kapsamlı belgeler](https://go.microsoft.com/fwlink/?LinkID=828772) sağlamaktadır.

## <a name="features-overview"></a>Özelliklere genel bakış
### <a name="base-maps"></a>Altlık Harita
Dört altlık harita sağlanmıştır: Koyu Gri Kanvas, Açık Gri Kanvas, OpenStreetMap ve Sokaklar.  Sokaklar, ArcGIS'in standart altlık haritasıdır.

Bir altlık haritayı uygulamak için görev bölmesinde haritayı seçin.

![](media/power-bi-visualization-arcgis/power-bi-esri-base-maps-new.png)

### <a name="location-type"></a>Konum türü
ArgGIS Maps for Power BI, verilerin haritada en iyi şekilde nasıl görüntüleneceğini otomatik olarak algılar. Noktalar veya Sınırlar seçeneğini belirler. Konum türü seçenekleri, bu seçimlere yönelik ince ayarlar yapmanızı sağlar.

![](media/power-bi-visualization-arcgis/power-bi-esri-location-types-new.png)

**Sınırlar**, yalnızca verileriniz standart coğrafi değerler içerdiğinde işe yarar. Esri, haritada gösterilecek şekli otomatik olarak belirler. Standart coğrafi değerlere ülkeler, iller, posta kodları vb. dahildir. Ancak, Coğrafi Kodlamada olduğu gibi Power BI da alanın varsayılan olarak sınır olması gerektiğini algılamayabilir veya verileriniz için bir sınıra sahip olmayabilir.  

### <a name="map-theme"></a>Harita teması
Dört harita teması sağlanmıştır. Yalnızca Konum ve Boyut temaları, Power BI'daki Alanlar bölmesinde konumla bağlantılı hale getirdiğiniz ve **Boyut** demetine eklediğiniz alanlara göre otomatik olarak seçilir. Şu anda **Boyut**'u kullanıyoruz ancak bunu **Yoğunluk Haritası** ile değiştirelim.  

![](media/power-bi-visualization-arcgis/power-bi-esri-map-theme-new.png)

<table>
<tr><th>Tema</th><th>Açıklama</th>
<tr>
<td>Yalnızca Konum</td>
<td>Konum Türü ayarlarına göre harita üzerinde veri noktaları veya doldurulmuş sınırlar çizer.</td>
</tr>
<tr>
<td>Yoğunluk Haritası</td>
<td>Verilere ilişkin bir yoğunluk haritası çizer.</td>
</tr>
<tr>
<td>Boyut</td>
<td>Harita üzerinde, Alanlar bölmesindeki Boyut demetinde bulunan değere göre boyutlandırılan veri noktalarını çizer.</td>
</tr>
<tr>
<td>Kümeleniyor</td>
<td>Harita üzerinde, bölgelerdeki veri noktası sayısını gösterir. </td>
</tr>
</table>


### <a name="symbol-style"></a>Sembol stili
Sembol stilleri, verilerin haritada nasıl gösterildiğine ilişkin ince ayarlar yapmanızı sağlar. Sembol stilleri, seçilen Konum türü ve Harita temasına bağlı ve bağlama duyarlıdır. Aşağıdaki örnekte, Konum türü **Boyut** olarak ayarlanmış bir haritada şeffaflık, stil ve boyut ile ilgili olarak yapılan birkaç ayarlama işlemi gösterilmektedir.

![](media/power-bi-visualization-arcgis/power-bi-esri-symbol-style-new.png)

### <a name="pins"></a>Raptiye
Raptiye ekleyerek haritanızdaki noktalara dikkat çekin.  

1. **Raptiye** sekmesini seçin.
2. Arama kutusuna anahtar sözcükler (adresler, yerler ve ilgi çekici noktalar gibi) yazın ve açılan menüden seçim yapın. Harita üzerinde bir sembol görüntülenir ve konum otomatik olarak yakınlaştırılır. Arama sonuçları, Raptiye bölmesinde konum kartları olarak kaydedilir. En fazla 10 konum kartı kaydedebilirsiniz.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin-arcgis-newer.png)
3. Power BI ilgili konum için bir raptiye ekler ve raptiyenin rengini değiştirebilirsiniz.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin-color-new.png)
4. Raptiye ekleyin ve silin.
   
   ![](media/power-bi-visualization-arcgis/power-bi-pin3.png)

### <a name="drive-time"></a>Sürüş zamanı
Sürüş zamanı bölmesi, bir konum seçmenize ve belirtilen bir yarıçap veya sürüş süresi için diğer harita özelliklerini belirlemenize olanak sağlar.  
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time.png)

1. **Sürüş zamanı** sekmesini seçin ve ardından, tekli veya çoklu seçim aracını belirleyin. Tekli seçim aracını kullanarak Washington D.C. üzerinde bulunan raptiyeyi seçin.
    ![](media/power-bi-visualization-arcgis/power-bi-esri-single-select.png)
   
   > [!TIP]
   > Harita üzerinde yakınlaştırma yapıldığında (+ simgesi ile) konum seçmek daha kolay hale gelir.
   > 
   > 
2. Birkaç günlüğüne Washington'a gideceğinizi ve hangi mağazaların makul bir sürüş mesafesinde olduğunu hesaplamak istediğinizi varsayalım. Arama alanını **Yarıçap** ve Mesafeyi **50** mil olarak değiştirin ve Tamam'ı seçin.    
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time-radius.png)
3. Yarıçap mor renkle gösterilir. Ayrıntılarını görüntülemek için herhangi bir konumu seçin. İsterseniz rengi ve ana hat ayarlarını değiştirerek yarıçapı biçimlendirebilirsiniz.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-drive-time.png)

### <a name="reference-layer"></a>Referans Katmanı
#### <a name="reference-layer---demographics"></a>Referans katmanı - Nüfus Bilgileri
ArcGIS Maps for Power BI, nüfus bilgilerine ilişkin katmanlar sunarak Power BI'daki verilerin bağlama göre ele alınmasına yardımcı olur.

1. **Referans katmanı** sekmesini ve **Nüfus Bilgileri**'ni seçin.
2. Listelenen her katmanda bir onay kutusu bulunur. Katmanı haritaya eklemek için bir onay işareti ekleyin.  Bu örnekte Average Household Income katmanını ekledik.<br/>
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-reference-layer-demographic.png)
3. Her katman aynı zamanda etkileşimlidir. Ayrıntıları görmek için bir balonun üzerine gelebileceğiniz gibi, harita üzerindeki gölgeli bir alana da tıklayabilirsiniz.<br/>
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-reference-layer-details.png)

#### <a name="reference-layer---arcgis"></a>Referans katmanı - ArcGIS
ArcGIS Online, kuruluşların genel web haritaları yayımlamasına olanak sağlar. Ayrıca Esri, Living Atlas üzerinden bir web haritaları seçkisi sunar. ArcGIS sekmesinde, genel kullanıma sunulan tüm web haritalarını veya Living Atlas haritalarını arayabilir ve bunları referans katmanları olarak haritaya ekleyebilirsiniz.

1. **Referans katmanı** sekmesini seçtikten sonra **ArcGIS** seçeneğini belirleyin.
2. Arama terimleri girin ve ardından bir harita katmanını seçin. Bu örnekte USA Congressional Districts katmanını seçtik.
   
    ![](media/power-bi-visualization-arcgis/power-bi-esri-demographics-esri2-new.png)
3. Ayrıntıları görmek için *Referans katmanından seçin* seçeneğini açmak üzere gölgeli bir alanı seçin: Referans katmanındaki sınırları veya nesneleri seçmek için referans katmanı seçim aracını kullanın.

<br/>

## <a name="selecting-data-points"></a>Veri noktalarını seçme
ArcGIS Maps for Power BI üç seçim modu sunar.

Anahtarları kullanarak seçim modunu değiştirin:

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-tools2.png)

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-single2.png) Tek veri noktalarını seçer.

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-marquee2.png) Harita üzerinde bir dikdörtgen çizer ve içerdiği veri noktalarını seçer.

![](media/power-bi-visualization-arcgis/power-bi-esri-selection-reference-layer2.png) Referans katmanlarındaki sınırların veya çokgenlerin, kapsanan veri noktalarının seçilmesi için kullanılmasına olanak sağlar.

> [!NOTE]
> Aynı anda en fazla 250 veri noktası seçilebilir.
> 
> 

<br/>

## <a name="getting-help"></a>Yardım alma
**Esri**, **ArcGIS Maps for Power BI**'ın özellikleri hakkında [kapsamlı belgeler](https://go.microsoft.com/fwlink/?LinkID=828772) sağlamaktadır.

Power BI [topluluğunun **ArcGIS Maps for Power BI**'a yönelik tartışma sayfasında](https://go.microsoft.com/fwlink/?LinkID=828771) soru sorabilir, en güncel bilgilere ulaşabilir, sorunları bildirebilir ve sorularınıza cevap bulabilirsiniz.

İyileştirme önerileriniz varsa lütfen [Power BI Ideas listesinde](https://ideas.powerbi.com) paylaşın.

<br/>

## <a name="managing-use-of-arcgis-maps-for-power-bi-within-your-organization"></a>Kuruluşunuzda ArcGIS Maps for Power BI kullanımını yönetme
Power BI kullanıcılara, kiracı yöneticilerine ve BT yöneticilerine ArcGIS Maps for Power BI'ın kullanılıp kullanılmayacağını belirleme olanağı sunar.

**Kullanıcı seçenekleri** Power BI Desktop'ta kullanıcılar, ArcGIS Maps for Power BI'ı **Seçenekler**'deki güvenlik sekmesinden devre dışı bırakarak kullanmayı bırakabilir. ArcGIS Haritaları devre dışı bırakıldığında varsayılan olarak yüklenmez.

![](media/power-bi-visualization-arcgis/power-bi-desktop-security-dialog2.png)

Power BI hizmetinde kullanıcılar, ArcGIS Maps for Power BI'ı Ayarlar sayfasındaki ArcGIS Maps for Power BI sekmesinden devre dışı bırakarak kullanmayı bırakabilir. ArcGIS Haritaları devre dışı bırakıldığında varsayılan olarak yüklenmez.

![](media/power-bi-visualization-arcgis/power-bi-use-arcgis-new.png)

**Kiracı yöneticisi seçenekleri** PowerBI.com'da kiracı yöneticileri, ArcGIS Maps for Power BI'ı devre dışı bırakarak kiracıdaki tüm kullanıcılar tarafından kullanılmasını önleyebilir. Bu işlemin ardından, Power BI'daki Görsel Öğeler bölmesinde artık ArcGIS Maps for Power BI simgesi görünmez.

![](media/power-bi-visualization-arcgis/power-bi-arcgis-admin-portal2.png)

**BT Yöneticisi seçenekleri** Power BI Desktop, bir kuruluşta dağıtılan bilgisayarlar genelinde ArcGIS Maps for Power BI'ı devre dışı bırakma amacıyla **Grup İlkesi** kullanımını destekler.

<table>
<tr><th>Öznitelik</th><th>Değer</th>
</tr>
<tr>
<td>key</td>
<td>Software\Policies\Microsoft\Power BI Desktop&lt;/td&gt;
</tr>
<tr>
<td>valueName</td>
<td>EnableArcGISMaps</td>
</tr>
</table>

1 (ondalık) değeri, ArcGIS Maps for Power BI'ı etkinleştirir.

0 (ondalık) değeri, ArcGIS Maps for Power BI'ı devre dışı bırakır.

## <a name="considerations-and-limitations"></a>Önemli Noktalar ve Sınırlamalar
ArcGIS Maps for Power BI aşağıdaki hizmetlerde ve uygulamalarda kullanılabilir:

<table>
<tr><th>Hizmet/Uygulama</th><th>Kullanılabilirlik</th></tr>
<tr>
<td>Power BI Desktop</td>
<td>Evet</td>
</tr>
<tr>
<td>Power BI hizmeti (PowerBI.com)</td>
<td>Evet</td>
</tr>
<tr>
<td>Power BI mobil uygulamaları</td>
<td>Evet</td>
</tr>
<tr>
<td>Power BI - web'de yayımlama</td>
<td>Hayır</td>
</tr>
<tr>
<td>Power BI Embedded</td>
<td>Hayır</td>
</tr>
<tr>
<td>Power BI hizmeti - ekleme (PowerBI.com)</td>
<td>Hayır</td>
</tr>
</table>

ArcGIS Maps for Power BI'ın kullanılamadığı hizmet veya uygulamalarda ilgili görselleştirme, Power BI logosu içeren boş bir görsel olarak gösterilir.

Adres bilgileri için coğrafi kodlama yapılırken yalnızca ilk 1500 adresin coğrafi kodlaması yapılır. Yer adlarına veya ülkelere yönelik coğrafi kodlama, 1500 adres sınırına tabi değildir.

<br/>

**ArcGIS Maps for Power BI birlikte nasıl çalışır?**
ArcGIS Maps for Power BI, Esri (www.esri.com) tarafından sağlanmaktadır. ArcGIS Maps for Power BI kullanımınız Esri'nin [koşullarına](https://go.microsoft.com/fwlink/?LinkID=8263222) ve [gizlilik ilkesine](https://go.microsoft.com/fwlink/?LinkID=826323) tabidir. ArcGIS Maps for Power BI görsellerini kullanmak isteyen Power BI kullanıcılarının, onay iletişim kutusunu kabul etmesi gerekir (ayrıntılı bilgi için bkz. Kullanıcı Onayı).  Esri tarafından sağlanan ArcGIS Maps for Power BI’ın kullanımı, Esri’nin Koşullarına ve Gizlilik İlkesine tabidir. Bunların bağlantıları, onay iletişim kutusunda da belirtilir. Her kullanıcı ArcGIS Maps for Power BI’ı ilk kez kullanmadan önce onay vermelidir. Kullanıcı, onayı kabul ettikten sonra görsele bağlı veriler en azından coğrafi kodlama (konum bilgilerini bir haritada gösterilebilen enlem ve boylam bilgilerine dönüştürme) için Esri’nin hizmetlerine gönderilir. Veri görselleştirmesine bağlı tüm verilerin Esri’nin hizmetlerine gönderilebildiğini varsaymanız gerekir. Esri; altlık haritalar, uzamsal analiz ve coğrafi kodlama gibi hizmetler sunar. ArcGIS Maps for Power BI görseli, sağlanan bir sertifika ile korunan ve Esri tarafından bakımı yapılan bir SSL bağlantısını kullanarak bu hizmetlerle etkileşime geçer. ArcGIS Maps for Power BI hakkında ek bilgilere Esri’nin [ArcGIS Maps for Power BI ürün sayfasından](https://www.esri.com/powerbi) ulaşılabilir.

Bir kullanıcı, ArcGIS Maps for Power BI aracılığıyla Esri tarafından sunulan bir Plus aboneliğine kaydolduğunda Esri ile doğrudan bir ilişki içine girer. Power BI, Esri’ye kullanıcı hakkındaki kişisel bilgileri göndermez. Kullanıcı, kendi AAD kimliğini kullanarak, Esri tarafından sağlanan bir AAD uygulamasında oturum açar ve bu uygulamaya güvenir. Kullanıcı bunu yaparak kendi kişisel bilgilerini doğrudan Esri ile paylaşmış olur. Kullanıcı, bir ArcGIS Maps for Power BI görseline Plus içeriği ekledikten sonra diğer Power BI kullanıcılarının da söz konusu içeriği görüntülemek veya düzenlemek için Esri’nin Plus aboneliğine ihtiyaç duyar. 

Esri tarafından sağlanan ArcGIS Maps for Power BI’ın nasıl çalıştığıyla ilgili teknik ayrıntılar içeren sorular için Esri’ye destek sitesi üzerinden ulaşın.


**ArcGIS Maps for Power BI kullanımı için herhangi bir ücret ödenir mi?**

Tüm Power BI kullanıcıları, ArcGIS Maps for Power BI'ı hiçbir ek ücret ödemeden kullanılabilir. Bu, **Esri** tarafından sağlanan bir bileşendir ve bu makalede daha önce belirtildiği üzere, kullanımınız **Esri** tarafından sağlanan koşullara ve gizlilik ilkesine tabidir.

**Power BI Desktop'ta önbelleğimin dolu olduğu hakkında bir hata iletisi alıyorum**

Bu hata üzerinde çalışılmaktadır.  Bu arada, önbelleğinizi temizlemek için lütfen C:\Users\\AppData\Local\Microsoft\Power BI Desktop\CEF konumundaki dosyaları silin ve Power BI'ı yeniden başlatın.

**ArcGIS Maps for Power BI, Esri Şekil Dosyalarını destekliyor mu?**

ArcGIS Maps for Power BI ülke/bölge, eyalet/il ve posta kodları gibi standart sınırları otomatik olarak algılar. Kendi şekillerinizi sağlamanız gerekiyorsa [Power BI Desktop (Önizleme) için Şekil Haritalarını](desktop-shape-map.md) kullanarak yapabilirsiniz.

**ArcGIS haritalarımı çevrimdışı görüntüleyebilir miyim?**

Hayır, Power BI'ın haritaları görüntülemesi için ağ bağlantısı gerekir.

**Power BI'dan ArcGIS Online hesabıma bağlanabilir miyim?**

Henüz bağlanamazsınız. [Bu fikri oylayın](https://ideas.powerbi.com/forums/265200-power-bi-ideas/suggestions/9154765-arcgis-geodatabases), ilgili özellik üzerinde çalışmaya başladığımızda size bir e-posta gönderelim.  

## <a name="next-steps"></a>Sonraki adımlar
[Sizinle paylaşılan bir ArcGIS haritasıyla etkileşim kurma](power-bi-visualizations-arcgis.md)

[ArcGIS Maps for Power BI'ın kullanıma sunulduğunu duyuran blog gönderisi](https://powerbi.microsoft.com/blog/announcing-arcgis-maps-for-power-bi-by-esri-preview/)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

