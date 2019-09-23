---
title: Çalışma alanlarınızdaki veri depolama alanlarını yönetme
description: Rapor ve veri kümesi yayınlamaya devam edebilmek için bireysel veya uygulama çalışma alanlarınızla veri depolama alanlarınızı nasıl yönetebileceğinizi öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2018
ms.author: maggies
LocalizationGroup: Administration
ms.openlocfilehash: a46fbb0679de30e554003d858e01756b9b242b1b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61191066"
---
# <a name="manage-data-storage-in-power-bi-workspaces"></a>Power BI çalışma alanlarında veri depolama alanlarını yönetme

Rapor ve veri kümesi yayınlamaya devam edebilmek için bireysel veya uygulama çalışma alanlarınızla veri depolama alanlarınızı nasıl yönetebileceğinizi öğrenin.

Kullanıcı ve uygulama çalışma alanları farklı veri kapasitelerine sahiptir:

* Tüm kullanıcılar en fazla 10 GB veri depolama alanına sahip olur.
* Power BI Pro lisansı olan kullanıcılar, her biri en fazla 10 GB veri depolama alanına sahip uygulama çalışma alanları oluşturabilir.
* Premium kapasitedeki bir uygulama çalışma alanı Power BI Pro kullanıcısının depolama alanında hesaba katılmaz.

Kiracı düzeyinde toplam kullanım, tüm Pro sürüm kullanıcıları ve kiracıdaki tüm uygulama çalışma alanları için Pro sürüm kullanıcısı başına 10 GB'ı aşamaz.

