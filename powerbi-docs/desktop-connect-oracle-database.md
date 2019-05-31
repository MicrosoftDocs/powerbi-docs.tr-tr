---
title: Oracle veritabanlarına bağlanma
description: Power BI Desktop'tan Oracle veritabanlarına bağlanmak için gerçekleştirilmesi gereken işlemler ve indirmeler
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/22/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b28c4ea9b4cacc77a7f98af5bfc006670f40af94
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61315028"
---
# <a name="connect-to-an-oracle-database"></a>Oracle veritabanlarına bağlanma
**Power BI Desktop**'tan bir Oracle veritabanına bağlanmak için Power BI Desktop'ın çalıştığı bilgisayarda doğru Oracle istemci yazılımının yüklü olması gerekir. Kullandığınız Oracle istemci yazılımı, yüklü Power BI Desktop sürümüne göre değişiklik gösterir: **32 bit** sürüm veya **64 bit** sürüm.

**Desteklenen sürümler**: Oracle 9 ve sonraki sürümler, Oracle istemci yazılımı 8.1.7 ve sonraki sürümler.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Power BI Desktop'ın hangi sürümünün yüklü olduğunu belirleme
Power BI Desktop’ın hangi sürümünün yüklü olduğunu belirlemek için **Dosya > Yardım > Hakkında**’yı seçip **Sürüm:** satırına bakın. Aşağıdaki resimde Power BI Desktop'ın 64 bit sürümü yüklüdür:

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Oracle istemcisini yükleme
Power BI Desktop'ın **32 bit** sürümü için, **32 bit** Oracle istemcisini indirip yüklemek amacıyla aşağıdaki bağlantıyı kullanın:

* [Oracle Developer Tools for Visual Studio (12.1.0.2.4) ile 32 bit Oracle Data Access Components (ODAC)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

Power BI Desktop'ın **64 bit** sürümü için, **64 bit** Oracle istemcisini indirip yüklemek üzere aşağıdaki bağlantıyı kullanın:

* [Windows x64 için 64 bit ODAC 12c Sürüm 4 (12.1.0.2.4)](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Oracle veritabanlarına bağlanma
Gerekli Oracle istemci sürücüsünü yükledikten sonra Oracle veritabanına bağlanabilirsiniz. Bağlantı kurmak için aşağıdaki adımları uygulayın:

1. Veri Al penceresinde **Veritabanı > Oracle Veritabanı**'nı seçin
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. Açılan **Oracle Veritabanı** iletişim kutusuna sunucu adını girip **Bağlan**'ı seçin. SID gerekiyorsa şu biçimi kullanarak belirtebilirsiniz: *SunucuAdı/SID*, burada SID veritabanının benzersiz adıdır. *SunucuAdı/SID* biçimi işe yaramıyorsa, HizmetAdı’nın bağlanırken kullanılan diğer ad olduğu *SunucuAdı/HizmetAdı*’nı kullanmayı deneyin.


   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)

   > [!TIP]
   > Bu adımda bağlanma ile ilgili bir sorun yaşıyorsanız Sunucu Adı alanında aşağıdaki biçimi kullanmayı deneyin: (DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=host_name)(PORT=port_num))(CONNECT_DATA=(SERVICE_NAME=service_name)))
   
3. Yerel veritabanı sorgusu kullanarak veri içeri aktarmak istiyorsanız sorgunuzu **SQL Deyimi** kutusuna girebilirsiniz. Bu kutuya ulaşmak için **Oracle Veritabanı** iletişim kutusunun **Gelişmiş seçenekler** bölümünü genişletmeniz gerekir.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. Oracle Veritabanı iletişim kutusuna Oracle veritabanı bilgilerini (SID veya yerel veritabanı sorgusu gibi isteğe bağlı bilgiler dahil) girdikten sonra bağlanmak için **Tamam**'ı seçin.
5. Oracle veritabanı için veritabanı kullanıcısı kimlik bilgileri gerekiyorsa açılan iletişim kutusuna bu bilgileri girin.


## <a name="troubleshooting"></a>Sorun giderme

Power BI Desktop'ı Microsoft Store'dan indirdiyseniz, bir Oracle sürücü hatasından dolayı Oracle veritabanlarına bağlanamayabilirsiniz. Bu sorunla karşılaşırsanız, "Nesne başvurusu ayarlanmadı" hata iletisi döndürülür. Sorunu gidermek için aşağıdakilerden birini yapın:

* Power BI Desktop'ı Store yerine https://powerbi.microsoft.com/desktop'dan indirin.

* Microsoft Store'daki sürümü kullanmak istiyorsanız, yerel bilgisayarınızda oraons.dll dosyasını _12.X.X\client_X_ klasöründen _12.X.X\client_X\bin_ klasörüne kopyalayın. Burada X, sürüm ve dizin numaralarını temsil eder.
