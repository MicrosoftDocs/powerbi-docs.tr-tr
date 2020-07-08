---
title: Power BI planlı bakımı
description: Yöneticiler için, Power BI planlı bakımının kuruluşlarını nasıl etkilediği ve atmaları gereken sonraki adımlar hakkında bilgi.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/19/2020
ms.author: kfollis
ms.custom: MC
ROBOTS: NOINDEX
LocalizationGroup: Admin
ms.openlocfilehash: cc9364129159b5527d309f125d42e661d0b4c206
ms.sourcegitcommit: a58d10ca62bc55e83b58cf8e8495ac01a4bd6532
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2020
ms.locfileid: "85120579"
---
# <a name="power-bi-planned-maintenance"></a>Power BI planlı bakımı

Power BI hizmetine yönelik planlı bakım, müşterilerimize güvenilir bir ürün sunma taahhüdümüzün gerekli bir parçasıdır. Planlı bakım gerçekleştiğinde, Power BI hizmeti bir süreliğine kuruluşunuzun kullanımına kapalı olur. Kullanıcılar Power BI hizmetine erişemez ve arka plan işlemleri başarısız olabilir. Bakımın ardından, hizmetin normal bir şekilde çalışmasını ve hem etkileşimli işlemlerin hem de arka plan işlemlerinin başarılı bir şekilde çalışmasını bekleriz.  

Kuruluşunuza olan etkisini en aza indirmeye yardımcı olmak için bakımlar normal iş saatlerinin dışında yapılacak şekilde planlanır. “Normal iş saatlerinin dışında” kavramının, dünyanın her yerinde kullanıcıları olan kuruluşları daha farklı şekilde etkileyeceğini biliyoruz. Kullanıcılarınızı etkileyen tüm durumlardan dolayı özür dileriz. Power BI’ı iyileştirmek ve bu bakım sürelerini en aza indirmek için çok çalışıyoruz.

Kuruluşunuz etkilenecekse sizi önceden bilgilendiririz. Microsoft 365 yöneticileri, Microsoft 365 İleti Merkezi’nde önceden bir bildirim görürler ve e-posta alırlar. Ayrıca, Premium Destek sözleşmeleri olan müşteriler Microsoft hesabı ekibi aracılığıyla bilgilendirilir.

## <a name="actions-to-take-now"></a>Hemen yapılması gereken eylemler

* Microsoft 365 yöneticilerinin Power BI planlı bakım hakkındaki iletiler için [İleti merkezini](https://admin.microsoft.com/Adminportal/Home#/MessageCenter) kontrol etmeleri gerekir. İletiyi, haberdar olması gereken ancak İleti merkezine erişimi olmayan kişilerle paylaşın.
* Microsoft 365 yöneticisi değilseniz BT departmanınıza veya iç destek ekiplerinize ulaşarak yaklaşan bakımlar hakkında bilgi alabilirsiniz.

## <a name="actions-to-take-when-maintenance-is-complete"></a>Bakım tamamlandığında yapılması gereken eylemler

* Kullanıcıların açık tarayıcı pencerelerini yenilemesi gerekir.
* Power BI Mobil uygulama kullanıcılarının en güncel sürümü kullandıklarını doğrulamaları ve oturumlarını kapatıp açmaları gerekir. Telefonunuzun uygulama mağazasını veya [Power BI Mobil](https://powerbi.microsoft.com/mobile/) sayfamızı kontrol edin.
* Yerel konumlardan veya OneDrive ve SharePoint konumlarından olması fark etmeksizin, kuruluş görsellerinin kullanıldığı raporları aktif bir şekilde düzenleyip yayımlayan müşterilerin yeniden yayımlamadan önce görseli kuruluş görsel mağazasından yeniden içeri aktarmaları veya güncelleştirilmiş PBIX’i indirmeleri gerekir. Kuruluş görselleri hakkında daha fazla bilgi için bkz. [Kuruluş görselleri](service-admin-portal.md#organization-visuals).
* Excel’de Analiz özelliğinden yararlanan Excel çalışma kitapları yenilenmezse bağlantı dizesini güncelleştirmeniz veya veri kümesi için ODC bağlantısını yeniden indirmeniz gerekir. Daha fazla bilgi için bkz. [Excel’de Analiz](../collaborate-share/service-analyze-in-excel.md#connect-to-power-bi-data).
* Power BI Embedded içerik bağlantıları, bakım tamamlandıktan sonra bağlanamayabilir. Örneğin, SharePoint veya Teams’e eklenen bir bağlantı kullanıcı hatasıyla sonuçlanabilir. Bu sorunu çözmek için Power BI’daki ekli bağlantıyı yeniden oluşturmanız ve sonra kullanıldıkları konumları güncelleştirmeniz gerekir. Ekli bağlantılar hakkında daha fazla bilgi için bkz. [SharePoint Online’da rapor web bölümü ekleme](../collaborate-share/service-embed-report-spo.md) ve [Power BI ile Microsoft Teams’de işbirliği yapma](../collaborate-share/service-embed-report-microsoft-teams.md).

## <a name="next-steps"></a>Sonraki adımlar

* [Hizmet kesintisi bildirimlerini etkinleştirme](service-interruption-notifications.md)
* [Yaklaşan değişiklikleri İleti merkezinde izleme](https://docs.microsoft.com/microsoft-365/admin/manage/message-center?view=o365-worldwide)