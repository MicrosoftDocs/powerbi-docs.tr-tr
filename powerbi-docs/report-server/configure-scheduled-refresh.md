---
title: Power BI raporlarında zamanlanmış yenilemeyi yapılandırma
description: Power BI raporunuzdaki verilerin yenilenmesi için zamanlanmış yenileme planı oluşturmanız gerekir.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: d8283f1abf05ab788336413bd18582ea71d4e43f
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34296281"
---
# <a name="how-to-configure-power-bi-report-scheduled-refresh"></a>Power BI raporlarında zamanlanmış yenilemeyi yapılandırma
Power BI raporunuzdaki verilerin yenilenmesi için zamanlanmış yenileme planı oluşturmanız gerekir. Bu işlem Power BI raporunun *Yönet* bölümünden gerçekleştirilir.

![Power BI raporunda başarılı zamanlanmış yenileme](media/configure-scheduled-refresh/scheduled-refresh-success.png)

## <a name="configure-data-source-credentials"></a>Veri kaynağı kimlik bilgilerini yapılandırma
Zamanlanmış veri yenileme planı oluşturmadan önce Power BI raporunuzda kullanılan **tüm veri kaynaklarının** kimlik bilgilerini ayarlamanız gerekir.

1. Web portalında Power BI raporuna sağ tıklayıp **Yönet**'i seçin.
   
    ![Power BI raporu bağlam menüsünden Yönet'i seçin](media/configure-scheduled-refresh/manage-power-bi-report.png)
2. Soldaki menüde **Veri kaynakları** sekmesini seçin.
3. Görüntülenen her bir veri kaynağı için bağlantı sırasında kullanılacak kimlik doğrulaması türünü belirleyin. Gerekli kimlik bilgilerini girin.
   
    ![Rapor yönetim ekranında veri kaynağı kimlik bilgileri](media/configure-scheduled-refresh/data-source-credentials.png)

## <a name="creating-a-schedule-refresh-plan"></a>Zamanlanmış Yenileme Planı oluşturma
Zamanlanmış yenileme planı oluşturmak için aşağıdaki adımları izleyin.

1. Web portalında Power BI raporuna sağ tıklayıp **Yönet**'i seçin.
   
    ![Power BI raporu bağlam menüsünden Yönet'i seçin](media/configure-scheduled-refresh/manage-power-bi-report.png)
2. Sol taraftaki menüde **Zamanlanmış yenileme** sekmesini seçin.
3. **Zamanlanmış yenileme** sayfasında **Yeni zamanlanmış yenileme planı**'nı seçin.
   
    ![Yeni zamanlanmış yenileme planı](media/configure-scheduled-refresh/new-scheduled-refresh-plan.png)
4. **Yeni Zamanlanmış Yenileme Planı** sayfasında bir açıklama girin ve veri modelinizin yenilenmesini istediğiniz zamanı ayarlayın.
5. Ardından **Zamanlanmış yenileme planı oluştur**'u seçin.
   
    ![Zamanlanmış yenileme planı oluşturma](media/configure-scheduled-refresh/create-scheduled-refresh-plan.png)

## <a name="modifying-a-schedule-refresh-plan"></a>Zamanlanmış Yenileme Planını değiştirme
Zamanlanan yenileme planını değiştirmek, yeni plan oluşturma ile benzerdir.

1. Web portalında Power BI raporuna sağ tıklayıp **Yönet**'i seçin.
   
    ![Power BI raporu bağlam menüsünden Yönet'i seçin](media/configure-scheduled-refresh/manage-power-bi-report.png)
2. Sol taraftaki menüde **Zamanlanmış yenileme** sekmesini seçin.
3. **Zamanlanmış yenileme** sayfasında yönetmek istediğiniz yenileme planının yanındaki **Düzenle** bağlantısını seçin.
   
    ![Düzenlemek istediğiniz planın yanındaki düzenle bağlantısını seçin](media/configure-scheduled-refresh/edit-scheduled-refresh-plan.png)
4. **Zamanlanmış Yenileme Planını Düzenle** sayfasında bir açıklama girin ve veri modelinizin yenilenmesini istediğiniz zamanı ayarlayın.
5. Ardından **Uygula**'yı seçin.
   
    ![Zamanlanmış yenileme planı düzenleme sayfası oluşturma ekranı ile benzerdir](media/configure-scheduled-refresh/edit-scheduled-refresh-plan-page.png)

## <a name="viewing-the-status-of-schedule-refresh-plan"></a>Zamanlanmış Yenileme Planının durumunu görüntüleme
Zamanlanmış yenileme planının durumunu Web portalında görüntüleyebilirsiniz.

1. Web portalında Power BI raporuna sağ tıklayıp **Yönet**'i seçin.
   
    ![Power BI raporu bağlam menüsünden Yönet'i seçin](media/configure-scheduled-refresh/manage-power-bi-report.png)
2. Sol taraftaki menüde **Zamanlanmış yenileme** sekmesini seçin.
3. **Zamanlanmış yenileme** sayfasında en sağdaki sütunda planın durumu görüntülenir.
   
   | **Durum** | **Açıklama** |
   | --- | --- |
   | Yeni Zamanlanmış Yenileme Planı |Plan oluşturuldu ancak çalıştırılmadı. |
   | Yenileniyor |Yenileme işlemi başlatıldı. |
   | Model Analysis Server'a aktarılıyor |Model rapor sunucusu katalog veritabanından barındırılan Analysis Services örneğine kopyalanıyor. |
   | Veriler yenileniyor |Model içindeki veriler yenileniyor. |
   | Modeldeki kimlik bilgileri kaldırılıyor |Modelden veri kaynağına bağlanmak için kullanılan kimlik bilgileri kaldırıldı. |
   | Model kataloğa kaydediliyor |Veri yenileme işlemi tamamlandı ve yenilenen model rapor sunucusu katalog veritabanına geri kaydediliyor. |
   | Tamamlandı: Veri Yenileme |Yenileme tamamlandı. |
   | Hata: |Yenileme sırasında bir hata oluştu ve görüntülendi. |

Geçerli durumu görmek için web sayfasının yenilenmesi gerekiyor. Durum otomatik olarak değişmez.

## <a name="next-steps"></a>Sonraki adımlar
Zamanlama oluşturma ve değiştirme hakkında daha fazla bilgi edinmek için bkz. [Zamanlama oluşturma, değiştirme ve silme](https://docs.microsoft.com/sql/reporting-services/subscriptions/create-modify-and-delete-schedules).

Zamanlanmış yenilemeyle ilgili sorunları gidermek için bkz. [Power BI Rapor Sunucusu'nda zamanlanmış yenileme ile ilgili sorunları giderme](scheduled-refresh-troubleshoot.md).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

