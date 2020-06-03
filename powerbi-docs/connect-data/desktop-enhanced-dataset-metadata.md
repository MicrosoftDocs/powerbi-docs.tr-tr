---
title: Power BI Desktop’ta gelişmiş veri kümesi meta verilerini kullanma (önizleme)
description: Bu makalede, Power BI’da gelişmiş veri kümesi meta verilerinin nasıl kullanılacağı açıklanmaktadır.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/21/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 42e3f36689e62b196f5d8cb82bd4dd5ee118bf8b
ms.sourcegitcommit: 5e5a7e15cdd55f71b0806016ff91256a398704c1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83793399"
---
# <a name="using-enhanced-dataset-metadata-preview"></a>Gelişmiş veri kümesi meta verilerini kullanma (önizleme)

Power BI Desktop, rapor oluşturduğunda, ilgili PBIX ve PBIT dosyalarında da veri kümesi meta verileri oluşturur. Önceden meta veriler Power BI Desktop’a özgü bir biçimde depolanıyordu. Base-64 kodlu M ifadeleri ve veri kaynaklar kullanılıyordu ve meta verilerin nasıl depolanacağına dair varsayımlarda bulunuluyordu.

**Gelişmiş veri kümesi meta verileri** özelliğinin yayınlanmasıyla birlikte, bu sınırlamaların çoğu kaldırıldı. **Gelişmiş veri kümesi meta verileri** özelliği etkin durumdayken, Power BI Desktop tarafından oluşturulan meta veriler, [Tablolu Nesne Modeli](https://docs.microsoft.com/bi-reference/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo)’ne göre, Analysis Services tablolu modelleri için kullanılanlara benzer bir biçimi kullanır.


**Gelişmiş veri kümesi meta verileri** özelliği stratejik ve temel niteliktedir; gelecekteki Power BI işlevleri bunun meta verileri temelinde oluşturulur. Gelişmiş veri kümesi meta verilerinden yararlanan bazı ek özellikler arasında, Power BI veri kümelerinin yönetimi için [XMLA okuma/yazma](https://docs.microsoft.com/power-platform-release-plan/2019wave2/business-intelligence/xmla-readwrite) ve yeni nesil özelliklerden yararlanmak için Analysis Services iş yüklerinden Power BI’a geçiş yer alır.



## <a name="enable-enhanced-dataset-metadata"></a>Gelişmiş veri kümesi meta verilerini etkinleştirme

**Gelişmiş veri kümesi meta verileri** özelliği şu anda önizleme aşamasındadır. Gelişmiş veri kümesi meta verilerini etkinleştirmek için Power BI Desktop’ta **Dosya > Seçenekler ve ayarlar > seçenekler > önizleme özellikleri** seçeneğini belirleyin ve sonra aşağıdaki görüntüde gösterildiği gibi **Gelişmiş meta veri biçimini kullanarak veri kümelerini depola** onay kutusunu seçin. 

![Önizleme özelliğini etkinleştirme](media/desktop-enhanced-dataset-metadata/enhanced-dataset-metadata-01.png)

Power BI Desktop’ı yeniden başlatmanız istenir.

![Yeniden başlatma istemi](media/desktop-enhanced-dataset-metadata/enhanced-dataset-metadata-02.png)

Önizleme özelliği etkinleştirildikten sonra Power BI Desktop, önceki meta veri biçimini kullanan PBIX ve PBIT dosyalarını yükseltmeye çalışır. 

> [!IMPORTANT]
> **Gelişmiş veri kümesi meta verileri** özelliğinin etkinleştirilmesi, raporlara geri alınamayan bir yükseltme uygulanmasıyla sonuçlanır. **Gelişmiş veri kümesi meta verileri** etkinleştirildikten sonra, Power BI Desktop ile yüklenen veya oluşturulan Power BI raporları, geri alınamayacak şekilde gelişmiş veri kümesi meta verileri biçimine dönüştürülür.

## <a name="report-backup-files"></a>Rapor yedekleme dosyaları

Raporun **gelişmiş veri kümesi meta verileri** özelliğini kullanacak şekilde güncelleştirilmesi geri alınamaz. Öte yandan güncelleştirme sırasında raporun özgün (güncelleştirme öncesi) biçiminin bir sürümünü kaydetmek için rapor yedekleme dosyası oluşturulur. Yedekleme dosyası 30 gün sonra kaldırılır. 

Yedek rapor dosyasını bulmak için aşağıdakileri yapın:

1. Şu konuma gidin: ```C:\Users\<user>\AppData\Local\Microsoft\Power BI Desktop\TempSaves\Backup```. Power BI Desktop’ın Microsoft Store sürümünü kullanıyorsanız şu konumu kullanın: ```C:\Users\<user>\Microsoft\Power BI Desktop Store App\TempSaves\Backups``` 

2. Orada raporun, özgün dosyanın adını ve zaman damgasını taşıyan bir kopyasını bulun.

3. Bu dosyayı saklamak için, tercih ettiğiniz bir konuma kopyalayın.

4. Söz konusu özgün dosyayı açmayı veya kullanmayı seçerseniz, Power BI Desktop’ta **Gelişmiş meta veri biçimi** önizleme özelliğinin devre dışı bırakıldığından emin olun. 

Yedekleme dosyası rapor yükseltildiğinde oluşturulur, bu nedenle yükseltme sonrası yapılan değişiklikler yedeklemeye dahil edilmez. **Gelişmiş meta veri biçimi** özelliği etkinleştirildikten sonra oluşturulan yeni raporların yedekleme dosyası yoktur.


## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Önizleme sürümünde, önizleme özelliği etkinleştirildiğinde aşağıdaki sınırlamalar geçerli olur.

### <a name="unsupported-features-and-connectors"></a>Desteklenmeyen özellikler ve bağlayıcılar
Yükseltilmemiş mevcut bir PBIX ve PBIT dosyası açıldıktan sonra, veri kümesi aşağıdaki özelliklerden veya bağlayıcılardan herhangi birini içeriyorsa yükseltme başarısız olur. Bu tür bir hata oluşursa, kullanıcı deneyimi üzerinde anında bir etki oluşmamalıdır ve Power BI Desktop önceki meta veri biçimini kullanmaya devam eder.

* Tüm özel bağlayıcılar
* Python betikleri
* Özel bağlayıcılar
* Azure DevOps Server
* BI Bağlayıcısı
* Denodo
* Dremio
* Exasol
* Indexima
* IRIS
* Jethro ODBC
* Kyligence Enterprise
* Mark Logic ODBC
* Qubole Presto
* Team Desk
* Sütun adlarında “\\n” gibi belirli karakter birleşimlerini içeren M ifadeleri
* **Gelişmiş veri kümesi meta verileri** özelliği etkin durumdayken veri kümeleri kullanıldığında Çoklu Oturum Açma (SSO) veri kaynakları, Power BI hizmetinde ayarlanamaz

Bu listelenen bağlayıcıları kullanan raporlar yeni biçime yükseltilmez. Zaten yükseltilmiş olan veya bu yeni özellik etkinleştirildikten sonra oluşturulmuş olan raporlar, listedeki desteklenmeyen özelliklerin veya bağlayıcıların eklenmesini desteklemez. 

Dinamik veri kaynakları olan sorgular desteklenmez. Dinamik veri kaynakları olan raporlar yeni biçime yükseltilmez ve zaten yükseltilmiş olan veya özellik etkinleştirildikten sonra yeni oluşturulmuş olan raporlar dinamik veri kaynaklarının eklenmesini desteklemez. Sorgunun dinamik veri kaynağının olması, kaynağın bir parametreye, işlev girişine veya geçici işleve bağlı olarak değişmesi anlamına gelir. 

Yukarı akış adımlarında veya dallarında hatalar olan sorgular desteklenmez. 

Ayrıca, **gelişmiş veri kümesi meta verilerini** kullanmak için başarıyla yükseltilmiş olan PBIX ve PBIT dosyaları, geçerli sürümde yukarıdaki özellikleri veya bağlayıcıları *kullanamaz*.




### <a name="lineage-view"></a>Köken görünümü
Yeni meta veri biçimini kullanan veri kümeleri, şu anda Power BI hizmetindeki veri kökeni görünümde yer alan veri akışları bağlantılarını göstermiyor.

## <a name="next-steps"></a>Sonraki adımlar

Power BI Desktop ile her şeyi yapabilirsiniz. Özellikler hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktop’taki Yenilikler](../fundamentals/desktop-latest-update.md)
* [Power BI Desktop ile sorgulara genel bakış](../transform-model/desktop-query-overview.md)
* [Power BI Desktop'taki veri türleri](desktop-data-types.md)
* [Power BI Desktop'ta verileri şekillendirme ve birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki genel sorgu görevleri](../transform-model/desktop-common-query-tasks.md)
