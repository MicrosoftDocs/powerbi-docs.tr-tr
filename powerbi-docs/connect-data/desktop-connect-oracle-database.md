---
title: Oracle veritabanlarına bağlanma
description: Power BI Desktop'tan Oracle veritabanlarına bağlanmak için gerçekleştirilmesi gereken işlemler ve indirmeler
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/05/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f43981121211c900b3cb4506b830ce09da3b5e20
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83295503"
---
# <a name="connect-to-an-oracle-database"></a>Oracle veritabanlarına bağlanma
Power BI Desktop'tan bir Oracle veritabanına bağlanmak için Power BI Desktop'ın çalıştığı bilgisayarda doğru Oracle istemci yazılımının yüklü olması gerekir. Kullandığınız Oracle istemci yazılımı, yüklediğiniz Power BI Desktop sürümüne göre değişiklik gösterir: 32 bit veya 64 bit.

Desteklenen Oracle sürümleri: 
- Oracle 9 ve üstü
- Oracle istemci yazılımı 8.1.7 ve üstü

> [!NOTE]
> Power BI Desktop, Şirket İçi Veri Ağ Geçidi veya Power BI Rapor Sunucusu için bir Oracle veritabanı yapılandırıyorsanız [Oracle Bağlantı Türü](https://docs.microsoft.com/sql/reporting-services/report-data/oracle-connection-type-ssrs?view=sql-server-ver15) makalesindeki bilgilere göz atın. 


## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Power BI Desktop'ın hangi sürümünün yüklü olduğunu belirleme
Power BI Desktop'ın hangi sürümünün yüklü olduğunu belirlemek için **Dosya** > **Yardım** > **Hakkında**'yı seçip **Sürüm** satırına bakın. Aşağıdaki resimde Power BI Desktop'ın 64 bit sürümü yüklüdür:

![Power BI Desktop sürümü](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Oracle istemcisini yükleme
- Power BI Desktop'ın 32 bit sürümü için [32 bit Oracle istemcisini indirip yükleyin](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html).

- Power BI Desktop'ın 64 bit sürümü için [64 bit Oracle istemcisini indirip yükleyin](https://www.oracle.com/database/technologies/odac-downloads.html).

> [!NOTE]
> Oracle istemcisinin kurulumu sırasında kurulum sihirbazında ilgili onay kutusunu seçerek *Makine düzeyinde ASP.NET için ODP.NET ve/veya Oracle Providers’ı yapılandır* seçeneğini etkinleştirdiğinizden emin olun. Oracle istemci sihirbazının bazı sürümlerinde onay kutusu varsayılan olarak seçilidir; bazılarında ise seçili değildir. Power BI’ın Oracle veritabanınıza bağlanabilmesi için onay kutusunun seçili olduğundan emin olun.

## <a name="connect-to-an-oracle-database"></a>Oracle veritabanlarına bağlanma
Gerekli Oracle istemci sürücüsünü yükledikten sonra Oracle veritabanına bağlanabilirsiniz. Bağlantı kurmak için aşağıdaki adımları uygulayın:

1. **Giriş** sekmesinde **Veri Al**'ı seçin. 

2. Görüntülenen **Veri Al** penceresinde **Diğer**'i seçin (gerekirse), **Veritabanı** > **Oracle veritabanı**'nı seçin ve sonra da **Bağlan**'ı seçin.
   
   ![Oracle veritabanına bağlanma](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. Görüntülenen **Oracle veritabanı** iletişim kutusuna **Sunucu** adını girip **Tamam**'ı seçin. SID gerekiyorsa şu biçimi kullanarak bu değeri belirtin: *SunucuAdı/SID*; burada *SID* veritabanının benzersiz adıdır. *SunucuAdı/SID* biçimi işe yaramıyorsa *SunucuAdı/HizmetAdı* biçimini kullanın. Burada *HizmetAdı* bağlanmak için kullandığınız diğer addır.


   ![Oracle sunucu adını girin](media/desktop-connect-oracle-database/connect-oracle-database_3.png)

   > [!TIP]
   > Bu adımda bağlanma ile ilgili bir sorun yaşıyorsanız **Sunucu** alanında aşağıdaki biçimi kullanmayı deneyin: *(DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=konak_adı)(PORT=bağlantı_noktası_numarası))(CONNECT_DATA=(SERVICE_NAME=hizmet_adı)))*
   
3. Yerel veritabanı sorgusu kullanarak verileri içeri aktarmak istiyorsanız sorgunuzu **SQL deyimi** kutusuna girin. Bu kutuya ulaşmak için **Oracle veritabanı** iletişim kutusunun **Gelişmiş seçenekler** bölümünü genişletmeniz gerekir.
   
   ![Gelişmiş seçenekleri genişletme](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. **Oracle veritabanı** iletişim kutusuna Oracle veritabanı bilgilerinizi (SID veya yerel veritabanı sorgusu gibi isteğe bağlı bilgiler dahil) girdikten sonra bağlanmak için **Tamam**'ı seçin.
5. Oracle veritabanı için veritabanı kullanıcısı kimlik bilgileri gerekiyorsa açılan iletişim kutusuna bu bilgileri girin.


## <a name="troubleshooting"></a>Sorun giderme

Power BI Desktop'ı Microsoft Store'dan indirdiyseniz, bir Oracle sürücü hatasından dolayı Oracle veritabanlarına bağlanamayabilirsiniz. Bu sorunla karşılaşırsanız, şu hata iletisi döndürülür: *Nesne başvurusu ayarlanmadı*. Sorunu gidermek için aşağıdakilerden adımlardan birini uygulayın:

* Power BI Desktop'ı Microsoft Store yerine [İndirme Merkezi](https://www.microsoft.com/download/details.aspx?id=58494)'nden indirin.

* Microsoft Store'daki sürümü kullanmak istiyorsanız, yerel bilgisayarınızda oraons.dll dosyasını _12.X.X\client_X_ klasöründen _12.X.X\client_X\bin_ klasörüne kopyalayın; burada _X_, sürüm ve dizin numaralarını gösterir.

Bir Oracle veritabanına bağlanırken Power BI Gateway’de *Nesne başvurusu ayarlanmadı* hata iletisini görürseniz, [Veri kaynağınızı yönetme - Oracle](service-gateway-onprem-manage-oracle.md) makalesindeki yönergeleri izleyin.

Power BI Rapor Sunucusu kullanıyorsanız [Oracle Bağlantı Türü](https://docs.microsoft.com/sql/reporting-services/report-data/oracle-connection-type-ssrs?view=sql-server-ver15) makalesindeki kılavuza göz atın.
