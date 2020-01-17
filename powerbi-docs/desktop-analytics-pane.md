---
title: Power BI Desktop'taki Analiz Bölmesini Kullanma
description: Power BI Desktop'ta görseller için dinamik başvuru çizgileri oluşturma
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 25d80cd81eb06913eb24c17ef10db47fa4d2bea5
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75761922"
---
# <a name="use-the-analytics-pane-in-power-bi-desktop"></a>Power BI Desktop'taki Analiz bölmesini kullanma
**Power BI Desktop**'taki **Analiz** bölmesini kullanarak görsellere *dinamik başvuru çizgileri* ekleyebilir ve önemli eğilimlere veya öngörülere odaklanılmasını sağlayabilirsiniz. **Analiz** bölmesi, Power BI Desktop’ın **Görselleştirmeler** alanında bulunur.

![](media/desktop-analytics-pane/analytics-pane_1.png)

> [!NOTE]
> **Analiz** bölmesi yalnızca Power BI Desktop tuvalinde bir görsel seçmeniz halinde görünür.

## <a name="search-within-the-analytics-pane"></a>Analiz bölmesinde arama
**Power BI Desktop**’ın Şubat 2018 sürümünden (sürüm 2.55.5010.201 veya üzeri) itibaren, **Görselleştirmeler** bölmesinin alt bölümü olan **Analiz** bölmesi içinde arama yapabilirsiniz. Aşağıdaki resimde gösterildiği gibi, **Analiz** bölmesi seçildiğinde arama kutusu görünür.

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

Yüzdelik satır yalnızca **Power BI Desktop**’ta içeri aktarılan veriler kullanılırken veya **Analysis Service 2016** veya sonraki sürümünü, **Azure Analysis Services**’ı ya da Power BI hizmetindeki bir veri kümesini çalıştıran bir sunucudaki modele canlı olarak bağlanıldığında kullanılır. 

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop ile yapabileceğiniz çok şey var. Sunulan özellikler hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop'taki Yenilikler](desktop-latest-update.md)
* [Power BI Desktop'ı İndirme](desktop-get-the-desktop.md)
* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop ile Sorgulara Genel Bakış](desktop-query-overview.md)
* [Power BI Desktop'taki Veri Türleri](desktop-data-types.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki Genel Sorgu Görevleri](desktop-common-query-tasks.md)    

