---
title: Power BI Rapor Sunucusu'nu yükseltme
description: Power BI Rapor Sunucusu'nu yükseltmeyi öğrenin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.custom: ''
ms.date: 09/22/2020
ms.openlocfilehash: 68494784e3c5b21c0c3e15bd5a3a816fd07e5f8b
ms.sourcegitcommit: 7ed995eed0fd6e718748accf87bae384211cd95d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2021
ms.locfileid: "99043563"
---
# <a name="upgrade-power-bi-report-server"></a>Power BI Rapor Sunucusu'nu yükseltme

Power BI Rapor Sunucusu'nu yükseltmeyi öğrenin.

 **İndirin** ![indirme simgesi](media/upgrade/download.png "indirme simgesi")

Power BI Rapor Sunucusu indirmek ve Power BI Rapor Sunucusu Power BI Desktop için, [Power BI rapor sunucusu ile şirket içi raporlamaya](https://powerbi.microsoft.com/report-server/)gidin.

## <a name="before-you-begin"></a>Başlamadan önce

Bir rapor sunucusunu yükseltmeden önce rapor sunucunuzu yedeklemek için aşağıdaki adımları uygulamanız önerilir.

### <a name="backing-up-the-encryption-keys"></a>Şifreleme anahtarlarını yedekleme

Bir rapor sunucusu yüklemesini ilk kez yapılandırırken, şifreleme anahtarlarını yedekleyin. Ayrıca hizmet hesaplarının kimliklerini her değiştirdiğinizde veya bilgisayarı her yeniden adlandırdığınızda da anahtarları yedekleyin. Daha fazla bilgi için bkz. [Reporting Services Şifreleme Anahtarlarını Yedekleme ve Geri Yükleme](/sql/reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys).

### <a name="backing-up-the-report-server-databases"></a>Rapor sunucusu veritabanlarını yedekleme

Rapor sunucusu durum bilgisi olmayan bir sunucu olduğundan, tüm uygulama verileri bir SQL Server Veritabanı Altyapısı örneğinde çalışan **reportserver** ve **reportservertempdb** veritabanlarında depolanır. SQL Server veritabanlarını yedeklemek için desteklenen yöntemlerden birini kullanarak **reportserver** ve **reportservertempdb** veritabanlarını yedekleyebilirsiniz. Bu öneriler rapor sunucusu veritabanlarına özeldir:

* **reportserver** veritabanını yedeklemek için tam kurtarma modelini kullanın.
* **reportservertempdb** veritabanını yedeklemek için basit kurtarma modelini kullanın.
* Her veritabanı için farklı yedekleme zamanlamaları kullanabilirsiniz. **reportservertempdb** veritabanının yedeklenmesinin tek nedeni, bir donanım arızası durumunda yeniden oluşturmak zorunda kalmamaktır. Donanım arızası durumunda **reportservertempdb** veritabanındaki verileri kurtarmanıza gerek yoktur ancak tablo yapısına ihtiyacınız olacaktır. **reportservertempdb** veritabanını kaybetmeniz durumunda geri almanın tek yolu, rapor sunucusu veritabanını yeniden oluşturmaktır. **reportservertempdb** veritabanının yeniden oluşturulacak olması durumunda, birincil rapor sunucusu veritabanıyla aynı ada sahip olması önemlidir.

SQL Server ilişkisel veritabanlarının yedeklenmesi ve kurtarılması hakkında daha fazla bilgi için bkz. [Back Up and Restore of SQL Server Databases (SQL Server Veritabanlarının Yedeklenmesi ve Geri Yüklenmesi)](/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases).

### <a name="backing-up-the-configuration-files"></a>Yapılandırma dosyalarını yedekleme

Power BI Rapor Sunucusu, uygulama ayarlarını depolamak için yapılandırma dosyalarını kullanır. Sunucuyu ilk kez yapılandırırken ve herhangi bir özel uzantıyı dağıtmanızın ardından dosyaları yedekleyin. Yedeklenecek dosyalar şunlardır:

* config.json
* RSHostingService.exe.config
* Rsreportserver.config
* Rssvrpolicy.config
* Reportingservicesservice.exe.config
* Rapor Sunucusu ASP.NET uygulamaları için web.config
* ASP.NET için machine.config

## <a name="upgrade-the-report-server"></a>Rapor sunucusunu yükseltme

Power BI Rapor Sunucusu'nu yükseltmek oldukça kolaydır. Dosyaları yüklemek için uygulamanız gereken yalnızca birkaç adım vardır.

1. PowerBIReportServer.exe dosyasını bulun ve yükleyiciyi başlatın.

2. **Upgrade Power BI Report Server** (Power BI Rapor Sunucusu'nu Yükselt) seçeneğini belirleyin.

    ![Power BI Rapor Sunucusu'nu yükseltme](media/upgrade/reportserver-upgrade1.png "Power BI Rapor Sunucusu'nu yükseltme")

3. Lisans hüküm ve koşullarını okuyup kabul ettikten sonra **Yükselt** seçeneğini belirleyin.

    ![Lisans sözleşmesi](media/upgrade/reportserver-upgrade-eula.png "Lisans sözleşmesi")

4. Yükseltme başarılı olduktan sonra Reporting Services Yapılandırma Yöneticisi'ni başlatmak için **Rapor Sunucusunu Yapılandır**'ı veya yükleyiciden çıkmak için **Kapat**'ı seçebilirsiniz.

    ![Yapılandırmayı yükseltme](media/upgrade/reportserver-upgrade-configure.png)

## <a name="enable-microsoft-update-security-fixes-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için Microsoft Update güvenlik düzeltmelerini etkinleştirme

Power BI Rapor Sunucusu, güvenlik düzeltmelerini Microsoft Update aracılığıyla alır. Bunları almak için Microsoft Update'i el ile etkinleştirmeniz gerekir.

1.  Etkinleştirmek istediğiniz bilgisayarda **Güncelleştirme ve güvenlik ayarları**'nın altında Windows Update'i açın.
2.  **Gelişmiş seçenekler**'i seçin.
3.  **Windows'u güncelleştirdiğinizde diğer Microsoft ürünleri için güncelleştirmeler alın** onay kutusunu seçin.

## <a name="upgrade-power-bi-desktop"></a>Power BI Desktop'ı yükseltme

Rapor sunucusunu yükselttikten sonra, tüm Power BI Rapor yazarlarının sunucu ile eşleşen Power BI Rapor Sunucusu Power BI Desktop sürümüne yükseltildiğinizden emin olun.

## <a name="next-steps"></a>Sonraki adımlar

* [Yönetici genel bakışı](admin-handbook-overview.md)  
* [Power BI Rapor Sunucusu için Power BI Desktop yüklemesi](install-powerbi-desktop.md)  
* [Reporting Services yüklemesini doğrulama](/sql/reporting-services/install-windows/verify-a-reporting-services-installation)  
* [Rapor sunucusu hizmet hesabını yapılandırma](/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager)  
* [Rapor sunucusu URL'lerini yapılandırma](/sql/reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager)  
* [Rapor sunucusu veritabanı bağlantısını yapılandırma](/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager)  
* [Bir rapor sunucusunu başlatma](/sql/reporting-services/install-windows/ssrs-encryption-keys-initialize-a-report-server)  
* [Rapor sunucusunda SSL bağlantılarını yapılandırma](/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server)  
* [Configure windows service accounts and permissions (Windows hizmet hesaplarını ve izinleri yapılandırma)](/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions)  
* [Power BI Rapor Sunucusu için tarayıcı desteği](browser-support.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)