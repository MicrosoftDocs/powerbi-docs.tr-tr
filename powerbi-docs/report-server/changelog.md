---
title: Power BI Rapor Sunucusu'na yönelik değişiklik günlüğü
description: Power BI Rapor Sunucusu'na yönelik bu değişiklik günlüğünde yeni öğelerin yanı sıra yayımlanan her bir derlemeye ilişkin hata düzeltmeleri yer alır.
author: jtarquino
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 03/31/2018
ms.author: jtarquino
ms.openlocfilehash: c80ded7a21eb8110467a2335253fa1a68942cc2c
ms.sourcegitcommit: 60fb46b61ac73806987847d9c606993c0e14fb30
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50101543"
---
# <a name="changelog-for-power-bi-report-server"></a>Power BI Rapor Sunucusu'na yönelik değişiklik günlüğü

Power BI Rapor Sunucusu'na yönelik bu değişiklik günlüğünde yeni öğelerin yanı sıra yayımlanan her bir derlemeye ilişkin hata düzeltmeleri yer alır.

Yeni özellikler ile ilgili ayrıntı bilgiler için bkz. [Power BI Rapor Sunucusu'ndaki yenilikler](whats-new.md). 

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
                - `Lookup()` veya `LookupSet()` ile `MultiLookup()` gibi türev işlevlerin RDL İfadelerinde kullanılması, artık `#Error` ile sonuçlanmıyor
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

    - *Sürüm: 1.1.6551.5155 (Derleme: 14.0.600.438), Yayımlanma Tarihi: 11 Aralık 2017*
        - Hata Düzeltmeleri
            - Belirli Power BI Desktop raporlarında yenilemeden sonra verilerin yenilenememesi.

    - *Sürüm: 1.1.6530.30789 (Derleme: 14.0.600.437), Yayımlanma Tarihi: 17 Kasım 2017*
        - Hata Düzeltmeleri
            - Temel Kimlik Doğrulaması Senaryolarına yönelik düzeltme 
            - Portal'daki Abonelikler, Önbellek Yenileme Planları ve Geçmiş Anlık Görüntüleri'ne ilişkin zamanlama sayfasında haftanın günlerinin seçilememesine yönelik düzeltme
            - Sayfalandırılmış Raporlar (RDL) için, TextBox sınıfında CanGrow özelliğinin false olarak ayarlandığı ifadelerin bulunması halinde değerlerin renklerinin ve yazı tiplerinin düzgün görüntülenmemesine yönelik düzeltme
            - Power BI Raporları için (PBIX), çizgi grafiğe Açıklamalar eklendiğinde boş bir görselin görüntülenmesine yönelik düzeltme

    - *Sürüm: 1.1.6514.9163 (Derleme: 14.0.600.434), Yayımlanma Tarihi: 1 Kasım 2017*
        - Hata Düzeltmeleri
            - Boyutu 500 MB'ı aşan PBIX raporlarına ilişkin karşıya yükleme güvenilirliği sorunlarına yönelik düzeltme
            - Boyutu 1 GB'ı aşan PBIX raporlarına ilişkin yükleme sorununa yönelik düzeltme

    - *Sürüm: 1.1.6513.3500 (Derleme: 14.0.600.433), Yayımlanma Tarihi: 31 Ekim 2017*
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

    - *Sürüm: 2.51.4885.1423 (Ekim 2017), Yayımlanma Tarihi: 17 Kasım 2017*
        - Hata Düzeltmeleri
            - x86 işletim sistemlerinde çalıştırılamayan 32 bit Power BI Desktop'a yönelik düzeltme
            - Power BI Raporları (PBIX) için, x ekseni kılavuz çizgilerini göstermeye yönelik düzeltme
            - Diğer küçük hata düzeltmeleri

    - *Sürüm: 2.51.4885.1041 (Ekim 2017), Yayımlanma Tarihi: 31 Ekim 2017*
        - Özellikler
            - Power BI Rapor Sunucusu bağlantısı için gerekli değişiklikleri içerir (Ekim 2017)

## <a name="june-2017"></a>Haziran 2017

- **Power BI Rapor Sunucusu**
    - *Derleme 14.0.600.309, Yayın Tarihi: 10 Ocak 2018*
        - Güvenlik Güncelleştirmeleri

    - *Derleme: 14.0.600.305, Yayımlanma Tarihi: 19 Eylül 2017*  
        - Hata Düzeltmeleri
            - En son [Bing Haritalar Web Denetimi](https://msdn.microsoft.com/library/mt712542.aspx) sürümüne yönelik güncelleştirme

    - *Derleme: 14.0.600.301, Yayımlanma Tarihi: July 11, 2017*
        - Hata Düzeltmeleri
            - `{{UserId}}` etiketinin, Power BI Raporlarında raporu yürüten kullanıcı yerine, depolanan kimlik bilgilerini çözümlemesi
            - Bazı görüntülerin Power BI Rapor Sunucusu'nda görüntülenememesi
            - Power BI Rapor Sunucusu'ndaki bir Power BI Raporunun adının değiştirilememesi
            - Power BI mobil uygulamasında Özel Görsellerin yüklenememesi (yerel önbelleğin temizlenmesi için mobil uygulamanın yeniden yüklenmesinin gerekmesi)

    - *Derleme: 14.0.600.271, Yayımlanma Tarihi: 12 Haziran 2017*
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
