---
title: Power BI Desktop'ta gruplandırma ve gruplama özelliklerini kullanma
description: Power BI Desktop'ta öğeleri nasıl gruplandıracağınızı ve gruplayacağınızı öğrenin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: b8d742e9238d438775115fd1ee2e287cf0ba0388
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65454261"
---
# <a name="use-grouping-and-binning-in-power-bi-desktop"></a>Power BI Desktop'ta gruplandırma ve gruplama özelliklerini kullanma
**Power BI Desktop** görsel oluştururken, temel alınan verilerde bulunan değerlere bağlı olarak verilerinizi öbekler (veya gruplar) halinde toplar. Genellikle sorun çıkmaz ancak bu öbeklerin sunulma biçimini geliştirmek istediğiniz zamanlar olabilir. Örneğin, üç ürün kategorisini daha büyük bir kategoriye (bir *gruba*) yerleştirmek isteyebilirsiniz. Başka bir örnek vermek gerekirse, satış rakamlarını eşit olarak bölünmüş 923.983 dolarlık gruplar yerine 1.000.000 dolarlık gruplar halinde görmek isteyebilirsiniz.

Power BI Desktop'ta görsellerinizdeki verileri ve eğilimleri daha açık şekilde görüntülemek, çözümlemek ve araştırmak için veri noktalarını **gruplandırabilirsiniz**. Ayrıca, değerleri eşit boyutlu gruplara bölerek verileri anlamlı şekillerde görselleştirmenize olanak sağlayan **Gruplama boyutunu** da tanımlayabilirsiniz. (Genellikle *gruplama* adı verilir.)

## <a name="using-grouping"></a>Gruplandırma özelliğini kullanma
Gruplandırma özelliğinden yararlanmak için, öğeleri çoklu olarak seçmek üzere Ctrl tuşunu basılı tutarak görsellerdeki bir veya daha fazla öğeye tıklayabilirsiniz. Ardından, çoklu seçim öğelerinden birine sağ tıklayıp açılan menüden **Grup**'u seçin.

![](media/desktop-grouping-and-binning/grouping-binning_1.png)

Oluşturulan grup, görselin **Açıklama** demetine eklenir ve ayrıca **Alanlar** listesinde de görünür.

![](media/desktop-grouping-and-binning/grouping-binning_2.png)

Grup oluşturduktan sonra **Açıklama** demetindeki alana veya **Alanlar** listesine sağ tıklayıp **Grupları Düzenle**'yi seçerek bu grubun üyelerini kolayca düzenleyebilirsiniz.

![](media/desktop-grouping-and-binning/grouping-binning_3.png)

Açılan **Gruplar** penceresinde yeni grup oluşturabilir veya mevcut grupları değiştirebilirsiniz. Ayrıca, **Gruplar ve üyeler** kutusundaki grup başlığına çift tıklayıp yeni bir ad yazarak da herhangi bir grubu *yeniden adlandırabilirsiniz*.

Grupları kullanarak her türlü işlemi gerçekleştirebilirsiniz. **Gruplandırılmamış değerler** listesindeki öğeleri yeni bir gruba veya mevcut gruplardan birine ekleyebilirsiniz. Yeni bir grup oluşturmak için, **Gruplandırılmamış değerler** kutusundaki iki veya daha fazla öğeyi seçip (Ctrl tuşunu basılı tutup tıklayarak) bu kutunun altındaki **Grup** düğmesine tıklayın.

Gruplandırılmamış bir değeri mevcut bir gruba ekleyebilirsiniz: Bunun için Gruplandırılmamış değeri ve ardından bu değeri eklemek istediğiniz mevcut grubu seçip **Grup** düğmesine tıklamanız yeterlidir. Bir gruptan öğe kaldırmak için söz konusu öğeyi **Gruplar ve üyeler** kutusundan seçip **Grubu Çöz**'e tıklayın. Ayrıca, gruplandırılmamış kategorilerin **Diğer** grubuna yerleştirilip yerleştirilmeyeceğine ya da gruplandırılmadan bırakılıp bırakılmayacağına da karar verebilirsiniz.

![](media/desktop-grouping-and-binning/grouping-binning_4.png)

> [!NOTE]
> **Alanlar** bölmesinde mevcut bir görselden çoklu seçim yapmak zorunda kalmadan herhangi bir alan için grup oluşturabilirsiniz. Yalnızca söz konusu alana sağ tıklayıp açılan menüden **Yeni Grup**'u seçin.

## <a name="using-binning"></a>Gruplamayı kullanma
**Power BI Desktop**'ta sayısal alanlar ve saat alanları için gruplama boyutunu ayarlayabilirsiniz. **Power BI Desktop**'ın görüntülediği verileri düzgün bir şekilde boyutlandırmak için gruplama özelliğini kullanabilirsiniz.

Bir gruplama boyutu uygulamak için bir **Alan**'a sağ tıklayıp **Yeni Grup**’u seçin.

![](media/desktop-grouping-and-binning/grouping-binning_5.png)

**Gruplar** penceresinde, **Gruplama boyutunu** istediğiniz boyuta ayarlayın.

![](media/desktop-grouping-and-binning/grouping-binning_6.png)

**Tamam**'ı seçtiğinizde **Alanlar** bölmesinin *(bölmeler)* eklenmiş olarak görüntülendiğini fark edeceksiniz. Daha sonra gruplama boyutunu bir görselde kullanmak için bu alanı tuvale sürükleyebilirsiniz.

![](media/desktop-grouping-and-binning/grouping-binning_7.png)

**Gruplamayı** uygulamalı olarak görmek için bu [videoya](https://www.youtube.com/watch?v=BRvdZSfO0DY) göz atın.

Böylece, raporlarınızdaki görsellerin istediğiniz şekilde gösterilmesini sağlamak için **gruplandırma** ve **gruplama** özelliklerini kullanarak gerçekleştirebileceğiniz tüm işlemlere değinmiş olduk.

