---
title: Power BI Rapor Sunucusu ile Power BI hizmetini karşılaştırma
description: Bu makalede Power BI Rapor Sunucusu ile Power BI hizmetinin özellikleri karşılaştırılmaktadır.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
ms.date: 07/28/2020
ms.openlocfilehash: 18629f38db7d8b88c47d4a1af3a5c3f6512433b4
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90859164"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Power BI Rapor Sunucusu ile Power BI hizmetini karşılaştırma

Power BI Rapor Sunucusu ile Power BI hizmetinin çok sayıda benzerliği ve bazı temel farklılıkları vardır. Bu tabloda hangisinin ne olduğu açıklanmaktadır.

## <a name="features-of-power-bi-report-server-and-the-power-bi-service"></a>Power BI Rapor Sunucusu ve Power BI hizmetinin özellikleri

| Özellikler | Power BI Rapor Sunucusu | Power BI Hizmeti | Notlar |
|---------|---------|---------|---------|
| Dağıtım | Şirket içi veya barındırılan bulut | Bulut | Power BI Rapor Sunucusu, Power BI Premium veya Yazılım Güvencesi ile SQL Server Enterprise lisansına sahipse Azure VM’lerde (barındırılan bulur) dağıtılabilir|
| Kaynak verileri | Bulut ve/veya şirket içi | Bulut ve/veya şirket içi |  |
| Lisans | Power BI Premium veya Yazılım Güvencesi (SA) ile SQL Server EE | Power BI Pro ve/veya Power BI Premium | |  
| Yaşam Döngüsü | Modern yaşam döngüsü ilkesi | Tam olarak yönetilen hizmet |  |
| Yayın döngüsü | Yılda üç kez (Ocak, Mayıs, Eylül) | Ayda bir kez | En son özellikler ve düzeltmeler ilk önce Power BI Hizmetine gelir. Hizmet için Power BI Desktop sürümlerinden gelen özellik dağıtımı, her sürümde Power BI Rapor Sunucusu’na sağlanır; diğer özelliklerden çoğu yalnızca Power BI hizmetine yöneliktir. |
| Power BI Desktop'ta Power BI raporları oluşturma | Evet | Evet |  |
| Tarayıcıda Power BI raporları oluşturma | Hayır | Evet |  |
| Power BI paylaşılan veri kümelerini barındırma ve bunlara bağlanma | Hayır | Evet | [Çalışma alanları arasında veri kümelerine giriş](../connect-data/service-datasets-across-workspaces.md) |
| Ağ geçidi gerekli | Hayır | Şirket içi veri kaynakları için evet |  |
| Gerçek zamanlı akış | Hayır | Evet | [Power BI'da gerçek zamanlı akış](../connect-data/service-real-time-streaming.md) |
| Panolar | Hayır | Evet | [Power BI hizmetindeki panolar](../consumer/end-user-dashboards.md) |
| Uygulamaları kullanarak rapor grupları dağıtma | Hayır | Evet | [Panolar ve raporlar içeren uygulamalar oluşturma ve yayımlama](../collaborate-share/service-create-distribute-apps.md) |
| İçerik paketleri | Hayır | Evet | [Kurumsal içerik paketleri: Giriş](../collaborate-share/service-organizational-content-pack-introduction.md) |
| Salesforce gibi hizmetlere bağlanma | Evet | Evet | Power BI hizmetindeki içerik paketleriyle [kullandığınız hizmetlere bağlanma](../connect-data/service-connect-to-services.md). Power BI Rapor Sunucusu'nda hizmetlere bağlanmak için sertifikalı bağlayıcıları kullanabilirsiniz. Ayrıntılar için bkz. [Power BI Rapor Sunucusu'nda Power BI raporu veri kaynakları](data-sources.md). |
| Soru-Cevap | Hayır | Evet | [Power BI hizmetinde ve Power BI Desktop'ta Soru-Cevap özelliği](../create-reports/power-bi-tutorial-q-and-a.md) 
| Hızlı içgörüler | Hayır | Evet | [Power BI ile otomatik olarak veri içgörüleri oluşturma](../consumer/end-user-insights.md) |
| Excel’de Analiz Et | Hayır | Evet | [Excel'de Çözümle](../collaborate-share/service-analyze-in-excel.md) 
| Sayfalandırılmış raporlar | Evet | Evet | [Power BI hizmetinde sayfalandırılmış raporlar şu anda](../paginated-reports/paginated-reports-report-builder-power-bi.md) Premium kapasitede önizleme aşamasındadır |
| Power BI mobil uygulamaları | Evet | Evet | [Power BI mobil uygulamalarına genel bakış](../consumer/mobile/mobile-apps-for-mobile-devices.md) |
| ARC GIS haritaları | Hayır | Evet | [Power BI hizmetinde ve Power BI Desktop'ta Esri tarafından sunulan ArcGIS haritaları](../visuals/power-bi-visualization-arcgis.md) |
| Power BI raporları için e-posta abonelikleri | Hayır | Evet | [Kendinizi veya başkalarını](../collaborate-share/service-report-subscribe.md) Power BI hizmetinde bir rapora veya panoya abone yapma |
| Sayfalandırılmış raporlar için e-posta abonelikleri | Evet | Evet | [Kendinizi ve başkalarını Power BI hizmetinde sayfalandırılmış raporlara abone yapma](../consumer/paginated-reports-subscriptions.md)<br><br>[Reporting Services’da e-posta teslimi](/sql/reporting-services/working-with-subscriptions-web-portal)  |
| Veri uyarıları | Hayır | Evet | Power BI hizmetinde [veri uyarıları](../create-reports/service-set-data-alerts.md)
| Satır düzeyi güvenlik (RLS) | Evet | Evet | DirectQuery (veri kaynağı) ve İçeri Aktarma modunda kullanılabilir <br><br>[Power BI hizmetinde](../admin/service-admin-rls.md) satır düzeyi güvenlik <br><br>[Power BI Rapor Sunucusu](row-level-security-report-server.md)'nda satır düzeyi güvenlik |
| Çok-çok ilişkileri | Hayır | Evet | Power BI Desktop’ta [Çoka çok ilişkileri uygulama](../transform-model/desktop-many-to-many-relationships.md) |
| Raporlar arası detaylandırma | Hayır | Evet | [Raporlar arası detaylandırmayı kullanma](../create-reports/desktop-cross-report-drill-through.md) |
| Tam ekran modu | Hayır | Evet | Power BI hizmetinde [tam ekran modu](../consumer/end-user-focus.md) |
| Gelişmiş Microsoft 365 işbirliği | Hayır | Yes | Microsoft 365 ile [bir çalışma alanında işbirliği yapma](../collaborate-share/service-collaborate-power-bi-workspace.md) |
| R betikleri ve görselleri | Hayır | Evet | Power BI Desktop’ta [R görselleri oluşturup](../create-reports/desktop-r-visuals.md) R betikleri çalıştırın ve bunları Power BI hizmetine yayımlayın. R betikleri veya görselleri içeren Power BI raporlarını Power BI Rapor Sunucusu’na kaydedemezsiniz.  |
| Python betikleri ve görselleri | Hayır | Evet | Power BI Desktop’ta [Python görselleri ve betikleri oluşturup](../connect-data/desktop-python-scripts.md) bunları Power BI hizmetine yayımlayın. Python betikleri veya görselleri içeren Power BI raporlarını Power BI Rapor Sunucusu’na kaydedemezsiniz. |
| Önizleme özellikleri | Hayır | Evet | [Power BI hizmetinin önizleme özelliklerini kullanma](../consumer/end-user-preview-features.md) |
| Power BI görselleri | Yes | Yes | [Power BI görselleri](../developer/visuals/power-bi-custom-visuals.md) |
| Bileşik modeller | Hayır | Yes |
| Power BI Desktop | Rapor Sunucusu için en iyi duruma getirilmiş sürüm, Rapor Sunucusu ile birlikte indirilebilir | Power BI Hizmeti için en iyi duruma getirilmiş sürüm, Microsoft Store’dan indirilebilir | [Rapor sunucusu için Power BI Desktop](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI hizmeti için Power BI Desktop](https://aka.ms/pbidesktopstore) |

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)