---
title: "Excel 2016'daki içeriği Power BI'da yayımlama"
description: "Bir Excel çalışma kitabını Power BI sitenizde yayımlamayı öğrenin."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 14845d060b3fa6e1dfcd8e5a25affd33183e480b
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2017
---
# <a name="publish-to-power-bi-from-excel-2016"></a>Excel 2016'daki içeriği Power BI'da yayımlama
Excel 2016 ile Excel çalışma kitaplarınızı, çalışma kitabı verilerine dayalı olarak son derece etkileşimli raporlar ve panolar oluşturabileceğiniz [Power BI](https://powerbi.microsoft.com) sitenizde doğrudan yayımlayabilirsiniz. Daha sonra öngörülerinizi, kuruluşunuzdaki diğer kişilerle paylaşabilirsiniz.

Daha fazla ilerlemeden aklınızda bulundurmanız gereken birkaç nokta vardır:

* Çalışma kitabınızı Power BI'da yayımlayabilmek için OneDrive İş'e kaydetmeniz gerekir.
* Office, OneDrive İş ve Power BI'da oturum açmak için kullandığınız hesap aynı olmalıdır.
* Power BI tarafından desteklenen herhangi bir içerik barındırmayan veya boş bir çalışma kitabını yayımlayamazsınız.
* Şifreli veya parola korumalı çalışma kitaplarını ya da Information Protection Management özellikli çalışma kitaplarını yayımlayamazsınız.
* Power BI'da içerik yayımlayabilmeniz için modern kimlik doğrulama etkinleştirilmiş (varsayılan) olmalıdır. Devre dışı bırakılırsa Dosya menüsündeki Yayımla seçeneği kullanılamaz.

## <a name="to-publish-your-excel-workbook"></a>Excel çalışma kitabınızı yayımlamak için
Excel'de **Dosya** > **Yayımla** seçeneğini belirleyin.

### <a name="local-file-publishing"></a>Yerel dosya yayımlama
Excel 2016, Şubat 2017 güncelleştirmesi itibarıyla yerel Excel dosyalarının yayımlanmasını desteklemektedir. Dosyaların OneDrive İş'e veya SharePoint Online'a kaydedilmesi gerekmez.

> [!IMPORTANT]
> Yerel dosyaları yayımlama özelliği yalnızca Office 365 aboneliği içeren Excel 2016'da kullanılabilir. Excel 2016 tek başına yüklemesinde "Yayımla" seçeneği bulunur ancak Excel çalışma kitaplarının OneDrive İş'e veya SharePoint Online'a kaydedilmesi gerekir.
> 
> 

**Yayımla**'yı seçtiğinizde, içeriği yayımlamak istediğiniz çalışma alanını seçebilirsiniz. Bu, erişiminiz olan kişisel çalışma alanınız veya grup çalışma alanınız olabilir.

![](media/service-publish-from-excel/pbi_choose_workspace.png)

Çalışma kitabınızı Power BI'a aktarmak için iki seçeneğe sahipsiniz.

![](media/service-publish-from-excel/pbi_uploadexport3.png)

Çalışma kitabınız yayımlandıktan sonra, Power BI'da bir kopya olarak ve yerel dosyadan ayrı şekilde saklanır. Dosyayı Power BI'da güncelleştirmek istiyorsanız güncelleştirilmiş sürümü tekrar yayımlamanız gerekir. Power BI'daki çalışma kitabında veya veri kümesinde verileri yenileyebilir ve bunlar için zamanlanmış yenileme ayarlayabilirsiniz.

### <a name="publishing-from-excel-standalone"></a>Tek başına yüklenen Excel'den yayımlama
Henüz yapmadıysanız ilk olarak çalışma kitabınızı OneDrive'a kaydetmeniz gerekir. Buluta Kaydet seçeneğini belirleyin ve OneDrive İş'te bir konum seçin.

![](media/service-publish-from-excel/pbi_savetoonedrive2.png)

Çalışma kitabınız OneDrive'a kaydedildikten sonra **Yayımla** seçeneğini belirlediğinizde, çalışma kitabınızı Power BI'a aktarmaya yönelik iki seçenek görürsünüz.

![](media/service-publish-from-excel/pbi_uploadexport2.png)

#### <a name="upload-your-workbook-to-power-bi"></a>Çalışma kitabınızı Power BI'a yükleme
Bu seçeneği belirlediğinizde çalışma kitabınız Power BI'da tıpkı Excel Online'da göründüğü gibi görünecektir. Ancak, Excel Online'dan farklı olarak öğeleri çalışma sayfalarınızdan panolara sabitlemenize yardımcı olacak harika özelliklere sahip olacaksınız.

Çalışma kitabınızı Power BI'da açıkken düzenleyemezsiniz ancak bazı değişiklikler yapmanız gerekirse **Düzenle** seçeneğini belirleyip çalışma kitabınızı Excel Online'da düzenlemeyi veya bilgisayarınızdaki Excel programında açmayı seçebilirsiniz. Yaptığınız değişiklikler OneDrive'daki çalışma kitabına kaydedilir.

Karşıya yüklediğinizde Power BI'da herhangi bir veri kümesi oluşturulmaz. Çalışma kitabınız, çalışma alanı gezinti bölmesindeki Raporlar bölümünde görünür. Power BI'a yüklenen çalışma kitaplarında özel bir Excel simgesi bulunur. Bu simge, söz konusu çalışma kitaplarının karşıya yüklendiğini belirtir.

Çalışma sayfalarında yalnızca veri varsa veya Power BI'da görmek istediğiniz PivotTable'lar ve Grafikler söz konusuysa bu seçimi yapın.
Excel'deki Power BI'a yayımla bölümünde bulunan Karşıya Yükle seçeneği, kullanım açısından tarayıcınızdaki Power BI hizmetinde var olan Veri Al > Dosyalar > OneDrive İş > Power BI üzerinde Excel'e Bağlanın, Yönetin ve Görüntüleyin seçeneğiyle hemen hemen aynıdır.

#### <a name="export-workbook-data-to-power-bi"></a>Çalışma kitabı verilerini Power BI'a aktarma
Bu seçeneği belirlediğinizde tablo ve/veya veri modellerindeki desteklenen tüm veriler Power BI'da yeni bir veri kümesine aktarılır. Power View sayfalarınız varsa bunlar Power BI'da rapor olarak yeniden oluşturulur.

Çalışma kitabınızı düzenlemeye devam edebilirsiniz. Değişiklikleriniz kaydedildikten sonra, genellikle yaklaşık bir saat içinde Power BI'daki veri kümesi ile eşitlenir. Daha hızlı bir sonuç elde etmek istiyorsanız Yayımla'yı seçtiğinizde değişiklikleriniz anında dışarı aktarılır. Raporlarınızda ve ponalarınızda bulunan tüm görselleştirmeler de güncelleştirilir.

Verileri bir veri modeline yüklemek için Al ve Dönüştür veya Power Pivot seçeneğini kullandıysanız ya da çalışma kitabınız, Power BI'da görmek istediğiniz görselleştirmeleri içeren Power View sayfaları içeriyorsa bu seçeneği belirleyin.

Excel'deki Power BI'a yayımla bölümünde bulunan Dışarı Aktar seçeneği, kullanım açısından tarayıcınızdaki Power BI hizmetinde var olan Veri Al > Dosyalar > OneDrive İş > Excel verilerini Power BI'a aktarın seçeneğiyle hemen hemen aynıdır.

## <a name="publishing"></a>Yayımlama
Seçeneklerden birini belirlediğinizde Excel, geçerli hesabınızı kullanarak Power BI'da oturum açar ve ardından çalışma kitabınızı Power BI sitenizde yayımlar. Excel'deki durum çubuğunu takip edin. İşlemlerinizin durumunu buradan görebilirsiniz.

![](media/service-publish-from-excel/pbi_publishingstatus.png)

İşlem tamamlandığında, doğrudan Excel'den Power BI'a gidebilirsiniz.

![](media/service-publish-from-excel/pbi_gotopbi.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki Excel verileri](service-excel-workbook-files.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

