---
title: Power BI Desktop'ta gruplandırma ve gruplama özelliklerini kullanma
description: Power BI Desktop'ta öğeleri nasıl gruplandıracağınızı ve gruplayacağınızı öğrenin
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 01/13/2021
LocalizationGroup: Create reports
ms.openlocfilehash: a44b6cbbc0517bee50d14447e790f6491483a894
ms.sourcegitcommit: 1cad78595cca1175b82c04458803764ac36e5e37
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2021
ms.locfileid: "98565873"
---
# <a name="use-grouping-and-binning-in-power-bi-desktop"></a>Power BI Desktop'ta gruplandırma ve gruplama özelliklerini kullanma
Power BI Desktop görsel oluştururken, temel alınan verilerde bulunan değerlere bağlı olarak verilerinizi öbekler (veya gruplar) halinde toplar. Genellikle sorun çıkmaz ancak bu öbeklerin sunulma biçimini geliştirmek istediğiniz zamanlar olabilir. Örneğin, üç ürün kategorisini daha büyük bir kategoriye (bir *gruba*) yerleştirmek isteyebilirsiniz. Başka bir örnek vermek gerekirse, satış rakamlarını 923.983 dolarlık parçalar yerine 1.000.000 dolarlık gruplar halinde görmek isteyebilirsiniz.

Power BI Desktop'ta görsellerinizdeki verileri ve eğilimleri daha açık şekilde görüntülemek, çözümlemek ve araştırmak için veri noktalarını *gruplandırabilirsiniz*. Ayrıca, değerleri eşit boyutlu gruplara bölerek verileri anlamlı şekillerde görselleştirmenize olanak sağlayan *gruplama boyutunu* da tanımlayabilirsiniz. Bu eylem genellikle *gruplama* olarak adlandırılır.

## <a name="using-grouping"></a>Gruplandırma özelliğini kullanma
Gruplandırma özelliğinden yararlanmak için, öğeleri çoklu olarak seçmek üzere Ctrl tuşunu basılı tutarak görsellerdeki bir veya daha fazla öğeye tıklayabilirsiniz. Ardından çoklu seçime dahil olan öğelerden birine sağ tıklayıp bağlam menüsünden **Grup**'u seçin.

![Gruplandır komutu, grafik, Gruplandırma, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_1.png)

Oluşturulan grup, görselin **Açıklama** demetine eklenir. Grup ayrıca **Alanlar** listesinde de görünür.

![Açıklama ve Alanlar listeleri, gruplandırma, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_2.png)

Oluşturduğunuz grubun üyelerini kolayca düzenleyebilirsiniz. **Açıklama** demetinde veya **Alanlar** listesinde alana sağ tıklayın ve **Grupları Düzenle**'yi seçin.

![Grupları Düzenle komutu, Açıklama ve Alanlar listeleri, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_3.png)

**Gruplar** iletişim kutusunda yeni grup oluşturabilir veya mevcut grupları değiştirebilirsiniz. Ayrıca grupları *yeniden adlandırabilirsiniz*. Tek yapmanız gereken **Gruplar ve üyeler** kutusundaki grup adına çift tıklayıp yeni bir ad girmektir.

Grupları kullanarak her türlü işlemi gerçekleştirebilirsiniz. **Gruplandırılmamış değerler** listesindeki öğeleri yeni bir gruba veya mevcut gruplardan birine ekleyebilirsiniz. Yeni bir grup oluşturmak için, **Gruplandırılmamış değerler** kutusundaki iki veya daha fazla öğeyi seçip (Ctrl tuşunu basılı tutup tıklayarak) bu kutunun altındaki **Grup** düğmesini seçin.

Gruplandırılmamış bir değeri mevcut bir gruba ekleyebilirsiniz: Bunun için **Gruplandırılmamış değerlerden** birini ve ardından bu değeri eklemek istediğiniz mevcut grubu seçip **Grup** düğmesini seçmeniz yeterlidir. Bir gruptan öğe kaldırmak için söz konusu öğeyi **Gruplar ve üyeler** kutusundan seçip **Grubu Çöz**'ü seçin. İsterseniz gruplandırılmamış kategorileri **Diğer** grubuna taşıyabilir veya gruplandırılmamış şekilde bırakabilirsiniz.

![Gruplar iletişim kutusu, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_4.png)

> [!NOTE]
> **Alanlar** kutusunda mevcut bir görselden çoklu seçim yapmak zorunda kalmadan herhangi bir alan için grup oluşturabilirsiniz. Yalnızca söz konusu alana sağ tıklayıp açılan menüden **Yeni Grup**'u seçin.

## <a name="using-binning"></a>Gruplamayı kullanma
**Power BI Desktop**'ta sayısal alanlar ve saat alanları için gruplama boyutunu ayarlayabilirsiniz. Hesaplanmış sütunlarınız için bölmeler oluşturabilirsiniz ancak bunu ölçüleriniz için yapamazsınız. Power BI Desktop'ın görüntülediği verileri düzgün bir şekilde boyutlandırmak için gruplama özelliğini kullanın.

Bir gruplama boyutu uygulamak için bir **Alan**'a sağ tıklayıp **Yeni Grup**’u seçin.

![Yeni Grup komutu, Alanlar listesi, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_5.png)

**Gruplar** iletişim kutusunda, **Gruplama boyutunu** istediğiniz boyuta ayarlayın.

![Grup boyutu, Gruplar iletişim kutusu, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_6.png)

**Tamam**'ı seçtiğinizde **Alanlar** bölmesinin **(bölmeler)** eklenmiş olarak görüntülendiğini fark edeceksiniz. Bu alanı tuvale sürükleyerek bölme boyutunu istediğiniz görselde kullanabilirsiniz.

![Gruplar alanını tuvale sürükleme, Power BI Desktop](media/desktop-grouping-and-binning/grouping-binning_7.png)

*Gruplamayı* uygulamalı olarak görmek için bu [videoya](https://www.youtube.com/watch?v=BRvdZSfO0DY) göz atın.

Böylece, raporlarınızdaki görsellerin istediğiniz şekilde gösterilmesini sağlamak için *gruplandırma* ve *gruplama* özelliklerini kullanarak gerçekleştirebileceğiniz tüm işlemlere değinmiş olduk.
