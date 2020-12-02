---
title: Excel Online tablosu veya SharePoint listesindeki her satır için bir sayfalandırılmış rapor dışarı aktarma
description: Bu makalede Power Automate'i kullanarak Excel Online tablosu veya SharePoint listesindeki her satır için bir sayfalandırılmış rapor dışarı aktarma işlemini otomatikleştireceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: how-to
ms.date: 11/17/2020
LocalizationGroup: Get started
ms.openlocfilehash: 74d61d40c4447f2649f5cce5fbcdcba68cd31afe
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96408010"
---
# <a name="export-a-paginated-report-for-each-row-in-an-excel-online-table-or-sharepoint-list"></a>Excel Online tablosu veya SharePoint listesindeki her satır için bir sayfalandırılmış rapor dışarı aktarma

[Power Automate](/power-automate/getting-started) ile Power BI sayfalandırılmış raporlarını birçok farklı biçim ve senaryo kapsamında dışarı aktarma ve dağıtma işlemlerini otomatikleştirebilirsiniz. Bu makalede bir Power Automate şablonu kullanarak tek veya birden çok sayfalandırılmış raporu yinelenen bir şekilde dışarı aktarmak için ayarlama sürecini otomatikleştireceksiniz. Bu raporları Excel Online tablosu veya SharePoint Online listesindeki her bir satır için istenen biçimde dışarı aktaracaksınız. Dışarı aktarılan sayfalandırılmış raporu OneDrive İş'e veya SharePoint Online sitesine dağıtabilir ya da Office 365 Outlook ile e-posta eki olarak gönderebilirsiniz.

:::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-overview.png" alt-text="Sayfalandırılmış raporu Excel Online tablosu kullanarak dışarı aktarma.":::

Excel Online tablonuzdaki veya SharePoint Online listenizdeki her bir satır, sayfalandırılmış raporu abonelik tabanlı olarak alacak tek bir kullanıcıyı temsil edebilir. Ya da her bir satır, dağıtmak istediğiniz benzersiz bir sayfalandırılmış raporu temsil edebilir. Tablonuzda veya listenizde raporu OneDrive, SharePoint Online veya Outlook ile dağıtma seçeneğini belirten bir sütun bulunması gerekir. Power Automate akışı, Switch deyiminde bu sütunu kullanır.

Power BI sayfalandırılmış raporlarına yönelik farklı Power Automate şablonları mı arıyorsunuz? Bkz. [Power Automate ile Power BI sayfalandırılmış raporlarını dışarı aktarma](service-automate-paginated-integration.md).

## <a name="prerequisites"></a>Önkoşullar  

Buradaki adımları takip etmek için aşağıdakilere sahip olduğunuzdan emin olun:

- Power BI kiracınızda ayrılmış kapasiteye sahip olan en az bir çalışma alanı. Bu kapasite A4/P1 - A6/P3 arası SKU'lardan herhangi biri olabilir. [Power BI Premium'daki ayrılmış kapasiteler](../admin/service-premium-what-is.md) hakkında daha fazla bilgi edinin.
- Power Automate'teki standart bağlayıcılara erişim (tüm Office 365 abonelikleriyle sunulur).
- Excel Online tablosu kullanıyorsanız bu tablonun Excel'de tablo olarak biçimlendirilmesi gerekir. Nasıl yapılacağını öğrenmek için bkz. [Tablo oluşturma](https://support.microsoft.com/office/create-a-table-in-excel-bf0ce08b-d012-42ec-8ecf-a2259c9faf3f).

## <a name="export-a-paginated-report-for-each-row-in-a-table-or-list"></a>Bir tablo veya listede bulunan her bir satır için bir sayfalandırılmış rapor dışarı aktarma

> [!NOTE]
> Aşağıdaki adımlarda ve görüntülerde **Excel Online tablosundaki her satır için bir Power BI sayfalandırılmış raporunu dışarı aktarma** şablonunu kullanarak akışı ayarlama süreci gösterilmiştir. Aynı adımları kullanarak **Power BI sayfalandırılmış raporunu her satır için SharePoint Online listesi biçiminde dışarı aktarma** şablonuyla da bir akış oluşturabilirsiniz. Sayfalandırılmış raporu dışarı aktarmaya yönelik bilgiler Excel Online tablosu yerine SharePoint Online listesi şeklinde sunulur.  

