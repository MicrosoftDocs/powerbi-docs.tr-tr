---
title: R programlama dilini kullanarak Power BI görselleri oluşturma
description: R programlama dilini kullanarak Power BI görselleri oluşturma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 969dc53f97156724d6c2b6b7dd6036b3fe8310aa
ms.sourcegitcommit: 10a87c016f497dbeba32f94ed1f3688a70816fea
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65514417"
---
# <a name="create-power-bi-visuals-using-r"></a>R programlama dilini kullanarak Power BI görselleri oluşturma
**Power BI Desktop** ile verilerinizi görselleştirmek için **R** programlama dilini kullanabilirsiniz.

## <a name="install-r"></a>R yükleme
**Power BI Desktop**, **R** altyapısını içermez, dağıtmaz veya yüklemez. **Power BI Desktop**'ta R betikleri çalıştırmak için yerel bilgisayarınıza **R**'yi ayrıca yüklemeniz gerekir. **R**'yi [Revolution Open indirme sayfası](https://mran.revolutionanalytics.com/download/) ve [CRAN Repository](https://cran.r-project.org/bin/windows/base/) de dahil olmak üzere pek çok konumdan ücretsiz olarak indirip yükleyebilirsiniz. R betiklerinin **Power BI Desktop**'taki güncel sürümü, yükleme yolunda Unicode karakterlerin yanı sıra boşlukların (boş karakterler) olmasını da destekler.

## <a name="enable-r-visuals"></a>R görsellerini etkinleştirme
R görsellerini etkinleştirmek için **Dosya > Seçenekler ve ayarlar > Seçenekler** öğesini seçin. Görüntülenen **Seçenekler** sayfasında, aşağıda gösterildiği şekilde, **Seçenekler** penceresinin **R betiği oluşturma** bölümünde yerel R yüklemenizin belirtildiğinden emin olun. Aşağıdaki görüntüde, yerel R yüklemesinin yolu **C:\Program Files\R\R-3.2.0** şeklindedir ve bu yol, metin kutusunda açıkça belirtilmektedir. Görüntülenen yolun, **Power BI Desktop**'ın kullanmasını istediğiniz yerel R yüklemesini doğru şekilde yansıttığından emin olun.
   
   ![](media/desktop-r-visuals/r-visuals-2.png)

R yüklemenizi belirttiğinizde R görselleri oluşturmaya başlayabilirsiniz.

## <a name="create-r-visuals-in-power-bi-desktop"></a>Power BI Desktop'ta R görselleri oluşturma
1. Bir R görseli eklemek için, aşağıdaki görüntüde gösterilen şekilde, **Görsel Öğeler** bölmesindeki **R Görseli** simgesini seçin.
   
   ![](media/desktop-r-visuals/r-visuals-3.png)

   Bir rapora R görseli eklediğinizde **Power BI Desktop** şu işlemleri gerçekleştirir:
   
   - Rapor tuvalinde bir yer tutucu R görseli görüntüsü görünür.
   
   - Orta bölmenin alt kısmında **R betik düzenleyicisi** görünür.
   
   ![](media/desktop-r-visuals/r-visuals-4.png)

2. Daha sonra, R betiğinizde kullanmak istediğiniz alanları, diğer **Power BI Desktop** görsellerinde yaptığınız gibi **Alanlar** bölmesindeki **Değerler** bölümüne ekleyin. 
    
    Yalnızca **Alanlar** kutusuna eklenmiş alanlar R betiğinizle kullanılabilir. Ayrıca, **Power BI Desktop R betik düzenleyicisinde** R betiğinizle çalışırken **Alanlar** bölmesine yeni alan ekleyebilir veya gereksiz alanları bu bölmeden çıkarabilirsiniz. **Power BI Desktop**, hangi alanları eklediğinizi veya kaldırdığınızı otomatik olarak algılar.
   
   > [!NOTE]
   > R görselleri için varsayılan toplama türü, *özetleme* şeklindedir.
   > 
   > 
   
