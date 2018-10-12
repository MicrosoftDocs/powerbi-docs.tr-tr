---
title: Power BI’da yer işaretlerini kullanma
description: Power BI Desktop'taki yer işaretleri, raporlarınızdaki görünümleri ve ayarları kaydetmenize ve akıcı sunumlar oluşturmanıza olanak sağlar
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/06/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1bb9921b31187d0df3debc644088a72e1d78207c
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46549926"
---
# <a name="use-bookmarks-to-share-insights-and-build-stories-in-power-bi"></a>Power BI’da öngörü paylaşmak ve hikayeler oluşturmak için yer işaretlerini kullanma 
Power BI’da **yer işaretlerini** kullanarak, filtreleme ve görsellerin durumu dahil olmak üzere bir rapor sayfasının geçerli olarak yapılandırılmış görünümünü yakalayabilir ve ardından, kaydedilmiş bu yer işaretini seçerek söz konusu duruma kolayca geri dönebilirsiniz. 

Ayrıca, bir yer işareti koleksiyonu oluşturabilir, bu yer işaretlerinin sırasını istediğiniz gibi düzenleyebilir ve daha sonra bir öngörü dizisini veya görselleriniz ve raporlarınız ile anlatmak istediğiniz hikayeyi vurgulamak için her bir yer işareti üzerinden ilerleyebilirsiniz. 

