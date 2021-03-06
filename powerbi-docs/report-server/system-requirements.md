---
title: Power BI Rapor Sunucusu'nu yüklemeye ilişkin donanım ve yazılım gereksinimleri
description: Bu makalede, Power BI Rapor Sunucusu'nu yüklemeye ve çalıştırmaya ilişkin minimum donanım ve yazılım gereksinimleri açıklanmaktadır.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 12/07/2020
ms.openlocfilehash: 10fb104d1c03ae5d08836b8e865178c347d848ce
ms.sourcegitcommit: 0bf42b6393cab7a37d21a52b934539cf300a08e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2020
ms.locfileid: "96781785"
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Power BI Rapor Sunucusu'nu yüklemeye ilişkin donanım ve yazılım gereksinimleri

Bu makalede, Power BI Rapor Sunucusu'nu yüklemeye ve çalıştırmaya ilişkin minimum donanım ve yazılım gereksinimleri açıklanmaktadır.

## <a name="processor-memory-and-operating-system-requirements"></a>İşlemci, Bellek ve İşletim Sistemi Gereksinimleri

| Bileşen | Gereksinim |
| --- | --- |
| .NET Framework |4.8<br><br>Sunucuda internet erişimi yoksa .NET Framework’ü [Windows için Microsoft .NET Framework 4.8 (Çevrimdışı Yükleyici)](https://support.microsoft.com/en-us/help/4503548/) sayfasından el ile yükleyebilirsiniz.<br/><br/> NET Framework 4.8 ile ilgili daha fazla bilgi, öneri ve yardım için bkz. [Geliştiriciler için .NET Framework Dağıtım Kılavuzu](/dotnet/framework/deployment/deployment-guide-for-developers).<br/><br/>Windows 8.1 ve Windows Server 2012 R2 için .NET Framework 4.8 yüklemesinden önce [KB2919355](https://support.microsoft.com/kb/2919355) güncelleştirmesinin yapılması gerekir. |
| Sabit Disk |Power BI Rapor Sunucusu için en az 1 GB'lık kullanılabilir sabit disk alanı gerekir.<br><br>Rapor sunucusu veritabanını barındıran veritabanı sunucusunda da ek alan gerekir. |
| Bellek |**Minimum:** 1 GB<br/><br/> **Önerilen:** En az 4 GB |
| İşlemci hızı |**En az:** x64 İşlemci: 1,4 GHz<br/><br/> **Önerilen:** 2,0 GHz veya daha yüksek |
| İşlemci türü |x64 İşlemci: AMD Opteron, AMD Athlon 64, Intel EM64T destekli Intel Xeon, EM64T destekli Intel Pentium IV |
| İşletim sistemi |Windows Server 2019 Datacenter<br><br>Windows Server 2019 Standard<br><br>Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br> |

> [!NOTE]
> Power BI Rapor Sunucusu yüklemesi yalnızca x64 işlemcilerde desteklenir.


## <a name="database-server-version-requirements"></a>Veritabanı sunucusu sürüm gereksinimleri

Rapor sunucusu veritabanlarını barındırmak için SQL Server kullanılır. SQL Server Veritabanı Altyapısı örneği yerel veya uzak bir örnek olabilir. Rapor sunucusu veritabanlarını barındırmak için kullanılabilecek SQL Server Veritabanı Altyapısı'nın desteklenen sürümleri şunlardır:

* Azure SQL Yönetilen Örneği (Power BI Rapor Sunucusu Ocak 2020 sürümü ve üzeri)
* SQL Server 2019
* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012

Rapor sunucusu veritabanını uzak bir bilgisayarda oluşturduğunuzda, bir etki alanı kullanıcı hesabı ya da ağ erişimi olan bir hizmet hesabı kullanacak şekilde yapılandırmanız gerekir. Uzak bir SQL Server örneği kullanacaksanız rapor sunucusunun, SQL Server örneğine bağlanmak için hangi kimlik bilgilerini kullanması gerektiğini dikkatli bir şekilde değerlendirin. Daha fazla bilgi için bkz. [Rapor Sunucusu Veritabanı Bağlantısını yapılandırma](/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager).

## <a name="considerations"></a>Dikkat edilmesi gerekenler

Power BI Rapor Sunucusu, bir rapor sunucusunu işlevsel hale getirmek için gereken temel ayarları yapılandırmak üzere varsayılan değerleri yükler. Aşağıdaki gereksinimler yerine getirilmelidir:

* Power BI Rapor Sunucusu için desteklenen diller şunlardır: İngilizce, Almanca, İspanyolca, Japonca, İtalyanca, Fransızca, Rusça, Basitleştirilmiş Çince, Geleneksel Çince, Portekizce (Brezilya), Korece
* Kurulumdan sonra, veritabanını rapor sunucusu için yapılandırmadan önce bir SQL Server Veritabanı Altyapısı kullanılabilir durumda olmalıdır. Veritabanı Altyapısı örneği, Reporting Services Yapılandırma Yöneticisi'nin oluşturacağı rapor sunucusu veritabanını barındırmalıdır. Veritabanı Altyapısı, asıl kurulum işlemi için gerekli değildir.
* [SQL Server Sürümleri Tarafından Desteklenen Reporting Services Özellikleri](/sql/reporting-services/reporting-services-features-supported-by-the-editions-of-sql-server-2016) makalesinde, SQL Server sürümleri arasındaki farklılıklar özetlenmektedir.
* Kurulumu çalıştıran kullanıcı hesabı, yerel Yöneticiler grubunun bir üyesi olmalıdır.
* Reporting Services Yapılandırma Yöneticisi’ni çalıştıran kullanıcı hesabı, rapor sunucusu veritabanlarını barındıran Veritabanı Altyapısındaki veritabanlarına erişme ve burada veritabanı oluşturma iznine sahip olmalıdır.
* Kurulumda, rapor sunucusuna ve web portalına erişim sağlayan URL'leri ayırmak için varsayılan değerler kullanılabilmelidir. Bu değerler; 80 numaralı bağlantı noktası, güçlü bir joker karakter ve **ReportServer** ile **Reports** biçimindeki sanal dizin adlarıdır.

## <a name="read-only-domain-controller-rodc"></a>Salt okunur etki alanı denetleyicisi (RODC)

 Rapor sunucusunu Salt Okunur Etki Alanı Denetleyicisi (RODC) olan bir ortama yükleyebilirsiniz. Ancak, Reporting Services’in düzgün çalışması için bir Okuma-Yazma Etki Alanı Denetleyicisine erişimi olmalıdır. Reporting Services yalnızca RODC erişimine sahipse hizmeti yönetmeye çalışırken hatalarla karşılaşabilirsiniz.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Power BI raporları ve Analysis Services canlı bağlantıları

Tablolu veya çok boyutlu örnekler için bir canlı bağlantı kullanabilirsiniz. Analysis Services sunucunuzun düzgün şekilde çalışması için doğru sürümünün yüklü olması gerekir.

| **Sunucu sürümü** | **Gerekli SKU** |
| --- | --- |
| 2012 SP1 CU4 veya sonraki sürümler |İş Zekası ve Enterprise SKU'su |
| 2014 |İş Zekası ve Enterprise SKU'su |
| 2016 ve sonraki sürümleri |Standart SKU veya sonraki sürümleri |

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Rapor Sunucusu nedir?](get-started.md)  
[Yönetici genel bakışı](admin-handbook-overview.md)  
[Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)  
[Rapor Oluşturucusu’nu indirme](https://www.microsoft.com/download/details.aspx?id=53613)  
[Download SQL Server Data Tools (SSDT) (SQL Server Veri Araçlarını (SSDT) indirme)](/sql/ssdt/download-sql-server-data-tools-ssdt)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
