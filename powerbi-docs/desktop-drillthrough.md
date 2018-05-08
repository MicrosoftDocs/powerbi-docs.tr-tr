---
title: Power BI Desktop'ta detaylandırma özelliğini kullanma
description: Power BI Desktop'ta yeni bir rapor sayfasında verilerin ayrıntılarına gitmeyi öğrenin
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 4/10/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 7be260a5989ffb6a9dc1b72dad90d227e0b6295b
ms.sourcegitcommit: bdb1fee3612bcc66153dcad8c4db2e99fb041014
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="use-drillthrough-in-power-bi-desktop"></a>Power BI Desktop'ta detaylandırma özelliğini kullanma
**Power BI Desktop**'ta **detaylandırma** özelliğini kullanarak raporunuzda tedarikçi, müşteri veya üretici gibi belirli bir varlığa odaklanan bir sayfa oluşturabilirsiniz. Odaklanmış bu rapor sayfası sayesinde kullanıcılar, diğer rapor sayfalarındaki bir veri noktasına sağ tıklayıp ilgili bağlama göre filtrelenmiş olan ayrıntılara ulaşmak için, odaklanmış sayfaya geçebilirler.

![](media/desktop-drillthrough/drillthrough_01.png)

## <a name="using-drillthrough"></a>Detaylandırmayı kullanma
1. **Detaylandırma** özelliğini kullanmak üzere detaylandırma yapacağınız varlık türü için görmek istediğiniz görsellere sahip olan bir rapor sayfası oluşturun. 

    Örneğin, üreticiler için detaylandırma yapmak istiyorsanız toplam satış, gönderilen toplam ürün sayısı, kategoriye göre satış rakamları, bölgeye göre satış rakamları gibi görsellere sahip bir detaylandırma sayfası oluşturabilirsiniz. Bu sayede ilgili sayfada detaylandırma gerçekleştirdiğinizde görseller seçtiğiniz üreticiye özgü hale gelir.

2. Ardından söz konusu detaylandırma sayfasındaki **Görsel Öğeler** bölmesinin **Alanlar** bölümünde, detaylandırmak istediğiniz alanı **Detaylandırma filtreleri** kutusuna sürüklemeniz gerekir.

    ![](media/desktop-drillthrough/drillthrough_02.png)

    **Detaylandırma filtreleri** kutusuna bir alan eklediğinizde **Power BI Desktop** otomatik olarak bir *geri* düğmesi görseli oluşturur. Bu görsel yayımlanmış raporlarda düğme haline gelir ve **Power BI hizmetinde** raporunuzu inceleyen kullanıcıların daha önce bulundukları rapor sayfasına (detaylandırma yapmayı seçtikleri sayfa) kolayca geri dönmesini sağlar.

    ![](media/desktop-drillthrough/drillthrough_03.png)

## <a name="use-your-own-image-for-a-back-button"></a>Geri düğmesi için kendi görüntünüzü kullanma    
 Geri düğmesi bir görüntü olduğu için istediğiniz görüntüyle değiştirebilirsiniz raporunuzu inceleyen kullanıcıların geldikleri sayfaya geri dönebilmesi için geri düğmesi olarak çalışmaya devam eder.

1. **Giriş** sekmesinde **Görüntü**’ye tıklayın, sonra görüntünüzü bulun ve detaylandırma sayfasına yerleştirin.
2. Detaylandırma sayfasında yeni görüntünüzü seçin ve Görüntü Biçimlendirme bölümü altında **Bağlantı** kaydırıcısını açık duruma ve **Tür** değerini **Geri** seçeneğine ayarlayın. Görüntünüz artık geri düğmesi olarak işlev görür.

    ![](media/desktop-drillthrough/drillthrough_05.png)

    **Detaylandırma** sayfanız tamamladığında ve kullanıcılar, raporunuzda detaylandırma sayfanızın **Detaylandırma filtreleri** kutusuna yerleştirmiş olduğunuz alanı kullanan bir veri noktasına sağ tıkladığında, söz konusu sayfada detaylandırmayı destekleyen bir içerik menüsü görüntülenir.

    ![](media/desktop-drillthrough/drillthrough_04.png)

    Rapor kullanıcıları detaylandırmayı seçtiğinde, sayfa, tıkladıkları veri noktası hakkındaki bilgileri gösterecek şekilde filtrelenir. Örneğin, Contoso (bir üretici) hakkındaki bir veri noktasına sağ tıklayıp detaylandırmayı seçtiklerinde açılan detaylandırma sayfası, Contoso için filtrelenmiş verileri içerir.

    > [!NOTE]
    > Yalnızca **Detaylandırma filtreleri** kutusundaki alan detaylandırma rapor sayfasına geçirilir. Diğer bağlam bilgileri geçirilmez.
    > 
    > 

Raporlarınızda **detaylandırma** özelliğini kullanmak için yapmanız gerekenler bu kadardır. Bu, detaylandırma filtreniz için seçtiğiniz varlık bilgilerini genişletilmiş görünümde göstermek için idealdir.

