---
title: Power BI Desktop'taki Access ve XLS içeri aktarma sorunlarını giderme
description: Power BI Desktop'ta ve Power Query'de Access veritabanlarını ve .XLS elektronik tablolarını içeri aktarmayla ilgili sorunları giderme
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 12/09/2020
LocalizationGroup: Troubleshooting
ms.openlocfilehash: b144412ee322aa9bec0a35bb3876a949abcd3f13
ms.sourcegitcommit: 8250187368d3de48663eb516a816ff701119b579
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2020
ms.locfileid: "96998910"
---
# <a name="troubleshoot-importing-access-and-excel-xls-files-in-power-bi-desktop"></a>Power BI Desktop'ta Access ve Excel .xls dosyalarını içeri aktarma sorunlarını giderme

Power BI Desktop'ta hem Access veritabanları hem de Excel çalışma kitaplarının önceki sürümleri (Excel 97-2003 türünde .XLS dosyaları), *Access Veritabanı Altyapısı*'nı kullanır. Access Veritabanı Altyapısı'nın düzgün şekilde çalışmasını engelleyebilecek üç yaygın durum söz konusudur.

## <a name="situation-1-no-access-database-engine-is-installed"></a>1\. Durum: Access Veritabanı Altyapısı’nın yüklenmemiş olması

