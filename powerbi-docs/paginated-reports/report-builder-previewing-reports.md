---
title: Power BI Rapor Oluşturucusu'nda raporları önizleme
description: Rapor Oluşturucusu sayfalandırılmış raporu oluştururken raporun istediğiniz gibi göründüğünü doğrulamak için sık sık raporun önizlemesini görüntülemek yararlı olur.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: ba6b5bdd-d8c6-4aa8-ba32-3a10b11969d4
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: afbc31e3ece8bc72ad52bb2fe7c3d871b2f68e1b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "78922954"
---
# <a name="previewing-reports-in-power-bi-report-builder"></a>Power BI Rapor Oluşturucusu'nda raporları önizleme
  Rapor Oluşturucusu sayfalandırılmış raporu oluştururken raporun istediğiniz gibi göründüğünü doğrulamak için sık sık raporun önizlemesini görüntülemek yararlı olur. Raporunuzu önizlemesini görmek için **Çalıştır**'a tıklayın. Rapor önizleme modunda işlenir.  
  
 Rapor Oluşturucusu rapor sunucusuna bağlıyken düzenleme oturumlarını kullanarak önizleme deneyimini geliştirir. Düzenleme oturumu bir veri önbelleği oluşturur ve önbellekteki veri kümelerinin tekrarlanan rapor önizlemelerinde kullanılabilmesini sağlar. Düzenleme oturumu doğrudan etkileşimli çalıştığınız bir özellik değildir ama önbelleğe alınmış veri kümesinin ne zaman yenilendiğini anlamak, raporun önizlemesini görüntülerken performansı geliştirmenize ve raporun neden hızlı veya yavaş işlendiğini anlamanıza yardımcı olur.  

  
> [!NOTE]  
> Rapor Oluşturucusu'nda önizleme işlemiyle tarayıcıda görüntüleme işlemi arasında bazı farklar vardır. Örneğin Tarih/Saat türünde bir parametre belirttiğinizde rapora eklenen takvim denetimi Rapor Oluşturucusu ile tarayıcıda birbirinden farklıdır. 
  
## <a name="improving-preview-performance"></a>Önizleme performansını geliştirme  
 Raporları nasıl oluşturduğunuz ve güncelleştirdiğiniz, raporun önizlemede işlenme hızını etkiler. Sunucu başvurusuna dayanan bir raporu ilk kez önizlediğinizde sizin için bir düzenleme oturumu oluşturulur ve rapor çalıştırıldığında kullanılan veriler depolanan bir veri önbelleğine eklenir. Raporda verileri etkilemeyen değişiklikler yaptığınızda, rapor tarafından verilerin önbelleğe alınmış kopyası kullanılır. Başka bir deyişle raporun önizlemesini her görüntülediğinizde veri değişikliği görmezsiniz. Yeni verileri istiyorsanız şeritteki **Yenile** düğmesine tıklayın.  
  
 Aşağıdaki eylemler önbelleğin yenilenmesine neden olur ve raporun önizlemesini bir sonraki görüntüleyişinizde raporun işlenmesini yavaşlatır:  
  
-   Veri kümesini ekleme, değiştirme veya silme. Önbelleğe alınmış veri kümesi bir raporda kullanılan tüm veri kümelerini içerir ve herhangi bir veri kümesinde değişiklik yapılması önbelleğe alınmış veri kümesini geçersiz kılar. Bu veri kümesinde adı, sorguyu veya alanları değiştirmeyi içerir.  
  
    > [!NOTE]  
    >  Veri kümesinde kullanmayı düşünmediğiniz çok fazla sayıda alan varsa, bu alanları atlamak için veri kümesini güncelleştirmeyi göz önünde bulundurmalısınız. Bu yeni bir düzenleme oturumu oluştursa ve raporun ilk önizlemesi yavaş olsa da, daha küçük bir önbelleğe alınmış veri kümesi rapor sunucusunun performansı açısından genel olarak avantajlıdır.  
  
