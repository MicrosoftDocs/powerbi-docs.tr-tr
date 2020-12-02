---
title: Power BI Desktop’ta PDF dosyalarına bağlanma
description: Power BI Desktop'ta PDF dosyalarına kolayca bağlanın ve bu dosyaları kullanın
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 07/16/2020
LocalizationGroup: Connect to data
ms.openlocfilehash: ba0c1c6babe63c02ef0cd96a7cb5695e2c916c68
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96405779"
---
# <a name="connect-to-pdf-files-in-power-bi-desktop"></a>Power BI Desktop'ta PDF dosyalarına bağlanma
Tıpkı Power BI Desktop'taki diğer veri kaynaklarında olduğu gibi Power BI Desktop'ta bir **PDF dosyasına** bağlanabilir ve dosyadaki verileri kullanabilirsiniz.

![PDF dosyalarındaki verilere bağlanma](media/desktop-connect-pdf/connect-pdf-04.png)

Aşağıdaki bölümlerde **PDF dosyasına** bağlanma, veri seçme ve bu verileri **Power BI Desktop**'a alma adımları anlatılmaktadır.

Her zaman **Power BI Desktop** uygulamasının en son sürümünü kullanmanızı öneririz. Son sürüme [Power BI Desktop'ı edinin](../fundamentals/desktop-get-the-desktop.md) bağlantısından ulaşabilirsiniz. 

## <a name="connect-to-a-pdf-file"></a>PDF dosyasına bağlanma
Bir **PDF** dosyasına bağlanmak için Power BI Desktop'ın **Giriş** şeridindeki **Veri Al**'ı seçin. Soldaki kategorilerden **Dosya**’yı seçtiğinizde **PDF** seçeneğini görebilirsiniz.

![Veri Al menüsünden PDF'i seçme](media/desktop-connect-pdf/connect-pdf-01.png)

Kullanmak istediğiniz PDF dosyasının konumunu belirtmeniz istenir. Dosya konumu belirtildikten ve PDF dosyası yüklendikten sonra bir **Gezgin** penceresi açılır ve dosyadaki kullanılabilir verileri görüntüler. Bu veriler arasından **Power BI Desktop**'a aktarılıp kullanılacak bir veya daha fazla öğe seçebilirsiniz.

![PDF dosyalarındaki verilere bağlanma](media/desktop-connect-pdf/connect-pdf-04.png)

PDF dosyasında bulunan öğelerin yanındaki onay kutusunu işaretlediğinizde ilgili öğe sağdaki bölmede görüntülenir. İçeri aktarmaya hazır olduğunuzda **Yükle** düğmesini seçerek verileri **Power BI Desktop**'a alabilirsiniz.

**Power BI Desktop**’un Kasım 2018 sürümünden başlayarak, PDF bağlantınız için isteğe bağlı parametreler olarak **Başlangıç Sayfası** ve **Son Sayfa**'yı belirtebilirsiniz. Ayrıca aşağıdaki biçimi kullanarak bu parametreleri M formül diliyle de belirtebilirsiniz:

`Pdf.Tables(File.Contents("c:\sample.pdf"), [StartPage=10, EndPage=11])`

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

PDF bağlayıcısıyla Premium kapasitedeki veri kümeleri üzerinde çalışırken PDF bağlayıcısı düzgün bağlantı kuramıyor. PDF bağlayıcısının Premium kapasitedeki veri kümeleriyle çalışabilmesi için veri kümesini ağ geçidi kullanacak şekilde yapılandırın ve veri kümesi bağlantısının ağ geçidinden geçmesini sağlayın.  


## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   
