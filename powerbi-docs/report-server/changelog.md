---
title: "Power BI Rapor Sunucusu'na yönelik değişiklik günlüğü"
description: "Power BI Rapor Sunucusu'na yönelik bu değişiklik günlüğünde yeni öğelerin yanı sıra yayımlanan her bir derlemeye ilişkin hata düzeltmeleri yer alır."
services: powerbi
documentationcenter: 
author: jtarquino
manager: jonhp
backup: maggies
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/17/2017
ms.author: jaimeta
ms.openlocfilehash: e56976943e58aba8c9ef36c576a16ab5eba4c796
ms.sourcegitcommit: 7d4ad2ba92a932d7cc6637348e0774be6623559e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2017
---
# <a name="changelog-for-power-bi-report-server"></a>Power BI Rapor Sunucusu'na yönelik değişiklik günlüğü

Power BI Rapor Sunucusu'na yönelik bu değişiklik günlüğünde yeni öğelerin yanı sıra yayımlanan her bir derlemeye ilişkin hata düzeltmeleri yer alır.

Yeni özellikler ile ilgili ayrıntı bilgiler için bkz. [Power BI Rapor Sunucusu'ndaki yenilikler](whats-new.md).

## <a name="october-2017"></a>Ekim 2017

- **Power BI Rapor Sunucusu**
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
    - *Derleme: 14.0.600.305, Yayımlanma Tarihi: 19 Eylül 2017*  
        - Hata Düzeltmeleri
            - En son [Bing Haritalar Web Denetimi](https://msdn.microsoft.com/library/mt712542.aspx) sürümüne yönelik güncelleştirme

    - *Derleme: 14.0.600.301, Yayımlanma Tarihi: July 11, 2017*
        - Hata Düzeltmeleri
            - {{UserId}} etiketinin, Power BI Raporlarında raporu yürüten kullanıcı yerine, depolanan kimlik bilgilerini çözümlemesi
            - Bazı görüntülerin Power BI Rapor Sunucusu'nda görüntülenememesi
            - Power BI Rapor Sunucusu'ndaki bir Power BI Raporunun adının değiştirilememesi
            - Power BI mobil uygulamasında Özel Görsellerin yüklenememesi (yerel önbelleğin temizlenmesi için mobil uygulamanın yeniden yüklenmesinin gerekmesi)

    - *Derleme: 14.0.600.271, Yayımlanma Tarihi: 12 Haziran 2017*
        - Power BI Rapor Sunucusu ilk sürümü

## <a name="next-steps"></a>Sonraki adımlar

[Kullanıcı el kitabı](user-handbook-overview.md)  
[Yönetici el kitabı](admin-handbook-overview.md)  
[Quickstart: Install Power BI Report Server (Hızlı Başlangıç: Power BI Rapor Sunucusu'nu yükleme)](quickstart-install-report-server.md)  
[Install Report Builder (Rapor Oluşturucusu'nu yükleme)](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT) (SQL Server Veri Araçlarını (SSDT) indirme)](http://go.microsoft.com/fwlink/?LinkID=616714)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)