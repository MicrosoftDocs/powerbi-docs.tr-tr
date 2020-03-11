---
title: Power BI hizmetinde sayfalandırılmış rapor yayımlama
description: Bu öğreticide, sayfalandırılmış bir raporu yerel bilgisayarınızdan yükleyerek Power BI hizmetinde yayımlamayı öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 01/03/2020
ms.openlocfilehash: 0207cbdbc3fae8636f8fd73a008d54ee7d10c5f9
ms.sourcegitcommit: ced8c9d6c365cab6f63fbe8367fb33e6d827cb97
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2020
ms.locfileid: "78921620"
---
# <a name="publish-a-paginated-report-to-the-power-bi-service"></a>Power BI hizmetinde sayfalandırılmış rapor yayımlama

Bu makalede, sayfalandırılmış bir raporu yerel bilgisayarınızdan yükleyerek Power BI hizmetinde yayımlama hakkında bilgi edineceksiniz. Sayfalandırılmış raporları Çalışma Alanım’a veya Premium kapasitede olan başka bir çalışma alanına yükleyebilirsiniz. Çalışma alanı adının yanında ![Power BI Premium kapasite elmas simgesi](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) elmas simgesini arayın. 

Rapor veri kaynağınız şirket içindeyse, raporu karşıya yükledikten sonra bir ağ geçidi oluşturmanız gerekir. Bu makalenin ilerleyen kısımlarındaki [Ağ geçidi oluşturma](#create-a-gateway) bölümüne bakın.

## <a name="add-a-workspace-to-a-premium-capacity"></a>Çalışma alanını Premium kapasiteye ekleme

Çalışma alanı adının yanında baklava simgesi ![Power BI Premium kapasite elmas simgesi](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) yoksa, çalışma alanını bir Premium kapasiteye eklemeniz gerekir. 

1. **Çalışma Alanları**’nı seçin, çalışma alanı adının yanındaki üç noktayı ( **...** ) ve sonra **Çalışma alanını düzenle**’yi seçin.

    ![Çalışma alanını düzenle seçeneğini belirleme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace.png)

1. **Çalışma alanını düzenle** iletişim kutusunda **Gelişmiş**’i genişletin, ardından **Ayrılmış kapasite**’yi **Açık** seçeneğine sürükleyin.

    ![Ayrılmış kapasite seçme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace-dialog.png)

   Bunu değiştirmeniz mümkün olmayabilir. Mümkün değilse, çalışma alanınızı bir Premium kapasiteye eklemek üzere size atama haklarını vermesi için Power BI Premium kapasite yöneticinize başvurun.

## <a name="from-report-builder-publish-a-paginated-report"></a>Report Builder'dan sayfalandırılmış rapor yayımlama

1. Rapor Oluşturucusu'nda sayfalandırılmış raporunuzu oluşturun ve yerel bilgisayarınıza kaydedin.

1. Report Builder'ın **Dosya** menüsünde **Farklı kaydet**'i seçin.

    ![Dosya menüsü > Kaydet > Farklı kaydet](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-save-as.png)

    Henüz Power BI'da oturum açmadıysanız bu aşamada oturum açmanız veya hesap oluşturmanız gerekir. Report Builder'ın sağ üst köşesinde **Oturum aç**'ı seçip gerekli adımları tamamlayın.

2. Sol taraftaki çalışma alanları listesinden adının yanında elmas simgesi ![Power BI Premium kapasite elması simgesi](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) bulunan çalışma alanlarından birini seçin. **Dosya adı** kutusuna bir ad yazıp **Kaydet**'i seçin. 

    ![Premium çalışma alanı seçme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-workspace.png)

4. Power BI hizmetini bir tarayıcıda açın ve sayfalandırılmış raporu yayımlamak istediğiniz Premium çalışma alanına göz atın. **Raporlar** sekmesinde raporunuzu görebilirsiniz.

    ![Raporlar listesinde sayfalandırılmış rapor](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

5. Power BI hizmetinde açmak için sayfalandırılmış raporu seçin. Parametreleri varsa, raporu görüntüleyebilmeniz için bunları seçmeniz gerekir.

    ![Parametreleri seçme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

6. Raporunuzun veri kaynağı şirket içi ortamdaysa bu veri kaynağına erişim sağlama amacıyla [ağ geçidi oluşturma](#create-a-gateway) hakkında bilgi edinin.

## <a name="from-the-power-bi-service-upload-a-paginated-report"></a>Power BI hizmetinden sayfalandırılmış rapor yükleme

İsterseniz işlemi Power BI hizmetinden başlatabilir ve sayfalandırılmış raporu karşıya yükleyebilirsiniz.

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

   **Raporlar** sekmesinde raporunuzu görebilirsiniz.

    ![Raporlar listesinde sayfalandırılmış rapor](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

1. Power BI hizmetinde açmak için seçin. Parametreleri varsa, raporu görüntüleyebilmeniz için bunları seçmeniz gerekir.
 
    ![Parametreleri seçme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

6. Raporunuzun veri kaynağı şirket içi ortamdaysa bu veri kaynağına erişim sağlama amacıyla [ağ geçidi oluşturma](#create-a-gateway) hakkında bilgi edinin.

## <a name="create-a-gateway"></a>Ağ geçidi oluşturma

Diğer tüm Power BI raporlarında olduğu gibi, rapor veri kaynağı şirket içindeyse verilere erişmek için bir ağ geçidi oluşturmanız veya bir ağ geçidine bağlanmanız gerekir.

1. Rapor adının yanındaki **Yönet**’i seçin.

   ![Sayfalandırılmış raporu yönetme](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-manage.png)

1. Ayrıntılı bilgi ve sonraki adımlar için şu Power BI hizmeti makalesine bakın: [Şirket içi veri ağ geçidi nedir?](../service-gateway-onprem.md)

### <a name="gateway-limitations"></a>Ağ geçidi sınırlamaları

Ağ geçitleri şu anda çok değerli parametreleri desteklememektedir.


## <a name="next-steps"></a>Sonraki adımlar

- [Power BI hizmetinde sayfalandırılmış rapor görüntüleme](../consumer/paginated-reports-view-power-bi-service.md)
- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
- [Öğretici: Uygulamaya müşterileriniz için sayfalandırılmış Power BI raporları ekleme](../developer/embed-paginated-reports-customers.md)