3. Artık bir çizim oluşturmak için seçtiğiniz verileri kullanabilirsiniz. 

    Siz alan seçtikçe **R betik düzenleyicisi**, düzenleyici bölmesinin üst kısmında bulunan gri bölümde yaptığınız seçimlere bağlı olarak yardımcı R betiği bağlama kodunu oluşturur. Yeni alan seçtiğinizde veya var olan bir alanı kaldırdığınızda R betik düzenleyicisinde yardımcı kod otomatik olarak oluşturulur veya kaldırılır.
   
   Aşağıdaki görüntüde gösterilen örnekte hp, gear ve drat olmak üzere üç alan seçilmiştir. Bu seçimlerin sonucunda R betik düzenleyicisi, aşağıdaki bağlama kodunu oluşturmuştur:
   
   * **dataset** adlı bir veri çerçevesi oluşturulmuştur
     * Bu veri çerçevesi, kullanıcı tarafından seçilen farklı alanlardan oluşmaktadır
   * Varsayılan toplama türü, *özetleme* şeklindedir
   * Tablo görsellerinde olduğu gibi alanlar da gruplandırılır ve yinelenen satırlar yalnızca bir kez görünür
   
   ![](media/desktop-r-visuals/r-visuals-5.png)
   
   > [!TIP]
   > Bazı durumlarda, otomatik gruplandırma işleminin gerçekleştirilmesini istemeyebilir veya yinelenenler de dahil olmak üzere tüm satırların görünmesini isteyebilirsiniz. Böyle durumlarda veri kümenize bir dizin alanı ekleyebilirsiniz. Böylece, tüm satırların benzersiz olduğu kabul edilir ve gruplandırma yapılması önlenir.
   > 
   > 
   
   Oluşturulan veri çerçevesi **dataset** olarak adlandırılır ve seçilen sütunlara, adlarıyla erişebilirsiniz. Örneğin, R betiğinizde *dataset$gear* yazarak gear alanına erişin. Boşluklu veya özel karakterler içeren alanlar için tek tırnak işareti kullanın.

4. Seçtiğiniz alanlara göre otomatik olarak oluşturulan veri çerçevesi ile R betiği yazmaya hazır hale gelirsiniz. R betiği yazdığınızda, varsayılan R cihazında bir çizim oluşturulur. Betik tamamlandığında **R betik düzenleyicisi** başlık çubuğunda **Çalıştır**'ı seçin. (**Çalıştır** seçeneği, başlık çubuğunun sağ tarafında bulunur.)
   
    **Çalıştır**’ı seçtiğinizde **Power BI Desktop**, çizimi tanımlar ve tuval üzerinde görüntüler. İşlem yerel R yüklemenizde gerçekleştirildiğinden, gerekli paketlerin yüklendiğinden emin olun.
   
   **Power BI Desktop**, aşağıdaki olaylardan herhangi biri meydana geldiğinde görseli yeniden çizer:
   
   * **R betik düzenleyicisi** başlık çubuğunda **Çalıştır** seçeneğini belirlediğinizde
   * Veri yenileme, filtreleme veya vurgulama işlemi nedeniyle her veri değişikliği gerçekleştiğinde

     Aşağıdaki görüntüde bağıntı çizim koduna ilişkin bir örnek ve farklı otomobil türlerinin öznitelikleri arasındaki bağıntılara ilişkin bir çizim gösterilmektedir.

     ![](media/desktop-r-visuals/r-visuals-6.png)

5. Görselleştirmelerin daha büyük bir görünümünü elde etmek için **R betik düzenleyicisi**'ni simge durumuna küçültebilirsiniz. **Power BI Desktop**'taki diğer görsellerde olduğu gibi, halka görselinde (yukarıdaki örnek görüntüsünde, sağdaki yuvarlak görsel) yalnızca spor otomobilleri seçerek bağıntı çiziminde çapraz filtre uygulayabilirsiniz.

    ![](media/desktop-r-visuals/r-visuals-7.png)

