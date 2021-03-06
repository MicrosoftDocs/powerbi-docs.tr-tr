---
title: Power BI hizmetindeki düğmelerin nasıl çalıştığını öğrenin
description: Düğmeler; rapor içi gezinti, detaylandırma ve çapraz rapor detaylandırma gibi çeşitli eylemleri başlatmak için kullanılabilir
author: mihart
ms.author: mihart
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: pbi-explore
ms.topic: how-to
ms.date: 12/21/2020
LocalizationGroup: Reports
ms.openlocfilehash: 140ca42dc34e98133beac5fff671cf1ef244501c
ms.sourcegitcommit: 0711972326521944fdd8572403c0b15f31b916da
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2020
ms.locfileid: "97721444"
---
# <a name="buttons-in-the-power-bi-service"></a>Power BI hizmetindeki düğmeler
İş arkadaşlarınızın gönderdiği raporlardaki düğmeleri fark etmiş ve bunların nasıl kullanılacağını öğrenmek istemiş olabilirsiniz. Bu düğmelerin bazılarının üzerinde sözcükler, bazılarında oklar, diğerlerinde ise grafikler ve hatta açılan menüler bulunur. Bu makale, düğmeleri tespit etme ve gerçekleştirdikleri işlemleri öğrenme konusunda size yol gösterecektir.

## <a name="how-to-recognize-a-button"></a>Düğmeleri tanıma
Düğmeler, rapor sayfasındaki şekillere, görüntülere veya simgelere benzer olabilir. Ancak seçtiğinizde (tıkladığınızda) bir eylem gerçekleştiriliyorsa bu muhtemelen bir düğmedir.

## <a name="types-of-buttons"></a>Düğmelerin türleri
Rapora oluşturucuları, gezinti ve keşif konusunda yardımcı olması için raporlara düğmeler ekler. Düğme türlerinden bazıları şunlardır: geri, yer işareti, oklar, Soru-Cevap, yardım ve boş. 

### <a name="back-buttons"></a>Geri düğmeleri 
Geri düğmesinin üzerinde bir ok olabilir ve bu düğmeyi seçtiğinizde Power BI bir önceki sayfayı açar.  Geri düğmeleri genellikle detaylandırmayla birlikte kullanılır. Aşağıda detaylandırma ile birlikte kullanılan geri düğmelerine bir örnek verilmiştir.

1. Kullanıcı çubuk grafikte **Sözcük** seçimi yapmış ve **Pazar sepeti çözümlemesi** detayına gidiyor.

    ![Detaylandır düğmesinin ekran görüntüsü.](media/end-user-buttons/power-bi-drillthrough.png)

2. **Pazar sepeti çözümlemesi**'ni seçtiğinizde Power BI, *Pazar sepeti çözümlemesi* rapor sayfasını açar ve kaynak sayfada yapılan seçimleri kullanarak hedef sayfada gösterilen içeriği filtreler.

    ![Geri düğmesinin ekran görüntüsü.](media/end-user-buttons/power-bi-back.png)

    **Sözcük** için filtrelenmiş olan **Pazar sepeti çözümlemesi** rapor sayfasına ulaşmış olursunuz. Önceki sayfaya geri dönmek için **Geri git** etiketine sahip geri düğmesini seçin. 

## <a name="bookmark-buttons"></a>Yer işareti düğmeleri
Rapor *tasarımcıları*, raporlarına genellikle yer işaretleri ekler. Sağ üst köşeden **Yer İşaretleri**'ni seçerek rapordaki yer işaretlerinin listesini görüntüleyebilirsiniz. Rapor tasarımcısının eklediği yer işareti *düğmesi*, ilgili yer işaretiyle ilişkilendirilmiş olan rapor sayfasına ulaşmak için alternatif bir yöntem sunar. Sayfada yer işaretine kaydedilmiş olan filtreler ve ayarlar uygulanmış olur. [Power BI’daki yer işaretleri hakkında daha fazla bilgi edinin](end-user-bookmarks.md). 

Bu örnekte düğme üzerinde bir yer işareti simgesi ve yer işaretinin adı bulunur: *Kentsel*. 

![Yer işareti düğmesinin ekran görüntüsü](media/end-user-buttons/power-bi-bookmark.png)

Yer işareti düğmesini seçtiğinizde Power BI, ilgili yer işareti için tanımlanmış olan konumu ve ayarları uygular.  Bu örnekte yer işareti, raporun *Büyüme fırsatları* sayfasındadır ve ilgili sayfaya **Kentsel** çapraz filtresi uygulanmıştır.

![Kentsel için filtrelenmiş rapor sayfasının ekran görüntüsü](media/end-user-buttons/power-bi-urban.png)


## <a name="drillthrough-buttons"></a>Detaylandır düğmeleri
Power BI hizmetinde detaylandırmak için kullanabileceğiniz iki yöntem vardır. Detaylandırma sizi farklı bir rapor sayfasına götürür ve hedef sayfadaki veriler, kaynak sayfada belirlediğiniz filtrelere ve seçimlere göre sunulur.