![Power BI'da yer işaretleri](media/desktop-bookmarks/bookmarks_01.png)

Yer işaretlemesine yönelik birçok kullanım vardır. Yer işaretlerini, rapor oluşturma konusundaki ilerleyişinizi izlemek için kullanabilirsiniz (yer işaretleri kolayca eklenebilir, silinebilir ve yeniden adlandırılabilir) ve yer işaretleri üzerinden sırayla ilerleyen PowerPoint benzeri bir sunum oluşturarak raporunuzla bir hikaye anlatmak için yer işaretlerinden yararlanabilirsiniz. Yer işaretleri, en iyi şekilde nasıl yararlanabileceğinize yönelik tercihlerinize bağlı olarak başka amaçlarla da kullanılabilir.

### <a name="enable-the-bookmarks-preview-versions-prior-to-march-2018"></a>Yer işaretleri önizlemesini (Mart 2018’den önceki sürümler) etkinleştirme
Power BI Desktop’ın Mart 2018 sürümünden itibaren, yer işaretleri genel kullanıma sunulmuştur. 

Her zaman en son sürüme yükseltmeniz önerilir. Ancak Power BI Desktop sürümünüz söz konusu sürümden eskiyse **Power BI Desktop**’ın **Ekim 2017** sürümü itibarıyla, **yer işaretleri** özelliğini deneyebilirsiniz. Bu özellik, **Power BI hizmetindeki** yer işareti özellikli raporlar için de kullanılabilir. Bu önizleme özelliğini etkinleştirmek için **Dosya > Seçenekler ve Ayarlar > Seçenekler > Önizleme Özellikleri** seçeneğini belirleyin ve ardından **Yer imleri**’nin yanındaki onay kutusunu işaretleyin. 

![Seçenekler penceresinde yer işaretlerini etkinleştirme](media/desktop-bookmarks/bookmarks_02.png)

Yer işaretlerinin önizleme sürümünü etkinleştirmeyi seçtikten sonra **Power BI Desktop**’ı yeniden başlatmanız gerekir.

## <a name="using-bookmarks"></a>Yer işaretlerini kullanma
Yer işaretlerini kullanmak için **Görünüm** şeridini ve ardından **Yer İşaretleri Bölmesi** kutusunu seçin. 

![Görünüm şeridinden etkinleştirerek Yer İşaretleri Bölmesini gösterin.](media/desktop-bookmarks/bookmarks_03.png)

Bir yer işareti oluşturduğunuzda aşağıdaki öğeler, bu yer işareti ile birlikte kaydedilir:

* Geçerli sayfa
* Filtreler
* Dilimleyiciler
* Sıralama düzeni
* Detay konumu
* Görünürlük (**Seçim** bölmesi kullanıldığında, bir nesnenin görünürlüğü)
* Herhangi bir görünür nesnenin odak veya **Spotlight** modları

Yer işaretleri şu anda çapraz vurgulama durumunu kaydetmemektedir. 

Bir rapor sayfasını yer işaretinde görünmesini istediğiniz şekilde yapılandırın. Rapor sayfanızı ve görsellerinizi istediğiniz şekilde düzenledikten sonra yer işareti eklemek için **Yer İşaretleri** bölmesinden **Ekle**'yi seçin. 

![Bir yer işareti ekleme](media/desktop-bookmarks/bookmarks_04.png)

**Power BI Desktop**, bir yer işareti oluşturur ve yer işaretine genel bir ad verir. Bir yer işaretini, yer işareti adının yanındaki üç nokta simgesini seçip görüntülenen menüden bir eylem seçerek kolayca *yeniden adlandırabilir*, *silebilir* veya *güncelleştirebilirsiniz*.

![Bir yer işareti için üç nokta simgesini kullanarak alt menü seçme](media/desktop-bookmarks/bookmarks_05.png)

**Yer İşaretleri** bölmesindeki yer işaretine tıklayarak yer işaretinizi görüntüleyebilirsiniz. 

Ayrıca her yer işaretinin, filtreler ve dilimleyiciler gibi *veri* özelliklerini, öne çıkanlar ve görünürlüğü gibi *görüntüleme* özelliklerini ve yer işareti eklendiğinde görünür olan sayfayı sunan sayfa değişikliklerini uygulayıp uygulamayacağını seçebilirsiniz. Bu özellikler, görsel türleri değiştirmek için yer işaretlerini kullanırken faydalıdır. Ancak bu durumda, filtrelerin kullanıcılar görsel türleri değiştirdikçe sıfırlanmaması için veri özelliklerini kapatmak isteyebilirsiniz. 

Bunun gibi değişiklikler yapmak için, bir önceki resimdeki gösterildiği gibi yer işaretinin adının yanında bulunan üç noktayı seçin, ardından *Veriler*, *Görüntü* ve diğer denetimlerin yanındaki onay işaretlerini seçin ya da seçimi kaldırın. 

## <a name="arranging-bookmarks"></a>Yer işaretlerini düzenleme
Yer işaretleri oluşturdukça bunları oluşturduğunuz sıranın hedef kitlenize sunmak istediğiniz sırayla aynı olmadığını düşünebilirsiniz. Sorun değil, yer işaretlerinin sırasını kolayca yeniden düzenleyebilirsiniz.

Geçerli sırayı değiştirmek için, aşağıdaki görüntüde gösterildiği gibi, **Yer İşaretleri** bölmesinde basit sürükleme ve bırakma işlemleri gerçekleştirin. Yer işaretleri arasındaki sarı çubuk, sürüklenen yer işaretinin nereye yerleştirileceğini belirtir.

![Sürükle ve bırak özelliğini kullanarak yer işareti sırasını değiştirme](media/desktop-bookmarks/bookmarks_06.png)

Yer işaretlerinizin sırası, sonraki bölümde açıklandığı gibi yer işaretlerinin **Görünüm** özelliği kullanılırken önemli hale gelebilir.

## <a name="bookmarks-as-a-slide-show"></a>Slayt gösterisi olarak yer işaretleri
Sırasıyla sunmak istediğiniz bir yer işareti koleksiyonunuz olduğunda, bir slayt gösterisi başlatmak için **Yer İşaretleri** bölmesindeki **Görünüm** seçeneğini belirleyebilirsiniz.

**Görünüm** modunda dikkat edilmesi gereken birkaç özellik vardır:

1. Yer işaretinin adı, tuvalin alt tarafında görüntülenen yer işareti başlık çubuğunda görünür.
2. Yer işareti başlık çubuğu, önceki ve sonraki yer işaretine gitmenize olanak sağlayan oklar içerir.
3. **Görünüm** modundan çıkmak için **Yer İşaretleri** bölmesindeki **Çıkış**’ı veya yer işareti başlık çubuğundaki **X** işaretini seçebilirsiniz. 

![Yer işareti bölmesindeki yer işareti başlık çubuğu özellikleri](media/desktop-bookmarks/bookmarks_07.png)

**Görünüm** modundayken sunumunuz için daha fazla alan sağlamak üzere **Yer İşaretleri** bölmesini kapatabilirsiniz (bölmedeki X işaretine tıklayarak). **Görünüm** modundayken tüm görseller etkileşimlidir ve normalde olduğu gibi çapraz vurgulama için kullanılabilir. 

## <a name="visibility---using-the-selection-pane"></a>Görünürlük - Seçim bölmesini kullanma
Yer işaretlerinin dahil edildiği sürümle birlikte yeni **Seçim** bölmesi de kullanıma sunulmuştur. **Seçim** bölmesi, geçerli sayfadaki tüm nesnelerin bir listesini sunar ve nesneyi seçip görünür olup olmayacağını belirtmenize olanak sağlar. 

![Seçim bölmesini etkinleştirme](media/desktop-bookmarks/bookmarks_08.png)

**Seçim** bölmesini kullanarak bir nesneyi seçebilirsiniz. Ayrıca, görselin sağındaki göz simgesine tıklayarak nesnenin geçerli durumda görünür olup olmayacağına ilişkin seçiminizi belirleyebilirsiniz. 

![Seçim bölmesi](media/desktop-bookmarks/bookmarks_09.png)

Bir yer işareti eklendiğinde her bir nesnenin görünürlük durumu da **Seçim** bölmesindeki ayarına göre kaydedilir. 

**Dilimleyicilerin**, görünür olup olmadıklarından bağımsız olarak rapor sayfalarını filtrelemeye devam ettiğini unutmayın. Bu nedenle, farklı dilimleyici ayarlarına sahip birçok farklı yer işareti oluşturabilir ve tek bir rapor sayfasının çeşitli yer işaretlerinde oldukça farklı görünmesini (ve farklı öngörüleri vurgulamasını) sağlayabilirsiniz.

## <a name="bookmarks-for-shapes-and-images"></a>Şekiller ve resimler için yer işaretleri
Yer işaretlerine şekil ve resim de bağlayabilirsiniz. Bu özellik kullanıldığında, bir nesneye tıkladığınızda o nesne ile ilişkili yer işareti gösterilir. Bu, özellikle düğmelerle çalışırken faydalı olabilir. [Power BI’da düğmeleri kullanma](desktop-buttons.md) ile ilgili makaleyi okuyarak daha fazla bilgi edinebilirsiniz. 

Bir nesneye yer işareti atamak için nesneyi seçin, ardından aşağıdaki görüntüde gösterildiği gibi **Şekil Biçimlendir** bölmesinden **Eylem** bölümünü genişletin.

![Bir nesneye yer işareti bağlantısı ekleme](media/desktop-bookmarks/bookmarks_10.png)

**Bağlantı** kaydırıcısını **Açık** olarak ayarladığınızda nesnenin bir geri düğmesi mi, bir yer işareti mi, yoksa bir Soru-Cevap komutu mu olacağını belirleyebilirsiniz. Yer işaretini seçerseniz ardından nesnenin hangi yer işaretlerine bağlanacağını seçebilirsiniz.

Nesne bağlantılı yer işaretlemesi ile pek çok ilgi çekici işlem yapabilirsiniz. Sadece bir nesneye tıklayarak rapor sayfanızdaki görsellere ilişkin bir içindekiler tablosu oluşturabilir veya aynı bilgilerle farklı görünümler (görsel türleri gibi) sağlayabilirsiniz.

Bağlantıyı açmak için, düzenleme modundayken CTRL tuşuna basıp bağlantıya tıklayabilirsiniz; düzenleme modunda değilseniz açmak için bağlantıya tıklamanız yeterlidir. 

## <a name="bookmark-groups"></a>Yer işareti grupları

**Power BI Desktop** uygulamasının Ağustos 2018 sürümünden itibaren yer işareti grupları oluşturabilir ve kullanabilirsiniz. Yer işareti grubu belirttiğiniz yer işaretlerinden oluşan ve grup halinde gösterilip düzenlenebilen bir koleksiyondur. 

Yer işareti grubu oluşturmak için CTRL tuşunu basılı tutarken gruba dahil etmek istediğiniz yer işaretlerini seçin ve ardından seçtiğiniz yer işaretlerinden birinin yanındaki üç noktaya tıklayıp açılan menüden **Grup** seçeneğini belirtin.

![Yer işareti grubu oluşturma](media/desktop-bookmarks/bookmarks_15.png)

**Power BI Desktop**, gruba otomatik olarak *Grup 1* adını verir. Elbette ada çift tıklayarak istediğiniz gibi değiştirebilirsiniz.

![Yer işareti grubunu yeniden adlandırma](media/desktop-bookmarks/bookmarks_16.png)

Herhangi bir yer işareti grubunun adına tıkladığınızda grup genişletilir veya daraltılır ve tek bir yer işareti gösterilmez. 

Yer işaretlerinin **Görüntüle** özelliğini kullandığınızda aşağıdaki işlemler gerçekleşir:

* Seçilen yer işareti bir grubun içindeyse **Görüntüle** seçeneğini belirlediğinizde görüntüleme oturumunda yalnızca *bu gruptaki* yer işaretleri gösterilir. 

* Seçilen yer işareti bir grup değilse veya en üst düzeydeyse (yer işareti grubunun adı gibi) gruptaki yer işaretleri dahil olmak üzere rapordaki tüm yer işaretleri oynatılır. 

Yer işaretleri grubunu çözmek için gruptaki yer işaretlerinden birini seçin, üç noktaya tıklayın ve açılan menüden **Grubu çöz**'ü seçin. 

![Yer işareti grubunu çözme](media/desktop-bookmarks/bookmarks_17.png)

Gruptaki bir yer işaretinden **Grubu çöz**'ü seçtiğinizde tüm yer işaretlerinin gruptan çıkarılacağını unutmayın (grup silinir ancak yer işaretleri silinmez). Gruptaki yer işaretlerinden birini kaldırmak isterseniz grup üyelerinden birinden **Grubu çöz**'ü seçerek grubu silmeniz ve ardından grupta olmasını istediğiniz üyeleri seçip (CTRL tuşuna basılı tutup tıklayarak) tekrar **Grup** öğesini seçmeniz gerekir. 


## <a name="using-spotlight"></a>Spotlight'ı kullanma
Yer işaretleri ile gelen bir diğer özellik de **Spotlight**'tır. Örneğin, **Görünüm** modunda yer işaretlerinizin sunumunu yaparken **Spotlight** ile ilgiyi belirli bir grafiğe çekebilirsiniz.

Şimdi aralarındaki farkları görmek için **Spotlight** ile **odak** modunu karşılaştıralım.

1. **Odak** modunda, **odak** modu simgesini seçerek bir görselin tuvalin tamamını doldurmasını sağlayabilirsiniz.
2. **Spotlight**'ı kullanarak ise sayfadaki tüm diğer görsellerin rengini neredeyse saydam olacak şekilde soldurarak bir görseli özgün boyutunda vurgulayabilirsiniz. 

![Odak modu ile Spotlight karşılaştırması](media/desktop-bookmarks/bookmarks_11.png)

Önceki görüntüdeki görsel için **odak** simgesi seçili olduğu için sayfa aşağıdaki gibi görünür:

![odak modu](media/desktop-bookmarks/bookmarks_12.png)

Görselin üç nokta menüsünden **Spotlight** seçildiğindeyse sayfa aşağıdaki gibi görünür:

![spotlight modu](media/desktop-bookmarks/bookmarks_13.png)

Bir yer işareti eklendiğinde bu modlardan biri seçiliyse seçili olan mod (odak veya Spotlight) yer işaretinde de korunur.

## <a name="bookmarks-in-the-power-bi-service"></a>Power BI hizmetinde yer işaretleri
**Power BI hizmetinde** en az bir yer işareti bulunan bir rapor yayımladığınızda, bu yer işaretlerini **Power BI hizmetinde** görüntüleyebilir ve yer işaretleriyle etkileşim kurabilirsiniz. Bir raporda yer işaretleri mevcut olduğunda söz konusu bölmelerden her birimi göstermek için **Görünüm > Seçim bölmesi** veya **Görünüm > Yer İşaretleri bölmesi**'ni seçebilirsiniz.

![Power BI hizmetinde yer işaretleri ve seçim bölmelerini görüntüleme](media/desktop-bookmarks/bookmarks_14.png)

**Power BI hizmetinde** **Yer İşaretleri bölmesi**, tıpkı **Power BI Desktop**'taki gibi çalışır. Yer işaretlerinizi bir slayt gösterisi gibi sırayla göstermek için **Görünüm** seçeneğini belirlemek de buna dahildir.

Yer işaretleri arasında gezinmek için gri renkli yer işareti başlık çubuğunu kullanmayı unutmayın. Siyah okları kullanırsanız yer işaretleri arasında değil, raporlar arasında gezinirsiniz.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar
**Yer işaretleri**’nin bu sürümünde dikkat etmeniz gereken bazı sınırlamalar ve önemli noktalar bulunmaktadır.

* Çoğu özel görsellerin yer işareti eklemeyle iyi çalışması gerekir. Yer işareti eklemeyle ve özel görselle ilgili bir sorunla karşılaşırsanız, bu özel görseli oluşturan kişiye başvurun ve görseline yer işareti desteği eklemesini isteyin. 
* Yer işareti oluşturduktan sonra rapor sayfasına bir görsel eklerseniz bu görsel, varsayılan durumunda görüntülenir. Bu, önceden yer işaretleri oluşturduğunuz bir sayfaya dilimleyici eklediğinizde dilimleyicinin varsayılan durumunda davranış göstereceği anlamına da gelir.
* Bir yer işareti oluşturulduktan sonra gerçekleştirdiğiniz görsel taşıma işlemleri, yer işaretinde gösterilir. 


## <a name="next-steps"></a>Sonraki adımlar
Yer işaretlerine benzeyen veya yer işaretleriyle etkileşim kuran özellikler hakkında daha fazla bilgi için aşağıdaki makalelere göz atın:

* [Power BI Desktop'ta detaylandırma özelliğini kullanma](desktop-drillthrough.md)
* [Bir pano kutucuğunu veya rapor görselini Odak modunda görüntüleme](consumer/end-user-focus.md)

