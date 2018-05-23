---
title: Power BI Desktop'ta detaylandırma özelliğini kullanma
description: Power BI Desktop'ta yeni bir rapor sayfasında verilerin ayrıntılarına gitmeyi öğrenin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 8c9a0d075c6d55baa1f518874fa668a3f0db8cb3
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Power BI Desktop'ta detaylandırma özelliğini kullanma
**Power BI Desktop**'ta **detaylandırma** özelliğini kullanarak raporunuzda tedarikçi, müşteri veya üretici gibi belirli bir varlığa odaklanan bir sayfa oluşturabilirsiniz. Odaklanmış bu rapor sayfası sayesinde kullanıcılar, diğer rapor sayfalarındaki bir veri noktasına sağ tıklayıp ilgili bağlama göre filtrelenmiş olan ayrıntılara ulaşmak için, odaklanmış sayfaya geçebilirler.

![detaylandırmayı kullanma](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Detaylandırmayı kullanma
1. **Detaylandırma** özelliğini kullanmak üzere detaylandırma yapacağınız varlık türü için görmek istediğiniz görsellere sahip olan bir rapor sayfası oluşturun. 

    Örneğin, üreticiler için detaylandırma yapmak istiyorsanız toplam satış, gönderilen toplam ürün sayısı, kategoriye göre satış rakamları, bölgeye göre satış rakamları gibi görsellere sahip bir detaylandırma sayfası oluşturabilirsiniz. Bu sayede ilgili sayfada detaylandırma gerçekleştirdiğinizde görseller seçtiğiniz üreticiye özgü hale gelir.

2. Ardından söz konusu detaylandırma sayfasındaki **Görsel Öğeler** bölmesinin **Alanlar** bölümünde, detaylandırmak istediğiniz alanı **Detaylandırma filtreleri** kutusuna sürüklemeniz gerekir.

    ![iyi detaylandırma](media/desktop-drillthrough/drillthrough_02.png)

    **Detaylandırma filtreleri** kutusuna bir alan eklediğinizde **Power BI Desktop** otomatik olarak bir *geri* düğmesi görseli oluşturur. Bu görsel yayımlanmış raporlarda düğme haline gelir ve **Power BI hizmetinde** raporunuzu inceleyen kullanıcıların daha önce bulundukları rapor sayfasına (detaylandırma yapmayı seçtikleri sayfa) kolayca geri dönmesini sağlar.

    ![detaylandırma görüntüsü](media/desktop-drillthrough/drillthrough_03.png)

## <a name="use-your-own-image-for-a-back-button"></a>Geri düğmesi için kendi görüntünüzü kullanma    
 Geri düğmesi bir görüntü olduğu için istediğiniz görüntüyle değiştirebilirsiniz raporunuzu inceleyen kullanıcıların geldikleri sayfaya geri dönebilmesi için geri düğmesi olarak çalışmaya devam eder.

1. **Giriş** sekmesinde **Görüntü**’ye tıklayın, sonra görüntünüzü bulun ve detaylandırma sayfasına yerleştirin.
2. Detaylandırma sayfasında yeni görüntünüzü seçin ve Görüntü Biçimlendirme bölümü altında **Bağlantı** kaydırıcısını açık duruma ve **Tür** değerini **Geri** seçeneğine ayarlayın. Görüntünüz artık geri düğmesi olarak işlev görür.

    ![geri görüntüsünü kullanma](media/desktop-drillthrough/drillthrough_05.png)

    **Detaylandırma** sayfanız tamamladığında ve kullanıcılar, raporunuzda detaylandırma sayfanızın **Detaylandırma filtreleri** kutusuna yerleştirmiş olduğunuz alanı kullanan bir veri noktasına sağ tıkladığında, söz konusu sayfada detaylandırmayı destekleyen bir içerik menüsü görüntülenir.

    ![detaylandırma menüsü](media/desktop-drillthrough/drillthrough_04.png)

    Rapor kullanıcıları detaylandırmayı seçtiğinde, sayfa, tıkladıkları veri noktası hakkındaki bilgileri gösterecek şekilde filtrelenir. Örneğin, Contoso (bir üretici) hakkındaki bir veri noktasına sağ tıklayıp detaylandırmayı seçtiklerinde açılan detaylandırma sayfası, Contoso için filtrelenmiş verileri içerir.

## <a name="pass-all-filters-in-drillthrough"></a>Detaylandırmadaki tüm filtreleri geçirme

**Power BI Desktop**’ın Mayıs 2018 sürümünden itibaren tüm uygulanan filtreleri, detaylandırma penceresine geçirebilirsiniz. Örneğin, söz konusu kategoriye filtrelenen görsellerin ve ürünlerin yalnızca belirli bir kategorisini seçmiş ve sonra detaylandırmayı seçmiş olabilirsiniz. Tüm bu filtreler uygulandığında detaylandırmanın nasıl göründüğünü merak edebilirsiniz.

Tüm uygulanan filtreleri tutmak için, **Görselleştirmeler** bölmesinin **Detaylandırma** bölümünde **Tüm filtreleri geçir** iki durumlu düğmesini **açık** olarak ayarlayın. 

![tüm filtreleri tutma](media/desktop-drillthrough/drillthrough_06.png)

Mayıs 2018’den önceki **Power BI Desktop** sürümlerinde bu davranış, bu iki durumlu düğmenin **kapalı** olarak ayarlanmasına eşdeğerdir.

Daha sonra bir görsel üzerinde detaylandırma yaptığınızda, kaynak görselde geçici filtrelerin uygulanması sonucunda hangi filtrelerin uygulandığını görebilirsiniz. Detaylandırma penceresinde, bu geçici filtreler italik olarak gösterilir. 

![italik geçici filtreler](media/desktop-drillthrough/drillthrough_07.png)

Araç ipuçları sayfalarında bunu kullanabilirsiniz, ancak bu sorunlu bir deneyim olacaktır (araç ipucu düzgün çalışmaz), bu nedenle araç ipuçlarıyla bu filtrelerin kullanılması önerilmez.

## <a name="add-a-measure-to-drillthrough"></a>Detaylandırmak için bir ölçü ekleyin

Tüm filtreleri detaylandırma penceresine geçirmeye ek olarak detaylandırma alanına bir ölçü de (veya özetlenen sayısal sütun) ekleyebilirsiniz. Tek yapmanız gereken, detaylandırma alanını Detaylandırma kartına sürükleyerek uygulamaktır. 

![Detaylandırma için bir ölçü ekleyin](media/desktop-drillthrough/drillthrough_08.png)

Bir ölçü (veya özetlenen sayısal sütun) eklediğinizde, alan bir görselin *Değer* alanında kullanılıyorsa sayfayı detaylandırabilirsiniz.

Raporlarınızda **detaylandırma** özelliğini kullanmak için yapmanız gerekenler bu kadardır. Bu, detaylandırma filtreniz için seçtiğiniz varlık bilgilerini genişletilmiş görünümde göstermek için idealdir.

## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki makaleler de ilginizi çekebilir:

* [Power BI Desktop’ta dilimleyicileri kullanma](desktop-slicers.md)

