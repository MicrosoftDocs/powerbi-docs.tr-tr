---
title: Bir Power BI çalışma alanı için OneDrive'daki dosyalara bağlanma
description: Power BI çalışma alanınız için OneDrive'da Excel, CSV ve Power BI Desktop dosyalarınızı depolama ve bunlara bağlanma hakkında bilgi edinin.
author: maggiesMSFT
ms.reviewer: lukasz
ms.service: powerbi
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 180fd8d451be794070d8b0f4d37c40965671d23d
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2020
ms.locfileid: "73854875"
---
# <a name="connect-to-files-stored-in-onedrive-for-your-power-bi-workspace"></a>Power BI çalışma alanınız için OneDrive'da depolanan dosyalara bağlanma
[Power BI'da bir çalışma alanı oluşturduktan](service-create-distribute-apps.md) sonra Power BI çalışma alanınız için OneDrive İş'te Excel, CSV ve Power BI Desktop dosyalarınızı depolayabilirsiniz. OneDrive'da depoladığınız dosyaları güncelleştirmeye devam edebilirsiniz. Bu güncelleştirmeler dosyalara bağlı olarak Power BI raporlarına ve panolarına otomatik olarak yansır. 

> [!NOTE]
> Yeni çalışma alanı deneyimi, Power BI çalışma alanlarıyla Office 365 grupları arasındaki ilişkileri değiştiriyor. Yeni çalışma alanlarından birini her oluşturduğunuzda otomatik olarak bir Office 365 grubu oluşturmazsınız. [Yeni çalışma alanları oluşturma](service-create-the-new-workspaces.md) hakkında bilgi edinin

Çalışma alanınıza dosya eklemek iki adımlı bir işlemdir: 

1. Çalışma alanınız için öncelikle [OneDrive İş'e dosyaları yüklersiniz](service-connect-to-files-in-app-workspace-onedrive-for-business.md#1-upload-files-to-the-onedrive-for-business-for-your-workspace).
2. Ardından [Power BI'da bu dosyalara bağlanırsınız](service-connect-to-files-in-app-workspace-onedrive-for-business.md#2-import-excel-files-as-datasets-or-as-excel-online-workbooks).

> [!NOTE]
> Çalışma alanları yalnızca [Power BI Pro](service-features-license-type.md) ile kullanılabilir.
> 

## <a name="1-upload-files-to-the-onedrive-for-business-for-your-workspace"></a>1 Çalışma alanınız için OneDrive İş'e dosya yükleme
1. Power BI hizmetinde Çalışma Alanı'nın yanındaki oku ve ardından çalışma alanı adınızın yanındaki üç nokta ( **…** ) simgesini seçin. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-ellipsis.png)
2. Office 365'te çalışma alanınız için OneDrive İş'i açmak üzere **Dosyalar**'ı seçin.
   
   > [!NOTE]
   > Çalışma alanı menüsünde **Dosyalar**'ı görmüyorsanız çalışma alanınız için OneDrive İş'i açmak üzere **Üyeler**'i seçin. Burada, **Dosyalar** seçeneğini belirleyin. Office 365, uygulamanızın grup çalışma alanı dosyaları için bir OneDrive depolama konumu ayarlar. Bu işlem biraz zaman alabilir. 
   > 
   > 
3. Buradan çalışma alanınız için OneDrive İş'e dosyalarınızı yükleyebilirsiniz. **Karşıya Yükle**'yi seçip dosyalarınıza gidin.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grpfilesonedrive.png)

## <a name="2-import-excel-files-as-datasets-or-as-excel-online-workbooks"></a>2 Excel dosyalarını veri kümeleri veya Excel Online çalışma kitapları olarak içeri aktarma
Dosyalarınız artık çalışma alanınız için OneDrive İş'te olduğuna göre bir tercih yapabilirsiniz. Seçenekleriniz şunlardır: 

* [Excel çalışma kitabından verileri bir veri kümesi olarak içeri aktarın](service-get-data-from-files.md). Ardından web tarayıcısında veya mobil cihazlarda görüntüleyebileceğiniz raporlar ile panolar oluşturmak için verileri kullanın.
* [Power BI'da Excel çalışma kitabının tamamına bağlanma](service-excel-workbook-files.md) ve bu çalışma kitabını tam olarak Excel Online'da göründüğü şekilde görüntüleme.

### <a name="import-or-connect-to-the-files-in-your-workspace"></a>Çalışma alanınızdaki dosyaları içeri aktarma veya bu dosyalara bağlanma
1. Power BI'da, çalışma alanı adının sol üst köşede bulunduğu çalışma alanına geçin. 
2. Gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-get-data-button.png)
3. **Dosyalar** kutusunda **Al**'ı seçin.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_getfiles.png)
4. **OneDrive** - *Çalışma Alanı Adınız*'ı seçin.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grp_one_drive_shrpt.png)
5. İstediğiniz dosyayı seçip **Bağlan** seçeneğini belirleyin.
   
    Bu noktada [Excel çalışma kitabındaki verileri içeri aktarmak](service-get-data-from-files.md) veya [Excel çalışma kitabının tamamına bağlanmak](service-excel-workbook-files.md) istediğinize karar verin.
6. **İçeri Aktar** veya **Bağlan** seçeneğini belirleyin.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_importexceldataorwholecrop.png)
7. **İçeri Aktar** seçeneğini belirlerseniz çalışma kitabı **Veri Kümeleri** sekmesinde görünür. 
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-import.png)
   
    **Bağlan** seçeneğini belirlerseniz çalışma kitabı **Çalışma Kitapları** sekmesinde yer alır.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-connect.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da uygulama ve çalışma alanı oluşturma](service-create-distribute-apps.md)
* [Excel çalışma kitaplarındaki verileri içeri aktarma](service-get-data-from-files.md)
* [Excel çalışma kitaplarının tamamına bağlanma](service-excel-workbook-files.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
* Geri bildirimde bulunmak ister misiniz? [Power BI Ideas](https://ideas.powerbi.com/forums/265200-power-bi) sayfasını ziyaret edin

