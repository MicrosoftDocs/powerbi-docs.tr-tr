---
title: "Power BI Rapor Sunucusu sürüm notları"
description: "Bu konu başlığında Power BI Rapor Sunucusu ile ilgili sınırlamalar ve sorunlar anlatılmaktadır."
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
ms.openlocfilehash: ffd0d1ce38a989121225a666ca4aa924df130216
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-report-server-release-notes"></a>Power BI Rapor Sunucusu sürüm notları
Bu konu başlığında Power BI Rapor Sunucusu ile ilgili sınırlamalar ve sorunlar anlatılmaktadır.

Power BI Rapor Sunucusu'nu ve Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop'ı indirmek için [On-premises reporting with Power BI Report Server (Power BI Rapor Sunucusu ile şirket içi raporlama)](https://powerbi.microsoft.com/report-server/) sayfasına gidin.

## <a name="october-2017"></a>Ekim 2017
* Power BI raporlarında içeri aktarılan veriler için destek
* Web portalında Excel çalışma kitaplarını görüntüleme özelliği. Bu, Office Online Server yapılandırılarak gerçekleştirilir.
* Yeni Power BI tablo ve matris görselleri için destek.
* REST API desteği

## <a name="june-2017"></a>Haziran 2017
* Haziran 2017'de yeni öğe sunulmamıştır.

## <a name="may-2017"></a>Mayıs 2017
* Power BI Rapor Sunucusu'nda, yalnızca Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop ile oluşturulan Power BI raporları çalıştırılabilir. Bu sayfanın en üstündeki bağlantıyı kullanarak Power BI Desktop'ı indirebilirsiniz.
* Power BI Raporları yalnızca Analysis Services'e yönelik canlı bağlantıları (tablosal veya çok boyutlu) destekler.
* R görselleri desteklenmemektedir.

**Sorun ve müşteri etkisi:** Hem SQL Server Reporting Services hem de Power BI Rapor Sunucusu aynı makinede yüklüyse bunlardan birini kaldırmanız halinde, Rapor Sunucusu Yapılandırma Yöneticisi'ni kullanarak kalan rapor sunucusuna bağlanamazsınız.

**Geçici çözüm**: Bu sorunu geçici olarak çözmek için, sunuculardan birini kaldırdıktan sonra aşağıdaki işlemleri gerçekleştirmeniz gerekir.

1. Yönetici modunda komut istemi başlatın.
2. Kalan rapor sunucusunun yüklü olduğu dizine gidin.
   
    *Power BI Rapor Sunucusu'nun varsayılan konumu: C:\Program Files\Microsoft Power BI Report Server*
   
    *SQL Server Reporting Services'in varsayılan konumu: C:\Program Files\Microsoft SQL Server Reporting Services*
3. Ardından bir sonraki klasöre gidin. Kalan sunucuya bağlı olarak bu *SSRS* veya *PBIRS* olacaktır.
4. WMI klasörüne gidin.
5. Aşağıdaki komutu çalıştırın:
   
    ```
    regsvr32 /i ReportingServicesWMIProvider.dll
    ```
   
    Aşağıdaki hatayı alırsanız yok sayabilirsiniz.
   
    ```
    The module "ReportingServicesWMIProvider.dll" was loaded but the entry-point DLLInstall was not found. Make sure that "ReportingServicesWMIProvider.dll" is a valid DLL or OCX file and then try again.
    ```

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Rapor Sunucusu'ndaki yenilikler](whats-new.md)  
[Kullanıcı el kitabı](user-handbook-overview.md)  
[Yönetici el kitabı](admin-handbook-overview.md)  
[Quickstart: Install Power BI Report Server (Hızlı Başlangıç: Power BI Rapor Sunucusu'nu yükleme)](quickstart-install-report-server.md)  
[Install Report Builder (Rapor Oluşturucusu'nu yükleme)](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT) (SQL Server Veri Araçlarını (SSDT) indirme)](http://go.microsoft.com/fwlink/?LinkID=616714)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