[Power BI fiyatlandırma modelinin](https://powerbi.microsoft.com/pricing) diğer özellikleri hakkında bilgi edinin.

Veri depolama alanınızda kendi veri kümelerinizin ve Excel raporlarınızın yanı sıra sizinle paylaşılan öğeler de bulunur. Veri kümeleri karşıya yüklediğiniz veya bağlandığınız veri kaynaklarıdır. Bu veri kaynakları, kullandığınız Power BI Desktop dosyalarını ve Excel çalışma kitaplarını içerir. Aşağıdaki öğeler de veri kapasitenize dahil edilir.

* Panolara sabitlenmiş olan Excel aralıkları.
* Power BI panolarına sabitlenmiş olan Reporting Services şirket içi görselleştirmeleri.
* Karşıya yüklenen görüntüler.

Paylaştığınız panoların boyutları, bu panolara sabitlenmiş öğelere göre değişir. Örneğin, iki farklı veri kümesine ait olan iki rapordaki öğeleri sabitlerseniz dosya boyutu iki veri kümesini de içerecektir.

<a name="manage"/>

## <a name="manage-items-you-own"></a>Size ait olan öğeleri yönetme

Power BI hesabınızda kullandığınız depolama alanı miktarını görün ve hesabınızı yönetin.

1. Kendi depolama alanınızı yönetmek için sol gezinti bölmesinde **Çalışma Alanım** sayfasına gidin.
   
    ![Çalışma Alanım](media/service-admin-manage-your-data-storage-in-power-bi/pbi_myworkspace.png)
2. Sağ üst köşedeki dişli simgesini ![Dişli simgesi](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) ve ardından \>  **Kişisel depolama alanını yönet**'i seçin.
   
    Üst taraftaki çubukta, depolama alanınızın ne kadarını kullandığınız gösterilir.
   
    ![Depolama sınırını yönetme](media/service-admin-manage-your-data-storage-in-power-bi/pbi_persnlstorage.png)
   
    Veri kümeleri ve raporlar iki sekmeye ayrılmıştır:
   
    **Bana ait:** Bunlar, Salesforce ve Dynamics CRM gibi hizmet veri kümeleri de dahil olmak üzere Power BI hesabınıza sizin yüklediğiniz raporlar ve veri kümeleridir.  
    **Diğerlerine ait:** Başkalarının sizinle paylaştığı raporlar ve veri kümeleridir.
1. Bir veri kümesini veya raporu silmek için çöp kutusu simgesini seçin ![çöp kutusu simgesi](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png)geçin.

Size veya başkalarına ait bazı rapor veya panoların bir veri kümesine bağlı olabileceğini unutmayın. İlgili veri kümesini silerseniz bağlı raporlar ve panolar artık çalışmaz.

## <a name="manage-your-app-workspace"></a>Uygulama çalışma alanınızı yönetme
1. **Çalışma Alanı** \>'nın yanındaki oku ve ardından uygulama çalışma alanının adını seçin.
   
    ![Uygulama çalışma alanı seçme](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupworkspaces.png)
2. Sağ üst köşedeki dişli simgesini ![dişli simgesi](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png) ve ardından \> **Grup depolama alanını yönet**’i seçin.
   
    Üst taraftaki çubukta, grup depolama alanınızın ne kadarının kullanıldığı gösterilir.
   
    ![Uygulama çalışma alanı depolama alanlarını yönetme](media/service-admin-manage-your-data-storage-in-power-bi/pbi_groupstorage.png)
   
    Veri kümeleri ve raporlar iki sekmeye ayrılmıştır:
   
    **Bize ait:** Bunlar, Salesforce ve Dynamics CRM gibi hizmet veri kümeleri de dahil olmak üzere grubun Power BI hesabına sizin yüklediğiniz veya başka birinin yüklediği raporlar ve veri kümeleridir.
    **Diğerlerine ait:** Başkalarının grubunuzla paylaştığı raporlar ve veri kümeleridir.
3. Bir veri kümesini veya raporu silmek için çöp kutusu simgesini seçin ![çöp kutusu simgesi](media/service-admin-manage-your-data-storage-in-power-bi/pbi_deleteicon.png)geçin.
   
   > [!NOTE]
   > Uygulama çalışma alanında düzenleme izinlerine sahip olan tüm üyeler uygulama çalışma alanındaki veri kümelerini ve raporları silme izinlerine de sahip olur.
   > 
   > 

Size veya gruptaki diğer kullanıcılara ait bazı rapor veya panoların bir veri kümesine bağlı olabileceğini unutmayın. İlgili veri kümesini silerseniz bağlı raporlar ve panolar artık çalışmaz.

## <a name="dataset-limits"></a>Veri kümesi sınırları
Power BI'a aktarılan her veri kümesi için 1 GB'lık bir sınır söz konusudur. Verileri içeri aktarmak yerine Excel deneyimini korumayı tercih ettiyseniz veri kümesi başına sınır 250 MB'tır.

## <a name="what-happens-when-you-reach-a-limit"></a>Sınıra ulaştığınızda ne olur?
Herhangi bir alandaki kapasite sınırına ulaştığınızda hizmet içinde uyarılar görürsünüz. 

Dişli simgesini ![dişli simgesi](media/service-admin-manage-your-data-storage-in-power-bi/pbi_gearicon.png)seçtiğinizde, veri kapasitesi sınırınızı aştığınızı belirten bir kırmızı çubuk görürsünüz.

![Depolama sınırına ulaşıldı](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit.png)

Bu sınır, **Kişisel depolama alanını yönet** bölümünde de belirtilir.

 ![Kişisel depolama alanını yönet, depolama sınırına ulaşıldı](media/service-admin-manage-your-data-storage-in-power-bi/manage-storage-limit2.png)

 Sınırlardan birine ulaşılmasına neden olacak bir eylem gerçekleştirmeye çalıştığınızda sınırı aştığınızı belirten bir ileti görürsünüz. Depoladığınız veri miktarını azaltmak ve sınır sorununu ortadan kaldırmak için depolama alanınızı [yönetebilirsiniz](#manage).

 ![Depolama sınırınızın üzerinde](media/service-admin-manage-your-data-storage-in-power-bi/powerbi-pro-over-limit.png)

 Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