Power BI Desktop hata iletisi Access Veritabanı Altyapısı'nın yüklenmediğini belirtiyorsa, Power BI Desktop sürümünüzle eşleşen (32 bit veya 64 bit) Access Veritabanı Altyapısı sürümünü yüklemeniz gerekir. Access Veritabanı Altyapısı'nı [indirmeler sayfasından](https://www.microsoft.com/download/details.aspx?id=13255) yükleyebilirsiniz.

Veri akışlarıyla çalışıyorsanız ve verilere bağlanırken bir ağ geçidi kullanıyorsanız, ağ geçidini çalıştıran bilgisayara Access Veritabanı Altyapısı'nı yüklemeniz gerekir. 

>[!NOTE]
>Yüklenen Access Veritabanı Altyapısı bit sürümü, Microsoft Office yüklemenizin bit sürümünden farklıysa Office uygulamaları, Access Veritabanı Altyapısı'nı kullanamaz.

## <a name="situation-2-the-access-database-engine-bit-version-32-bit-or-64-bit-is-different-from-your-power-bi-desktop-bit-version"></a>2\. Durum: Access Veritabanı Altyapısı bit sürümünün (32 bit veya 64 bit) Power BI Desktop bit sürümünüzden farklı olması

Bu durum genellikle Microsoft Office'in yüklenen sürümü 32 bit, yüklenen Power BI Desktop sürümü ise 64 bit olduğunda oluşur. Tersi de olabilir ve her iki durumda da bit sürümü uyumsuzluğu oluşur. Microsoft 365 aboneliği kullanıyorsanız farklı bir sorun ve çözüm için [Durum 3](#situation-3-trouble-using-access-or-xls-files-with-a-microsoft-365-subscription)’e bakın. Aşağıdaki çözümlerden herhangi biri bit sürümü uyuşmazlığından kaynaklanan bu hatayı giderebilir:

### <a name="solution-1"></a>Çözüm 1

Power BI Desktop'ın sürümünü Microsoft Office yüklemenizin bit sürümüyle eşleşecek şekilde değiştirin. 

1. Power BI Desktop'ın bit sürümünü değiştirmek için Power BI Desktop'ı kaldırın ve ardından Office yüklemenizle eşleşen Power BI Desktop sürümünü yükleyin. 

1. Bir Power BI Desktop sürümü seçmek için, Power BI Desktop indirme sayfasında **Gelişmiş indirme seçenekleri**'ni seçin.
   
   ![Power BI Desktop indirme sayfasındaki Gelişmiş indirme seçenekleri](media/desktop-access-database-errors/desktop-access-errors-1.png)
   
1. Görünen indirme sayfasında dilinizi ve ardından **İndir** düğmesini seçin. 
 
1. Görünen ekranda 32 bit sürüm için PBIDesktop.msi onay kutusunu, 64 bit sürüm için ise PBIDesktop_x64.msi onay kutusunu işaretleyin. 

   Aşağıdaki ekran görüntüsünde 64 bit sürüm seçilidir.
   
   ![Power BI Desktop indirme türünü seçin](media/desktop-access-database-errors/desktop-access-errors-2.png)
   
   >[!NOTE]
   >Power BI Desktop'ın 32 bit sürümünü kullanıyorsanız, çok büyük veri modelleri oluştururken yetersiz bellek sorunlarıyla karşılaşabilirsiniz.

### <a name="solution-2"></a>Çözüm 2

Microsoft Office bit sürümünü Power BI Desktop yüklemenizin bit sürümüyle eşleşecek şekilde değiştirin:

1. Microsoft Office’i kaldırın

2. Office’in Power BI Desktop yüklemenizle eşleşen sürümünü yükleyin.

### <a name="solution-3"></a>Çözüm 3

Hata, bir .XLS dosyası (bir Excel 97-2003 çalışma kitabı) açmaya çalıştığınızda oluşuyorsa .XLS dosyasını Excel'de açıp .XLSX dosyası olarak kaydederek Access Veritabanı Altyapısı'nı kullanmaktan kaçınabilirsiniz.

### <a name="solution-4"></a>Çözüm 4

Önceki üç çözüm uygun değilse Access Veritabanı Altyapısı'nın iki sürümünü birden yüklemek de mümkündür. Ancak, bu geçici çözüm önerilmez. İki sürümü birden yüklemek Excel ve Power BI Desktop için bu Power Query sorununu giderse de, Access Veritabanı Altyapısı'nın ilk yüklenen bit sürümünü otomatik olarak kullanan tüm uygulamalar için hatalara ve sorunlara neden olur. 

Access Veritabanı Altyapısının her iki bit sürümünü de yüklemek için aşağıdaki adımları izleyin:

1. [İndirme sayfasından](https://www.microsoft.com/download/details.aspx?id=13255) Access Veritabanı Altyapısının her iki bit sürümünü de yükleyin. 

1. Access Veritabanı Altyapısı'nın her bir sürümünü, */passive* anahtarını kullanarak çalıştırın. Örnek:

   ```console
   c:\users\joe\downloads\AccessDatabaseEngine.exe /passive

   c:\users\joe\downloads\AccessDatabaseEngine_x64.exe /passive
   ```

## <a name="situation-3-trouble-using-access-or-xls-files-with-a-microsoft-365-subscription"></a>3\. Durum: Bir Microsoft 365 aboneliğiyle Access veya .XLS dosyaları kullanılırken sorun yaşanması

Bir Microsoft 365 aboneliği (**Office 2013** veya **Office 2016**) kullanıyorsanız Access Veritabanı Altyapısı sağlayıcısı *yalnızca* Microsoft Office işlemlerinin erişebildiği sanal bir kayıt defteri konumuna kayıtlıdır. Sonuç olarak, Mashup Altyapısı (Office 365 Excel ve Power BI Desktop dışındaki çalıştırma işlemlerinden sorumludur ve bir Office işlemi değildir), Access Veritabanı Altyapısı sağlayıcısını kullanamaz.

Bu durumu ortadan kaldırmak için Power BI Desktop yüklemenizin bit sürümüyle (bit sürümleri hakkında daha fazla bilgi için önceki bölümlere göz atın) eşleşen [Access Veritabanı Altyapısı yeniden dağıtılabilir paketini indirip yükleyin](https://www.microsoft.com/download/details.aspx?id=13255). Bit sürümleri hakkında daha fazla bilgi için bu makalenin önceki bölümlerine bakın.

## <a name="other-situations-that-can-cause-import-issues"></a>İçeri aktarma sorunlarına neden olabilecek diğer durumlar

Access veya .XLS dosyalarıyla ilgili mümkün olduğu kadar çok sayıda sorunu ele almak için elimizden geleni yapıyoruz. Bu makalede ele alınmayan bir sorunla karşılaşırsanız sorunla ilgili sorunuzu [Power BI Desteği](https://powerbi.microsoft.com/support/)'ne gönderin. Birçok müşteriyi etkileyebilecek sorunları düzenli olarak kontrol edip makalelerimizde bu sorunlara yer veriyoruz.

