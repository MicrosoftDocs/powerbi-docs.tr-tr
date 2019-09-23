---
title: Görsel öğeler kullanarak Power BI raporlarını geliştirme
description: Duvar kağıdı ve görsel üst bilgi gibi görsel öğeleri kullanarak raporları geliştirme
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 87d530bdf966e549e67427f68fa8b23895120e48
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514062"
---
# <a name="use-visual-elements-to-enhance-power-bi-reports"></a>Görsel öğeler kullanarak Power BI raporlarını geliştirme

**Power BI Desktop** ile, raporlarınızın görünümünü geliştirmek için duvar kağıdı ve görselleştirmelere yönelik geliştirilmiş görsel üst bilgiler gibi görsel öğeler kullanabilirsiniz.

![Raporları geliştirmek için duvar kağıdı ve küçük görsel üst bilgiler ekleme](media/desktop-visual-elements-for-reports/visual-elements-for-reports_01.png)

**Power BI Desktop**'ın Temmuz 2018 sürümünden başlayarak, raporlarınızda kullanılacak geliştirmeler yapabilir, analizleriniz ve raporlarınızın eskisinden daha da cazip olmasını sağlayabilirsiniz. Bu makalede açıklanan geliştirmeler şunlardır: 

* Arka planınızın verilerinizle anlatmak istediğiniz hikayeyi geliştirmesi veya öğelerini vurgulaması için raporlarınıza **duvar kağıdı** uygulama
* Rapor tuvalinizde mükemmel hizalanmış görseller oluşturmak için, tek tek görselleştirmeler için geliştirilmiş **görsel üst bilgiler** kullanma. 

Aşağıdaki bölümlerde bu geliştirmelerin nasıl kullanılacağı ve bunların raporlarınıza nasıl uygulanacağı açıklanır.

## <a name="using-wallpaper-in-power-bi-reports"></a>Power BI raporlarında duvar kağıdı kullanma

Rapor sayfanızın dışındaki gri alanı **duvar kağıdı** kullanarak biçimlendirebilirsiniz. Aşağıdaki görüntüde, duvar kağıdının nereye uygulandığını netleştiren bir ok vardır. 

![Duvar kağıdı raporun çevresindeki gri alanı kaplar](media/desktop-visual-elements-for-reports/visual-elements-for-reports_02.png)

Duvar kağıdını her rapor sayfası için ayarlayabileceğiniz gibi, aynı duvar kağıdının raporunuzun her sayfasında kullanılmasını da sağlayabilirsiniz. Duvar kağıdınızı ayarlamak için, raporunuzda hiçbir görsel seçili değilken **Biçimlendirme** simgesine dokunun veya tıklayın; bölmede **Duvar kağıdı** kartı gösterilir.

![Biçimlendirme bölmesinde Duvar Kağıdı alanı](media/desktop-visual-elements-for-reports/visual-elements-for-reports_03.png)

**Renk** açılan listesini seçerek **duvar kağıdı** olarak uygulanacak bir renk belirtebilir veya **Görüntü Ekle** düğmesini seçerek duvar kağıdı olarak uygulanacak görüntüyü belirtebilirsiniz. Ayrıca duvar kağıdınız ister renk ister görüntü olsun, **Saydamlık** kaydırıcısını kullanarak duvar kağıdı için saydamlık da ayarlayabilirsiniz.

**Duvar kağıdı** için geçerli olan aşağıdaki tanımları da aklınızda bulundurmanız yararlı olur:

* Rapor alanınızın dışındaki gri alan, **duvar kağıdı** alanıdır
* Tuvalde görselleri yerleştirebileceğiniz alan rapor **sayfası** olarak adlandırılır ve **Biçim bölmesinde** **Sayfa arka planı** açılan listesi kullanılarak değiştirilebilir.

Rapor **sayfası** her zaman ön plandadır (duvar kağıdıyla karşılaştırıldığında), **duvar kağıdı** bunun arkasında yer alır ve rapor sayfasının er gerideki öğesidir. Sayfaya saydamlık uyguladığınızda raporunuzdaki görsellere de saydamlık uygulanır; böylelikle arka planınız görsellerinizin arasından görünür durumda olur.

Tüm yeni raporlar için varsayılan ayarlar şöyledir:

* Rapor **sayfası** **beyaz** ve saydamlığı da **%100** olarak ayarlanır
* **Duvar kağıdı** **beyaz** renge ve saydamlığı da **%0**'a ayarlanır

Sayfa arka planınızı %50'den yüksek bir saydamlığa ayarladığınızda, raporunuzu oluşturur veya düzenlerken size rapor tuvalinin sınırındaki kenarlığı göstermek için noktalı bir kenarlık görüntülenir. 

