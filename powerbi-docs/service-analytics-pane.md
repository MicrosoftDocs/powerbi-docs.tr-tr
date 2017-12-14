---
title: "Power BI hizmetindeki Analiz bölmesi"
description: "Power BI hizmetinde görseller için dinamik başvuru çizgileri oluşturma"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 05/02/2017
ms.author: mihart
ms.openlocfilehash: 30fc0731f819f063aa04e856e8acc75a69f64a59
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="analytics-pane-in-power-bi-service"></a>Power BI hizmetindeki Analiz bölmesi
**Power BI hizmetindeki** **Analiz** bölmesini kullanarak görselleştirmelere dinamik *başvuru çizgileri* ekleyebilir ve önemli eğilimlere veya öngörülere odaklanılmasını sağlayabilirsiniz.

![](media/service-analytics-pane/power-bi-analytics-pane.png)

> [!NOTE]
> **Analiz** bölmesi yalnızca rapor tuvalinde bir görsel seçmeniz halinde görünür.
> 
> 

## <a name="using-the-analytics-pane"></a>Analiz bölmesini kullanma
**Analiz** bölmesi ile aşağıdaki türlerde dinamik başvuru çizgileri (kullanılabilen çizgiler görsel türüne göre değişiklik gösterir) oluşturabilirsiniz:

* X Ekseni sabit çizgisi
* Y Ekseni sabit çizgisi
* Min. çizgi
* Maks. çizgi
* Ortalama çizgisi
* Ortanca çizgisi
* Yüzdebirlik çizgisi

Aşağıdaki bölümlerde, **Analiz** bölmesini ve dinamik başvuru çizgilerini görselleştirmelerinizde nasıl kullanabileceğiniz gösterilmiştir.

Bir görsel için kullanılabilen dinamik başvuru çizgilerini görüntülemek için şu adımları uygulayın:

1. Bir görsel oluşturun veya seçin, ardından **Görsel Öğeler** bölmesindeki **Analiz** simgesini ![](media/service-analytics-pane/power-bi-analytics-icon.png)seçin.
2. Oluşturmak istediğiniz çizgi türüne ilişkin aşağı oku belirleyerek söz konusu çizgi türünün seçeneklerini genişletin. Bu örnekte, **Ortalama Çizgisi** seçeneğini belirleyeceğiz.
   
   ![](media/service-analytics-pane/power-bi-add.png)
3. Yeni bir çizgi oluşturmak için **+ Ekle**'yi seçin. Ardından, metin kutusuna çift tıklayıp istediğiniz adı yazarak çizgiye bir ad verebilirsiniz.
   
   Çizginiz için *renk*, *saydamlık*, *stil* ve *konum* (görselin veri öğelerine göre) gibi çok çeşitli seçenekler belirleyebilir ve etiketin dahil edilip edilmemesini tercih edebilirsiniz. Daha da önemlisi, görseldeki veri öğeleriyle otomatik olarak doldurulan **Measure** açılan menüsünü seçerek çizginizin görseldeki hangi **Ölçüye** dayanacağını belirleyebilirsiniz. Bu örnekte, *Open store count*'u ölçü olarak belirleyecek, *Avg # Open Stores* olarak etiketleyecek ve aşağıda gösterildiği gibi birkaç başka seçeneği daha özelleştireceğiz.
   
   ![](media/service-analytics-pane/power-bi-average-line.png)
4. Bir veri etiketi görüntülemek istiyorsanız **Veri etiketi** kaydırıcısını açık durumuna getirin. Bu işlemi gerçekleştirdiğinizde veri etiketiniz için ek seçenekler barındıran yeni bir bölüme sahip olursunuz.
5. **Analiz** bölmesindeki **Ortalama çizgisi**'nin yanında görünen sayıya dikkat edin. Bu, o anda görselinizde hangi türden kaç dinamik çizgi bulunduğunu gösterir. 9 değerinde bir mağaza sayım hedefi için **Sabit çizgi** eklersek **Analiz** bölmesinde, bu görselde uygulanmış bir **Sabit çizgi** başvuru çizgisine de sahip olduğumuz gösterilir.
   
   ![](media/service-analytics-pane/power-bi-reference-lines.png)
   
   Seçtiğiniz görselde (bu örnekte, bir **Harita** görseli) dinamik başvuru çizgileri kullanılamıyorsa **Analiz** bölmesini seçtiğinizde aşağıdaki görüntüyle karşılaşırsınız.
   
   ![](media/service-analytics-pane/power-bi-no-lines.png)

**Analiz** bölmesiyle dinamik başvuru çizgileri oluşturarak çok çeşitli öngörülere dikkat çekebilirsiniz.

Dinamik başvuru çizgilerinin kullanılabildiği görsel türlerini genişletmek de dahil daha fazla özellik ve işlev sunmayı planlıyoruz; bu nedenle yenilikleri sık sık kontrol etmenizde fayda var.

## <a name="limitations"></a>Sınırlamalar
Dinamik başvuru çizgilerinin kullanılabilirliği, birlikte çalışan görsele göre değişiklik gösterir. Aşağıdaki liste, şu anda hangi görseller için hangi dinamik çizgilerin kullanılabildiğini göstermektedir:

Aşağıdaki görsellerle dinamik çizgiler tüm özellikleriyle birlikte kullanılabilir:

* Alan grafiği
* Çizgi grafik
* Dağılım grafiği
* Kümelenmiş Sütun grafik
* Kümelenmiş Çubuk grafik

Şu görsellerle **Analiz** bölmesinde yalnızca bir *sabit çizgi* kullanılabilir:

* Yığılmış Alan
* Yığılmış Çubuk
* Yığılmış Sütun
* %100 Yığılmış Çubuk
* %100 Yığılmış Sütun

Aşağıdaki görseller için *eğilim çizgisi* şu anda kullanılabilecek tek seçenektir:

* Yığılmamış Çizgi
* Kümelenmiş Sütun grafik

Son olarak, aşağıdakiler gibi Kartezyen olmayan görsellerle şu anda **Analiz** bölmesinde başvuru çizgileri kullanılamaz:

* Matris
* Pasta grafiği
* Halka
* Tablo

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Desktop'taki Analiz bölmesi](desktop-analytics-pane.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

