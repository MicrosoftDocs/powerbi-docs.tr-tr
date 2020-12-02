---
title: Power BI Desktop'ta CSV dosyalarına bağlanma
description: Power BI Desktop'ta CSV dosyası verilerine kolayca bağlanma ve bunları kullanma
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 08/29/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: 3bb37d4ba3b3ca7d5fec3f8577b971432f5a9d0f
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96411391"
---
# <a name="connect-to-csv-files-in-power-bi-desktop"></a>Power BI Desktop'ta CSV dosyalarına bağlanma
Power BI Desktop'tan virgülle ayrılmış değer (*CSV*) dosyalarına bağlanma işlemi Excel çalışma kitaplarına bağlanma işlemiyle oldukça benzerdir. Her iki işlem de kolayca gerçekleştirilebilir ve bu makalede, erişiminizin bulunduğu herhangi bir CSV dosyasına nasıl bağlanacağınız adım adım gösterilmiştir.

Başlamak için, Power BI Desktop'taki **Giriş** şeridinde **Veri Al > CSV** seçeneğini belirleyin.

![Veri Al menüsünün ekran görüntüsü.](media/desktop-connect-csv/connect-to-csv_1.png)

Görüntülenen **Aç** iletişim kutusundan CSV dosyanızı seçin.

![Aç iletişim kutusunun ekran görüntüsü.](media/desktop-connect-csv/connect-to-csv_2.png)

**Aç** seçeneğini belirlediğinizde, Power BI Desktop dosyaya erişir ve dosya kaynağı, sınırlayıcı türü ve dosyadaki veri türlerini algılamak için kullanılması gereken satır sayısı gibi bazı dosya özniteliklerini belirler.

Bu dosya öznitelikleri ve seçenekler, aşağıda gösterildiği gibi, **CSV al** iletişim kutusunun üst kısmındaki açılır seçicilerde gösterilir. Açılır seçicilerdeki başka bir seçeneği belirleyerek, algılanan bu ayarlardan herhangi birini elle değiştirebilirsiniz.

![CSV içeri aktarma iletişim kutusunun ekran görüntüsü.](media/desktop-connect-csv/connect-to-csv_3.png)

Seçimlerinizden memnun olduğunuzda, dosyayı Power BI Desktop'a aktarmak için **Yükle**'yi seçebilir veya içeri aktarma işleminden önce verileri daha fazla şekillendirmek ve dönüştürmek üzere **Sorgu Düzenleyicisi**'ni açmak için **Düzenle** seçeneğini belirleyebilirsiniz.

Verileri Power BI Desktop'a yükledikten sonra, tabloyu ve sütunlarını (Power BI Desktop'ta Alanlar olarak gösterilir), Power BI Desktop'taki Rapor görünümü'nün sağ tarafındaki **Alanlar** bölmesinde görürsünüz.

![Alanlar bölmesini gösteren Power BI Desktop penceresinin ekran görüntüsü.](media/desktop-connect-csv/connect-to-csv_4.png)

Yapmanız gereken tüm işlemler bunlardır. Ardından, CSV dosyanızdaki veriler Power BI Desktop'a aktarılır.

Görsel ve rapor oluşturmak veya diğer Excel çalışma kitapları, veritabanları ya da başka bir veri kaynağı gibi, bağlanmak veya içeri aktarmak isteyebileceğiniz verilerle etkileşime geçmek için Power BI Desktop'taki verileri kullanabilirsiniz.

> [!IMPORTANT]
> Power BI Desktop, bir CSV dosyasını içeri aktardığınızda, Güç Sorgu Düzenleyicisi’nde gerçekleştirilen bir adım olarak *columns=x* parametresi oluşturur (*x* değeri, ilk içeri aktarma işlemi esnasında CSV dosyasında bulunan sütunların sayısıdır). Bunun ardından daha fazla sütun eklenirse ve veri kaynağı yenilemeye ayarlanırsa, sütunların ilk *x* sayısının ötesindeki hiçbir sütun yenilenmez. 


## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   
