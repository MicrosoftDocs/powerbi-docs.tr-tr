---
title: Power BI Rapor Sunucusu ile Power BI hizmetini karşılaştırma
description: Bu makalede Power BI Rapor Sunucusu ile Power BI hizmetinin özellikleri karşılaştırılmaktadır.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 05/07/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: 598b3e75aa134a5b5e2ee2a8c01316133b60fdac
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44727272"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Power BI Rapor Sunucusu ile Power BI hizmetini karşılaştırma

Power BI Rapor Sunucusu ile Power BI hizmeti, çok sayıda benzerliğe ve bazı temel farklılıklara sahiptir. Bu tabloda hangisinin ne olduğu açıklanmaktadır.

| Özellikler | Power BI Rapor Sunucusu | Power BI Hizmeti | Notlar
|---------|---------|---------|---------|
| Dağıtım | Şirket içi veya barındırılan bulut | Bulut | Power BI Rapor Sunucusu, Power BI Premium lisansına sahipse Azure VM’lerde (barındırılan bulur) dağıtılabilir
| Kaynak verileri | Bulut ve/veya şirket içi | Bulut ve/veya şirket içi |  
| Lisans | Power BI Premium veya Yazılım Güvencesi ile SQL Server EE | Power BI Pro ve/veya Power BI Premium |  
| Yaşam Döngüsü | Modern yaşam döngüsü ilkesi | Tam olarak yönetilen hizmet |  
| Yayın döngüsü | 4 ayda bir kez | Ayda bir kez | En son özellikler ve düzeltmeler ilk önce Power BI Hizmetine gelir. Çoğu temel işlevsellik, önümüzdeki birkaç yayında Power BI Rapor Sunucusuna gelecektir; bazı özellikler yalnızca Power BI hizmetine yöneliktir.
| Power BI Desktop'ta Power BI raporları oluşturma | Evet | Evet |  
| Tarayıcıda Power BI raporları oluşturma | Hayır | Evet |  
| Ağ geçidi gerekli | Hayır | Şirket içi veri kaynakları için evet |  
| Gerçek zamanlı akış | Hayır | Evet | [Power BI'da gerçek zamanlı akış](../service-real-time-streaming.md)
| Panolar | Hayır | Evet | [Power BI hizmetindeki panolar](../service-dashboards.md) 
| Uygulamaları kullanarak rapor grupları dağıtma | Hayır | Evet | [Panolar ve raporlar içeren uygulamalar oluşturma ve yayımlama](../service-create-distribute-apps.md) 
| İçerik paketleri | Hayır | Evet | [Kurumsal içerik paketleri: Giriş](../service-organizational-content-pack-introduction.md) 
| Salesforce gibi hizmetlere bağlanma | Hayır | Evet | Power BI hizmeti ile [kullandığınız hizmetlere bağlanma](../service-connect-to-services.md)
| Soru-Cevap | Hayır | Evet | [Power BI hizmetinde ve Power BI Desktop'ta Soru-Cevap özelliği](../power-bi-q-and-a.md) 
| Hızlı içgörüler | Hayır | Evet | [Power BI ile otomatik olarak veri içgörüleri oluşturma](../service-insights.md) 
| Excel'de Analiz Et | Hayır | Evet | [Excel'de Çözümle](../service-analyze-in-excel.md) 
| Sayfalandırılmış raporlar | Evet | Hayır | Sayfalandırılmış raporlar Power BI hizmetinde kullanılamaz ancak [sayfalandırılmış rapor öğelerini Power BI panolarına sabitleyebilirsiniz](https://docs.microsoft.com/sql/reporting-services/pin-reporting-services-items-to-power-bi-dashboards)
| Power BI mobil uygulamaları | Evet | Evet | [Power BI mobil uygulamalarına genel bakış](../consumer/mobile/mobile-apps-for-mobile-devices.md) 
| ARC GIS haritaları | Hayır | Evet | [Power BI hizmetinde ve Power BI Desktop'ta Esri tarafından sunulan ArcGIS haritaları](../power-bi-visualization-arcgis.md)
| Power BI raporları için e-posta abonelikleri | Hayır | Evet | Power BI hizmetinde [bir rapora veya panoya abone olma](../service-report-subscribe.md) 
| Sayfalandırılmış raporlar için e-posta abonelikleri | Evet | Hayır | [Raporlama Hizmetleri'nde e-posta teslimi](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  
| Veri uyarıları | Hayır | Evet | Power BI hizmetinde [veri uyarıları](../service-set-data-alerts.md)
| Satır düzeyi güvenlik | DirectQuery modunda yalnızca veri kaynağı üzerinden | DirectQuery (veri kaynağı) ve İçeri Aktarma modunda kullanılabilir | Power BI ile [satır düzeyi güvenlik (RLS)](../service-admin-rls.md) 
| Tam ekran modu | Hayır | Evet | Power BI hizmetinde [tam ekran modu](../service-fullscreen-mode.md) 
| Gelişmiş Office 365 işbirliği | Hayır | Evet | Office 365 ile [bir uygulama çalışma alanında işbirliği](../service-collaborate-power-bi-workspace.md) 
| R görselleri | Hayır | Evet | Power BI hizmetinde [R görselleri oluşturma](../visuals/service-r-visuals.md)  
| Önizleme özellikleri | Hayır | Evet | [Power BI hizmetinin önizleme özelliklerini kullanma](../service-preview-features.md) 
| Özel görseller | Evet | Evet | [Power BI'daki özel görseller](../power-bi-custom-visuals.md) 
| Power BI Desktop | Rapor Sunucusu için en iyi duruma getirilmiş sürüm, Rapor Sunucusu ile birlikte indirilebilir | Power BI Hizmeti için en iyi duruma getirilmiş sürüm, Microsoft Store’dan indirilebilir | [Rapor sunucusu için Power BI Desktop](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI hizmeti için Power BI Desktop](http://aka.ms/pbidesktopstore)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)  