6. Ayrıca, görseli özelleştirmek için R betiğini değiştirebilir ve çizim oluşturma komutuna parametre ekleyerek R programlama dilinin gücünden yararlanabilirsiniz.

    Başlangıçta, çizim oluşturma komutu şu şekildeydi:

    corrplot(M, method = "color",  tl.cex=0.6, tl.srt = 45, tl.col = "black")

    R betiğinde yapılan birkaç değişikliğin ardından yeni komut şu şekildedir:

    corrplot(M, method = "circle", tl.cex=0.6, tl.srt = 45, tl.col = "black", type= "upper", order="hclust")

    Değişikliklerin ardından R görseli, aşağıdaki görüntüde gösterildiği gibi, artık daireler çiziyor, yalnızca üst yarıyı dikkate alıyor ve bağıntılı öznitelikleri kümelemek için matrisi yeniden sıralıyor.

    ![](media/desktop-r-visuals/r-visuals-8.png)

    Bir R betiği yürütülürken hata oluşursa R görseli çizilmez ve tuvalde bir hata iletisi görüntülenir. Hataya ilişkin ayrıntılar için, tuvalde görüntülenen R görseli hata iletisinde **Ayrıntılara göz atın** seçeneğini belirleyin.

    ![](media/desktop-r-visuals/r-visuals-9.png)

    > **R betiklerinin güvenliği:** R görselleri, güvenlik veya gizlilik riskleri taşıyan kodlar içerebilecek R betiklerinden oluşturulur. Bir R görselini ilk kez görüntülemeye veya R görseliyle ilk kez etkileşim kurmaya çalışan kullanıcılar bir güvenlik uyarısı iletisiyle karşılaşır. R görsellerini yalnızca, yazara ve kaynağa güvenmeniz halinde veya ilgili R betiğini gözden geçirip anladıktan sonra etkinleştirin.
    > 
    > 

## <a name="known-limitations"></a>Bilinen sınırlamalar
**Power BI Desktop**'ta R görsellerine ilişkin bazı sınırlamalar mevcuttur:

* Veri boyutu sınırlamaları: R görseli tarafından çizim için kullanılan veri 150.000 satırla sınırlıdır. 150.000'den fazla satır seçilirse yalnızca ilk 150.000 satır kullanılır ve görüntünün üzerinde bir ileti görüntülenir.
* Hesaplama süresi sınırlaması: Bir R görseli hesaplaması beş dakikadan uzun sürerse betik zaman aşımına uğrar ve bir hata oluşur.
* İlişkiler: Diğer Power BI Desktop görsellerinde olduğu gibi, aralarında tanımlanmış hiçbir ilişki bulunmayan farklı tablolardan veri alanları seçilirse hata oluşur.
* R görselleri veri güncelleştirme, filtreleme ve vurgulama işlemlerinden sonra yenilenir. Ancak, görüntünün kendisi etkileşimli değildir ve çapraz filtrelemenin kaynağı olamaz.
* R görselleri, diğer görselleri vurgulama işlemine yanıt verir ancak diğer öğelere çapraz filtreleme uygulamak için R görsellerindeki öğelere tıklayamazsınız.
* Yalnızca varsayılan R görüntüleme cihazında çizilen çizimler tuval üzerinde doğru şekilde görüntülenir. Farklı bir R görüntüleme cihazını açıkça kullanmaktan kaçının.
* Bu sürümde RRO yüklemeleri, Power BI Desktop'ın 32 bit sürümü tarafından otomatik olarak tanımlanmaz; bu nedenle, **Seçenekler ve ayarlar > Seçenekler > R betiği oluşturma** bölümündeki R yükleme dizininin yolunu elle sağlamanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar
Power BI'da R kullanımı ile ilgili aşağıdaki ek bilgilere göz atın.

* [Power BI Desktop'ta R Betikleri Çalıştırma](desktop-r-scripts.md)
* [Power BI ile harici bir R IDE kullanma](desktop-r-ide.md)

