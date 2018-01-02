---
title: "Power BI Rapor Sunucusu'nu yüklemeye ilişkin Donanım ve Yazılım gereksinimleri"
description: "Bu makalede, Power BI Rapor Sunucusu'nu yüklemeye ve çalıştırmaya ilişkin minimum donanım ve yazılım gereksinimleri açıklanmaktadır."
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
ms.openlocfilehash: b9aff56a964a2a8c91d614a427ad77810680176f
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Power BI Rapor Sunucusu'nu yüklemeye ilişkin donanım ve yazılım gereksinimleri
Bu makalede, Power BI Rapor Sunucusu'nu yüklemeye ve çalıştırmaya ilişkin minimum donanım ve yazılım gereksinimleri açıklanmaktadır.

## <a name="processor-memory-and-operating-system-requirements"></a>İşlemci, Bellek ve İşletim Sistemi Gereksinimleri
| Bileşen | Gereksinim |
| --- | --- |
| .NET Framework |4.6<br><br>.NET Framework'ü [Windows için Microsoft .NET Framework 4.6 (Web Yükleyicisi)](http://support.microsoft.com/kb/3045560) sayfasından elle yükleyebilirsiniz.<br/><br/> NET Framework 4.6 ile ilgili daha fazla bilgi, öneri ve yardım için bkz. [Geliştiriciler için .NET Framework Dağıtım Kılavuzu](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).<br/><br/>Windows 8.1 ve Windows Server 2012 R2 için .NET Framework 4.6 yüklemesinden önce [KB2919355](http://support.microsoft.com/kb/2919355) güncelleştirmesinin yapılması gerekir. |
| Sabit Disk |Power BI Rapor Sunucusu için en az 1 GB'lık kullanılabilir sabit disk alanı gerekir.<br><br>Rapor sunucusu veritabanını barındıran veritabanı sunucusunda da ek alan gerekir. |
| Bellek |**Minimum:** 1 GB<br/><br/> **Önerilen:** En az 4 GB |
| İşlemci hızı |**En az:** x64 İşlemci: 1,4 GHz<br/><br/> **Önerilen:** 2,0 GHz veya daha yüksek |
| İşlemci türü |x64 İşlemci: AMD Opteron, AMD Athlon 64, Intel EM64T destekli Intel Xeon, EM64T destekli Intel Pentium IV |
| İşletim sistemi |Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br><br>Windows 8.1<br><br>Windows 8.1 Pro<br><br>Windows 8.1 Enterprise<br><br>Windows 8<br><br>Windows 8 Pro<br><br>Windows 8 Enterprise |

> [!NOTE]
> Power BI Rapor Sunucusu yüklemesi yalnızca x64 işlemcilerde desteklenir.
> 
> 

## <a name="database-server-version-requirements"></a>Veritabanı sunucusu sürüm gereksinimleri
Rapor sunucusu veritabanlarını barındırmak için SQL Server kullanılır. SQL Server Veritabanı Altyapısı örneği yerel veya uzak bir örnek olabilir. Rapor sunucusu veritabanlarını barındırmak için kullanılabilecek SQL Server Veritabanı Altyapısı'nın desteklenen sürümleri şunlardır:

* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012
* SQL Server 2008 R2
* SQL Server 2008

Rapor sunucusu veritabanını uzak bir bilgisayarda oluşturmak için bağlantıyı, ağ erişimi olan bir hizmet hesabı veya bir etki alanı kullanıcısı hesabı kullanacak şekilde yapılandırmanız gerekir. Uzak bir SQL Server örneği kullanacaksanız rapor sunucusunun, SQL Server örneğine bağlanmak için hangi kimlik bilgilerini kullanması gerektiğini dikkatli bir şekilde değerlendirin. Daha fazla bilgi için bkz. [Rapor Sunucusu Veritabanı Bağlantısını yapılandırma](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager).

## <a name="considerations"></a>Önemli noktalar
Power BI Rapor Sunucusu, bir rapor sunucusunu işlevsel hale getirmek için gereken temel ayarları yapılandırmak üzere varsayılan değerleri yükler. Aşağıdaki gereksinimler yerine getirilmelidir:

* Kurulumdan sonra, veritabanını rapor sunucusu için yapılandırmadan önce bir SQL Server Veritabanı Altyapısı kullanılabilir durumda olmalıdır. Veritabanı Altyapısı örneği, Reporting Services Yapılandırma Yöneticisi'nin oluşturacağı rapor sunucusu veritabanını barındırmalıdır. Veritabanı Altyapısı, asıl kurulum işlemi için gerekli değildir.
* Kurulumu çalıştırmak için kullanılan kullanıcı hesabı, yerel Yöneticiler grubunun bir üyesi olmalıdır.
* Reporting Services Yapılandırma Yöneticisi için kullanılan kullanıcı hesabı, rapor sunucusu veritabanlarını barındıran Veritabanı Altyapısındaki veritabanlarına erişme ve burada veritabanı oluşturma iznine sahip olmalıdır.
* Kurulumda, rapor sunucusuna ve web portalına erişim sağlayan URL'leri ayırmak için varsayılan değerler kullanılabilmelidir. Bu değerler; 80 numaralı bağlantı noktası, güçlü bir joker karakter ve **ReportServer** ile **Reports** biçimindeki sanal dizin adlarıdır.

## <a name="read-only-domain-controller-rodc"></a>Salt okunur etki alanı denetleyicisi (RODC)
 Rapor sunucusu, Salt Okunur Etki Alanı Denetleyicisine (RODC) sahip bir ortama yüklenebilse de Reporting Services, düzgün şekilde çalışmak için bir Okuma-Yazma Etki Alanı Denetleyicisi erişimine ihtiyaç duyar. Reporting Services yalnızca RODC erişimine sahipse hizmeti yönetmeye çalışırken hatalarla karşılaşabilirsiniz.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Power BI raporları ve Analysis Services canlı bağlantıları
Tablolu veya çok boyutlu örnekler için bir canlı bağlantı kullanabilirsiniz. Analysis Services sunucunuzun düzgün şekilde çalışması için doğru sürümünün yüklü olması gerekir.

| **Sunucu sürümü** | **Gerekli SKU** |
| --- | --- |
| 2012 SP1 CU4 veya sonraki sürümleri |İş Zekası ve Enterprise SKU'su |
| 2014 |İş Zekası ve Enterprise SKU'su |
| 2016 ve sonraki sürümleri |Standart SKU veya sonraki sürümleri |

## <a name="next-steps"></a>Sonraki adımlar
[Kullanıcı el kitabı](user-handbook-overview.md)  
[Yönetici el kitabı](admin-handbook-overview.md)  
[Quickstart: Install Power BI Report Server (Hızlı Başlangıç: Power BI Rapor Sunucusu'nu yükleme)](quickstart-install-report-server.md)  
[Install Report Builder (Rapor Oluşturucusu'nu yükleme)](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT) (SQL Server Veri Araçlarını (SSDT) indirme)](http://go.microsoft.com/fwlink/?LinkID=616714)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
