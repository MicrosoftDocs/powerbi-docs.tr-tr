---
title: Power BI Rapor Sunucusu için tarayıcı desteği
description: Power BI Rapor Sunucusu ve Rapor Görüntüleyicisi Denetimlerini yönetmek ve görüntülemek için desteklenen tarayıcı sürümlerini öğrenin.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 01/25/2018
ms.author: maghan
ms.openlocfilehash: b340ba2f2798c518d1705c03f7ec526a43bc019d
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721789"
---
# <a name="browser-support-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için tarayıcı desteği
Power BI Rapor Sunucusu ve Rapor Görüntüleyicisi Denetimlerini yönetmek ve görüntülemek için desteklenen tarayıcı sürümlerini öğrenin.

## <a name="browser-requirements-for-the-web-portal"></a>Web portalı için tarayıcı gereksinimleri
Web portalı için desteklenen tarayıcıların güncel listesi aşağıda verilmiştir.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9-10.11*

* Apple Safari (+)
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple iOS**  
*iOS 10 yüklü iPhone ve iPad*

* Apple Safari (+)

**Google Android**  
*Android 4.4 (KitKat) veya sonraki bir sürümü yüklü telefonlar ve tabletler*

* Google Chrome (+)
  
  **(+)** En son yayımlanan genel sürüm

## <a name="browser-requirements-for-the-report-viewer-web-control-2015"></a>Rapor Görüntüleyicisi web denetimi için tarayıcı gereksinimleri (2015)
Rapor Görüntüleyicisi web denetimi için desteklenen tarayıcıların güncel listesi aşağıda verilmiştir. Rapor görüntüleyicisi raporların web portalında görüntülenmesini sağlar.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9-10.11*

* Apple Safari (+)
  
  **(+)** En son yayımlanan genel sürüm

### <a name="authentication-requirements"></a>Kimlik doğrulaması gereksinimleri
Tarayıcılar, istemci isteklerinin başarılı olması için rapor sunucusu tarafından işlenmesi gereken belirli kimlik doğrulaması şemalarını destekler. Aşağıdaki tabloda Windows işletim sistemi üzerinde çalışan tarayıcılar tarafından desteklenen varsayılan kimlik doğrulaması türleri tanımlanmıştır.

| **Tarayıcı türü** | **Desteklenen Kimlik Doğrulaması Türü** | **Tarayıcı varsayılan ayarı** | **Sunucu varsayılan ayarı** |
| --- | --- | --- | --- |
| **Microsoft Edge** (+) |Anlaşma, Kerberos, NTLM, Temel |Anlaşma |Evet. Varsayılan kimlik doğrulaması ayarları Edge ile uyumludur. |
| **Microsoft Internet Explorer** |Anlaşma, Kerberos, NTLM, Temel |Anlaşma |Evet. Varsayılan kimlik doğrulaması ayarları Internet Explorer ile uyumludur. |
| **Google Chrome**(+) |Anlaşma, NTLM, Temel |Anlaşma |Evet. Varsayılan kimlik doğrulaması ayarları Chrome ile uyumludur. |
| **Mozilla Firefox**(+) |NTLM, Temel |NTLM |Evet. Varsayılan kimlik doğrulaması ayarları Firefox ile uyumludur. |
| **Apple Safari**(+) |NTLM, Temel |Temel |Evet. Varsayılan kimlik doğrulaması ayarları Safari ile uyumludur. |

 **(+)** En son yayımlanan genel sürüm

### <a name="script-requirements-for-viewing-reports"></a>Raporları görüntülemek için betik gereksinimleri
Rapor görüntüleyicisini kullanmak için tarayıcınızı betikleri çalıştıracak şekilde yapılandırmanız gerekir.

Betik çalıştırma etkin değilse raporları açtığınızda aşağıdakine benzer bir hata iletisi görürsünüz:

```
Your browser does not support scripts or has been configured to not allow scripts to run. Click here to view this report without scripts
```

 Betik desteği olmadan görüntülemeyi seçerseniz rapor HTML biçiminde oluşturulur ve rapor araç çubuğu ile belge haritası gibi rapor görüntüleyicisi özellikleri sunulmaz.

> [!NOTE]
> Rapor araç çubuğu, HTML Görüntüleyicisi bileşeninin bir parçasıdır. Araç çubuğu varsayılan olarak tarayıcı penceresi içinde görüntülenen tüm raporların üstünde görünür. Rapor görüntüleyicisinin sunduğu özellikler arasında rapordaki bilgilerde arama yapabilme, belirli bir sayfaya kaydırabilme ve görüntüleme kolaylığı sağlama amacıyla sayfa boyutunu ayarlayabilme bulunur. Rapor araç çubuğu veya HTML Görüntüleyicisi hakkında daha fazla bilgi için bkz. [HTML Görüntüleyicisi ve Rapor Araç Çubuğu](https://docs.microsoft.com/sql/reporting-services/html-viewer-and-the-report-toolbar).
> 
> 

## <a name="browser-support-for-report-viewer-web-server-controls-in-visual-studio"></a>Visual Studio'daki Rapor Görüntüleyicisi web sunucusu denetimleri için tarayıcı desteği
Rapor Görüntüleyicisi Web sunucusu denetimi, rapor işlevlerini bir ASP.NET web uygulamasına eklemek için kullanılır. Rapor Görüntüleyicisi Denetimi'ne ulaşma hakkında daha fazla bilgi için bkz. [Integrating Reporting Services Using Report Viewer Controls - Get Started (Rapor Görüntüleyicisi Denetimlerini Kullanarak Reporting Services'i Tümleştirme - Başlangıç)](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started).

Betik desteği etkinleştirilmiş bir tarayıcı kullanın. Betik çalıştıramayan tarayıcılarda raporu görüntüleyemezsiniz.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)
  
  **(+)** En son yayımlanan genel sürüm

## <a name="next-steps"></a>Sonraki adımlar
[Yönetici genel bakışı](admin-handbook-overview.md)  
[Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)  
[Install Report Builder (Rapor Oluşturucusu'nu yükleme)](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT) (SQL Server Veri Araçlarını (SSDT) indirme)](http://go.microsoft.com/fwlink/?LinkID=616714)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

