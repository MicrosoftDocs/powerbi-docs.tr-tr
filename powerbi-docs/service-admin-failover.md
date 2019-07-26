---
title: Power BI yüksek kullanılabilirlik, yük devretme ve olağanüstü durum kurtarma ile ilgili SSS
description: Power BI hizmetinin kullanıcılarına nasıl yüksek kullanılabilirlik, iş sürekliliği ve olağanüstü durum kurtarma sağladığını öğrenin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/30/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: b3fa7fd07a4c7f1992623871ed408b959582a125
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68270600"
---
# <a name="power-bi-high-availability-failover-and-disaster-recovery-faq"></a>Power BI yüksek kullanılabilirlik, yük devretme ve olağanüstü durum kurtarma ile ilgili SSS

Bu makale Power BI hizmetinin kullanıcılarına nasıl yüksek kullanılabilirlik, iş sürekliliği ve olağanüstü durum kurtarma sağladığını açıklar. Bu makaleyi okuduktan sonra yüksek kullanılabilirliğin nasıl elde edildiğini, Power BI’ın hangi koşullar altında yük devrettiğini ve yük devreden hizmetten neler beklenebileceğini daha iyi kavramış olursunuz.

## <a name="what-does-high-availability-mean-for-power-bi"></a>Power BI için "yüksek kullanılabilirlik" ne anlama gelir?

Power BI, tam olarak yönetilen bir hizmet olarak yazılımdır (SaaS).  Microsoft bunu, kullanıcıların her zaman raporlarına erişebilmelerini sağlamak için altyapı hatalarına karşı dayanıklı çalışacak şekilde tasarlar ve çalıştırır.  Hizmet [%99,9 SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) ile desteklenir.

## <a name="what-is-a-power-bi-failover"></a>Power BI yük devretme nedir?

Power BI, iş sürekliliğini garanti etmek için Azure veri merkezlerinde (bölgeler olarak da bilinir) her bileşenin birden çok örneğini bulundurur. Bir bölgede Power BI’ın erişilemez veya çalışamaz duruma gelmesine neden olan bir kesinti veya sorun oluşması durumunda Power BI o bölgedeki tüm bileşenlerinin yükünü yedek örneğine devreder. Yük devretme, kullanılabilirlik ve çalışabilirliği yeni bir bölgedeki ([Microsoft Güven Merkezi](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location)’nde belirtildiği gibi bu bölge genellikle aynı coğrafi konumdadır) Power BI hizmeti örneğine geri yükler.

