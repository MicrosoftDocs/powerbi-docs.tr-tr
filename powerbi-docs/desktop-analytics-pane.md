---
title: "Power BI Desktop'taki Analiz Bölmesini Kullanma"
description: "Power BI Desktop'ta görseller için dinamik başvuru çizgileri oluşturma"
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: add95532f645c143aea0f58200f9e3b1467320d0
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="using-the-analytics-pane-in-power-bi-desktop"></a>Power BI Desktop'taki Analiz Bölmesini Kullanma
**Power BI Desktop**'taki **Analiz** bölmesini kullanarak görsellere *dinamik başvuru çizgileri* ekleyebilir ve önemli eğilimlere veya öngörülere odaklanılmasını sağlayabilirsiniz. **Analiz** bölmesi, Ağustos 2016 sürümü itibarıyla (2.37.4464.321 veya sonraki sürümler), aşağıda gösterildiği gibi Power BI Desktop'ın **Görsel Öğeler** alanında bulunur.

![](media/desktop-analytics-pane/analytics-pane_1.png)

> [!NOTE]
> **Analiz** bölmesi yalnızca Power BI Desktop tuvalinde bir görsel seçmeniz halinde görünür.
> 
> 

## <a name="enable-forecasting-preview"></a>Tahmin Etmeyi Etkinleştirme (Önizleme)
Ayrıca, **Power BI Desktop**'ın Eylül 2016 sürümüyle birlikte (2.39.4526.362 veya sonraki sürümler), **Analiz** bölmesinde *tahmin etme* işlemleri gerçekleştirebilirsiniz. Bu önizleme özelliğini etkinleştirmek için **Dosya >Seçenekler ve Ayarlar >Seçenekler**'e gitmeniz ve sol bölmedeki **Önizleme Özellikleri**'ni seçmeniz gerekir. **Tahmin Etme**'nin yanındaki onay kutusunu, aşağıdaki görüntüde gösterildiği gibi işaretleyin. Değişikliklerin etkili olması için **Power BI Desktop**'ı yeniden başlatmanız gerekir.

![](media/desktop-analytics-pane/analytics-pane_1b.png)

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

1. Bir görsel oluşturun veya seçin, ardından **Görsel Öğeler** bölmesindeki **Analiz** simgesini seçin.
   
   ![](media/desktop-analytics-pane/analytics-pane_2.png)
2. Oluşturmak istediğiniz çizgi türüne ilişkin aşağı oku belirleyerek söz konusu çizgi türünün seçeneklerini genişletin. Bu örnekte, **Ortalama Çizgisi** seçeneğini belirleyeceğiz.
   
   ![](media/desktop-analytics-pane/analytics-pane_3.png)
3. Yeni bir çizgi oluşturmak için **+ Ekle**'yi seçin. Ardından, metin kutusuna çift tıklayıp istediğiniz adı yazarak çizgiye bir ad verebilirsiniz.
   
   Çizginiz için *renk*, *saydamlık*, *stil* ve *konum* (görselin veri öğelerine göre) gibi çok çeşitli seçenekler belirleyebilir ve etiketin dahil edilip edilmemesini tercih edebilirsiniz. Daha da önemlisi, görseldeki veri öğeleriyle otomatik olarak doldurulan **Ölçü** açılan menüsünü seçerek çizginizin görseldeki hangi **Ölçüye** dayanacağını belirleyebilirsiniz. Bu örnekte, *Weather*'ı ölçü olarak belirleyecek, *Average Weather* olarak etiketleyecek ve aşağıda gösterildiği gibi birkaç seçeneği daha özelleştireceğiz.
   
   ![](media/desktop-analytics-pane/analytics-pane_4.png)
4. Bir veri etiketi görüntülemek istiyorsanız **Veri etiketi** kaydırıcısını açık durumuna getirin. Bu işlemi gerçekleştirdiğinizde aşağıdaki görüntüde gösterildiği gibi veri etiketiniz için ek seçenekler barındıran yeni bir bölüme sahip olursunuz.
   
   ![](media/desktop-analytics-pane/analytics-pane_5.png)
5. **Analiz** bölmesindeki **Ortalama çizgisi**'nin yanında görünen sayıya dikkat edin. Bu, o anda görselinizde hangi türden kaç dinamik çizgi bulunduğunu gösterir. *Cost of Living* için **Maks. çizgi** eklersek **Analiz** bölmesinde bu görsele uygulanmış bir **Maks. Çizgi** dinamik başvuru çizgisine sahip olduğumuz gösterilir.
   
   ![](media/desktop-analytics-pane/analytics-pane_6.png)

Seçtiğiniz görselde (bu örnekte, bir **Harita** görseli) dinamik başvuru çizgileri kullanılamıyorsa **Analiz** bölmesini seçtiğinizde aşağıdaki görüntüyle karşılaşırsınız.

![](media/desktop-analytics-pane/analytics-pane_7.png)

**Analiz** bölmesiyle dinamik başvuru çizgileri oluşturarak çok çeşitli öngörülere dikkat çekebilirsiniz.

Dinamik başvuru çizgilerinin kullanılabildiği görsel türlerini genişletmek de dahil daha fazla özellik ve işlev sunmayı planlıyoruz; bu nedenle yenilikleri sık sık kontrol etmenizde fayda var.

## <a name="apply-forecasting"></a>Tahmin Uygulama
**Tahmin** özelliğini, bir görseli seçip **Analiz** bölmesindeki **Tahmin** bölümünü genişleterek kullanabilirsiniz. Tahmini değiştirmek için, *Tahmin uzunluğu* ve *Olasılık aralığı* gibi birçok giriş sağlayabilirsiniz. Aşağıdaki görüntüde tahmin uygulanmış basit bir çizgi görseli gösterilmektedir ancak hayal gücünüzden yararlanarak (ve *tahmin etme* özelliğiyle deneme yaparak) bu özelliğin modellerinize nasıl uygulanabileceğini anlayabilirsiniz.

![](media/desktop-analytics-pane/analytics-pane_8.png)

## <a name="limitations"></a>Sınırlamalar
Dinamik başvuru çizgilerinin kullanılabilirliği, birlikte çalışılan görsele göre değişiklik gösterir. Aşağıdaki liste, şu anda hangi görseller için hangi dinamik çizgilerin kullanılabildiğini göstermektedir:

Aşağıdaki görsellerle dinamik çizgiler tüm özellikleriyle birlikte kullanılabilir:

* Alan grafiği
* Çizgi grafik
* Dağılım grafiği
* Kümelenmiş Sütun grafik
* Kümelenmiş Çubuk grafik

Şu görsellerle **Analiz** bölmesinde yalnızca *sabit çizgi* kullanılabilir:

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
Power BI Desktop ile yapabileceğiniz pek çok şey vardır. Sunulan özellikler hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop'taki Yenilikler](desktop-latest-update.md)
* [Power BI Desktop'ı İndirme](desktop-get-the-desktop.md)
* [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md)
* [Power BI Desktop ile Sorgulara Genel Bakış](desktop-query-overview.md)
* [Power BI Desktop'taki Veri Türleri](desktop-data-types.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki Genel Sorgu Görevleri](desktop-common-query-tasks.md)    

