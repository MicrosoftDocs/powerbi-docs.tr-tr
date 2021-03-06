---
title: Klasik bir çalışma alanı için OneDrive 'daki dosyalara bağlanma
description: Klasik Power BI çalışma alanınız için OneDrive 'da Excel, CSV ve Power BI Desktop dosyalarınızı depolama ve bu dosyalara bağlanma hakkında bilgi edinin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: lukasz
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: how-to
ms.date: 01/28/2021
LocalizationGroup: Share your work
ms.openlocfilehash: f6544a137b8f656e938db4516de5e8c0685394b4
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99085832"
---
# <a name="connect-to-files-stored-in-onedrive-for-a-classic-workspace"></a>Klasik bir çalışma alanı için OneDrive 'da depolanan dosyalara bağlanma
[Power BI içinde *Klasik* bir çalışma alanı oluşturduğunuzda](service-create-workspaces.md), ilişkili bir OneDrive iş ile bir Microsoft 365 grubu da oluşturursunuz. Bu makalede Excel, CSV ve Power BI Desktop dosyalarınızı ilgili OneDrive İş kaynağında depolama ve güncel tutma adımları açıklanmaktadır. Bu güncelleştirmeler dosyalara bağlı olarak Power BI raporlarına ve panolarına otomatik olarak yansır.

> [!NOTE]
> *Yeni* çalışma alanı deneyimi Power BI çalışma alanları ve Microsoft 365 grupları arasındaki ilişkiyi değiştirir. Yeni çalışma alanlarından birini her oluşturduğunuzda otomatik olarak bir Microsoft 365 grubu oluşturmazsınız. Ayrıca, [Yeni bir çalışma alanı için bir OneDrive çalışma alanı da ayarlayabilirsiniz](service-create-the-new-workspaces.md#set-a-workspace-onedrive).

Klasik çalışma alanınıza dosya eklemek iki adımlı bir işlemdir: 

1. Çalışma alanınız için öncelikle [OneDrive İş'e dosyaları yüklersiniz](#1-upload-files-to-the-onedrive-for-business-for-your-workspace).
2. Ardından [Power BI'da bu dosyalara bağlanırsınız](#2-import-excel-files-as-datasets-or-as-excel-online-workbooks).

> [!NOTE]
> Çalışma alanları yalnızca bir [Power BI Pro lisansı](../fundamentals/service-features-license-type.md) ile kullanılabilir.
> 

## <a name="1-upload-files-to-the-onedrive-for-business-for-your-workspace"></a>1 Çalışma alanınız için OneDrive İş'e dosya yükleme
1. Power BI hizmetinde Çalışma Alanı'nın yanındaki oku ve ardından çalışma alanı adınızın yanındaki üç nokta ( **…** ) simgesini seçin. 
   
   ![Seçili çalışma alanı adını gösteren Power BI çalışma alanının ekran görüntüsü.](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-ellipsis.png)
2. Microsoft 365'te çalışma alanınız için OneDrive İş'i açmak üzere **Dosyalar**'ı seçin.
   
   > [!NOTE]
   > Çalışma alanı menüsünde **Dosyalar**'ı görmüyorsanız çalışma alanınız için OneDrive İş'i açmak üzere **Üyeler**'i seçin. Burada, **Dosyalar** seçeneğini belirleyin. Microsoft 365, uygulamanızın grup çalışma alanı dosyaları için bir OneDrive depolama konumu ayarlar. Bu işlem biraz zaman alabilir.
   > 
   > 
3. Buradan çalışma alanınız için OneDrive İş'e dosyalarınızı yükleyebilirsiniz. **Karşıya Yükle**'yi seçip dosyalarınıza gidin.
   
   ![Bir dosyayı karşıya yüklemek için nasıl gezinileceği gösterilen OneDrive İş’in ekran görüntüsü.](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grpfilesonedrive.png)

## <a name="2-import-excel-files-as-datasets-or-as-excel-online-workbooks"></a>2 Excel dosyalarını veri kümeleri veya Excel Online çalışma kitapları olarak içeri aktarma
Dosyalarınız artık çalışma alanınız için OneDrive İş'te olduğuna göre bir tercih yapabilirsiniz. Seçenekleriniz şunlardır: 

* [Excel çalışma kitabından verileri bir veri kümesi olarak içeri aktarın](../connect-data/service-get-data-from-files.md). Ardından web tarayıcısında veya mobil cihazlarda görüntüleyebileceğiniz raporlar ile panolar oluşturmak için verileri kullanın.
* [Power BI'da Excel çalışma kitabının tamamına bağlanma](../connect-data/service-excel-workbook-files.md) ve bu çalışma kitabını tam olarak Excel Online'da göründüğü şekilde görüntüleme.

### <a name="import-or-connect-to-the-files-in-your-workspace"></a>Çalışma alanınızdaki dosyaları içeri aktarma veya bu dosyalara bağlanma
1. Power BI'da, çalışma alanı adının sol üst köşede bulunduğu çalışma alanına geçin. 
2. Gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin. 
   
   ![Gezinti bölmesinde görüntülenen Veri Al düğmesinin ekran görüntüsü.](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-get-data-button.png)
3. **Dosyalar** kutusunda **Al**'ı seçin.
   
   ![Al düğmesini gösteren, Dosyalar iletişim kutusunun ekran görüntüsü.](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_getfiles.png)
4. **OneDrive** - *Çalışma Alanı Adınız*'ı seçin.
   
    ![Yerel Dosya, OneDrive ve SharePoint’i gösteren, çalışma alanınızı seçmeye yarayan üç kutucuğun ekran görüntüsü.](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grp_one_drive_shrpt.png)
5. İstediğiniz dosyayı seçip **Bağlan** seçeneğini belirleyin.
   
    Bu noktada [Excel çalışma kitabındaki verileri içeri aktarmak](../connect-data/service-get-data-from-files.md) veya [Excel çalışma kitabının tamamına bağlanmak](../connect-data/service-excel-workbook-files.md) istediğinize karar verin.
6. **İçeri Aktar** veya **Bağlan** seçeneğini belirleyin.
   
    ![Excel’den İçeri Aktar veya Excel’e Bağlan seçeneklerini gösteren OneDrive İş iletişim kutusunun ekran görüntüsü.](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_importexceldataorwholecrop.png)
7. **İçeri Aktar** seçeneğini belirlerseniz çalışma kitabı **Veri Kümeleri** sekmesinde görünür. 
   
    ![Veri Kümeleri sekmesini gösteren Power BI’daki Çalışma Alanları’nın ekran görüntüsü.](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-import.png)
   
    **Bağlan** seçeneğini belirlerseniz çalışma kitabı **Çalışma Kitapları** sekmesinde yer alır.
   
    ![Çalışma Kitapları sekmesini gösteren Power BI’daki Çalışma Alanları’nın ekran görüntüsü.](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-connect.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da uygulama ve çalışma alanı oluşturma](../collaborate-share/service-create-distribute-apps.md)
* [Excel çalışma kitaplarındaki verileri içeri aktarma](../connect-data/service-get-data-from-files.md)
* [Excel çalışma kitaplarının tamamına bağlanma](../connect-data/service-excel-workbook-files.md
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
* Geri bildirimde bulunmak ister misiniz? [Power BI Ideas](https://ideas.powerbi.com/forums/265200-power-bi) sayfasını ziyaret edin
