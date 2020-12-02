---
title: Power BI Desktop'tan bir Web sayfasına bağlanma
description: Power BI Desktop'ta Web sayfası verilerine kolayca bağlanma ve bunları kullanma
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 05/08/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: 0b66c069daedeb714fad3545d61f9cde8f2271da
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96411276"
---
# <a name="connect-to-webpages-from-power-bi-desktop"></a>Power BI Desktop'tan Web sayfalarına bağlanma

Power BI Desktop'ta bir Web sayfasına bağlanıp verilerini içeri aktararak görsellerinizde ve veri modellerinizde kullanabilirsiniz.

Power BI Desktop'ta **Giriş** şeridinden **Veri Al > Web**'i seçin.

![Web seçimini gösteren Power BI Desktop’ın ekran görüntüsü.](media/desktop-connect-to-web/connect-to-web-01.png)

Verilerini içeri aktarmak istediğiniz Web sayfasının URL'sini girmenizi isteyen bir iletişim kutusu açılır.

![URL alanını gösteren Web iletişim kutusunun ekran görüntüsü.](media/desktop-connect-to-web/connect-to-web-02.png)

URL'yi yazdıktan (veya yapıştırdıktan) sonra **Tamam**'ı seçin. Power BI Desktop web içeriğine nasıl erişmek istediğinizi belirtmenizi ister.

![Web’e bağlanırken kullanılacak kimlik bilgileri](media/desktop-connect-to-web/connect-to-web-03.png)

Power BI Desktop web sayfasına bağlanır ve sayfadaki verileri **Gezgin** penceresinde görüntüler. Kullanılabilir veri öğelerinden birini (sayfanın tamamını içeren bir tablo gibi) seçtiğinizde **Gezgin** penceresinin sağ tarafında, seçtiğiniz verilerin önizlemesi görüntülenir.

![Seçili tablolardaki verilerin önizlemesini gösteren Gezgin iletişim kutusunun ekran görüntüsü.](media/desktop-connect-to-web/connect-to-web-04.png)

**Verileri Dönüştür** düğmesini seçerek **Sorgu Düzenleyicisi**’ni başlatabilir, Power BI Desktop’a aktarmadan önce Web sayfasındaki verileri burada şekillendirebilir ve dönüştürebilirsiniz. Dilerseniz **Yükle** düğmesini seçerek, sol bölmede seçtiğiniz tüm veri öğelerini içeri aktarabilirsiniz.

**Yükle**'yi seçtiğinizde Power BI Desktop seçilen öğeleri içeri aktarır ve Power BI Desktop'ta Raporlar Görünümü'nün sağ tarafında bulunan **Alanlar** bölmesinde kullanılabilir hale getirilir.

![Seçili tabloların listesini gösteren Alanlar bölmesinin ekran görüntüsü.](media/desktop-connect-to-web/connect-to-web-05.png)

Web sayfalarına bağlanmak ve verilerini Power BI Desktop'a aktarmak için yapmanız gerekenler bu kadardır.

Bu işlemin ardından, içeri aktarılan alanları Rapor tuvaline sürükleyebilir ve dilediğiniz görselleştirmeleri oluşturabilirsiniz. Ayrıca Web sayfasından aldığınız bu verileri diğer tüm verilerle olduğu gibi kullanabilirsiniz. Verileri şekillendirebilir, modelinizdeki diğer veri kaynaklarıyla arasında ilişki oluşturabilir ve istediğiniz Power BI raporunu oluşturmak için diğer tüm işlevlerden faydalanabilirsiniz.

Web sayfalarına bağlanma hakkında ayrıntılı bilgi için bkz. [Power BI Desktop ile Çalışmaya Başlama Kılavuzu](../fundamentals/desktop-getting-started.md).

## <a name="certificate-revocation-check"></a>Sertifika iptal denetimi

Power BI, verilerinizi korumak için web bağlantılarına güvenlik uygular. Fiddler ile web isteklerini yakalama gibi bazı senaryolarda web bağlantıları düzgün çalışmayabilir. Bu tür senaryolara olanak tanımak için Power BI Desktop’taki **Sertifika iptal denetimini etkinleştir** seçeneğinin onay işaretini kaldırıp PowerBI Desktop’ı yeniden başlatabilirsiniz. 

Bu seçeneği değiştirmek için **Dosya > Seçenekler**’i seçin ve sonra soldaki bölmede **Güvenlik** seçeneğini belirleyin. Aşağıdaki görüntüde bu onay kutusu gösterilmektedir. Kutunun işaretini kaldırmak, web bağlantılarını daha az güvenli hale getirir. 

![Sertifika iptal denetimini etkinleştirme veya devre dışı bırakma](media/desktop-connect-to-web/connect-to-web-06.png)


## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop'taki veri kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Power BI Desktop'ta CSV dosyalarına bağlanma](desktop-connect-csv.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   
