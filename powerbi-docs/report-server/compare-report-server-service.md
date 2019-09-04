---
title: Power BI Rapor Sunucusu ile Power BI hizmetini karşılaştırma
description: Bu makalede Power BI Rapor Sunucusu ile Power BI hizmetinin özellikleri karşılaştırılmaktadır.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.date: 08/29/2019
ms.openlocfilehash: 0755b41fbeef1f62d2722e3529007dc4f8773634
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70186071"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Power BI Rapor Sunucusu ile Power BI hizmetini karşılaştırma

Power BI Rapor Sunucusu ile Power BI hizmetinin çok sayıda benzerliği ve bazı temel farklılıkları vardır. Bu tabloda hangisinin ne olduğu açıklanmaktadır.

## <a name="features-of-power-bi-report-server-and-the-power-bi-service"></a>Power BI Rapor Sunucusu ve Power BI hizmetinin özellikleri

| Özellikler | Power BI Rapor Sunucusu | Power BI Hizmeti | Notlar |
|---------|---------|---------|---------|
| Dağıtım | Şirket içi veya barındırılan bulut | Bulut | Power BI Rapor Sunucusu, Power BI Premium lisansına sahipse Azure VM’lerde (barındırılan bulur) dağıtılabilir |
| Kaynak verileri | Bulut ve/veya şirket içi | Bulut ve/veya şirket içi |  |
| Lisans | Power BI Premium veya Yazılım Güvencesi ile SQL Server EE | Power BI Pro ve/veya Power BI Premium | |  
| Yaşam Döngüsü | Modern yaşam döngüsü ilkesi | Tam olarak yönetilen hizmet |  |
| Yayın döngüsü | 4 ayda bir kez | Ayda bir kez | En son özellikler ve düzeltmeler ilk önce Power BI Hizmetine gelir. Çoğu temel işlevsellik, önümüzdeki birkaç yayında Power BI Rapor Sunucusuna gelecektir; bazı özellikler yalnızca Power BI hizmetine yöneliktir. |
| Power BI Desktop'ta Power BI raporları oluşturma | Evet | Evet |  |
| Tarayıcıda Power BI raporları oluşturma | Hayır | Evet |  |
| Ağ geçidi gerekli | Hayır | Şirket içi veri kaynakları için evet |  |
| Gerçek zamanlı akış | Hayır | Evet | [Power BI'da gerçek zamanlı akış](../service-real-time-streaming.md) |
| Panolar | Hayır | Evet | [Power BI hizmetindeki panolar](../consumer/end-user-dashboards.md) |
| Uygulamaları kullanarak rapor grupları dağıtma | Hayır | Evet | [Panolar ve raporlar içeren uygulamalar oluşturma ve yayımlama](../service-create-distribute-apps.md) |
| İçerik paketleri | Hayır | Evet | [Kurumsal içerik paketleri: Giriş](../service-organizational-content-pack-introduction.md) |
| Salesforce gibi hizmetlere bağlanma | Evet | Evet | Power BI hizmetindeki içerik paketleriyle [kullandığınız hizmetlere bağlanma](../service-connect-to-services.md). Power BI Rapor Sunucusu'nda hizmetlere bağlanmak için sertifikalı bağlayıcıları kullanabilirsiniz. Ayrıntılar için bkz. [Power BI Rapor Sunucusu'nda Power BI raporu veri kaynakları](data-sources.md). |
| Soru-Cevap | Hayır | Evet | [Power BI hizmetinde ve Power BI Desktop'ta Soru-Cevap özelliği](../power-bi-tutorial-q-and-a.md) 
| Hızlı içgörüler | Hayır | Evet | [Power BI ile otomatik olarak veri içgörüleri oluşturma](../consumer/end-user-insights.md) |
| Excel'de Analiz Et | Hayır | Evet | [Excel'de Çözümle](../service-analyze-in-excel.md) 
| Sayfalandırılmış raporlar | Evet | Evet | [Power BI hizmetinde sayfalandırılmış raporlar şu anda](../paginated-reports-report-builder-power-bi.md) Premium kapasitede önizleme aşamasındadır |
| Power BI mobil uygulamaları | Evet | Evet | [Power BI mobil uygulamalarına genel bakış](../consumer/mobile/mobile-apps-for-mobile-devices.md) |
| ARC GIS haritaları | Hayır | Evet | [Power BI hizmetinde ve Power BI Desktop'ta Esri tarafından sunulan ArcGIS haritaları](../visuals/power-bi-visualization-arcgis.md) |
| Power BI raporları için e-posta abonelikleri | Evet | Evet | [Kendinizi veya başkalarını](../service-report-subscribe.md) Power BI hizmetinde bir rapora veya panoya abone yapma |
| Sayfalandırılmış raporlar için e-posta abonelikleri | Evet | Evet | [Kendinizi ve başkalarını Power BI hizmetinde sayfalandırılmış raporlara abone yapma](../paginated-reports-subscriptions.md)<br><br>[Reporting Services’da e-posta teslimi](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  |
| Veri uyarıları | Hayır | Evet | Power BI hizmetinde [veri uyarıları](../service-set-data-alerts.md)
| Satır düzeyi güvenlik (RLS) | Evet | Evet | DirectQuery (veri kaynağı) ve İçeri Aktarma modunda kullanılabilir <br><br>[Power BI hizmetinde](../service-admin-rls.md) satır düzeyi güvenlik <br><br>[Power BI Rapor Sunucusu](row-level-security-report-server.md)'nda satır düzeyi güvenlik |
| Tam ekran modu | Hayır | Evet | Power BI hizmetinde [tam ekran modu](../consumer/end-user-focus.md) |
| Gelişmiş Office 365 işbirliği | Hayır | Evet | Office 365 ile [bir uygulama çalışma alanında işbirliği](../service-collaborate-power-bi-workspace.md) |
| R görselleri | Hayır | Evet | Power BI Desktop'ta [R görselleri oluşturma](../desktop-r-visuals.md) ve bunları Power BI hizmetine yayımlama. R görseli içeren Power BI raporlarını Power BI Rapor Sunucusu'na kaydedemezsiniz.  |
| Önizleme özellikleri | Hayır | Evet | [Power BI hizmetinin önizleme özelliklerini kullanma](../consumer/end-user-preview-features.md) |
| Özel görseller | Evet | Evet | [Power BI'daki özel görseller](../power-bi-custom-visuals.md) |
| Power BI Desktop | Rapor Sunucusu için en iyi duruma getirilmiş sürüm, Rapor Sunucusu ile birlikte indirilebilir | Power BI Hizmeti için en iyi duruma getirilmiş sürüm, Microsoft Store’dan indirilebilir | [Rapor sunucusu için Power BI Desktop](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI hizmeti için Power BI Desktop](http://aka.ms/pbidesktopstore) |

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)  