Yük devredilen bir Power BI hizmeti örneği yalnızca _okuma işlemlerini_ destekler. Bu da yük devretme sırasında şu işlemlerin desteklenmediği anlamına gelir: yenileme, rapor yayımlama işlemleri, pano veya rapor değişiklikleri ve Power BI meta verilerinde değişiklikler gerektiren diğer işlemler (örneğin bir rapora yorum ekleme).  Pano görüntüleme ve rapor görüntüleme gibi (DirectQuery veya Canlı Bağlantı'yla şirket içi veri kaynaklarına dayalı olmayan) okuma işlemleri normal çalışmaya devam eder.

## <a name="how-are-backup-instances-kept-in-sync-with-my-data"></a>Yedekleme örnekleri verilerimle nasıl eşitleniyor?

Tüm Power BI hizmeti bileşenleri yedekleme örneklerini düzenli olarak eşitler. Power BI'da karşıya yüklenen veya değiştirilen tüm içerik için 15 dakikalık aralıklarla belirli bir noktaya eşitlemeyi hedefleriz. Yük devretme durumunda, Power BI yedekleme örneklerinin başka bölgelerde var olması ve yük devretme gerçekleştiğinde kullanılabilmesi için [Azure depolama coğrafi olarak yedekli çoğaltma](/azure/storage/common/storage-redundancy-grs) ve [ Azure SQL coğrafi olarak yedekli çoğaltmayı](/azure/sql-database/sql-database-active-geo-replication) kullanır.

## <a name="where-are-the-failover-clusters-located"></a>Yük devretme kümeleri nerede bulunur?

[Microsoft Güven Merkezi](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location)’nde açıklanan durumlar dışında yedekleme örnekleri kuruluşunuzun Power BI’a kaydı sırasında seçtiğiniz coğrafi bölgenin (geo) içinde yer alır. Coğrafi bölge çeşitli bölgeler içerebilir ve Microsoft verilerin dayanıklılığı için onları belirli bir coğrafi bölge içindeki bölgelerden herhangi birine çoğaltabilir. Microsoft, müşteri verilerini coğrafi bölgenin dışına çoğaltmaz veya taşımaz. Power BI’ın sunduğu coğrafi bölgeler ve bu coğrafi bölgelerin kapsadığı bölgelerin eşlemesi için bkz. [Microsoft Güven Merkezi](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location).

## <a name="how-does-microsoft-decide-to-failover"></a>Microsoft yük devretmeye nasıl karar verir?

Yük devretmenin gerekli olabileceğini gösteren iki farklı sistem vardır:

- Dış ve iç izleme yoklamalarımız kullanılabilirlikte bir eksikliği veya düzgün çalışamama durumunu gösterir. Bu göstergeler Power BI bileşenlerinde veya bir bölgede Power BI’ın bağımlı olduğu bir veya daha fazla hizmette algılanan kesintilere bağlı olabilir.
- Microsoft Azure’ın merkezi operasyon takımı bir bölgedeki önemli kesintileri bize bildirir.

Her iki durumda da yük devretme kararı Power BI yönetim takımının üyeleri tarafından alınır; bu kararın kendisi otomatik değildir. Karar alındıktan sonra yük devretme işlemi otomatik olarak gerçekleştirilir.

## <a name="how-do-i-know-power-bi-is-now-in-failover-mode"></a>Power BI’ın yük devretme modunda olduğunu nasıl anlarım?

Power BI destek sayfasına bildirim gönderilir ([https://powerbi.microsoft.com/en-us/support/](https://powerbi.microsoft.com/en-us/support/)). Bildirim; yayımlama, yenileme, pano oluşturma, pano çoğaltma ve izin değişiklikleri gibi yük devretme sırasında kullanılamayan önemli işlemleri içerir.

## <a name="how-long-does-it-take-power-bi-to-fail-over"></a>Power BI’ın yük devretmesi ne kadar sürer?

Yük devretme kararı alındıktan sonra yük devretme örneğinin kullanılabilir duruma gelmesi 60 dakika kadar sürebilir.

## <a name="when-does-my-power-bi-instance-return-to-the-original-region"></a>Power BI örneğim ne zaman özgün bölgesine döner?

Power BI hizmeti örnekleri, yük devretmeye neden olan sorun çözüldüğünde özgün bölgelerine döner. Power BI destek sayfasını gözden geçirin: Sorun çözüldüğünde Power BI takımı yük devretmeyi açıklayan bildirimi kaldırır. O noktada, işlemler normal dönmüş olmalıdır.

## <a name="am-i-responsible-for-the-availability-of-my-power-bi-solution"></a>Power BI çözümümün kullanılabilirliğinden ben mi sorumluyum?

Kuruluşunuzda kullanılan Power BI çözümü aşağıdaki öğelerden birini içeriyorsa çözümünüzün yüksek kullanılabilirliğini güvence altına almak için bazı önlemler almanız gerekir:

- Kuruluşunuzda Power BI Premium kullanılıyorsa Premium kapasitenin dağıtımınızın yük gereksinimlerini karşılayacak şekilde boyutlandırıldığından emin olmanız gerekir.  [Power BI Premium Planlama ve Dağıtım teknik incelemesi](https://aka.ms/Premium-Capacity-Planning-Deployment) ve [Power BI Premium Kapasite Ölçümleri uygulaması](service-admin-premium-monitor-capacity.md), bu gereksinimi planlamanıza ve karşılamanıza yardımcı olabilir. Yardımcı olmak için Power BI’daki yönetim portalına ve ölçümler uygulamasına düzenli olarak yeni özellikler ekliyoruz.
- Kuruluşunuz şirket içi veri kaynaklarına şirket içi ağ geçidini kullanarak erişiyorsa yüksek kullanılabilirliği desteklemek için ağ geçidini [bu makalede açıklandığı gibi](/data-integration/gateway/service-gateway-high-availability-clusters) ayarlamanız gerekir. İster içeri aktarma modunda raporları yeniliyor olun ister DirectQuery veya Canlı Bağlantı kullanarak veri veya veri modellerine erişiyor olun bu yönergeleri izleyebilirsiniz.

## <a name="will-gateways-function-when-in-failover-mode"></a>Ağ geçitleri yük devretme modunda çalışır mı?

Hayır. Şirket içi veri kaynaklarından alınması gereken veriler (Doğrudan Sorgu ve Canlı Bağlantı’yı temel alan herhangi bir rapor ve pano) yük devretme sırasında çalışmaz. Öte yandan ağ geçidi yapılandırması değişmez: Power BI örneği özgün durumuna döndüğünde ağ geçitleri de normal işlevlerine döner.
