---
title: Power BI Rapor Oluşturucusu’nda rapor tasarlamaya yönelik ipuçları
description: Power BI Sayfalandırılmış Rapor Oluşturucusu’nda sayfalandırılmış rapor tasarlarken aşağıdaki ipuçlarından faydalanın.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: c1490ff0-5b8a-43c1-8d22-e459395db4f6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: d7e232d09eee2a4cfff17d4565443195e6f7f1aa
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840361"
---
# <a name="report-design-tips-in-power-bi-report-builder"></a>Power BI Rapor Oluşturucusu’nda rapor tasarlamaya yönelik ipuçları
  Power BI Sayfalandırılmış Rapor Oluşturucusu’nda sayfalandırılmış rapor tasarlarken aşağıdaki ipuçlarından faydalanın.  
  
   
  
##  <a name="DesigningReports"></a> Raporları tasarlama  
  
-   İyi tasarlanmış bir rapor, eyleme dönüşen bilgiler aktarır. Raporun yanıtlamak istediği soruları belirleyin. Raporu tasarlarken bu soruları aklınızda tutun.  
  
-   Etkili veri görselleştirmeleri tasarlamak için, rapor okuyucusunun kolayca anlayabileceği bilgileri nasıl görüntüleyeceğinizi düşünün. Görselleştirmek istediğiniz verilere uygun bir veri bölgesi seçin. Örneğin, özet ve toplu bilgileri daha etkili bir şekilde aktarmak için sayfalar dolusu ayrıntılı bilgi içeren bir tablodansa bir grafik kullanmak daha faydalı olur. Grafikler, haritalar, göstergeler, mini grafikler, veri çubukları ve bir tablix’i temel alan çeşitli kılavuz düzenlerindeki tablosal veriler içeren, herhangi bir veri bölgesinde yer alan verileri görselleştirebilirsiniz. 
  
-   Raporu özel bir dışarı aktarma biçiminde teslim etmeyi planlıyorsanız, dışarı aktarma biçimini tasarımınızın ilk aşamalarında test edin. Özellik desteği, seçtiğiniz işleyiciye göre değişir.  
  
-   Karmaşık düzenleri oluştururken aşamalar halinde ilerleyin. Rapor öğelerini düzenlemek için dikdörtgenleri kapsayıcı olarak kullanabilirsiniz. Çalışma alanınızı en üst düzeye çıkarmak için veri bölgelerini doğrudan tasarım yüzeyinde oluşturabilir, tamamladıkça her birini dikdörtgen kapsayıcıya sürükleyebilirsiniz. Dikdörtgenleri kapsayıcı olarak kullandığınızda içeriğin tamamını tek adımda konumlandırabilirsiniz. Dikdörtgenler, rapor öğelerinin her sayfada nasıl işlendiğinin denetlenmesine yardımcı olur.  
  
-   Bir rapordaki dağınıklığı azaltmak için, özel rapor öğeleri için koşullu görünürlük kullanıp öğelerin gösterilip gösterilmeyeceğini kullanıcının seçmesini sağlamanız faydalı olabilir. Görünürlüğü, bir parametreye veya metin kutusunun durumuna göre ayarlayabilirsiniz. Geçici ifade sonuçlarını göstermek için koşullu olarak gizlenmiş metin kutuları ekleyebilirsiniz. Bir raporda beklenmeyen veriler görüntülendiğinde, ifadelerdeki hataları ayıklamak için bu geçici sonuçları gösterebilirsiniz.  
  
-   Tablix hücrelerinde veya dikdörtgenlerde iç içe geçmiş öğelerle çalışırken, kapsayıcı ve içindeki öğeler için farklı arka plan renkleri ayarlayabilirsiniz. Arka plan varsayılan olarak **Renksizdir**. Belirli bir arka plan rengi olan öğeler, arka planı **Renksiz** olarak ayarlanmış öğelerin içinden görünür. Bu teknik, tablix hücrelerindeki kenarlık görünürlüğü gibi görüntü özelliklerini ayarlamaya yönelik doğru öğeyi seçmenize yardımcı olabilir.  
  
 Raporunuzu tasarlarken göz önünde bulundurulacak noktalar hakkında daha fazla bilgi edinmek için bkz. [Rapor Oluşturucusu’nda bir Rapor Planlama](report-builder-planning-report.md)).  
  
##  <a name="NamingConventions"></a> Raporlar, veri kaynakları ve veri kümeleri için adlandırma kuralları  
  
