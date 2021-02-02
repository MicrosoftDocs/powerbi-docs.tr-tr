---
title: Bir Power BI görselinden verileri dışarı aktarma
description: Bir rapor görselindeki ve pano görselindeki verileri dışarı aktarıp Excel'de görüntüleyin.
author: mihart
ms.author: mihart
ms.reviewer: cmfinlan
featuredvideoid: removed
ms.service: powerbi
ms.subservice: pbi-explore
ms.topic: how-to
ms.date: 01/31/2021
LocalizationGroup: Consumers
ms.openlocfilehash: f0373ae170b9b81d81514478b432ecb445e757aa
ms.sourcegitcommit: 2e81649476d5cb97701f779267be59e393460097
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/02/2021
ms.locfileid: "99422318"
---
# <a name="export-data-from-a-visual"></a>Bir görseldeki verileri dışarı aktarma

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]


Bir görselin oluşturulması için kullanılan verileri görmek için [söz konusu verileri Power BI’da görüntüleyebilir](end-user-show-data.md) veya Excel'e aktarabilirsiniz. Bu makalede, Excel 'e nasıl verileceği gösterilmektedir.

Verilerin Excel 'e aktarılması için Power BI Pro bir lisans gerekir ya da pano veya raporun Premium kapasiteyi kullanarak sizinle paylaşılması gerekir. Daha fazla bilgi edinmek için bkz. [Hangi lisansa sahibim?](end-user-license.md). 

> [!IMPORTANT]
> Excel 'e dışa aktardıysanız rapor yazarı veya Power BI yöneticiniz bu özelliği devre dışı bırakmış olabilir. Bu, genellikle özel verileri korumak için yapılır.


## <a name="export-data-from-a-visual-on-a-dashboard"></a>Panodaki verileri görselden dışarı aktarma

1. Bir Power BI panosu başlatın. Burada ***Pazarlama ve satış örneği** _ uygulamasındaki panoyu kullanacağız. Bu uygulamayı [AppSource.com adresinden indirebilirsiniz](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample).

    ![Uygulama panosu](media/end-user-export/power-bi-dashboard.png)

2. Bir görselin üzerine gelerek _ *Diğer seçenekler** (...) seçeneğini ortaya çıkarın ve tıklayarak eylem menüsünü görüntüleyin.

    ![Üç nokta seçildiğinde görünen menü](media/end-user-export/power-bi-option-menu.png)

3. **CSV'ye Aktar**’ı seçin.

4. Bundan sonra ne olacağı, kullandığınız tarayıcıya bağlıdır. Dosyayı kaydetmeniz istenebilir veya tarayıcının altında dışarı aktarılmış dosyanın bir bağlantısını görebilirsiniz. Varsayılan olarak dışarı aktardığınız dosya yerel İndirilenler klasörünüze kaydedilir. 

    ![Dışarı aktarılmış dosya bağlantısını gösteren Chrome tarayıcısı](media/end-user-export/power-bi-dashboards-export.png)

5. Dosyayı Excel'de açın. 

    > [!NOTE]
    > Veriler üzerinde izinleriniz yoksa, Excel'e dışarı aktaramaz veya Excel'de açamazsınız. Dışarı aktarma izinleri istemek için Pano sahibine veya Power BI yöneticinize başvurun. 

    ![Excel’de Yılbaşından Bugüne Toplam Birim Sayısı](media/end-user-export/power-bi-excel.png)


## <a name="export-data-from-a-visual-in-a-report"></a>Rapordaki görselden verileri dışarı aktarma
Bir rapordaki görselden verileri .csv veya .xlsx (Excel) biçiminde dışarı aktarabilirsiniz. 

1. Bir panoda, temel alınan raporu açmak için kutucuk seçin.  Bu örnekte, yukarıdakiyle aynı görseli seçiyoruz, *Yılbaşından Bugüne Toplam Birimler Var %*. 

    ![Vurgulanan pano kutucuğu](media/end-user-export/power-bi-export-tile.png)

    Bu kutucuk *Satış ve Pazarlama Örneği* raporundan oluşturulduğu için bu rapor açılır. Ayrıca, seçili kutucuk görselini içeren sayfada açılır. 

2. Raporda görseli seçin. Sağ taraftaki **Filtreler** bölmesine dikkat edin. Bu görsele filtreler uygulanmıştır. Filtreler hakkında daha fazla bilgi için bkz. [Raporda filtre kullanma](end-user-report-filter.md).

    ![Filtre bölmesi seçildi](media/end-user-export/power-bi-export-filter-pane.png)


3. Görselleştirmenin sağ üst köşesinde **Diğer seçenekler (...)** öğesini seçin. **Verileri dışarı aktar** seçeneğini belirleyin.

    ![Açılan menüden seçilen Verileri dışarı aktar](media/end-user-export/power-bi-export-reports.png)

