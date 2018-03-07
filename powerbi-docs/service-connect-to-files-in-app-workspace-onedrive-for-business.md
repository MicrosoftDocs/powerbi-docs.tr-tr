---
title: "Bir Power BI uygulaması çalışma alanı için OneDrive'daki dosyalara bağlanma"
description: "Power BI uygulama çalışma alanınız için OneDrive'da Excel, CSV ve Power BI Desktop dosyalarınızı depolama ve bunlara bağlanma hakkında bilgi edinin."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: ajayan
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 8a078475bc01dec37d49f654d1fa90162a9d8366
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-files-stored-in-onedrive-for-your-power-bi-app-workspace"></a>Power BI uygulama çalışma alanınız için OneDrive'da depolanan dosyalara bağlanma
[Power BI'da bir uygulama çalışma alanı oluşturduktan](service-create-distribute-apps.md) sonra Power BI uygulama çalışma alanınız için OneDrive İş'te Excel, CSV ve Power BI Desktop dosyalarınızı depolayabilirsiniz. OneDrive'da depoladığınız dosyaları güncelleştirmeye devam edebilirsiniz ve bu güncelleştirmeler dosyalara bağlı olarak Power BI raporlarına ve panolarına otomatik olarak yansır. 

Uygulama çalışma alanınıza dosya ekleme iki adımlı bir işlemdir: 

1. Uygulama çalışma alanınız için öncelikle [OneDrive İş'e dosyaları yüklersiniz](service-connect-to-files-in-app-workspace-onedrive-for-business.md#1-upload-files-to-the-onedrive-for-business-for-your-app-workspace).
2. Ardından [Power BI'da bu dosyalara bağlanırsınız](service-connect-to-files-in-app-workspace-onedrive-for-business.md#2-import-excel-files-as-datasets-or-as-excel-online-workbooks).

> [!NOTE]
> Uygulama çalışma alanları yalnızca [Power BI Pro](service-free-vs-pro.md) ile kullanılabilir.
> 
> 

## <a name="1-upload-files-to-the-onedrive-for-business-for-your-app-workspace"></a>1 Uygulama çalışma alanınız için OneDrive İş'e dosya yükleme
1. Power BI hizmetinde Çalışma Alanı'nın yanındaki oku ve ardından çalışma alanı adınızın yanındaki üç nokta (**…**) simgesini seçin. 
   
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

* [Excel çalışma kitabındaki verileri veri kümesi olarak içeri aktarma](service-get-data-from-files.md) ve web tarayıcısında veya mobil cihazlarda görüntüleyebileceğiniz raporlar ile panolar oluşturmak için verileri kullanma.
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
   
    Burası [Excel çalışma kitabındaki verileri içeri aktarmak](service-get-data-from-files.md) mı yoksa [Excel çalışma kitabının tamamına bağlanmak](service-excel-workbook-files.md) mı istediğinize karar vereceğiniz noktadır.
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