-   Verilerin kaynağını belgelendiren veri kaynakları ve veri kümeleri için adlandırma kurallarını kullanın.  
  
    1.  **Veri kaynakları.** Güvenlik riski oluşturabileceği için gerçek bir sunucu veya veritabanı kullanmak istemiyorsanız kullanıcıya verinin kaynağını belirten bir diğer ad kullanın.  
  
    2.  **Veri kümeleri.** Hangi veri kaynağının temel alındığını belirten bir ad kullanın.  
  
##  <a name="Data"></a> Verilerle çalışma  
  
-   İlk adım olarak, çalışırken kullanmak istediğiniz tüm verilerin Rapor Verileri bölmesinde görünmesini sağlayın. Raporla yanıtlanması amaçlanan soruları geliştirdikçe, rapor veri kümelerindeki verileri nasıl sadece ihtiyaç duyulan şeylerle sınırlandırabileceğinizi düşünün.  
  
-   Genel olarak, yalnızca raporda görüntüleyeceğiniz verileri ekleyin. Kullanıcının raporda görmek istediği verileri seçmesine olanak tanımak için veri kümesi sorgularınızda sorgu değişkenlerini kullanın. Paylaşılan veri kümeleri oluşturuyorsanız, aynı işlevselliği sağlamak için filtreleri rapor parametrelerini temel alarak sunun.  
  
-   Sorgu yazma konusunda deneyimliyseniz, orta miktarda veriler söz konusu olduğunda verileri sorgudan ziyade raporda gruplandırarak daha iyi sonuçlar elde edebilirsiniz. Tüm gruplandırmanızı sorguda yaparsanız rapor, büyük olasılıkla sorgu sonuçları kümesinin bir gösterimi olacaktır. Öte yandan, bir grafik veya matriste yer alan çok fazla miktardaki veriye yönelik toplu değerleri görüntülemek için ayrıntı verilerini eklemek gerekmez.  
  
-   Gereksinimlerinize bağlı olarak, rapor verisi kaynaklarını, veri kümesi sorgusu komut metnini ve parametre değerlerinin adlarını ve konumlarını raporda görüntüleyebilirsiniz. Yeni kullanıcıların çoğu, verilerin nereden geldiğini merak eder. Rapordaki dağınıklığı azaltmak için, bu tür bilgiler ile metin kutularını koşullu olarak gizleyebilir ve kullanıcıların bunu görmek isteyip istemediklerini seçmelerine olanak tanıyabilirsiniz. Bu bilgileri raporun son sayfasına eklemeyi deneyin. Metin kutusu görünürlüğünü, kullanıcının değiştirebileceği bir parametreye göre ayarlayın.  
  
##  <a name="DesignSurface"></a> Rapor tasarım yüzeyi ile etkileşim kurma  
 Rapor tasarım yüzeyi WYSIWIG değildir. Tasarım yüzeyine rapor öğelerini yerleştirdiğinizde, bunların göreli konumları öğelerin işlenmiş rapor sayfasında nasıl görüneceğini etkiler. Boşluk korunur.  
  
-   Öğeleri rapor tasarım yüzeyinde hizalayıp düzenlemek için dayama çizgilerini ve düzen düğmelerini kullanın. Örneğin, seçilen öğelerin üstlerini ve kenarlarını hizalayabilirsiniz. Bir öğeyi, farklı bir öğenin boyutuyla aynı olacak şekilde yeniden boyutlandırabilir veya öğeler arasındaki aralığı ayarlayabilirsiniz.  
  
-   Seçili öğelerin konumunu ve boyutunu tasarım yüzeyinde ayarlamak için ok tuşlarını kullanın. Örneğin, aşağıdaki tuş bileşimleri oldukça kullanışlıdır:  
  
    -   **Ok tuşları** Seçilen rapor öğesini taşır.  
  
    -   **CTRL + Ok tuşları** Seçilen rapor öğesini sürükler.  
  
    -   **CTRL + SHIFT + Ok tuşları** Seçilen rapor öğesinin boyutunu büyütür veya küçültür.  
  
-   Bir dikdörtgene öğe eklemek için, dikdörtgen kapsayıcıdaki öğenin ilk konumunu işaret etmek için farenin sol üst ucunu kullanın. Seçili nesneleri kolayca konumlandırmak için klavye kısayollarını kullanın. Dikdörtgen, içerisindeki öğelerin boyutunu uyum sağlayacak şekilde otomatik olarak genişletir.  
  
