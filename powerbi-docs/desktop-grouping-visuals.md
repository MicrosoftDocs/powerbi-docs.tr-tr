---
title: Power BI Desktop'ta gruplandırmayı kullanma
description: Power BI Desktop'ta görselleri nasıl gruplandıracağınızı öğrenin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/12/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 6b6266547704077769174c2ae0a9675503f10dca
ms.sourcegitcommit: a77977a43342db4399a4dffb862b96907d16de35
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2019
ms.locfileid: "69029592"
---
# <a name="use-grouping-in-power-bi-desktop"></a>Power BI Desktop'ta gruplandırmayı kullanma
**Power BI Desktop**’ta **gruplandırma** özelliğini kullanarak raporunuzdaki düğmeleri, metin kutularını, şekilleri, görüntüleri ve oluşturduğunuz her türlü görseli gruplandırabilirsiniz. Bir rapordaki görsellerin gruplandırılması, grubu tek bir nesne gibi ele almanızı sağlar, böylece taşımayı, yeniden boyutlandırmayı ve raporunuzdaki katmanlarla çalışmayı daha kolay, daha hızlı ve daha sezgisel hale getirir.

![Gruplandırma özelliğini kullanma](media/desktop-grouping-visuals/grouping-visuals-01.png)


## <a name="creating-groups"></a>Grup oluşturma

Power BI Desktop’ta bir görsel grubu oluşturmak için tuvalden ilk görseli seçin, sonra CTRL düğmesini basılı tutarak grupa eklemek istediğiniz bir veya daha fazla görsele daha tıklayın, sonra görsel koleksiyonuna sağ tıklayıp görüntülenen menüden **Grup**’u seçin.

![gruplandırılacak iki veya daha fazla öğe seçme](media/desktop-grouping-visuals/grouping-visuals-02.png)

Gruplar **Seçim** bölmesinde görüntülenir. Raporunuz için gereken sayıda görsel grubu oluşturabilir ve ayrıca görsel gruplarını iç içe yerleştirebilirsiniz. Aşağıdaki görüntüde, *Avustralya* grubu *Kartlar* grubunun altına yerleştirilmiştir. Grup adının yanındaki şapka karakterini seçerek grubu genişletebilir, şapka karakterini tekrar seçerek grubu daraltabilirsiniz. 

![grupları iç içe yerleştirme](media/desktop-grouping-visuals/grouping-visuals-03.png)

**Seçim** bölmesinde, görselleri bir gruba eklemek, gruptan çıkarmak, bir grubu iç içe yerleştirmek veya iç içe yerleştirilmiş gruptan tek bir görsel çıkarmak için tek tek sürükleyip bırakabilirsiniz. Ayarlamak istediğiniz görseli sürükleyip istediğiniz yere yerleştirmeniz yeterlidir. Çakışma varsa, görsellerin katmanları *Katman sırası* listesindeki sıralarına göre belirlenir.

![grupları sürükleyip bırakma](media/desktop-grouping-visuals/grouping-visuals-04.png)

Grubu çözmek için grubu seçin, sağ tıklayın ve açılan menüden **grubu çöz**’ü seçin.

## <a name="hide-and-show-visuals-or-groups"></a>Görselleri veya grupları gizleme ve gösterme

**Seçim** bölmesini kullanarak grupları kolayca gizleyebilir veya gösterebilirsiniz. Bir grubu gizlemek için, grup (veya tek görsel) adının yanındaki göz düğmesini seçerek görseli veya grubu gizli ya da görünür hale getirin. Aşağıdaki görüntüde, *Avustralya* grubu gizlidir ve *Kartlar* grubunda iç içe yerleştirilmiş grupların geri kalanı gösterilmektedir.


![grupları gizleme ve görüntüleme](media/desktop-grouping-visuals/grouping-visuals-05.png)

Bir grubu gizlediğinizde, o grubun içindeki tüm görseller gizlenir ve bu durum, göz düğmesinin gri olmasıyla gösterilir (tüm grup gizli olduğundan kapatılıp açılamaz). Bir grup içinde yalnızca belirli görselleri gizlemek için, ilgili görselin yanındaki göz düğmesini açık duruma getirdiğinizde yalnızca gruptaki o görsel gizlenir.

## <a name="selecting-visuals-within-a-group"></a>Bir grup içinde görseller seçme

Bir görsel grubu içinde gezinip öğe seçmenin birkaç yolu vardır. Aşağıdaki listede davranış açıklanmaktadır:

* Bir grup içinde boş bir alana tıklandığında (görseller arasındaki boşluk gibi) hiçbir şey seçilmez
* Bir grup içindeki görsele tıklandığında tüm grup seçilir, ikinci kez tıkladığında tek görsel seçilir
* Bir grup ve sonra rapor kanvasındaki başka bir nesneyi seçmek, ardından da sağ tıklama menüsünden **Grup**'u seçmek iç içe yerleştirilmiş bir grup oluşturur
* İki grup seçtikten sonra sağ tıklamak, seçili grupları iç içe yerleştirmek yerine birleştirme seçeneğini gösterir

## <a name="apply-background-color"></a>Arka plan rengi uygulama

Ayrıca, aşağıdaki görüntüde gösterildiği gibi **Görselleştirmeler** bölmesinin **Biçimlendirme** bölümünü kullanarak bir gruba arka plan rengi uygulayabilirsiniz. 

![gruplar için arka plan rengi](media/desktop-grouping-visuals/grouping-visuals-06.png)

Arka plan rengi uyguladıktan sonra gruptaki görseller arasında bulunan boşluğa tıkladığınızda grup seçilir (bu işlemi, bir gruptaki görseller arasında bulunan boşluğa tıkladığınızda grubu seçmeyen işlemle karşılaştırın). 


## <a name="next-steps"></a>Sonraki adımlar
Gruplandırma daha fazla bilgi edinmek için aşağıdaki videoya göz atın:

* [Power BI Desktop'ta gruplandırma - video](https://youtu.be/sf4n7VXoQHY?t=10)

Aşağıdaki makaleler de ilginizi çekebilir:

* [Power BI Desktop'ta çapraz rapor detaylandırma özelliğini kullanma](desktop-cross-report-drill-through.md)
* [Power BI Desktop’ta dilimleyicileri kullanma](visuals/power-bi-visualization-slicers.md)

