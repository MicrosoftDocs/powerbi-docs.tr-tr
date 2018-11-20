---
title: Power BI Desktop'taki Access ve XLS içeri aktarma sorunlarını giderme
description: Power BI Desktop'ta ve Power Query'de Access veritabanlarını ve .XLS elektronik tablolarını içeri aktarmayla ilgili sorunları giderme
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/24/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 47bcfabddfeb5bfec828c7b14fef4798350939da
ms.sourcegitcommit: a739a99e1006834a0f56e387c0bd9d945fb8a76b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51679007"
---
# <a name="resolve-issues-importing-access-and-xls-files-in-power-bi-desktop"></a>Power BI Desktop'ta Access ve .XLS dosyalarını içeri aktarmaya ilişkin sorunlarını giderme
**Power BI Desktop**'ta hem **Access veritabanları** hem de **Excel çalışma kitaplarının** önceki sürümleri (Excel 97-2003 türünde .XLS dosyaları) *Access Veritabanı Altyapısı*'nı kullanır. Access Veritabanı Altyapısı'nın düzgün şekilde çalışmasını engelleyebilecek üç yaygın durum söz konusudur:

### <a name="situation-1-no-access-database-engine-installed"></a>1. Durum: Access Veritabanı Altyapısı'nın yüklenmemiş olmaması
Power BI Desktop hata iletisi Access Veritabanı Altyapısı'nın yüklenmediğini belirtiyorsa Power BI Desktop sürümünüzle eşleşen (32 bit veya 64 bit) Access Veritabanı Altyapısı sürümünü yüklemeniz gerekir. Access Veritabanı Altyapısı'nı [indirmeler sayfasından](http://www.microsoft.com/download/details.aspx?id=13255) yükleyebilirsiniz.

>[!NOTE]
>Yüklenen Access Veritabanı Altyapısı bit sürümü Microsoft Office yüklemenizin bit sürümünden farklıysa Office uygulamaları, Access Veritabanı Altyapısı'nı kullanamaz.

### <a name="situation-2-the-access-database-engine-bit-version-32-bit-or-64-bit-is-different-from-your-power-bi-desktop-bit-version"></a>2. Durum: Access Veritabanı Altyapısı bit sürümünün (32 bit veya 64 bit) Power BI Desktop bit sürümünüzden farklı olması
Bu durum genellikle Microsoft Office'in yüklenen sürümü 32 bit, yüklenen Power BI Desktop sürümü ise 64 bit olduğunda oluşur. Bunun tersi de söz konusu olabilir ve bir sürümü uyuşmazlığı her iki durumda da oluşur. (Office 365 aboneliği kullanıyorsanız farklı bir sorun ve bu sorunun çözümü için **3. Durum**'a bakın.) Aşağıdaki çözümlerden herhangi biri bit sürümü uyuşmazlığından kaynaklanan bu hatayı giderebilir:

1. Power BI Desktop'ın sürümünü Microsoft Office yüklemenizin bit sürümüyle eşleşecek şekilde değiştirin. Power BI Desktop'ın bit sürümünü değiştirmek için Power BI Desktop'ı kaldırın ve ardından Office yüklemenizle eşleşen Power BI Desktop sürümünü yükleyin. Bir Power BI Desktop sürümü seçmek için, masaüstüne yönelik indirme sayfasında **Gelişmiş yükleme seçenekleri**'ne tıklayın.
   
   ![](media/desktop-access-database-errors/desktop-access-errors-1.png)
   
   Görünen indirme sayfasında dilinizi ve ardından **İndir** düğmesini seçin. Görünen ekranda 32 bit sürüm için PBIDesktop.msi onay kutusunu, 64 bit sürüm için ise PBIDesktop_x64.msi onay kutusunu işaretleyin. Aşağıdaki ekranda 64 bit sürüm seçilidir.
   
   ![](media/desktop-access-database-errors/desktop-access-errors-2.png)
   
   >[!NOTE]
   >Power BI Desktop'ın 32 bit sürümü kullanılırken çok büyük veri modelleri oluşturduğunuz sırada yetersiz bellek sorunlarıyla karşılaşabilirsiniz.
2. Microsoft Office sürümünü Power BI Desktop yüklemenizin bit sürümüyle eşleşecek şekilde değiştirin. Microsoft Office'in bit sürümünü değiştirmek için Office'i kaldırın ve ardından Power BI Desktop yüklemenizle eşleşen Office sürümünü yükleyin.
3. Hata, bir .XLS dosyası (bir Excel 97-2003 çalışma kitabı) açılmaya çalışılırken oluştuysa .XLS dosyasını Excel'de açıp .XLSX dosyası olarak kaydederek Access Veritabanı Altyapısı'nı kullanmaktan kaçınabilirsiniz.
4. Önceki üç çözüm uygun değilse Access Veritabanı Altyapısı'nın iki sürümünü birden yüklemek de mümkündür ancak bu önerilen bir çözüm *değildir*. İki sürümü birden yüklemek Excel ve Power BI Desktop için bu Power Query sorununu giderse de Access Veritabanı Altyapısı'nın ilk yüklenen bit sürümünü otomatik olarak kullanan tüm uygulamalar için hatalara ve sorunlara neden olur. Access Veritabanı Altyapısı'nın her iki bit sürümünü birden yüklemek için her iki sürümü de [indirin](http://www.microsoft.com/download/details.aspx?id=13255) ve ardından */passive* anahtarını kullanarak bunları tek tek çalıştırın. Örneğin:
   
       c:\users\joe\downloads\AccessDatabaseEngine.exe /passive
   
       c:\users\joe\downloads\AccessDatabaseEngine_x64.exe /passive

### <a name="situation-3-trouble-using-access-or-xls-files-with-an-office-365-subscription"></a>3. Durum: Bir Office 365 aboneliğiyle Access veya .XLS dosyaları kullanılırken sorun yaşanması
Bir Office 365 aboneliği (**Office 2013** veya **Office 2016**) kullanıyorsanız Access Veritabanı Altyapısı sağlayıcısı *yalnızca* Office işlemlerinin erişebildiği sanal bir kayıt defteri konumuna kayıtlıdır. Sonuç olarak, bir Office işlemi olmayan Mashup Altyapısı (Office 365 Excel ve Power BI Desktop dışındaki çalıştırma işlemlerinden sorumludur) Access Veritabanı Altyapısı sağlayıcısını kullanamaz.

Bu durumu ortadan kaldırmak için Power BI Desktop yüklemenizin bit sürümüyle (bit sürümleri hakkında daha fazla bilgi için önceki bölümlere göz atın) eşleşen [Access Veritabanı Altyapısı yeniden dağıtılabilir paketini indirip yükleyin](http://www.microsoft.com/download/details.aspx?id=13255).

### <a name="other-situations-that-cause-import-issues"></a>İçeri aktarma sorunlarına neden olan diğer durumlar
Access veya .XLS dosyalarıyla ilgili mümkün olduğu kadar çok sayıda sorunu ele almak için elimizden geleni yapıyoruz. Bu makalede ele alınmayan bir sorunla karşılaşırsanız lütfen sonunla ilgili sorunuzu [Power BI Desteği](https://powerbi.microsoft.com/support/)'ne gönderin. Birçok müşteriyi etkileyebilecek sorunları düzenli olarak kontrol edip makalelerimizde bu sorunlara yer veriyoruz.