Raporda detaylandırmayı kullanma yöntemlerinden biri, görseldeki veri noktalarından birine sağ tıklayıp **Detaylandır**'ı ve ardından hedefi seçmektir. Bu yöntem yukarıdaki **Geri düğmesi** başlıklı bölümde anlatılmıştır. Ancak rapor tasarımcıları bazen eylemi daha belirgin hale getirmek ve önemli içgörülere dikkat çekmek için detaylandırma *düğmesi* kullanır.  

Detaylandırma düğmelerinde birden fazla önkoşul olabilir. Tüm önkoşulları yerine getirmediğinizde düğme çalışmaz. Bir örneğe göz atalım.

Aşağıda bizi *Mağaza ayrıntıları* sayfasına götürecek olan bir detaylandırma düğmesi gösterilmiştir. Düğmenin üzerine geldiğinizde mağaza ve ürün seçmemiz gerektiğini bildiren bir araç ipucu görüntülenir. İki seçimi de yapana kadar düğmeyi seçemezsiniz.

![Üzerine gelindiğinde görünen ipucuna sahip detaylandırma düğmesinin ekran görüntüsü.](media/end-user-buttons/power-bi-drill-two-selections.png)

Bir ürün (**Sözcük**) ve bir mağaza (**Leo**) seçtiğimize göre düğmenin rengi değişir ve düğme etkin duruma gelir.

![Mağaza ayrıntıları için detaylandır düğmesinin ekran görüntüsü.](media/end-user-buttons/power-bi-select-both.png)

Detaylandırma düğmesini seçtiğinizde *Mağaza* rapor sayfası açılır. *Mağaza* sayfası **Sözcük** ve **Leo** seçimlerinize göre filtrelenir.

![Mağaza raporları sayfasının ekran görüntüsü.](media/end-user-buttons/power-bi-store.png)

Detaylandırma düğmelerinde hedef seçeneği sunan açılan menüler de bulunabilir. Kaynak rapor sayfasında gerekli seçimleri yaptıktan sonra detaylandırmak istediğiniz hedef rapor sayfasını seçebilirsiniz. Aşağıdaki örnekte detaylandırma seçimimizi *Pazar ayrıntıları* rapor sayfası olarak değiştiriyoruz. 

![Birden fazla hedefe sahip detaylandırma açılan menüsünün ekran görüntüsü](media/end-user-buttons/power-bi-destination.png)

## <a name="page-navigation"></a>Sayfa gezintisi

Sayfa gezintisi düğmeleri sizi aynı rapordaki farklı bir sayfaya götürür. Rapor tasarımcıları gezinti düğmelerini genellikle bir hikaye anlatmak veya rapor içgörüleri arasında gezinti yapmanızı sağlamak için oluşturur. Aşağıdaki örnekte rapor tasarımcısı, raporun her sayfasına eklediği düğmeyle sizi ilk sayfa olan üst düzey özet sayfasına geri yönlendirmektedir. Bu raporda çok fazla sayfa bulunduğundan bu sayfa gezinti düğmesi yararlıdır.

![Ekip puan kartı adlı sayfa gezintisi düğmesinin ekran görüntüsü.](media/end-user-buttons/power-bi-nav-button.png)


## <a name="qa-buttons"></a>Soru-Cevap düğmeleri 
Bir Soru-Cevap düğmesini seçtiğinizde Power BI Soru-Cevap Gezgini penceresi açılır. Soru-Cevap penceresi rapor sayfasının en üstünde görüntülenir ve X simgesinden kapatılabilir. [Soru-Cevap hakkında bilgi edinin](end-user-q-and-a.md)

![Verilerinizle ilgili bir soru sorun metninin yer aldığı Power BI Soru-Cevap Gezgini penceresinin ekran görüntüsü.](media/end-user-buttons/power-bi-qna.png)

## <a name="web-url"></a>Web URL'si
Web URL'si düğmeleri yeni bir tarayıcı penceresi açar. Rapor tasarımcıları bu tür düğmeleri başvuru kaynağı sunmak, kuruluşun web sitesine ya da yardım sayfasına bağlantı vermek veya farklı bir rapora ya da panoya bağlantı sağlamak için ekleyebilir. Aşağıdaki örnekte bulunan Web URL'si düğmesi, raporun kaynak dosyasını indirmenizi sağlar. 

Sayfa ayrı bir pencerede açıldığından Power BI raporuna dönmek için pencereyi kapatabilir veya Power BI sekmenizi seçebilirsiniz.

![PBIX dosyasını indir düğmesinin ve indirme bağlantısı bulunan yeni tarayıcı penceresinin ekran görüntüsü](media/end-user-buttons/power-bi-url.png)

## <a name="next-steps"></a>Sonraki adımlar
[Yer işaretleri](end-user-bookmarks.md)    
[Detaydan çıkma, detaya gitme](end-user-drill.md)