![%50'den yüksek bir saydamlık noktalı kenarlığa neden olur](media/desktop-visual-elements-for-reports/visual-elements-for-reports_04.png)

Noktalı kenarlığın *yalnızca* raporunuz düzenlenirken gösterildiğini ve yayımlanan raporunuz kişiler tarafından görüntülenirken, örneğin *Power BI hizmetinde* görüntülenirken bu kenarlığın **gösterilmediğini** anımsamak önemlidir.

> [!NOTE]
> Duvar kağıdı olarak koyu renkli arka planlar kullanıyor ve metin rengini çok açık veya beyaz olarak ayarlıyorsanız **PDF'ye dışarı aktar** özelliği duvar kağıdını dışarı aktarmayacağından beyaz yazı tiplerinin oluşturulan PDF dosyasında görünmeyebileceğini unutmayın. **PDF'ye dışarı aktar** özelliği hakkında daha fazla bilgi için bkz. [PDF'ye dışarı aktarma](desktop-export-to-pdf.md).


## <a name="using-improved-visual-headers-in-power-bi-reports"></a>Power BI raporlarında geliştirilmiş görsel üst bilgiler kullanma

**Power BI Desktop**'ın Temmuz 2018 tarihli sürümünden başlayarak, raporlardaki görsellerin üst bilgileri önemli ölçüde geliştirildi. Başlıca geliştirmeler üst bilginin görselden ayrılması, böylelikle konumunun tercih ettiğiniz düzen ve yerleşime göre ayarlanabilmesi ve üst bilginin artık görselin üstünde kaymak yerine içinde gösterilmesidir. 

Varsayılan olarak, üst bilgi başlıkla hizalanmış üst bilginin içinde gösterilir. Aşağıdaki görüntüde, üst bilgiyi (sabitle simgesi, genişlet simgesi ve üç nokta simgesi) görselin içinde, sağa hizalanmış olarak ve görselin başlığıyla aynı yatay konum üzerinde görebilirsiniz.

![Görsel üst bilgileri şimdi görselin içinde durabilir veya taşınabilir](media/desktop-visual-elements-for-reports/visual-elements-for-reports_05.png)

Görselinizin başlığı yoksa, aşağıdaki görüntüde gösterildiği gibi üst bilgi görselin üst kısmında sağa hizalanmış olarak kaydırılır. 

![Başlık yoksa görsel üst bilgiler görsellerin üzerinde kayar](media/desktop-visual-elements-for-reports/visual-elements-for-reports_07.png)

Görsel raporunuzun en üstüne konumlandırıldıysa, görsel üst bilgisi görselin altına yaslanır. 

![Raporun üst kenarlığında yer aldığında, görsel üst bilgileri alta yaslanır](media/desktop-visual-elements-for-reports/visual-elements-for-reports_08.png)

Her görselin **Görselleştirmeler** bölmesinin **Biçimlendirme** bölümünde **Görsel üst bilgi** adlı bir de kartı vardır. Bu kartta görsel üst bilginin her türlü özelliğini ayarlayabilirsiniz

![Her görselin Biçimlendirme bölmesinde bir Görsel üst bilgi kartı vardır](media/desktop-visual-elements-for-reports/visual-elements-for-reports_09.png)

> [!NOTE]
> Siz raporu yazar veya düzenlerken, geçişlerin görünürlüğü raporunuzu etkilemez. Raporu yayımlamalı ve etkiyi görmek için rapora okuma modunda bakabilirsiniz. Bu davranış, görsel üst bilgilerde sağlanan birçok seçeneğin, özellikle de düzenlemenin sorunlarını size bildiren uyarı simgelerinin düzenleme sırasında önemli olmasını güvence altına alır.

Yalnızca **Power BI hizmetinde** gösterilen raporlar için, **Çalışma Alanım > Raporlar**'a gidip **Ayarlar** simgesini seçerek görsel üst bilgilerin kullanımını ayarlayabilirsiniz. Orada, **Ayarlar** simgesini seçtiğiniz raporun ayarlarını görür ve aşağıdaki görüntüde gösterildiği gibi ayarları belirleyebilirsiniz.

![Power BI hizmetinde geliştirilmiş görsel üst bilgileri kullanma ayarları](media/desktop-visual-elements-for-reports/visual-elements-for-reports_10.png)

### <a name="enabling-improved-visual-headers-for-existing-reports"></a>Mevcut raporlar için geliştirilmiş görsel üst bilgileri etkinleştirme

Yeni görsel üst bilgi, tüm yeni raporlarda varsayılan davranıştır. Mevcut raporlar için, **Dosya > Seçenekler ve ayarlar > Seçenekler**'e giderek ve ardından **Rapor ayarları** bölümünde **Modern görsel üst bilgiyi güncelleştirilmiş stil oluşturma seçenekleri ile birlikte kullanın** onay kutusunu etkinleştirerek **Power BI Desktop**'ta bu davranışı etkinleştirmeniz gerekir.

![Mevcut raporların geliştirilmiş görsel üst bilgileri kullanması için Seçenekler'in işaretlenmesi gerekir](media/desktop-visual-elements-for-reports/visual-elements-for-reports_06.png)


## <a name="next-steps"></a>Sonraki adımlar
**Power BI Desktop** ve Power BI Desktop'la çalışmaya başlama hakkında daha fazla bilgi için aşağıdaki makalelere başvurun.

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop ile Sorgulara Genel Bakış](desktop-query-overview.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'taki Verilere Bağlanma](desktop-connect-to-data.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki Genel Sorgu Görevleri](desktop-common-query-tasks.md)   

