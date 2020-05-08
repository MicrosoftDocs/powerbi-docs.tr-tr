---
title: Power BI Desktop'tan yayımlama
description: Power BI Desktop'tan yayımlama
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 3a67c36b2594696e1c576693cc5808eb0227c1c7
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "76709614"
---
# <a name="publish-datasets-and-reports-from-power-bi-desktop"></a>Power BI Desktop'tan veri kümesi ve rapor yayımlama
Power BI Desktop dosyasını Power BI hizmetine yayımladığınızda, modeldeki verileri Power BI çalışma alanınızda yayımlarsınız. Aynı durum **Rapor** görünümünde oluşturduğunuz raporlar için de geçerlidir. Çalışma Alanı gezgininizde tüm raporları ve aynı adda yeni bir veri kümesi görürsünüz.

Power BI Desktop'tan yayımlamak ile Power BI Desktop dosyasına bağlanmak ve bu dosyayı yüklemek için Power BI'da **Veri Al** seçeneğini kullanmak aynı etkiyi yapar.

> [!NOTE]
> Power BI'da raporda yaptığınız hiçbir değişiklik özgün Power BI Desktop dosyasına geri kaydedilmez. Bu değişiklikler raporlardaki görselleştirmeleri eklemeyi, silmeye veya değiştirmeyi içerir.
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>Bir Power BI Desktop veri kümesini ve raporları yayımlamak için
1. Power BI Desktop'ta **Dosya** \> **Yayımla** \> **Power BI'da Yayımla**'yı seçin veya şeritten **Yayımla**'yı seçin.  

   ![Yayımla düğmesi](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)

2. Power BI'da oturum açın.
3. Hedefi seçin.

   ![Yayımlama hedefi seçme](media/desktop-upload-desktop-files/pbid_publish_select_destination.png)

Yayımlama tamamlandığında, raporunuz için bir bağlantı alırsınız. Raporu Power BI sitenizde açmak için bağlantıyı seçin.

![Yayımlama başarılı iletişim kutusu](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="republish-or-replace-a-dataset-published-from-power-bi-desktop"></a>Yeniden yayımlama veya Power BI Desktop'tan yayımlanmış bir veri kümesini değiştirme
Bir Power BI Desktop dosyası yayımladığınızda veri kümesi ve Power BI Desktop'ta oluşturduğunuz tüm raporlar Power BI sitenize yüklenir. Power BI Desktop dosyasını yeniden yayımladığınızda Power BI sitenizdeki veri kümesi, Power BI Desktop dosyasından güncelleştirilen veri kümesiyle değiştirilir.

Bu basit bir işlem olsa da bilmeniz gereken bazı noktalar vardır:

* Power BI'da, Power BI Desktop dosyasıyla aynı adda iki veya daha fazla veri kümesi olması yayımlama işleminin başarısız olmasına yol açabilir. Power BI'da aynı adda yalnızca bir veri kümeniz olduğundan emin olun. Ayrıca, dosyayı yeniden adlandırarak yayımlayabilir ve dosya ile aynı adda yeni bir veri kümesi oluşturabilirsiniz.
* Bir sütunu veya ölçüyü yeniden adlandırırsanız ya da silerseniz Power BI'da bu alanı içeren tüm görselleştirmeler bozulabilir. 
* Power BI mevcut sütunlardaki bazı biçim değişikliklerini yok sayar. Örneğin, bir sütunun biçimini %0,25 yerine %25 olarak değiştirdiğinizde.
* Power BI'daki mevcut veri kümeniz için yapılandırılmış bir yenileme zamanlamanız olduğunu düşünün. Dosyanıza yeni veri kaynakları ekleyip ardından yeniden yayımladığınızda, zamanlanmış sonraki yenilemeden önce bunlarda oturum açmanız gerekir.
* Bir yenileme zamanlaması tanımlanmışsa ve Power BI Desktop’tan yayımlanan bir veri kümesi yeniden yayımlanırsa, yeniden yayımlama işlemi yapıldığında bir veri kümesi yenilemesi başlatılır. 

