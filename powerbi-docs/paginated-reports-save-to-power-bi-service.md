---
title: Power BI hizmetinde sayfalandırılmış rapor yayımlama (Önizleme)
description: Bu öğreticide, sayfalandırılmış bir raporu yerel bilgisayarınızdan yükleyerek Power BI hizmetinde yayımlamayı öğreneceksiniz.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: report-builder
ms.topic: conceptual
ms.date: 11/05/2018
ms.author: maggies
ms.openlocfilehash: 1114f1949c68e4bebf2d636906bf754e7de77273
ms.sourcegitcommit: b03912343a5a214c6bb972aaa6aa051c2a5f4332
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2018
ms.locfileid: "52900279"
---
# <a name="publish-a-paginated-report-to-the-power-bi-service-preview"></a>Power BI hizmetinde sayfalandırılmış rapor yayımlama (Önizleme)

Bu makalede, sayfalandırılmış bir raporu yerel bilgisayarınızdan yükleyerek Power BI hizmetinde yayımlama hakkında bilgi edineceksiniz. Sayfalandırılmış raporları Çalışma Alanım’a veya Premium kapasitede olan başka bir çalışma alanına yükleyebilirsiniz. Çalışma alanı adının yanında ![Power BI Premium kapasite elmas simgesi](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) elmas simgesini arayın. 

Rapor veri kaynağınız şirket içindeyse, raporu karşıya yükledikten sonra [bir ağ geçidi oluşturmanız](#create-a-gateway-to-an-on-premises-data-source) gerekir.

## <a name="add-a-workspace-to-a-premium-capacity"></a>Çalışma alanını Premium kapasiteye ekleme

Çalışma alanı adının yanında baklava simgesi ![Power BI Premium kapasite elmas simgesi](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) yoksa, çalışma alanını bir Premium kapasiteye eklemeniz gerekir. 

1. **Çalışma Alanları**’nı seçin, çalışma alanı adının yanındaki üç noktayı (**...**) ve sonra **Çalışma alanını düzenle**’yi seçin.

    ![Çalışma alanını düzenle seçeneğini belirleme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace.png)

1. **Çalışma alanını düzenle** iletişim kutusunda **Gelişmiş**’i genişletin, ardından **Ayrılmış kapasite**’yi **Açık** seçeneğine sürükleyin.

    ![Ayrılmış kapasite seçme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace-dialog.png)

   Bunu değiştirmeniz mümkün olmayabilir. Mümkün değilse, çalışma alanınızı bir Premium kapasiteye eklemek üzere size atama haklarını vermesi için Power BI Premium kapasite yöneticinize başvurun.


## <a name="upload-a-paginated-report"></a>Sayfalandırılmış raporu karşıya yükleme

1. Rapor Oluşturucusu'nda sayfalandırılmış raporunuzu oluşturun ve yerel bilgisayarınıza kaydedin.

1. Power BI hizmetini bir tarayıcıda açın ve raporu yayımlamak istediğiniz Premium çalışma alanına göz atın. Adın yanındaki elmas simgesine ![Power BI Premium kapasite elmas simgesi](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) dikkat edin. 

1. **Veri Al**’ı seçin.

    ![Power BI Veri Al](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-get-data.png)

1. **Dosyalar** kutusunda **Al**'ı seçin.

    ![Power BI Dosya Al](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-files-get.png)

1. **Yerel dosya**’yı seçin > sayfalandırılmış rapora göz atın > **Aç**’ı seçin.

    ![Yerel Dosya seçme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-local-file.png)

1. **Devam** > **Kimlik bilgilerini düzenle**’yi seçin.

    ![Kimlik bilgilerini düzenle’yi seçin](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-edit-credentials.png)

1. Kimlik bilgilerinizi yapılandırın > **Oturum aç**’ı seçin.

    ![Kimlik bilgilerini düzenle](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-credentials.png)

   Raporunuzu rapor listesinde görürsünüz.

    ![Raporlar listesinde sayfalandırılmış rapor](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

1. Power BI hizmetinde açmak için seçin. Parametreleri varsa, raporu görüntüleyebilmeniz için bunları seçmeniz gerekir.
 
    ![Parametreleri seçme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

## <a name="create-a-gateway"></a>Ağ geçidi oluşturma

Diğer tüm Power BI raporlarında olduğu gibi, rapor veri kaynağı şirket içindeyse verilere erişmek için bir ağ geçidi oluşturmanız veya bir ağ geçidine bağlanmanız gerekir.

1. Rapor adının yanındaki **Yönet**’i seçin.

   ![Sayfalandırılmış raporu yönetme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-manage.png)

1. Ayrıntılı bilgi ve sonraki adımlar için Power BI hizmetinin [Ağ geçidi yükleme](service-gateway-install.md) makalesine bakın.

### <a name="gateway-limitations"></a>Ağ geçidi sınırlamaları

Ağ geçitleri şu anda çok değerli parametreleri desteklememektedir.


## <a name="next-steps"></a>Sonraki adımlar

- [Power BI hizmetinde sayfalandırılmış rapor görüntüleme](paginated-reports-view-power-bi-service.md)
- [Power BI Premium’da sayfalandırılmış raporlar nelerdir? (Önizleme)](paginated-reports-report-builder-power-bi.md)
