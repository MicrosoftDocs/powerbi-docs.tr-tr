---
title: Bir panoyu, raporu, çalışma kitabını, veri kümesini veya çalışma alanını silme
description: Power BI'daki neredeyse tüm nesneleri silmeyi öğrenin
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 09/11/2018
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: 770b2796eb8f29cadfe8371cb2baef12cec7c0e8
ms.sourcegitcommit: 52ac456bf2ac025b22ea634c28482f22e1cc19ac
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2018
ms.locfileid: "48910303"
---
# <a name="delete-almost-anything-in-power-bi-service"></a>Power BI'daki neredeyse tüm nesneleri silme
Bu makalede, Power BI hizmetindeki bir panoyu, raporu, çalışma kitabını, veri kümesini, uygulamayı, görselleştirmeyi ve çalışma alanını silmeyle ilgili bilgiler sunulmaktadır.

## <a name="delete-a-dashboard"></a>Bir panoyu silme
Panoları kaldırabilirsiniz. Bir panoyu kaldırdığınızda bağlı olduğu veri kümesi veya o panoyla ilişkilendirilmiş raporlar silinmez.

* Sahibi olduğunuz panoları kaldırabilirsiniz. İş arkadaşlarınızla paylaşmış olduğunuz panoları Power BI çalışma alanınızdan kaldırdığınızda ilgili pano bu kişilerin Power BI çalışma alanlarından da kaldırılır.
* Sizinle paylaşılmış olan bir panoya ihtiyacınız kalmadıysa söz konusu panoyu kaldırabilirsiniz.  Kaldırdığınız panolar başkalarının Power BI çalışma alanından kaldırılmaz.
* [Kurumsal içerik paketine](service-organizational-content-pack-disconnect.md) dahil olan panoları kaldırmak için, ilişkilendirilmiş veri kümesini kaldırmanız gerekir.

### <a name="to-delete-a-dashboard"></a>Bir panoyu silmek için
1. Çalışma alanınızda **Panolar** sekmesini seçin.
2. Silmek istediğiniz panoyu bulun ve Sil simgesini ![sil simgesi](media/service-delete/power-bi-delete-icon.png)geçin.

    ![video](media/service-delete/power-bi-delete-dash.gif)

## <a name="delete-a-report"></a>Bir raporu silme
Endişelenmeyin, bir raporu sildiğinizde raporun temel aldığı veri kümesi silinmez.  Rapordan sabitlediğiniz görselleştirmeler de güvendedir. Bu görselleştirmeler silinene kadar panoda kalmaya devam eder.

### <a name="to-delete-a-report"></a>Bir raporu silmek için
1. Çalışma alanınızda **Raporlar** sekmesini seçin.
2. Silmek istediğiniz raporu bulup Sil simgesini   ![sil simgesi](media/service-delete/power-bi-delete-icon.png)geçin.   

    ![çalışma alanının raporlar sekmesi](media/service-delete/power-bi-delete-reportnew.png)
3. Silme işlemini onaylayın.

   ![Raporu sil iletişim kutusu](media/service-delete/power-bi-delete-report.png)

   > [!NOTE]
   > [İçerik paketlerinde](service-organizational-content-pack-introduction.md) bulunan raporlar bu yöntemle silinemez.  Bkz. [Kurumsal içerik paketi bağlantılarını kaldırma](service-organizational-content-pack-disconnect.md).
   >
   >

## <a name="delete-a-workbook"></a>Bir çalışma kitabını silme
Çalışma kitaplarını kaldırabilirsiniz. Ancak bir çalışma kitabını kaldırdığınızda bu çalışma kitabındaki verilerin kullanıldığı tüm raporlar ve pano kutucukları da kaldırılır.

OneDrive İş hesabında kayıtlı çalışma kitaplarının Power BI'dan silinmesi, OneDrive'dan kaldırılmasını sağlamaz.

### <a name="to-delete-a-workbook"></a>Bir çalışma kitabını silmek için
1. Çalışma alanınızda **Çalışma Kitapları** sekmesini seçin.
2. Silmek istediğiniz çalışma kitabını bulun ve Sil ![sil simgesi](media/service-delete/power-bi-delete-report2.png) simgesini seçin.

    ![Çalışma kitapları sekmesi](media/service-delete/power-bi-delete-workbooknew.png)
3. Silme işlemini onaylayın.

   ![Çalışma kitabını kaldır iletişim kutusu](media/service-delete/power-bi-delete-confirm.png)

## <a name="delete-a-dataset"></a>Bir veri kümesini silme
Veri kümeleri silinebilir. Ancak bir veri kümesini sildiğinizde ilgili veri kümesindeki verilerin kullanıldığı tüm raporlar ve pano kutucukları da silinir.

Veri kümesi bir veya daha fazla [kurumsal içerik paketinin](service-organizational-content-pack-disconnect.md) parçasıysa söz konusu veri kümesini silmek için, kullanıldığı içerik paketlerinden kaldırmanız, işlemin tamamlanmasını beklemeniz ve silmeyi tekrar denemeniz gerekir.

### <a name="to-delete-a-dataset"></a>Bir veri kümesini silmek için
1. Çalışma alanınızda **Veri Kümeleri** sekmesini seçin.
2. Silmek istediğiniz veri kümesini bulup üç nokta (...) simgesini seçin.  

    ![Veri Kümeleri sekmesi](media/service-delete/power-bi-delete-datasetnew.png)
