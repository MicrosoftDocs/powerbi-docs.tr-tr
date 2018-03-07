---
title: "Power BI Desktop'ta detaylandırma özelliğini kullanma"
description: "Power BI Desktop'ta yeni bir rapor sayfasında verilerin ayrıntılarına gitmeyi öğrenin"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f4cf7b0b850445b794c092f01b7e9a837ca3f215
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Power BI Desktop'ta detaylandırma özelliğini kullanma
**Power BI Desktop**'ta **detaylandırma** özelliğini kullanarak raporunuzda tedarikçi, müşteri veya üretici gibi belirli bir varlığa odaklanan bir sayfa oluşturabilirsiniz. Odaklanmış bu rapor sayfası sayesinde kullanıcılar, diğer rapor sayfalarındaki bir veri noktasına sağ tıklayıp ilgili bağlama göre filtrelenmiş olan ayrıntılara ulaşmak için, odaklanmış sayfaya geçebilirler.

![](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Detaylandırmayı kullanma
**Detaylandırma** özelliğini kullanmak için detaylandırma yapacağınız varlık türü hakkında görmek istediğiniz görsellere sahip olan bir rapor sayfası oluşturun. Örneğin, üreticiler için detaylandırma yapmak istiyorsanız toplam satış, gönderilen toplam ürün sayısı, kategoriye göre satış rakamları, bölgeye göre satış rakamları gibi görsellere sahip bir detaylandırma sayfası oluşturabilirsiniz. Bu sayede ilgili sayfada detaylandırma gerçekleştirdiğinizde görseller tıkladığınız ve detaylandırma yapmak istediğiniz üreticiye özgü hale gelir.

Ardından söz konusu detaylandırma sayfasındaki **Görsel Öğeler** bölmesinin **Alanlar** bölümünde, detaylandırmak istediğiniz alanı **Detaylandırma filtreleri** kutusuna sürüklemeniz gerekir.

![](media/desktop-drillthrough/drillthrough_02.png)

**Detaylandırma filtreleri** kutusuna bir alan eklediğinizde **Power BI Desktop** otomatik olarak bir *geri* düğmesi görseli oluşturur. Bu görsel yayımlanmış raporlarda düğme haline gelir ve **Power BI hizmetinde** raporunuzu inceleyen kullanıcıların daha önce bulundukları rapor sayfasına (detaylandırma yapmayı seçtikleri sayfa) kolayca geri dönmesini sağlar.

![](media/desktop-drillthrough/drillthrough_03.png)

*Geri* düğmesi bir görüntü olduğu için bunu istediğiniz görüntüyle değiştirebilirsiniz. Bu işlemden sonra da düğme olarak çalışmaya devam eder ve raporunuzu inceleyen kullanıcıları geldikleri sayfaya geri dönmesini sağlar. Geri düğmesi için kendi seçtiğiniz bir görüntüyü kullanmak isterseniz detaylandırma sayfasına bir görüntü görseli yerleştirip bunu seçtikten sonra *Geri düğmesi* kaydırıcısını Açık konuma getirmeniz yeterlidir. Bu sayede görüntünüz *geri* düğmesi görevi görür.

![](media/desktop-drillthrough/drillthrough_05.png)

**Detaylandırma** sayfanızı tamamladığınızda, kullanıcılar, raporunuzda detaylandırma sayfanızın **Detaylandırma filtreleri** kutusuna yerleştirmiş olduğunuz bir alanı kullanan veri noktasına sağ tıklayarak, söz konusu sayfada detaylandırma yapmalarını sağlayan bir bağlam menüsü ile karşılaşır.

![](media/desktop-drillthrough/drillthrough_04.png)

Kullanıcılar detaylandırmayı seçtiğinde, sayfa, tıkladıkları veri noktası hakkındaki bilgileri gösterecek şekilde filtrelenir. Örneğin, Contoso (bir üretici) hakkındaki bir veri noktasına sağ tıklayıp detaylandırmayı seçtiklerinde açılan detaylandırma sayfası, Contoso için filtrelenmiş verileri içerir.

> [!NOTE]
> Yalnızca **Detaylandırma filtreleri** bölmesinde bulunan alan, detaylandırma rapor sayfasına geçirilir. Diğer bağlam bilgileri geçirilmez.
> 
> 

Raporlarınızda **detaylandırma** özelliğini kullanmak için yapmanız gerekenler bu kadardır. Bu, detaylandırma filtreniz için seçtiğiniz varlık bilgilerini genişletilmiş görünümde göstermek için idealdir.

