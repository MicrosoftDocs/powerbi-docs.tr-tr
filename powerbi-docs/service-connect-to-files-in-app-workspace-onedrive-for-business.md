---
title: Bir Power BI uygulaması çalışma alanı için OneDrive'daki dosyalara bağlanma
description: Power BI uygulama çalışma alanınız için OneDrive'da Excel, CSV ve Power BI Desktop dosyalarınızı depolama ve bunlara bağlanma hakkında bilgi edinin.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukasz
ms.service: powerbi
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 52b7748b6b634caf87de01ddc965576339a04b8b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61175075"
---
# <a name="connect-to-files-stored-in-onedrive-for-your-power-bi-app-workspace"></a>Power BI uygulama çalışma alanınız için OneDrive'da depolanan dosyalara bağlanma
[Power BI'da bir uygulama çalışma alanı oluşturduktan](service-create-distribute-apps.md) sonra Power BI uygulama çalışma alanınız için OneDrive İş'te Excel, CSV ve Power BI Desktop dosyalarınızı depolayabilirsiniz. Onedrive'da depoladığınız dosyaları güncelleştirmeye devam edebilirsiniz. Bu güncelleştirmeler, otomatik olarak Power BI rapor ve panolarındaki dosyalara bağlı yansıtılır. 

> [!NOTE]
> Yeni çalışma alanı deneyimi, Power BI çalışma alanları ve Office 365 grupları arasındaki ilişkiyi değiştirir. Yeni çalışma alanları birini her oluşturduğunuzda bir Office 365 grubu otomatik olarak oluşturmayın. Hakkında bilgi edinin [yeni çalışma alanları oluşturma](service-create-the-new-workspaces.md)

Uygulama çalışma alanınıza dosya ekleme iki adımlı bir işlemdir: 

1. Uygulama çalışma alanınız için öncelikle [OneDrive İş'e dosyaları yüklersiniz](service-connect-to-files-in-app-workspace-onedrive-for-business.md#1-upload-files-to-the-onedrive-for-business-for-your-app-workspace).
2. Ardından [Power BI'da bu dosyalara bağlanırsınız](service-connect-to-files-in-app-workspace-onedrive-for-business.md#2-import-excel-files-as-datasets-or-as-excel-online-workbooks).

> [!NOTE]
> Uygulama çalışma alanları yalnızca [Power BI Pro](service-features-license-type.md) ile kullanılabilir.
> 

## <a name="1-upload-files-to-the-onedrive-for-business-for-your-app-workspace"></a>1 Uygulama çalışma alanınız için OneDrive İş'e dosya yükleme
1. Power BI hizmetinde Çalışma Alanı'nın yanındaki oku ve ardından çalışma alanı adınızın yanındaki üç nokta ( **…** ) simgesini seçin. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-ellipsis.png)
2. Office 365'te uygulama çalışma alanınız için OneDrive İş'i açmak üzere **Dosyalar**'ı seçin.
   
   > [!NOTE]
   > Uygulama çalışma alanı menüsünde **Dosyalar**'ı görmüyorsanız uygulama çalışma alanınız için OneDrive İş'i açmak üzere **Üyeler**'i seçin. Burada, **Dosyalar** seçeneğini belirleyin. Office 365, uygulamanızın grup çalışma alanı dosyaları için bir OneDrive depolama konumu ayarlar. Bu işlem biraz zaman alabilir. 
   > 
   > 
3. Buradan uygulama çalışma alanınız için OneDrive İş'e dosyalarınızı yükleyebilirsiniz. **Karşıya Yükle**'yi seçip dosyalarınıza gidin.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grpfilesonedrive.png)

## <a name="2-import-excel-files-as-datasets-or-as-excel-online-workbooks"></a>2 Excel dosyalarını veri kümeleri veya Excel Online çalışma kitapları olarak içeri aktarma
Dosyalarınız artık uygulama çalışma alanınız için OneDrive İş'te olduğuna göre bir tercih yapabilirsiniz. Seçenekleriniz şunlardır: 

* [Bir veri kümesi olarak Excel çalışma kitabındaki verileri içeri aktarma](service-get-data-from-files.md). Ardından verileri raporlar ve bir web tarayıcısında veya mobil cihazlarda görüntüleyebileceğiniz panolar oluşturmak için kullanın.
* [Power BI'da Excel çalışma kitabının tamamına bağlanma](service-excel-workbook-files.md) ve bu çalışma kitabını tam olarak Excel Online'da göründüğü şekilde görüntüleme.

### <a name="import-or-connect-to-the-files-in-your-app-workspace"></a>Uygulama çalışma alanınızdaki dosyaları içeri aktarma veya bu dosyalara bağlanma
1. Power BI'da, uygulama çalışma alanı adının sol üst köşede bulunduğu uygulama çalışma alanına geçin. 
2. Sol gezinti bölmesinin alt tarafında **Veri Al**'ı seçin. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-get-data-button.png)
3. **Dosyalar** kutusunda **Al**'ı seçin.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_getfiles.png)
4. **OneDrive** - *Uygulama Çalışma Alanı Adınız*'ı seçin.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grp_one_drive_shrpt.png)
5. İstediğiniz dosyayı seçip **Bağlan** seçeneğini belirleyin.
   
    Bu noktada, karar kullanılıp kullanılmayacağını [Excel çalışma kitabından veri içe](service-get-data-from-files.md), veya [tüm Excel çalışma kitaplarına bağlanma](service-excel-workbook-files.md).
6. **İçeri Aktar** veya **Bağlan** seçeneğini belirleyin.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_importexceldataorwholecrop.png)
7. **İçeri Aktar** seçeneğini belirlerseniz çalışma kitabı **Veri Kümeleri** sekmesinde görünür. 
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-import.png)
   
    **Bağlan** seçeneğini belirlerseniz çalışma kitabı **Çalışma Kitapları** sekmesinde yer alır.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-connect.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da uygulama ve uygulama çalışma alanı oluşturma](service-create-distribute-apps.md)
* [Excel çalışma kitaplarındaki verileri içeri aktarma](service-get-data-from-files.md)
* [Excel çalışma kitaplarının tamamına bağlanma](service-excel-workbook-files.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
* Geri bildirimde bulunmak ister misiniz? [Power BI Ideas](https://ideas.powerbi.com/forums/265200-power-bi) sayfasını ziyaret edin