-   Veri kaynağını ekleme, değiştirme veya silme. Bu veri kaynağının adını veya özelliklerini, veri uzantısını ya da veri kaynağına yönelik bağlantının özelliklerini değiştirmeyi içerir.  
  
-   Raporun kullandığı veri kaynağını başka bir veri kaynağıyla değiştirme.  
  
-   Raporun dilini değiştirme.  
  
-   Raporun kullandığı derlemeleri veya özel kodları değiştirme.  
  
-   Rapordaki sorgu parametrelerini veya parametre değerlerini ekleme, değiştirme veya silme.  
  
 Rapor düzeninde ve veri biçimlendirmesinde yapılan değişiklikler önbelleğe alınmış veri kümesini etkilemez. Önbelleğe alınmış veri kümesini yenilemeden aşağıdaki eylemleri yapabilirsiniz:  
  
-   Tablo, matris veya grafik gibi veri bölgelerini ekleme veya kaldırma.  
  
-   Raporda sütunlar ekleme veya silme. Veri kümesindeki tüm alanlar raporda kullanılabilir. Raporda alanların eklenmesi veya kaldırılması veri kümesini etkilemez.  
  
-   Tablolarda ve matrislerde alanların sırasını değiştirme.  
  
-   Satır ve sütun gruplarını ekleme, değiştirme veya silme.  
  
-   Alanlardaki veri değerlerinin biçimlendirmesini ekleme, değiştirme veya silme.  
  
-   Resimleri, çizgileri veya metin kutularını ekleme, değiştirme veya silme.  
  
-   Sayfa sonlarını değiştirme.  
  
Düzenleme oturumu, raporun önizlemesini ilk görüntülediğinizde oluşturulur. Varsayılan olarak düzenleme oturumları 7200 saniye (2 saat) sürer. Raporu her çalıştırdığınızda oturum iki saate sıfırlanır. Düzenleme oturumunun süresi dolduğunda veri önbelleği silinir. Düzenleme oturumunun süresi dolarsa, raporun önizlemesini bir sonraki görüntüleyişinizde oturum otomatik olarak yeniden oluşturulur.
  
Varsayılan olarak veri önbelleği en çok beş veri kümesi barındırabilir. Parametre değerlerinin birçok farklı bileşimini kullanıyorsanız rapora daha fazla veri gerekebilir. Bunun için önbelleğin yenilenmesi gerekir ve raporun önizlemesini bir sonraki görüntüleyişinizde rapor daha yavaş işlenir. 
  
## <a name="concurrency-of-report-updates"></a>Raporu güncelleştirmelerinin eşzamanlılığı  
Çoğunlukla raporu güncelleştirme ve Power BI hizmetine kaydetme işleminin bir adımı olarak raporun önizlemesini görüntülersiniz. Siz raporu güncelleştirirken aynı anda başka biri de güncelleştiriyor ve kaydediyor olabilir. Son kaydedilen rapor, daha sonra görüntüleme ve güncelleştirme için sağlanan sürümü oluşturur. Başka bir deyişle sizin önizlemesini görüntülediğiniz rapor sürümü yeniden açtığınız sürüm olmayabilir. Rapor Oluşturucusu menüsünde **Farklı Kaydet** seçeneğini kullanarak raporu yeni bir adla kaydedebilirsiniz.  
  
## <a name="external-report-items"></a>Dış rapor öğeleri  
 Raporunuzda, rapordan ayrı depolanan dış resimler gibi öğeler bulunabilir. Öğeler ayrı depolandığından bunların farklı bir konuma taşınması veya silinmesi mümkündür. Böyle bir durumda raporunuzun önizlemesi başarısız olabilir. Raporu güncelleştirip öğenin güncelleştirilmiş konumunu belirtebilir ya da öğe silinmişse bunu mevcut bir öğeyle değiştirebilir veya öğenin başvurusunu kaldırabilirsiniz.  
  
## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
  
