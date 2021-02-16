---
title: Power BI Rapor Sunucusu’na yönelik değişiklik günlüğü
description: Power BI Rapor Sunucusu'na yönelik bu değişiklik günlüğünde yeni öğelerin yanı sıra yayımlanan her bir derlemeye ilişkin hata düzeltmeleri yer alır.
author: jtarquino
ms.author: jaimeta
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 02/11/2021
ms.openlocfilehash: 768e0e8a360c2434fdb66cf309d24857707b9d59
ms.sourcegitcommit: 00e3eb2ec4f18d48a73cfd020bb42d08e859ad06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2021
ms.locfileid: "100531597"
---
# <a name="change-log-for-power-bi-report-server"></a>Power BI Rapor Sunucusu’na yönelik değişiklik günlüğü

Power BI Rapor Sunucusu'na yönelik bu değişiklik günlüğünde yeni öğelerin yanı sıra yayımlanan her bir derlemeye ilişkin hata düzeltmeleri yer alır.

Yeni özellikler hakkında daha fazla bilgi için bkz. [Power BI Rapor Sunucusu’ndaki yenilikler](whats-new.md). 


## <a name="january-2021"></a>Ocak 2021
- **Power BI Rapor Sunucusu**
    - *Sürüm: 1.10.7698.27886 (derleme 15.0.1105.195), Yayın tarihi: 28 Ocak 2021*
        - Özellikler
            - Yeni simgeler Power BI ve Power BI raporlara yeniden yapılır.
            - Yayın sürümü 3.5.0 ile gönderilen özel Visual API
            - Yeni Portal önizleme deneyimi, ReportServer kataloğunun ConfigurationInfo tablosundaki ' UsePortalV2 ' Özellik anahtarının arkasına eklendi.
        - Hata düzeltmeleri
            - Gelişmiş model meta verilerini kullanan belirli modellerle Power BI raporlarının Zamanlanmış olarak yenilenmesi ile ilgili sorun düzeltildi.
            - Portalda veri odaklı abonelikler düzenlenirken sorun düzeltildi.
        - Güvenlik güncelleştirmeleri

- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
   - *Sürüm: 2.88.1382.0 (ocak 2021), Yayın tarihi: 28 ocak 2021* (yeni derleme ve yeni sürüm)
        - Power BI Rapor Sunucusu bağlantı için gereken değişiklikleri içerir (Ocak 2021)        
   
## <a name="october-2020"></a>Ekim 2020
- **Power BI Rapor Sunucusu**
    - *Sürüm: 1.9.7675.15620 (Derleme 15.0.1104.300), Yayın Tarihi: 8 Ocak 2021*
        - Hata düzeltmeleri
            - Yalnızca küçük/büyük harflerin farklı olduğu iki veya daha fazla veri kaynağına sahip olan raporların yenilenmesiyle ilgili sorun düzeltildi.
            - Belirli iç içe birleştirme kombinasyonlarına sahip raporların yenilenmesiyle ilgili sorun düzeltildi.
    - *Sürüm: 1.9.7627.11028 (Derleme 15.0.1104.264), Yayın Tarihi: 18 Kasım 2020*
        - Hata düzeltmeleri
            - Kullanıcıların portal aracılığıyla site ayarlarındaki alanları değiştirmesini engelleyen sorun düzeltildi.
            - "EnterData" veri kaynağı kullanılırken Power BI raporlarının yenilenmesiyle ilgili sorun düzeltildi.
            - Gelişmiş veri kümesi meta verileri kullanan bazı modellerin yenilenmesiyle ilgili soru düzeltildi.
            - Bazı Power BI raporlarının Rapor Sunucusu'na yayımlanmasına engel olan sorun düzeltildi.
    - *Sürüm: 1.9.7604.41261 (Derleme 15.0.1104.239), Yayın Tarihi: 27 Ekim 2020*
         - Özellikler
            - Power BI Rapor Sunucusu’ndaki gelişmiş veri kümesi meta verilerine yönelik destek kullanıma sunuldu.
            - DirectQuery ve yenilemeye yönelik Power BI raporlarının bağlantılarını güncelleştirme özelliği eklendi. (Diğer bilgiler için bkz. [Veri kaynağı bağlantı dizelerini değiştirme](./connect-data-source-apis.md).)
        - Güvenlik güncelleştirmeleri
        - Hata düzeltmeleri
            - Kullanıcıların Power BI rapor yenileme zamanlamalarını değiştirmelerini engelleyen bir sorun düzeltildi.
            - Kimlik bilgilerinin süresi dolduğunda, kullanıcıların raporları yönetirken aldıkları kafa karıştırıcı hata iletileri düzeltildi.
            - Adında nokta bulunan raporların dışarı aktarılmasıyla ilgili bir sorun düzeltildi.
            - Tablix’teki ekran okuyucusu sorunları düzeltildi.
            - Günlük dosyalarının bazı durumlarda boş olmasıyla ilgili bir sorun düzeltildi.
            - Karşıya yükleme sırasında Excel dosyasının üzerine yazılmasıyla ilgili sorun düzeltildi.
            - Model.UpdateCacheSnapshot REST API yöntemiyle ilgili sorun düzeltildi.
            - XMLA yoluyla SAP BW veri kaynağı bağlantıları ile ilgili sorun düzeltildi.
            - “Power BI’a bağlan” iletişim kutusuyla ilgili bir sorun düzeltildi.
            - CustomHeaders gelişmiş özelliğinin varsayılan değeriyle ilgili sorun düzeltildi.
            - MHTML işleyicisi, daha yeni HTML DOCTYPE’ı kullanacak şekilde güncelleştirildi.

- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
   - *Sürüm: 2.86.1321.0 (Ekim 2020), Yayın tarihi: 18 Kasım 2020*
        - Hata düzeltmeleri
   - *Sürüm: 2.86.961.0 (Ekim 2020), Yayın Tarihi: 27 Ekim 2020* (yeni derleme ve yeni sürüm)
        - Power BI Rapor Sunucusu bağlantısı için gerekli değişiklikleri içerir (Ekim 2020)        
   
## <a name="may-2020"></a>Mayıs 2020
- **Power BI Rapor Sunucusu**
    - *Sürüm: 1.8.7485.35104 (Derleme 15.0.1103.234), Yayın Tarihi: 30 Haziran 2020*
        - Hata düzeltmeleri
            - Ölçeği genişletme senaryolarındaki, karşıya yüklendikten sonra raporların düzenlemeleri sunucuda hemen yansıtmamasıyla ilgili bir sorun düzeltildi.
    - *Sürüm: 1.8.7468.41510 (Derleme 15.0.1103.232), Yayın Tarihi: 15 Haziran 2020*
        - Hata düzeltmeleri
            - Karşıya yüklendikten sonra raporların düzenlemeleri sunucuda hemen yansıtmamasıyla ilgili bir sorun düzeltildi.
            - Sorguları birleştirmek için benzer eşleşme kullanıldığında yenilemenin başarısız olmasıyla ilgili bir sorun düzeltildi.
    - *Sürüm: 1.8.7450.37410 (Derleme 15.0.1103.227), Yayın Tarihi: 27 Mayıs 2020*
         - Özellikler
            -  Özelleştirilebilir katalog bağlantı havuzu boyutu için destek eklendi. (Daha fazla bilgi için bkz. [MaxCatalogConnectionPoolSizePerProcess ayarı](/sql/reporting-services/report-server/rsreportserver-config-configuration-file#bkmk_service).)
            -  Yenileme işlemi sırasında rapor görüntüleme davranışı iyileştirildi.
        - Güvenlik güncelleştirmeleri
        - Hata düzeltmeleri
            - Klasör ve rapor adlarındaki tek tırnak işaretleriyle ilgili iki sorun düzeltildi.
            - Belirli tarayıcılarla yatay kaydırmaya ve Kayıtları Gör özelliğine ilişkin bir sorun düzeltildi.
            - Temeldeki modelde şema hatalarına sebep olabilen, rapor açıkken zamanlanan yenileme işlemiyle ilgili bir sorun düzeltildi.
            - PDF dışarı aktarmasının alternatif metninin çok baytlı karakterler için doğru bir şekilde kodlanmamasıyla ilgili bir sorun düzeltildi.
            - LoadReport’u yürüten özel uygulamaların hatalı bir şekilde TrustedHeader hatası almasıyla ilgili bir sorun düzeltildi.
            - Zamanlanan yenilemenin ağır yükünün başarısız yenilemelere neden olmasıyla ilgili bir sorun düzeltildi.
            - Rapor adı klasör adıyla eşleştiğinde raporların yanlış konuma kaydedilmesiyle ilgili bir sorun düzeltildi.
            - Belge Haritası’ndaki sekme sorunları düzeltildi.
            - DAX sorguları kullandıklarında veri temelli aboneliklerin başarısız olmasıyla ilgili bir sorun düzeltildi.
            - URL erişimi sırasında FindString’in eşleşmelerin yerini bulamamasıyla ilgili bir sorun düzeltildi.
            - Raporlar taşındığında ekli veri kaynaklarını bozan bir sorun düzeltildi.
            - Zamanlanan yenilemenin belirli veri kaynakları için başarısız olmasına neden olan bir sorun düzeltildi.
            - Geçersiz isteklere yönelik fırsatları azaltmak için rapor zamanlamaya doğrulama aşaması eklendi.


- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
   - *Sürüm: 2.81.5831.1181 (Mayıs 2020), Yayınlanma tarihi: 9 Haziran 2020*
        - Hata Düzeltmesi
           -  Market görselleri için düzeltme
   - *Sürüm: 2.81.5831.941 (Mayıs 2020), Yayınlama tarihi: 27 Temmuz 2020* (yeni derleme ve yeni sürüm)
        - Power BI Rapor Sunucusu bağlantısı için gerekli değişiklikleri içerir (Mayıs 2020)        
   
## <a name="january-2020"></a>Ocak 2020
- **Power BI Rapor Sunucusu**
    - *Sürüm: 1.6.7364.4075 (Derleme 15.0.1102.777), Yayın Tarihi: 2 Mart 2020*
         - Hata Düzeltmeleri
           -  Belirli veri kaynakları için karşıdan yükleyemeyen Power BI raporları düzeltmesi
           -  Portaldan Power BI Rapor Sunucusu Masaüstü bağlantısı indirme konumu düzeltmesi
           -  Excel işlemesi için DynamicImageDPI düzeltmesi
           -  Çok kullanıcılı bazı senaryolarda yanlış iş parçacığı kültürü kullanan Oracle bağlantıları düzeltmesi (daha fazla bilgi için bkz. [UseInstalledUICulture belgeleri](./connect-data-sources.md))
           -  Rapor ekleme işleminde hatalara neden olan CustomHeaders varsayılan değerinin düzeltmesi
           -  Bazı durumlarda yanlış oluşturulan SQL parametre adlarının düzeltmesi
    - *Sürüm: 1.6.7327.3007 (Derleme 15.0.1102.759), Yayın Tarihi: 23 Ocak 2020*
         - Özellikler
            -  Power BI raporlarından Excel’e aktarma.
           -  Sayfalandırılmış raporlar için Power BI Premium veri kümesi desteği.
           -  Sayfalandırılmış rapor öğeleri için AltText (alternatif metin) desteği.
           -  Özel üst bilgiler için destek.
           -  Katalog olarak Azure SQL Yönetilen Örnekler için destek.
           -  Katalog için Saydam Veritabanı Şifrelemesi.
        - Güvenlik güncelleştirmeleri
        - Hata düzeltmeleri
            - Ekran okuyucuların erişilebilirliği, rapor işleme ve klavye gezintisiyle ilgili düzeltmeler.
            - Çok baytlık Rapor başlıklarını kaydetme düzeltmesi.
            - Rapor sunucusunun güvenilirliğini etkileyen ayrıntılı günlük için düzeltme.
          - Mobil cihaz üzerindeki Power BI raporlarında canlı veriler sağlama düzeltmesi.
          - Power BI raporlarını filtrelenmiş dışarı aktarma işleminde görseller arasında çapraz vurgulama uygulama düzeltmesi.
          - Sayfalandırılmış raporlarda görünürlük için ifade kullanarak Word’e aktarırken alt bilgi yazma düzeltmesi. 
     
- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
    - *Sürüm: 2.76.5678.1521 (Ocak 2020), Yayın Tarihi: 23 Ocak 2020* (yeni derleme ve yeni sürüm)
        - Power BI Rapor Sunucusu bağlantısı için gerekli değişiklikleri içeriyor (Ocak 2020)        


## <a name="september-2019"></a>Eylül 2019
- **Power BI Rapor Sunucusu**
    - *Sürüm: 1.6.7236.4246 (Derleme 15.0.1102.646), Yayın Tarihi: 25 Ekim 2019*
        - Güvenlik güncelleştirmeleri
        - Hata düzeltmeleri
            - .Net Framework 4.7 düzeltmesi yüklenmedi.
            - 110083 hatası ile çoklu değer parametrelerine sahip Teradata için sayfalandırılmış raporların düzeltilmesi.
            - Birden çok web hizmeti URL bağlaması varsa ve bunlardan biri https://+80/reportserver ise URLRoot değeri çalışmıyor sorununun düzeltilmesi.
          - Rapor alanının dışında gösterilen sayfalandırılmış raporların çok değerli parametresi için düzeltme.
          
    - *Sürüm: 1.6.7221.30698 (Derleme 15.0.1102.620), Yayınlanma Tarihi: 9 Ekim 2019*
        - Hata düzeltmeleri
            - Metin Filtresi özel görseli için düzeltme.
            - Açılır liste dilimleyicilerinin performansıyla ilgili bir sorun düzeltildi.
            - Telemetriden Şerit PII için düzeltme.
          - URL’lerin büyük/küçük harfe duyarlı olmaması için düzeltme.
          
    - *Sürüm 1.6.7206.38019 (Derleme 15.0.1102.597), Yayınlanma tarihi: 26 Eylül 2019*
        - Güvenlik güncelleştirmeleri
        - Hata düzeltmeleri
           - Sayfalandırılmış raporlar
             - Internet Explorer ve Microsoft Edge kullanılırken karşılaşılan erişilebilirlik sorunlarıyla ilgili çözüm.
             - Bağlantıyı test ederken karşılaşılan SAP HANA sorunlarıyla ilgili çözüm.
             - E-posta adresleri listesi sağlanırken bulunan sorunlar için çözüm.
             - DirectQuery veri kaynağı ve tümleşik kimlik doğrulaması kullanan Power BI raporları için çözüm.
             - Anlık görüntü etkinleştirildiğinde Sayfalandırılmış raporların filtre parametreleriyle işlenmesine yönelik çözüm.
             - Rapor yürütme sırasında saklı yordamların çift yürütülmesine yönelik çözüm.
             - Özel hizmet hesabı Power BI Rapor Sunucusu’nu çalıştıracak şekilde yapılandırıldığında varsayılan hizmet hesabına SQL Server oturum açma izinlerinin verilmesiyle ilgili çözüm.
             - Japonca saat diliminde yenileme sırasında modellere erişimle ilgili çözüm.
             - Yenileme sırasında raporun yeni bir sürümü karşıya yüklendiğinde eski modeller için çözüm.
             - '&' karakterini içeren parametre değerlerine yönelik çözüm.
         - Programlama
             - Web API: /PowerBIReports({Id})/DataSources (PATCH), bağlantı dizesi güncelleştirmelerine izin verecek şekilde güncelleştirildi.
         
- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
    - *Sürüm: 2.73.5586.1501 (Eylül 2019), Yayın Tarihi: 25 Ekim 2019*
        - Hata düzeltmeleri
            - Telemetri çözümü.
            
    - *Sürüm: 2.73.5586.1241 (Eylül 2019), Yayınlanma Tarihi: 9 Ekim 2019*
        - Hata düzeltmeleri
            - Metin Filtresi özel görseli için düzeltme.
            - Açılır liste dilimleyicilerinin performansı için düzeltme.
            - Telemetriden Şerit PII için düzeltme.
            
    - *Sürüm: 2.73.5586.821 (Eylül 2019), Yayınlanma tarihi: 26 Eylül 2019* (yeni derleme ve yeni sürüm)
        - Power BI Rapor Sunucusu bağlantısı için gerekli değişiklikleri içeriyor (Eylül 2019)

    
## <a name="may-2019"></a>Mayıs 2019

- **Power BI Rapor Sunucusu**          
    - *Sürüm 1.5.7074.36177 (Derleme 15.0.1102.371), Yayınlanma tarihi: 21 Mayıs 2019*
        - Hata Düzeltmeleri
            - Sayfalandırılmış Raporlar
                - PDF yazı tipi eklemeyi her zaman etkinleştirme hatası düzeltildi.
                - Https üzerinden gönderilen tanımlama bilgilerinin Güvenli olarak ayarlanması sorunu düzeltildi
                - Betik hatalarından dolayı açılan listelerdeki sorunlar düzeltildi
                - Android telefonlarda Mobil Uygulama ile ilgili görüntü sorunları düzeltildi
                - Mali yılın başlangıcından bağımsız olarak Mobil Rapor Zaman Gezgini'nde doğru hafta numaralarının gösterilmesi için düzeltme yapıldı
                - Yöneticilerin yasaklanmış mime türlerini belirtmesi için 'RestrictedResourceMimeTypeForUpload' yapılandırılabilir özelliği eklendi
         - Özellikler
            - PBIRS'e Güvenilen Görseller için destek eklendi

- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
    - *Sürüm: 2.69.5467.1801 (Mayıs 2019), Yayınlama tarihi: 21 Mayıs 2019*
        - Hata düzeltmeleri
            - PBIRS'ye PBIX yüklenirken kimlik bilgilerinin yeniden girilmesini önleyecek düzeltme yapıldı
            - Dosya adında # bulunan belgeleri açma sorunu düzeltildi
            - PBIRS Seçim penceresinde geriye doğru gezinti için daha kolay bir bağlantı eklendi
            - PBIRS'de Geri düğmesini görüntülemek, uyarı görsel iletilerini göstermek için Yüksek Karşıtlık modu düzeltildi.
            - Seçim bölmesi, tuval ölçeklendirme için kullanıcı arabirimi düzeltildi.

    - *Sürüm: 2.69.5467.5201 (Mayıs 2019), Yayınlama tarihi: 30 Temmuz 2019*
        - Hata düzeltmeleri
            - Yanlış telemetri günlüğü için düzeltme

## <a name="january-2019"></a>Ocak 2019

- **Power BI Rapor Sunucusu**          
    - *Sürüm 1.4.7024.16477 (Derleme 15.0.1102.299), Yayınlanma tarihi: 28 Mart 2019*
        - Hata Düzeltmeleri
            - Power BI Raporları
                - SAP Hana ve SAP BW için doğrudan sorgu kullanılırken temel kimlik bilgileriyle ilgili sorun düzeltildi
                - "Microsoft.OData.Core.NetFX35.V7 dosyası veya bütünleştirilmiş kodu yüklenemedi" hatası ile başarısız olan OData akışı veri yenilemesi düzeltildi

- **Power BI Rapor Sunucusu**            
    - *Sürüm 1.4.6969.7395 (Derleme 15.0.1102.235), Yayın Tarihi: 30 Ocak 2019*
        - Hata Düzeltmeleri
            - Power BI Raporları
                - Doğrudan sorgu kullanılırken temel kimlik bilgileriyle ilgili sorun düzeltildi
                - Satır düzeyi güvenlik filtreleri uygulanmış durumdayken çift yönlü ilişkiler düzeltildi
                - Ölçeği genişletilen bir ortamda model yenileme sonrasında eski veriler düzeltildi
                - Firefox 63+ üzerinde tablo/matris için çift kaydırma çubuğu düzeltildi
                - Internet Explorer'da +/- simge boyutu düzeltildi
            - Sayfalandırılmış Raporlar
                - Rapor için paylaşılan veri kaynağının kullanımını güncelleştirmeyle ilgili sorun düzeltildi

    - *Sürüm 1.4.6960.38798 (Derleme 15.0.1102.222), Yayın Tarihi: 22 Ocak 2019*
        - Özellikler
            - Power BI Raporları 
                - Satır düzeyi güvenlik desteği
                - Matris satır üst bilgilerini genişletme ve daraltma
                - .pbix dosyaları arasında kopyalama ve yapıştırma
                - Akıllı hizalama kılavuzları
                - SAP BW 2.0 Bağlayıcısı desteği
            - Yöneticiler
                - Rapor sunucusuna yüklenebilecek kaynakların uzantılarını kısıtlayabilme
                - Desteklenen köprü şemalarını kısıtlayabilme
            - Programlama
                - Yeni Web API'si: /PowerBIReports({Id})/DataModelRoles (GET)
                - Yeni Web API'si: /PowerBIReports({Id})/DataModelRoleAssignments (GET & PUT)
                - Diğer ayrıntılar için bkz. [Power BI Rapor Sunucusu REST API'si](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0)
        - Hata Düzeltmeleri
            - HTML Eklemeye İlişkin Güvenlik Açığı
            - PDF'ye dışarı aktarmada Euro simgesi gösterilmiyor
            - Power BI raporlarında birden çok veri kaynağıyla bir parolanın kaydedilmesi, değiştirilmeyen parolaları geçersiz kılıyor
            - Power BI Mobil Uygulaması boşta bırakıldıktan sonra görsellerde görüntüleme sorunları oluyor

- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
    - *Sürüm: 2.65.5313.1562 (Ocak 2019), Yayın Tarihi: 30 Ocak 2019*
        - Power BI Rapor Sunucusu kaldırıldıktan sonra kısayol ve sabitlenmiş simgeler kalıyor
        - Power BI Rapor Sunucusu'nu başlatma menüsüne siyah simge üzerinde siyah metinle sabitleme sorunu düzeltildi

    - *Sürüm: 2.65.5313.1421 (Ocak 2019), Yayın Tarihi: 22 Ocak 2019* (yeni derleme ve yeni sürüm)
        - Power BI Rapor Sunucusu bağlantısı için gerekli değişiklikleri içeriyor (Ocak 2019) 
    - *Sürüm: 2.65.5313.5141 (Ocak 2019), Yayınlama tarihi: 31 Temmuz 2019* (yeni derleme ve yeni sürüm)
        - Hata düzeltmeleri
            - Yanlış telemetri günlüğü için düzeltme

## <a name="august-2018"></a>Ağustos 2018

- **Power BI Rapor Sunucusu**
    - *Sürüm 1.3.6816.37243 (Derleme 15.0.2.557), Yayın Tarihi: 30 Ağustos 2018*
        - Hata düzeltmeleri
            - Sunucu, bağlama yeniden yönlendirmesinin güncelleştirilmediği önceki Power BI Rapor Sunucusu sürümlerinden yükseltildiğinde müşterinin şu hata iletisiyle karşılaşmasına neden olan sorun düzeltildi:      
            *`
            Failed to load expression host assembly. Details: Could not load file or assembly 'Microsoft.ReportingServices.ProcessingObjectModel, Version=2018.7.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040) (rsErrorLoadingExprHostAssembly)
             `*
             
            - Veri Etiketi Saydamlık hatası düzeltildi.
            
    - *Sürüm 1.3.6801.38816 (Derleme 15.0.2.540), Yayın Tarihi: 15 Ağustos 2018*
        - Özellikler
            - Power BI Raporlarında artık Kerberos ile SAP HANA SSO Doğrudan Sorgu desteği sunulmaktadır
            - Sürümdeki Özel Görsel API'si sürümü: 1.13.0
            - Power BI görselleri, sunucu API'sinin geçerli sürümüyle uyumlu eski bir sürüme döner (varsa)

- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
    - *Sürüm: 2.61.5192.641 (Ağustos 2018), Yayın Tarihi: 15 Ağustos 2018*
        - Power BI Rapor Sunucusu bağlantısı için gerekli değişiklikleri içerir (Ağustos 2018)         
    - *Sürüm: 2.61.5192.7701 (Ağustos 2018), Yayın Tarihi: 8 Ağustos 2019* (yeni derleme ve yeni sürüm)
        - Hata düzeltmeleri
            - Yanlış telemetri günlüğü için düzeltme
            
## <a name="march-2018"></a>Mart 2018

- **Power BI Rapor Sunucusu**
    - *Sürüm 1.2.6690.34729 (Derleme 15.0.2.402), Yayın Tarihi: 27 Nisan 2018*
        - Hata düzeltmeleri
            - SQL Server Reporting Services 2017 kataloglarının geçişini etkinleştirme
            - Power BI Raporları (PBIX) için
                - Bir sunucu, özel kimlik doğrulaması kullanacak şekilde yapılandırıldığında raporlar yenilenebilir
                - Bir raporun özelliklerini değiştirmek, veri kaynağı kimlik bilgilerini sıfırlamaz
            - Sayfalandırılmış Raporlar (RDL) için
                - `Lookup()` veya `LookupSet()` ile `MultiLookup()` gibi türev işlevlerinin RDL İfadelerinde kullanılması, artık `#Error` ile sonuçlanmıyor
                - Bağlantılı raporlar, yazdırma sırasında hedef raporun sayfa boyutuna uyuyor
                - Basamaklı parametreler kullanan bağlantılı raporlar için abonelikler oluşturulabilir
                - IE11 kullanılırken çok değerli parametre varsayılanları değiştirilebilir
                - Veri temelli abonelik teslim seçenekleri düzenlenebilir
                - Abonelik yürütülürken abonelikler görüntülenebilir ve düzenlenebilir
                - Veri kaynağı kimlik bilgilerini ayarlamak, ifade temelli bağlantı dizelerini kaldırmaz
            - KPI'lar için
                - Veriler güncelleştirildiğinde eğilim satırları yenilenir
            - Genel kararlılık iyileştirmeleri

    - *Sürüm 1.2.6660.39920 (Derleme 15.0.2.389), Yayın Tarihi: 28 Mart 2018*
        - Hata düzeltmeleri
            - Power BI Raporları (PBIX) için, Power BI Görsellerinden Veri Dışa Aktarmanın çalışmaması sorunu için düzeltme
            - Power BI Raporları (PBIX) için, URL filtrelerinin çalışmaması sorunu için düzeltme
            - Sayfalandırılmış Raporlar (RDL) için, Power BI Rapor Sunucusu Mart yayınına yükseltmenin ardından IE11’de görüntülerin düzgün görüntülenmemesi sorunu için düzeltme

    - *Sürüm 1.2.6648.38132 (Derleme 15.0.2.378), Yayın Tarihi: 19 Mart 2018*
        - Güvenlik Güncelleştirmeleri
        - Erişilebilirlik Geliştirmeleri
        - Hata düzeltmeleri
            - Sayfalandırılmış Raporlar (RDL) için, özellikleri düzenlendikten sonra geri alınan bağlantılı bir rapordaki parametrelerin görünürlüğü için düzeltme
            - Kayan zaman aşımı tanımlama bilgisini yoksayan özel form kimlik doğrulaması içeren web portalı için düzeltme
            - Satır içeriği boş olduğunda eşit olmayan satır yüksekliği oluşturan Word’e dışarı aktarma için düzeltme
            - Sayfalandırılmış Raporlar (RDL) için, veri kaynağının kimlik bilgilerini değiştirdiğimizde silinen ifadeye dayalı bağlantı dizesiyle ilgili bir sorun düzeltildi
            - Metin değerleri ile KPI kullanma yeteneği için düzeltme
            - Sayfalandırılmış Raporlar (RDL) için, mevcut bir Sayfalandırılmış Rapora (RDL) yeni veri kümesi atama yeteneği için düzeltme
            - Diğer kararlılık ve kullanılabilirlik düzeltmeleri

- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
    - Sürüm: 2.56.5023.1043 (Mart 2018), Yayın Tarihi: 19 Mart 2018
        - Power BI Rapor Sunucusu bağlantısı için gerekli değişiklikleri içerir (Mart 2018)

## <a name="october-2017"></a>Ekim 2017

- **Power BI Rapor Sunucusu**
    - *Sürüm 1.1.6582.41691 (Derleme 14.0.600.442), Yayın Tarihi: 10 Ocak 2018*
        - Güvenlik Güncelleştirmeleri
        - Hata Düzeltmeleri
            - 400 döndüren Model.GetParameters için düzeltme
            - Paylaşılan veri kümesini var olan Sayfalandırılmış Raporlara (RDL) ayarlama için düzeltme
            - Raporu farklı parametre değerleri ile PDF'e aktarırken ExecutionNotFoundException hatası için düzeltme

    - *Sürüm 1.1.6551.5155 (Derleme 14.0.600.438), Yayın Tarihi: 11 Aralık 2017*
        - Hata Düzeltmeleri
            - Belirli Power BI Desktop raporlarında yenilemeden sonra verilerin yenilenememesi.

    - *Sürüm 1.1.6530.30789 (Derleme 14.0.600.437), Yayın Tarihi: 17 Kasım 2017*
        - Hata Düzeltmeleri
            - Temel Kimlik Doğrulaması Senaryolarına yönelik düzeltme 
            - Portal'daki Abonelikler, Önbellek Yenileme Planları ve Geçmiş Anlık Görüntüleri'ne ilişkin zamanlama sayfasında haftanın günlerinin seçilememesine yönelik düzeltme
            - Sayfalandırılmış Raporlar (RDL) için, TextBox sınıfında CanGrow özelliğinin false olarak ayarlandığı ifadelerin bulunması halinde değerlerin renklerinin ve yazı tiplerinin düzgün görüntülenmemesine yönelik düzeltme
            - Power BI Raporları için (PBIX), çizgi grafiğe Açıklamalar eklendiğinde boş bir görselin görüntülenmesine yönelik düzeltme

    - *Sürüm 1.1.6514.9163 (Derleme 14.0.600.434), Yayın Tarihi: 1 Kasım 2017*
        - Hata Düzeltmeleri
            - Boyutu 500 MB'ı aşan PBIX raporlarına ilişkin karşıya yükleme güvenilirliği sorunları düzeltildi
            - Boyutu 1 GB’ı aşan PBIX raporlarına ilişkin yükleme sorunları düzeltildi

    - *Sürüm 1.1.6513.3500 (Derleme 14.0.600.433), Yayın Tarihi: 31 Ekim 2017*
        - Özellikler
            - Katıştırılmış Veri Modeli Desteği
            - Excel Çalışma Kitabı Görüntüleme (Office Online Server tümleştirmesi etkin durumdayken)
            - Zamanlanmış Veri Yenileme (PBIX)
            - Doğrudan Sorgu Desteği
            - Büyük Dosya Desteği (2 GB'a kadar)
            - Genel REST API
            - Power BI Desktop'ta Paylaşılan Veri Kümesi desteği (oData aracılığıyla)
            - PBIX dosyaları için URL Parametresi Desteği
            - Erişilebilirlik geliştirmeleri

- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
    - *Sürüm: 2.51.4885.3981 (Ekim 2017), Yayın Tarihi: 10 Nisan 2018*
        - Güvenlik Güncelleştirmeleri

    - *Sürüm: 2.51.4885.2501 (Ekim 2017), Yayın Tarihi: 10 Ocak 2018*
        - Güvenlik Güncelleştirmeleri

    - *Sürüm: 2.51.4885.1423 (Ekim 2017), Yayın Tarihi: 17 Kasım 2017*
        - Hata Düzeltmeleri
            - x86 işletim sistemlerinde çalıştırılamayan 32 bit Power BI Desktop'a yönelik düzeltme
            - Power BI Raporları (PBIX) için, x ekseni kılavuz çizgilerini göstermeye yönelik düzeltme
            - Diğer küçük hata düzeltmeleri

    - *Sürüm: 2.51.4885.1041 (Ekim 2017), Yayın Tarihi: 31 Ekim 2017*
        - Özellikler
            - Power BI Rapor Sunucusu bağlantısı için gerekli değişiklikleri içerir (Ekim 2017)

## <a name="june-2017"></a>Haziran 2017

- **Power BI Rapor Sunucusu**
    - *Derleme 14.0.600.309, Yayın Tarihi: 10 Ocak 2018*
        - Güvenlik Güncelleştirmeleri

    - *Derleme 14.0.600.305, Yayın Tarihi: 19 Eylül 2017*  
        - Hata Düzeltmeleri
            - En son [Bing Haritalar Web Denetimi](/bingmaps/v8-web-control/) sürümüne yönelik güncelleştirme

    - *Derleme 14.0.600.301, Yayın Tarihi: 11 Temmuz 2017*
        - Hata Düzeltmeleri
            - `{{UserId}}` etiketinin, Power BI Raporlarında raporu yürüten kullanıcı yerine, depolanan kimlik bilgilerini çözümlemesi
            - Bazı görüntülerin Power BI Rapor Sunucusu'nda görüntülenememesi
            - Power BI Rapor Sunucusu'ndaki bir Power BI Raporunun adının değiştirilememesi
            - Power BI mobil uygulamasında Power BI görsellerinin yüklenememesi (yerel önbelleğin temizlenmesi için mobil uygulamanın yeniden yüklenmesinin gerekmesi)

    - *Derleme 14.0.600.271, Yayın Tarihi: 12 Haziran 2017*
        - Power BI Rapor Sunucusu ilk sürümü

- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
    - *Sürüm: 2.47.4766.4901 (Haziran 2017), Yayın Tarihi: 10 Ocak 2018*
        - Güvenlik Güncelleştirmeleri

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Rapor Sunucusu nedir?](get-started.md)
[Yönetici genel bakışı](admin-handbook-overview.md)  
[Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)  
[Rapor Oluşturucusu’nu indirme](https://www.microsoft.com/download/details.aspx?id=53613)  
[Download SQL Server Data Tools (SSDT) (SQL Server Veri Araçlarını (SSDT) indirme)](/sql/ssdt/download-sql-server-data-tools-ssdt)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