3. Açılan listeden **Sil**'i seçin.

   ![üç nokta menüsü](media/service-delete/power-bi-delete-datasetnew2.png)
4. Silme işlemini onaylayın.

   ![Panoyu sil iletişim kutusu](media/service-delete/power-bi-delete-dataset-confirm.png)

## <a name="delete-an-app-workspace"></a>Bir uygulama çalışma alanını silme
> [!WARNING]
> Bir uygulama çalışma alanı oluşturduğunuzda bir Office 365 grubu oluşturmuş olursunuz. Bir uygulama çalışma alanını sildiğinizde de oluşturduğunuz Office 365 grubunu silmiş olursunuz. Başka bir deyişle, söz konusu grup SharePoint ve Microsoft Teams gibi diğer O365 ürünlerinden de silinir.
>
>

Kendi oluşturduğunuz uygulama çalışma alanlarını silebilirsiniz. Ayrıca silme işleminin ardından ilişkili uygulama, tüm grup üyeleri için silinir ve AppSource'unuzdan kaldırılır (uygulamayı kuruluşunuzun tamamında yayımladıysanız). Bir uygulama çalışma alanını silmek, uygulama çalışma alanından ayrılmaktan farklıdır.

### <a name="to-delete-an-app-workspace---if-you-are-an-admin"></a>Yöneticisi olduğunuz bir uygulama çalışma alanını silmek için
1. Sol gezinti bölmesinde, **Çalışma Alanı**'nı seçin

    ![Uygulama çalışma alanları](media/service-delete/power-bi-delete-workspace.png)
2. Silmek istediğiniz çalışma alanının sağ tarafındaki üç nokta (...) simgesini seçip **Çalışma alanını düzenle**'yi seçin.

   ![üç nokta menüsü > Çalışma alanını düzenle](media/service-delete/power-bi-edit-workspace.png)
3. **Çalışma alanını düzenle** penceresinde, **Çalışma alanını sil** > **Sil**'i seçin.

    ![çalışma alanını silme](media/service-delete/power-bi-delete-workspace2.png)

### <a name="to-remove-an-app-workspace-from-your-list"></a>Bir uygulama çalışma alanını listenizden kaldırma
Artık bir uygulama çalışma alanının üyesi olmak istemiyorsanız ***ayrılabilir*** ve ilgili girişin listenizden kaldırılmasını sağlayabilirsiniz. Siz bir çalışma alanından ayrıldığınızda diğer çalışma alanı üyeleri için herhangi bir değişiklik olmaz.  

> [!IMPORTANT]
> Uygulama çalışma alanındaki tek Yönetici sizseniz Power BI ayrılmanıza izin vermez.
>
>

1. Kaldırmak istediğiniz çalışma alanında işleme başlayın.
2. Sağ üst köşede üç nokta (...) simgesini seçin ve **Çalışma alanından ayrıl** > **Ayrıl** seçeneğini belirleyin.

      ![çalışma alanından ayrılma](media/service-delete/power-bi-leave-workspace.png)

   > [!NOTE]
   > Açılan listede göreceğiniz seçenekler, uygulama çalışma alanında Yönetici veya Üye olma durumunuza göre değişir.
   >
   >

## <a name="delete-or-remove-an-app"></a>Bir Uygulamayı silme veya kaldırma
Uygulamaları uygulama listesi sayfanızdan kolayca kaldırabilirsiniz. Ancak bir uygulamayı kalıcı olarak silme işlemi yalnızca Yönetici tarafından gerçekleştirilebilir.

### <a name="remove-an-app-from-your-app-list-page"></a>Bir uygulamayı uygulama listesi sayfanızdan kaldırma
Uygulama listesi sayfanızdan sildiğiniz uygulamalar diğer üyeler için silinmez.

1. Sol gezinti bölmesinde **Uygulamalar**'ı seçerek uygulama listesi sayfasını açın.
2. Silmek istediğiniz uygulamanın üzerine gelip Sil simgesini ![](media/service-delete/power-bi-delete-report2.png) seçin.

   ![Uygulama seçme](media/service-delete/power-bi-delete-app.png)

   Yanlışlıkla kaldırdığınız uygulamaları geri almak için kullanabileceğiniz birçok seçenek vardır.  Uygulama oluşturucusunun uygulamayı yeniden göndermesini isteyebilir, uygulama bağlantısını içeren özgün e-postayı bulabilir, [Bildirim merkezinizde](service-notification-center.md) uygulamayla ilgili bildirimin mevcut olup olmadığına bakabilir veya kuruluşunuzun [AppSource](service-install-use-apps.md) sayfasını kontrol edebilirsiniz.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
Bu makalede Power BI hizmetinin başlıca yapı taşlarını silme yöntemleri ele alınmıştır. Ancak Power BI'da silebileceğiniz başka öğeler de vardır.  

* [Öne Çıkan panonuzu kaldırma](service-dashboard-featured.md)
* [Bir panoyu kaldırma (sık kullanılanlardan çıkarma)](service-dashboard-favorite.md)
* [Bir rapor sayfasını silme](service-delete.md)
* [Bir pano kutucuğunu silme](service-dashboard-edit-tile.md)
* [Bir rapor görselleştirmesini silme](service-delete.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