4. Özetlenen verileri veya temel alınan verileri dışarı aktarma seçeneklerini görürsünüz. *Satış ve pazarlama örneği* uygulamasını kullanıyorsanız, **Temel alınan veriler** devre dışı olacaktır. Görselde görüntülenenden daha fazla veri görmek için ek izinler gerekir (temel alınan veriler). Bu izinler, verilerin uygun şekilde görüntülenmesini, yeniden kullanılmasını veya amaçlanan kitleden başka kişilerle paylaşılmasını korur.

    **Özetlenmiş veriler**: Görselde şu anda gördükleriniz için verileri dışarı aktarmak istiyorsanız bu seçeneği belirtin.  Bu tür bir dışarı aktarma işlemi size yalnızca görselin şu anki durumunu oluşturmak için kullanılan verileri gösterir. Görselde uygulanmış filtreler varsa, dışarı aktardığınız veriler de filtrelenecektir. Örneğin, bu görsel için dışa aktarma işlemi yalnızca 2014 ve merkezi bölgenin verilerini ve yalnızca dört üreticinin verilerini içerir: VanArsdel, Natura, Aliqui ve Pirum. Görselinizin toplamaları (toplam, ortalama vb.) varsa, dışarı aktarma da toplanacaktır. 
  

    **Temel alınan veriler**: Görselde gördüklerinize **ek olarak** temel alınan veri kümesinden ek verileri dışarı aktarmak istiyorsanız bu seçeneği belirleyin.  Buna veri kümesinde bulunmasına karşın görselde kullanılmayan veriler dahil olabilir. Görselde uygulanmış filtreler varsa, dışarı aktardığınız veriler de filtrelenecektir.  Görselinizin toplamaları (toplam, ortalama vb.) varsa, dışarı aktarma işlemi toplamayı kaldırır; temelde verileri düzleştirir. 

    ![Temel alınan veya özetlenmiş verileri seçtiğiniz menü](media/end-user-export/power-bi-export-underlying.png)

5. Bundan sonra ne olacağı, kullandığınız tarayıcıya bağlıdır. Dosyayı kaydetmeniz istenebilir veya tarayıcının altında dışarı aktarılmış dosyanın bir bağlantısını görebilirsiniz. Microsoft Teams'de Power BI uygulamasını kullanıyorsanız, dışarı aktarılan dosyanız yerel İndirilenler klasörünüze kaydedilir. 

    ![Microsoft Edge tarayıcısında dışarı aktarılan dosya görüntüleme](media/end-user-export/power-bi-export-edge-screen.png)

    > [!NOTE]
    > Veriler üzerinde izinleriniz yoksa, Excel'e dışarı aktaramaz veya Excel'de açamazsınız. Dışarı aktarma izinleri istemek için rapor sahibine veya Power BI yöneticinize başvurun. 


6. Dosyayı Excel'de açın. Panodaki aynı görselden aktarıldığımız veri miktarını karşılaştırın. Fark, bu dışarı aktarmanın **Temel alınan verileri** içermesidir. 

    ![Örnek Excel](media/end-user-export/power-bi-underlying.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
Excel 'e aktarılmayla ilgili birçok önemli noktalar vardır. Bu, rapor tasarımcıları ve Power BI yöneticilerinin bireyler için veya hatta kuruluşun tamamında devre dışı bırakabilecek özelliklerden biridir. Özel verilerin yanlış hedef kitleye açık olmamasını sağlamak için bunu yapabilirsiniz. 

Bu özelliği kullanamadığınızı fark ederseniz, belirli bir görselden veya tüm görsellerden neden veri aktarmadığınızı anlamak için rapor sahibine ve yöneticinize ulaşın. Bu özellik özellikle devre dışı bırakılmış olabilir ve belki de etkinleştirebilirler.  Diğer zamanlarda, bir dışa aktarmanın çalışmamasının belirli nedenleri olabilir.  Bu, izinler, veri içerikleri, veri türü, görsel tür, tasarımcı alanları adı ve daha fazlası ile ilgili olabilir. Rapor sahibine veya yöneticisine başvururken, bu makalelere başvurun: [yönetici Kiracı ayarları](../guidance/admin-tenant-settings.md), [satır düzeyi güvenlik](../admin/service-admin-rls.md)ve [veri koruma](../admin/service-security-data-protection-overview.md).

- Excel 'e aktarılabilecek satır sayısı için bir sınır vardır.  . Xlsx dosyaları için sınır 150.000 satırdır.  . Csv dosyaları için sınır 30.000 satırdır. 

- Veri kümesinde verilere RLS (rol düzeyi güvenlik) uygulanmış olabilir. Bu, bazı verilerin sizin görmeniz için uygun olmadığından, sizin için gizli olabileceği anlamına gelir.  Örneğin, bir kişi Yöneticisi kullanıyorsanız, HR veri kümesinde yalnızca doğrudan size rapor veren çalışanlar için verileri görmenizi sağlayan RLS uygulanmış olabilir. 

- Bazı görsel türleri desteklenmez. Bunlar özel görseller, R görselleri ve daha fazlasını içerir. 

## <a name="next-steps"></a>Sonraki adımlar

[Görsel oluşturmak için kullanılan verileri görüntüleme](end-user-show-data.md)