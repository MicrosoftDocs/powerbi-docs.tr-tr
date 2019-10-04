---
title: Power BI Rapor Sunucusu'na yönelik değişiklik günlüğü
description: Power BI Rapor Sunucusu'na yönelik bu değişiklik günlüğünde yeni öğelerin yanı sıra yayımlanan her bir derlemeye ilişkin hata düzeltmeleri yer alır.
ms.author: jaimeta
author: jtarquino
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 03/31/2018
ms.openlocfilehash: 71c2135092b0b9bb2b02f4559d40c0b10814a51f
ms.sourcegitcommit: e2c5d4561455c3a4806ace85defbc72e4d7573b4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71325719"
---
# <a name="changelog-for-power-bi-report-server"></a>Power BI Rapor Sunucusu'na yönelik değişiklik günlüğü

Power BI Rapor Sunucusu'na yönelik bu değişiklik günlüğünde yeni öğelerin yanı sıra yayımlanan her bir derlemeye ilişkin hata düzeltmeleri yer alır.

Yeni özellikler ile ilgili ayrıntı bilgiler için bkz. [Power BI Rapor Sunucusu'ndaki yenilikler](whats-new.md). 

## <a name="september-2019"></a>Eylül 2019

- **Power BI Rapor Sunucusu**          
    - *Sürüm 1.6.7206.38019 (Derleme 15.0.1102.597), Yayınlanma tarihi: 26 Eylül 2019*
        - Güvenlik güncelleştirmeleri
        - Hata Düzeltmeleri
           - Sayfalandırılmış Raporlar
             - IE ve Edge kullanılırken karşılaşılan erişilebilirlik sorunlarıyla ilgili çözüm.
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
            - Sunucu önceki Power BI Rapor Sunucusu sürümlerinden yükseltildiğinde bir bağlama yeniden yönlendirmesi güncelleştirilmediğinde müşterinin şu hatayla karşılaşmasına neden olan sorun düzeltildi:      
            *`
            Failed to load expression host assembly. Details: Could not load file or assembly 'Microsoft.ReportingServices.ProcessingObjectModel, Version=2018.7.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040) (rsErrorLoadingExprHostAssembly)
             `*
             
            - Veri Etiketi Saydamlık hatası düzeltildi.
            
    - *Sürüm 1.3.6801.38816 (Derleme 15.0.2.540), Yayın Tarihi: 15 Ağustos 2018*
        - Özellikler
            - Power BI Raporlarında artık Kerberos ile SAP HANA SSO Doğrudan Sorgu desteği sunulmaktadır
            - Sürümdeki Özel Görsel API'si sürümü: 1.13.0
            - Özel görseller sunucu API'sinin geçerli sürümüyle uyumlu eski bir sürüme döner (varsa)

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
            - Sayfalandırılmış Raporlar (RDL) için, veri kaynağının kimlik bilgilerini değiştirdiğimizde silinen ifadeye dayalı bağlantı dizesi için düzeltme
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
            - Boyutu 500 MB'ı aşan PBIX raporlarına ilişkin karşıya yükleme güvenilirliği sorunlarına yönelik düzeltme
            - Boyutu 1 GB'ı aşan PBIX raporlarına ilişkin yükleme sorununa yönelik düzeltme

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
            - En son [Bing Haritalar Web Denetimi](https://msdn.microsoft.com/library/mt712542.aspx) sürümüne yönelik güncelleştirme

    - *Derleme 14.0.600.301, Yayın Tarihi: 11 Temmuz 2017*
        - Hata Düzeltmeleri
            - `{{UserId}}` etiketinin, Power BI Raporlarında raporu yürüten kullanıcı yerine, depolanan kimlik bilgilerini çözümlemesi
            - Bazı görüntülerin Power BI Rapor Sunucusu'nda görüntülenememesi
            - Power BI Rapor Sunucusu'ndaki bir Power BI Raporunun adının değiştirilememesi
            - Power BI mobil uygulamasında Özel Görsellerin yüklenememesi (yerel önbelleğin temizlenmesi için mobil uygulamanın yeniden yüklenmesinin gerekmesi)

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
[Download SQL Server Data Tools (SSDT) (SQL Server Veri Araçlarını (SSDT) indirme)](http://go.microsoft.com/fwlink/?LinkID=616714)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
