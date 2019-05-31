---
title: Power BI Rapor Sunucusu'na yönelik değişiklik günlüğü
description: Power BI Rapor Sunucusu'na yönelik bu değişiklik günlüğünde yeni öğelerin yanı sıra yayımlanan her bir derlemeye ilişkin hata düzeltmeleri yer alır.
ms.author: jtarquino
author: jtarquino
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 03/31/2018
ms.openlocfilehash: bb25bfb9b3278ef5eccfd54436a6de430d17677d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65990615"
---
# <a name="changelog-for-power-bi-report-server"></a>Power BI Rapor Sunucusu'na yönelik değişiklik günlüğü

Power BI Rapor Sunucusu'na yönelik bu değişiklik günlüğünde yeni öğelerin yanı sıra yayımlanan her bir derlemeye ilişkin hata düzeltmeleri yer alır.

Yeni özellikler ile ilgili ayrıntı bilgiler için bkz. [Power BI Rapor Sunucusu'ndaki yenilikler](whats-new.md). 

## <a name="may-2019"></a>Mayıs 2019

- **Power BI Rapor Sunucusu**          
    - *Yayımlanan 1.5.7074.36177 (derleme 15.0.1102.371), sürüm: 21 Mayıs 2019*
        - Hata Düzeltmeleri
            - Sayfalandırılmış Raporlar
                - Her zaman pdf yazı tipi katıştırma etkinleştirme Düzelt.
                - Güvenli olarak https üzerinden gönderilen tanımlama bilgilerini ayarlamak düzeltme
                - Pop ile ilgili sorunlar için düzeltme komut dosyası hataları nedeniyle çıkarır
                - Android telefonlardaki mobil uygulaması ile görünen sorunları düzeltin
                - Mali Yıl başlangıcı bağımsız olarak doğru hafta sayıları göstermek mobil rapor zaman Gezgini için düzeltme
                - Eklenen RestrictedResourceMimeTypeForUpload yöneticilerin belirtmek yapılandırılabilir özellik yasaklanmış' MIME türleri
         - Özellikler
            - PBIRS için güvenilen görselleri için destek ekleme

- **Power BI Desktop (Power BI Rapor Sunucusu için en iyi duruma getirilmiş)**
    - *Sürüm: Yayımlanan 2.69.5467.1801 (Mayıs 2019): 21 Mayıs 2019*
        - Hata düzeltmeleri
            - PBIRS PBIX yükleme sırasında yeniden giriş kimlik bilgilerinin önlemek için düzeltme
            - Düzeltmeleri ile dosya adında # belgelerini açma
            - Geri gezinme PBIRS seçim penceresinde daha kolay bağlantı eklendi
            - Yüksek karşıtlık modunda geri düğmesini görüntülemek için uyarı visual iletilerini göster PBIRS için düzeltin.
            - UI düzeltmeler seçim bölmesi, tuval ölçeklendirme.

## <a name="january-2019"></a>Ocak 2019

- **Power BI Rapor Sunucusu**          
    - *Yayımlanan 1.4.7024.16477 (derleme 15.0.1102.299), sürüm: 28 Mart 2019*
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

    - *Sürüm: 2.65.5313.1421 (Ocak 2019), Yayın Tarihi: 22 Ocak 2019*
        - Power BI Rapor Sunucusu bağlantısı için gerekli değişiklikleri içeriyor (Ocak 2019)  

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