-   Bir tablix hücresine birden çok öğe eklemek için ilk olarak bir dikdörtgen ve ardından öğeleri ekleyin.  
  
     Varsayılan olarak, her tablix hücresi bir metin kutusu içerir. Bir hücreye dikdörtgen eklediğinizde, dikdörtgen metin kutusunun yerini alır. Örneğin, hücrenin bulunduğu satırın yüksekliğini değiştirdikçe grafiğin veya göstergenin nasıl genişleyeceğini kolayca kontrol etmek için, iç içe geçmiş göstergeleri bir tablix hücresinde bulunan dikdörtgene yerleştirin.  
  
-   Tasarım yüzeyindeki görünümü ayarlamak için **Yakınlaştırma** denetimini kullanın. Tüm sayfayla veya daha küçük bölümleriyle çalışabilirsiniz.  
  
-   Rapor Verileri bölmesindeki alanları Gruplandırma bölmesine sürüklemek istediğinizde bunları tasarım yüzeyindeki diğer rapor öğelerinin üzerinden sürüklemeyin. Bunu yaparsanız diğer öğeler seçilir ve tablix veri bölgesinin seçimi kaldırılır. Alanı Rapor Verileri bölmesine ve ardından Gruplandırma panosuna sürükleyin.  
  
###  <a name="Selecting"></a> Öğeleri seçme  
 Rapor tasarım yüzeyinde olmasını istediğiniz nesneyi kolayca seçmek için ESC tuşunu, sağ tıklama bağlam menüsünü, Özellikler bölmesini ve Gruplandırma bölmesini kullanın.  
  
-   -   Tasarım yüzeyinde aynı alanı kaplayan rapor öğeleri yığının arasında geçiş yapmak için ESC’ye basın.  
  
    -   Bazı rapor öğelerinde, rapor öğesini veya rapor öğesinin istediğiniz bir parçasını seçmek için, sağ tıklayınca açılan bağlam menüsünü kullanmayı deneyin.  
  
    -   Özellikler bölmesi mevcut seçime yönelik özellikleri görüntüler.  
  
    -   Bir tablix veri bölgesinde satır ve sütun gruplarıyla çalışmak için Gruplandırma bölmesinden grubu seçin.  

  
##  <a name="ReportItems"></a> Belirli türden rapor öğeleriyle çalışma  
  
###  <a name="Parameters"></a> Parametrelerle çalışma  
  
-   Rapor parametrelerinin birincil amacı, veri kaynağındaki verileri filtreleyip yalnızca raporun amacı için gerekli olanları almaktır.  
  
-   Rapor parametreleri için, etkileşim olanağı tanıma ve bir kullanıcının istediği sonuçları almasına yardımcı olma arasındaki dengeyi bulun. Örneğin, popüler olduğunu bildiğiniz değerlere bir parametre için varsayılan değerleri ayarlayabilirsiniz.  
  
###  <a name="Text"></a> Metin ile çalışma  
  
-   Çok satırlı bir öğeyi bir metin kutusuna yapıştırdığınızda bu metin, bir metin çalıştırması olarak eklenir. Her metin çalıştırması sadece birim olarak biçimlendirilebilir. Her satırı bağımsız olarak biçimlendirmek için, ihtiyacınız oldukça metin çalıştırmasında RETURN tuşuna basarak yeni bir satır ekleyin. Ardından, metin kutusundaki her bağımsız metin satırına biçimlendirme ve stil uygulayabilirsiniz.  
  
-   Bir metin kutusunda veya metin kutusundaki yer tutucuda biçim özellikleri ve eylemleri ayarlayabilirsiniz. Yalnızca bir satırlık metin varsa, özelliklerin metinden ziyade metin kutusunda ayarlanması daha verimli olur.  
  
###  <a name="Expressions"></a> İfadelerle çalışma  
  
-   Basit ve karmaşık ifade biçimlerini anlayın. Basit ifade biçimlerini doğrudan metin kutularına, Özellikler bölmesindeki özelliklere, iletişim kutusundaki ifade kabul eden konumlara yazabilirsiniz.
  
-   Bir ifade oluşturduğunuzda, bu ifade her parçanın bağımsız olarak oluşturulmasına ve değerinin doğrulanmasına yardımcı olur. Ardından, tüm parçaları son bir ifadede birleştirebilirsiniz. Bir matris hücresine metin kutusu ekleyip ifadenin her parçasını görüntülemek ve metin kutusunda koşullu görünürlük ayarlamak kullanışlı bir tekniktir. Metin kutusu gizliyken kenarlık stilini ve rengini denetlemek için ilk olarak metin kutusunu bir dikdörtgene yerleştirin ve ardından dikdörtgenin kenarlık stilini ve rengini matris ile eşleşecek şekilde ayarlayın.  
  
