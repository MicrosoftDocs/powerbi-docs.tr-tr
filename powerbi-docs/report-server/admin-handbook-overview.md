---
title: "Power BI Rapor Sunucusu'na yönelik yönetici el kitabına genel bakış"
description: "Power BI, mobil ve sayfalandırılmış raporlarınızı depolayabileceğiniz ve yönetebileceğiniz şirket içi konum olan Power BI Rapor Sunucusu'na yönelik yönetici el kitabına hoş geldiniz."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/01/2017
ms.author: asaxton
ms.openlocfilehash: 6307e6cc3beb119ffaba40344736ff29e293fc95
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="administrator-handbook-overview-power-bi-report-server"></a>Power BI Rapor Sunucusu'na yönelik yönetici el kitabına genel bakış
Power BI, mobil ve sayfalandırılmış raporlarınızı depolayabileceğiniz ve yönetebileceğiniz şirket içi konum olan Power BI Rapor Sunucusu'na yönelik yönetici el kitabına hoş geldiniz.

![](media/admin-handbook-overview/admin-handbook.png)

Bu el kitabı, Power BI Rapor Sunucunuzu planlama, dağıtma ve yönetme ile ilgili kavramları anlamanıza yardımcı olacaktır.

## <a name="installing-and-migration"></a>Yükleme ve geçiş
Power BI Rapor Sunucusu'nu kullanmaya başlamak için yüklemeniz gerekir. Bu görevi gerçekleştirmenizi sağlayacak bilgileri sizinle paylaşacağız.

Power BI Rapor Sunucusu'na yönelik yükleme, yükseltme veya geçiş işlemlerine başlamadan önce rapor sunucusunun [sistem gereksinimlerine](system-requirements.md) göz atın.

### <a name="installing"></a>Yükleme
Yeni bir Power BI Rapor Sunucusu dağıtıyorsanız aşağıdaki belgelerden faydalanabilirsiniz. Hızlı başlangıç belgesi hemen işe koyulmanızı sağlayacaktır. Dilerseniz ayrıntılı yükleme belgesini de inceleyebilirsiniz.

* [Quickstart: Install Power BI Report Server (Hızlı Başlangıç: Power BI Rapor Sunucusu'nu yükleme)](quickstart-install-report-server.md)
* [Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)

### <a name="migration"></a>Geçiş
SQL Server Reporting Services için yerinde yükseltme seçeneği mevcut değildir. Power BI Rapor Sunucusu'na dönüştürmek istediğiniz bir SQL Server Reporting Services örneğiniz varsa geçiş yapmanız gerekir. Geçiş yapmak istemenizi sağlayacak başka nedenler de mevcuttur. Daha ayrıntılı bilgi için geçiş belgesini inceleyin.

[Rapor sunucusu yüklemesini geçirme](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>Rapor sunucunuzu yapılandırma
Rapor sunucunuzu yapılandırmak için kullanabileceğiniz birçok seçenek mevcuttur. SSL kullanacak mısınız? E-posta sunucusu yapılandırıyor musunuz? Görselleştirmeleri sabitlemek için Power BI hizmetini tümleştirmek istiyor musunuz?

Yapılandırmanın büyük bölümü Rapor Sunucusu Yapılandırma Yöneticisi'nde gerçekleştirilir. Daha ayrıntılı bilgi için [yapılandırma yöneticisi](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode) belgelerini inceleyin.

## <a name="security"></a>Güvenlik
Güvenlik ve koruma her kuruluş için önemli konulardır. Kimlik doğrulaması, yetkilendirme, roller ve izinler hakkında bilgi edinmek için [güvenlik](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection) belgelerine göz atabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
[Quickstart: Install Power BI Report Server (Hızlı Başlangıç: Power BI Rapor Sunucusu'nu yükleme)](quickstart-install-report-server.md)  
[How to find your report server product key (Rapor sunucusu ürün anahtarınızı bulma)](find-product-key.md)  
[Install Power BI Desktop optimized for Power BI Report Server (Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yükleme)](install-powerbi-desktop.md)  
[Install Report Builder (Rapor Oluşturucusu'nu yükleme)](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT) (SQL Server Veri Araçlarını (SSDT) indirme)](http://go.microsoft.com/fwlink/?LinkID=616714)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