1. [flow.microsoft.com](https://flow.microsoft.com/) adresinden Power Automate'te oturum açın. 
1. **Şablonlar**'ı seçip  **sayfalandırılmış raporlar** araması yapın. 

    :::image type="content" source="media/service-automate-paginated-integration/power-bi-paginate-automate.png" alt-text="Power BI sayfalandırılmış raporlarına yönelik Power Automate şablonlarının ekran görüntüsü.":::

1. **Excel Online tablosundaki her satır için bir Power BI sayfalandırılmış raporunu dışarı aktarma** veya **SharePoint Online listesindeki her satır için bir Power BI sayfalandırılmış raporunu dışarı aktarma** şablonunu seçin. Excel Online, Power BI, OneDrive İş, SharePoint Online ve Office 365 Outlook'ta oturum açtığınızdan emin olun. **Devam**’ı seçin.  

   :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-excel-online-1.png" alt-text="Excel Online tablosundaki her satır için bir Power BI sayfalandırılmış raporunu dışarı aktarma.":::

1. Akışınızın **Yinelenme** değerini ayarlamak için **Sıklık** alanından bir seçenek belirleyip istediğiniz **Aralık** değerini girin.

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-recurrence-2.png" alt-text="Akışınız için yinelenme değerini seçin.":::

1. (İsteğe bağlı) **Gelişmiş seçenekleri göster**'i seçerek ek **Yinelenme** parametrelerini ayarlayabilirsiniz. Bunların arasında **Saat dilimi**, **Başlangıç saati**, **Şu günlerde**, **Şu saatlerde** ve **Şu dakikalarda** parametreleri bulunur.

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-advanced-recurrence-3.png" alt-text="İsteğe bağlı olarak gelişmiş yinelenme seçeneklerini belirleyebilirsiniz.":::

1. **Konum** kutusunda Excel Online tablonuzun veya SharePoint Online listenizin kayıtlı olduğu OneDrive İş veya SharePoint Online sitesini seçin. Ardından açılan menüden **Belge Kitaplığı**'nı seçin.

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-location-4.png" alt-text="Excel Online tablosunun konumunu seçin.":::

1. **Dosya** kutusunda Excel Online dosyasını veya SharePoint Online listesini seçin. **Tablo** kutusundaki açılan menüden tablonun veya listenin adını seçin. 
 
    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-file-table-5.png" alt-text="Excel Online dosyasını ve tablonun adını seçin.":::

    > [!TIP]
    > Verileri Excel'de tablo olarak biçimlendirmeyi öğrenmek için bkz. [Tablo oluşturma](https://support.microsoft.com/office/create-a-table-in-excel-bf0ce08b-d012-42ec-8ecf-a2259c9faf3f). 

1. Dosya adı için kullanılacak bir değişken başlatın. **Ad** ve **Değer** için varsayılan değerleri kullanabilir veya değiştirebilirsiniz ancak **Tür** alanını **Dize** olarak bırakın.  

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-name-type-6.png" alt-text="Ad ve Değer alanını doldurup Tür alanını Dize olarak bırakın.":::

1. **Her Birine Uygula** bölümündeki **Önceki adımdan bir çıkış seç** kutusu varsayılan olarak **değer** şeklindedir. Bu ayar, **Her Birine Uygula** alanındaki eylemleri Excel Online tablonuzda veya SharePoint Online listenizde bulunan her satır için yineler.  

1. **Çalışma alanı** kutusunda ayrılmış kapasitede bulunan bir çalışma alanını seçin. **Rapor** kutusunda seçtiğiniz çalışma alanında bulunan ve dışarı aktarmak istediğiniz sayfalandırılmış raporu seçin. Açılan menüden **Özel değer girin**'i seçerseniz **Çalışma alanı** ve **Rapor** için Excel Online tablonuzda veya SharePoint Online listenizde bulunan bir sütunu seçebilirsiniz. Bu sütunlarda Çalışma Alanı Kimlikleri ve Rapor Kimlikleri bulunmalıdır.  

1. Açılan menüden **Dışarı Aktarma Biçimi** seçin veya Excel Online tablonuzda bulunan ve istenen dışarı aktarma biçimlerini içeren bir sütun olarak ayarlayın. Örneğin PDF, DOCX veya PPTX olabilir. İsteğe bağlı olarak sayfalandırılmış rapora yönelik parametreler belirtebilirsiniz. Parametrelerle ilgili ayrıntılı açıklamalar için bkz. [Power BI Rest API için bağlayıcı başvurusu](/connectors/powerbi/#export-to-file-for-paginated-reports).

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-export-format-9.png" alt-text="Sayfalandırılmış Raporlar için Dosyaya Aktar bölümünü doldurma.":::

1. **Değer** kutusuna dışarı aktarılan sayfalandırılmış rapor için bir ad girin. Dosya uzantısı girdiğinizden emin olun. Bunu .pdf, .docx veya .pptx gibi sabit bir değer olarak ayarlayabilirsiniz. İsterseniz Excel tablonuzda bulunan ve istediğiniz dışarı aktarma biçimini tanımlayan sütunu seçerek dinamik olarak ayarlayabilirsiniz. 

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-output-value-10.png" alt-text="Raporun adını ve dosya uzantısını seçin.":::

1. **Switch** eyleminde **Üzerinde** kutusuna Excel Online tablonuzda bulunan ve istenen dağıtım yöntemini gösteren sütunu ekleyin: **OneDrive**, **SharePoint** veya **E-posta**. 

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-switch-11.png" alt-text="Switch eyleminde Üzerinde kutusunu Excel Online tablonuzdaki sütunla doldurun.":::

1. **Durum**, **Durum 2** ve **Durum 3** alanlarına önceki adımda Excel Online tablosu sütununda bulunan değerleri girin.  

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-case-1-2-3-12.png" alt-text="Durum, Durum 2 ve Durum 3 değerlerini girin.":::

1. Sayfalandırılmış raporunuzu OneDrive'a kaydettiğiniz durumda kaydedilmesini istediğiniz **Klasör Yolunu** seçin.  

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-case-onedrive-13.png" alt-text="OneDrive'a kaydettiğiniz durum.":::

1. Sayfalandırılmış raporunuzu SharePoint Online'a kaydettiğiniz durumda kaydedilmesini istediğiniz **Site Adresi** ve **Klasör Yolu** bilgilerini girin. 

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-case-sharepoint-14.png" alt-text="Sayfalandırılmış raporunuzu SharePoint Online'a kaydettiğiniz durumda.":::

1. Sayfalandırılmış raporunuzu Outlook aracılığıyla e-posta olarak gönderdiğiniz durumda **Alıcı**, **Konu** ve **Gövde** kutularını doldurun. Bu kutularda statik içerikler veya Excel Online tablonuzdan ya da SharePoint Online listenizden gelen dinamik içerikler bulunabilir. Power Automate, sayfalandırılmış raporunuzu bu e-postaya otomatik olarak ekler.  

    :::image type="content" source="media/service-automate-paginated-excel-sharepoint-list/excel-template-case-email-15.png" alt-text="Sayfalandırılmış raporunuzu Outlook aracılığıyla e-posta olarak gönderdiğiniz durum.":::

1. İşlemleri tamamladığınızda  **Sonraki adım** veya **Kaydet**'i seçin. Power Automate akışı oluşturup değerlendirir ve varsa hataları bildirir. 

1. Hatalar varsa **Akışı düzenle** ile düzeltin. Yoksa **Geri** okunu seçerek akış ayrıntılarını görüntüleyin ve yeni akışı çalıştırın. 


## <a name="next-steps"></a>Sonraki adımlar

- [Power Automate ile Power BI sayfalandırılmış raporlarını dışarı aktarma](service-automate-paginated-integration.md)
- [Power Automate kullanmaya başlama](/power-automate/getting-started/)
- Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