###  <a name="Indicators"></a> Göstergeler ile çalışma  
  
-   Varsayılan olarak, bir gösterge en az üç durum gösterir. Bir rapora gösterge ekledikten sonra, durumları ekleyerek veya kaldırarak bunu yapılandırabilirsiniz. Kullanıcılarınızın bunu daha kolay görüntülemesi için, renk ve şekil yönünden farklılık gösteren bir gösterge seçin.  
  
##  <a name="Rendering"></a> Rapor sayfasındaki rapor öğelerinin işlenmesini denetleme  
  
-   Rapor tasarımı yüzeyindeki rapor öğeleri, ilişkili veri kümesinin, ifadenin, alt raporun veya metnin içeriklerinin sığabilmesi için büyür.  
  
    -   Bir öğeyi rapor sayfasında konumlandırdığınızda, öğe ve bunun sağında başlayan tüm öğelerin arasındaki mesafe, rapor öğesi yatay olarak büyüdükçe korunması gereken en düşük mesafe haline gelir. Benzer şekilde, bir öğe ve üstündeki öğe arasındaki mesafe, en üstteki öğe dikey olarak büyüdükçe korunması gereken en düşük mesafe haline gelir.  
  
    -   Rapordaki öğeler verilerini barındırabilmek için büyür ve aşağıdaki kuralları kullanarak eş öğeleri (aynı üst kapsayıcı içindeki öğeler) kendi yolunun dışına iter:  
  
    -   Her öğe, kendisi ve üstünde biten öğeler arasındaki en düşük mesafeyi korumak için aşağıya iner.  
  
    -   Her öğe, kendisi ve solunda biten öğeler arasındaki en düşük mesafeyi korumak için sağa kayar. Sağdan sola düzene sahip sistemler için, her öğe kendisi ve sağında biten öğeler arasındaki en düşü mesafeyi korumak için sola kayar.  
  
    -   Kapsayıcılar, alt öğelerin büyümesine uyum sağlamak için genişler. Seçili bir öğe için, Özellikler bölmesindeki Üst özellik, öğe için kapsayıcıyı tanımlar. Rapor öğelerinin kapsama hiyerarşisini görmek için Belge Ana Hattı bölmesini de kullanabilirsiniz.  
  
    -   **Düzen** araç çubuğu, kenarların, merkezlerin ve rapor öğelerine yönelik boşlukların hizalanmasını sağlayan birden fazla tuş sunar. **Düzen** araç çubuğunu etkinleştirmek için **Görünüm** menüsünden **Araç Çubukları**’na gelip **Düzen**’e tıklayın.  
  
-   Raporu bir .pdf dosyası halinde kaydetmeyi planlıyorsanız, rapor genişliğinin net bir değer ile ayarlanmış olması gerekir. Bu değeri belirlerken, dışarı aktarma biçiminde elde etmek istediğiniz sonuçları dikkate alın. Örneğin, rapor sayfası genişliğini tam 20,16125 cm olarak, sol ve sağ boşlukları da 1,27 cm olarak ayarlayın.  
  
-   Raporu, yazdırmayla uyumlu bir görünümde işlemek için rapor görüntüleyicisi araç çubuğundaki **Yazdırma Düzeni** ve **Sayfa Düzeni** seçeneklerini kullanın. İstenmeyen yatay sayfaları aşağıdakileri yapın:  
  
    1.  Veri bölgelerinin ve raporun kenarlarının arasındaki fazladan boşlukları kaldırın.  
  
    2.  **Rapor Özellikleri** iletişim kutusundaki sayfa boşluklarını azaltın.  
  
    3.  Rapor öğelerinin nasıl işlendiğini kolayca denetlemek için **Dikdörtgenleri** kapsayıcı olarak kullanın.  
  
    4.  Sütun başlıklarında, metin kutusu özelliği WritingMode’u dikey metin kullanacak şekilde değiştirin.  
  
 Bu davranış, rapor öğelerinin genişlik ve yükseklik özellikleri, raporun gövdesinin boyutu, sayfa yüksekliğinin ve genişliğinin tanımı, üst raporun boşluk ayarları ve sayfalandırmaya yönelik işleyiciye özel destek gibi faktörler bir araya gelerek işlenen bir sayfada hangi rapor öğelerinin birlikte sığdırılacağını belirler. 
 
## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)  
