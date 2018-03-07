---
title: "Power BI Desktop'taki satır içi hiyerarşi etiketlerini kullanma"
description: "Power BI Desktop'taki satır içi hiyerarşi etiketlerini kullanma"
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
ms.openlocfilehash: 9d5675b17973839f52699c5af9bfad9c8714a58e
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="use-inline-hierarchy-labels-in-power-bi-desktop"></a>Power BI Desktop'taki satır içi hiyerarşi etiketlerini kullanma
**Power BI Desktop**, hiyerarşik olarak detaya gitmeyi iyileştirmeye yönelik iki özellikten birincisi olan **satır içi hiyerarşi etiketlerinin** kullanımını destekler. Şu anda geliştirme aşamasında olan ikinci özellik ise iç içe geçmiş hiyerarşi etiketlerini kullanabilme özelliğidir. (Sık sık güncelleştirmeler yayımladığımızdan bu özellik için takipte kalmanızda yarar var.)   

## <a name="how-inline-hierarchy-labels-work"></a>Satır içi hiyerarşi etiketleri nasıl çalışır?
Satır içi hiyerarşi etiketleri sayesinde, **Tümünü Genişlet** özelliğini kullanarak görselleri genişlettiğinizde hiyerarşi etiketlerini görebilirsiniz. Hiyerarşik verilerinizi genişlettiğinizde bu farklı hiyerarşi etiketlerine göre **sıralama** yapmayı da tercih edebilmeniz söz konusu hiyerarşi etiketlerini görebilmenin sunduğu harika avantajlardan biridir.

### <a name="using-the-built-in-expand-all-feature-without-sorting-by-hierarchy-labels"></a>Yerleşik Tümünü Genişlet özelliğini kullanma (hiyerarşi etiketlerine göre sıralama yapmadan)
Satır içi hiyerarşi etiketlerini uygulamaları olarak görmeden önce **Tümünü Genişlet** özelliğinin varsayılan olarak nasıl davranış gösterdiğini inceleyelim. Bunu gerçekleştirmemiz, satır içi hiyerarşi etiketlerinin ne kadar kullanışlı olabildiğini anlayabilmemize (ve bunun tadını çıkarmamıza) yardımcı olur.

Aşağıdaki görüntüde, yıllık satışlara yönelik bir çubuk grafik görseli bulunmaktadır. Sağ tıkladığınızda, **Tümünü Genişlet** seçeneğini belirleyebilirsiniz.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_4.png)

**Tümünü Genişlet** seçeneği belirlendiğinde, görsel, olan tarih hiyerarşisini *Year* ile *Quarter* arasında genişletir (aşağıdaki görüntüde gösterildiği gibi).

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_5.png)

*Year* ve *Quarter* etiketlerinin satır içinde birlikte gösterildiğine dikkat edin. Siz hiyerarşinin altında bulunan **Tümünü Genişlet** seçeneğini belirledikçe bu etiketleme şeması uygulanmaya devam edilir.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_6.png)

İşte *tarih/saat* veri türüne sahip alanlarla ilişkili yerleşik *Tarih* hiyerarşisi böyle davranış gösterir. Şimdi bir sonraki bölüme geçelim ve yeni satır içi hiyerarşi etiketleri özelliğinin nasıl fark yarattığını görelim.

### <a name="using-inline-hierarchy-labels"></a>Satır içi hiyerarşi etiketlerini kullanma
Şimdi de ölçüsüz hiyerarşilerin bulunduğu verilerin kullanıldığı farklı bir grafiğe göz atalım. Aşağıdaki görselde, eksen olarak *Color* seçeneğinin kullanıldığı **Sales Amount** adlı bir çubuk grafik bulunuyor. Bu verilerdeki *Color* ve *Class*, ölçüsüz bir hiyerarşi oluşturur. Burada, hiyerarşide detaya gitmek için *Tümünü Genişlet* seçeneğini tekrar belirleyebilirsiniz.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_7.png)

**Tümünü Genişlet** seçeneği belirlendiğinde, hiyerarşi etiketlerinin satır içi görüntüsünü içeren bir sonraki düzey gösterilir. Varsayılan olarak, satır içi hiyerarşiler ölçü değerine (bu örnekte, **SalesAmount**) göre sıralanır. Satır içi hiyerarşi etiketleri etkinleştirildiğinde, aşağıdaki görüntüde gösterildiği gibi sağ üst köşedeki üç nokta (**...**) simgesini seçip **Sıralama Ölçütü: Color Class** seçeneğini belirleyerek bu verileri hiyerarşiye göre sıralamayı da tercih edebilirsiniz.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_8.png)

**Color Class** seçildiğinde veriler, aşağıdaki görüntüde gösterildiği gibi, ölçüsüz hiyerarşi seçimine göre sıralanır.

![](media/desktop-inline-hierarchy-labels/inlinehierarchy_9.png)

> [!NOTE]
> Satır içi hiyerarşi etiketi özelliği henüz yerleşik saat hiyerarşisinin değere göre sıralanmasını desteklememektedir; bu hiyerarşi yalnızca hiyerarşi sırasına göre sıralanabilir.
> 
> 

## <a name="troubleshooting"></a>Sorun giderme
Görselleriniz, genişletilmiş bir satır içi hiyerarşi düzeyi durumunda takılabilir. Bazı durumlarda, görsellerinizden bazılarının, genişletildikleri modda takıldığını ve detaydan çıkma özelliğinin çalışmadığını görebilirsiniz. Aşağıdaki adımlardan birini uyguladığınızda bu sorunla karşılaşabilirsiniz: (Sorunun çözümüne bu adımların *altında* yer verilmiştir.)

Şu adımlar görselinizin genişletilmiş bir durumda takılmasına neden olabilir:

1. **Satır içi hiyerarşi etiketi** özelliğini etkinleştirmeniz
2. Hiyerarşi içeren görseller oluşturmanız
3. Ardından, **Tümünü Genişlet** seçeneğini belirleyip dosyayı kaydetmeniz
4. Bu işlemi gerçekleştirdikten sonra **Satır içi hiyerarşi etiketi** özelliğini *devre dışı bırakıp* Power BI Desktop'ı yeniden başlatmanız
5. Ardından dosyanızı yeniden açmanız

Söz konusu adımları uygularsanız ve görselleriniz genişletilmiş modda takılırsa görsellerinizle ilgili bu sorunları gidermek için aşağıdakileri gerçekleştirebilirsiniz:

1. **Satır içi hiyerarşi etiketi** özelliğini yeniden etkinleştirin ve ardından Power BI Desktop'ı yeniden başlatın
2. Dosyanızı yeniden açın ve etkilenen görselleriniz için en üst düzeye çıkmak üzere detaydan çıkma özelliğini kullanın
3. Dosyanızı kaydedin
4. **Satır içi hiyerarşi etiketi** özelliğini devre dışı bırakın ve ardından Power BI Desktop'ı yeniden başlatın
5. Dosyanızı yeniden açın

Alternatif olarak, görselinizi silip yeniden oluşturmayı da tercih edebilirsiniz.

