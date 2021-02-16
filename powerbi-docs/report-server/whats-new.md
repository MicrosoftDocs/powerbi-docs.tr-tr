---
title: Power BI Rapor Sunucusu'ndaki yenilikler
description: Power BI Rapor Sunucusu’nun son sürümündeki yenilikler hakkında bilgi edinin. Önemli özelliklere yer verilen bu makale, yeni sürümler yayınlandıkça güncelleştirilmektedir.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/27/2021
ms.openlocfilehash: a0e5ced79c5aee6d6392b3d52fcc8e6d638faf27
ms.sourcegitcommit: 00e3eb2ec4f18d48a73cfd020bb42d08e859ad06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2021
ms.locfileid: "100531942"
---
# <a name="whats-new-in-power-bi-report-server"></a>Power BI Rapor Sunucusu'ndaki yenilikler

Power BI Rapor Sunucusu en son sürümlerindeki yenilikler ve Power BI Rapor Sunucusu için Power BI Desktop hakkında bilgi edinin. Önemli özelliklere yer verilen bu makale, her yeni yayınla birlikte güncelleştirilmektedir. Power BI Rapor Sunucusu’ndaki yenilikler hakkında daha fazla bilgi için bkz. [Power BI Rapor Sunucusu’na yönelik değişiklik günlüğü](changelog.md).

[Power BI rapor sunucusu için Power BI rapor sunucusu ve Power BI Desktop](https://powerbi.microsoft.com/report-server/)indirin.

## <a name="january-2021"></a>Ocak 2021

Yeni ve güncelleştirilmiş özelliklerin listesi aşağıda verilmiştir. Ayrıntılar için bkz. [ocak 2021 için blog gönderisi Power BI rapor sunucusu](https://powerbi.microsoft.com/blog/power-bi-report-server-january-2021-feature-summary/).

### <a name="power-bi-desktop-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için Power BI Desktop

Öne çıkan yeni özelliklerden bazıları aşağıda verilmiştir.

**Power BI raporları**

- Tüm Filtreleri Uygula genel kullanıma sunulmuştur
- Görsel Yakınlaştırma kaydırıcısı
- Web bağlantıları için sertifika iptal denetimi
- Mobil Düzen görünümünde seçim bölmesi
- Power BI desteği için argıs

**Veri bağlantısı**

- Hive LLAP Bağlayıcısı genel kullanıma sunuldu
- Yeni bağlayıcılar: Actia, Anaplan, yıldız yağmuru Presto

### <a name="new-connection-metadata-format-preview"></a>Yeni bağlantı meta verileri biçimi (Önizleme)

Bağlantı meta verilerinin Ekim 'de. pbix dosya biçiminde depolanma biçimini güncelleştirdik. Bu güncelleştirme,. pbix dosyalarını programlı olarak erişilebilir ve düzenlenebilir hale getirmek için uzun süreli bir yolculuğun bir parçasıdır. Power BI hizmeti ile ayda ayda bir olan Power BI Desktop sürümündeki değişikliği zaten etkinleştirdik. Bu ay başlayarak rapor sunucusu için Power BI Desktop bu sürümündeki değişiklikleri önizliyoruz.

Bu sürümden itibaren, önizlemeyi açıp gelişmiş biçime yükseltmenizi isteyen aşağıdaki bildirimi görürsünüz:

"Yakında kullanıma sunulacak. Power BI daha iyi performans ve güvenlik güncelleştirmeleri almak için gelişmiş meta veri biçimi önizlemesini açın."

Şunlara dikkat edin:

- Mevcut veri kümeleri, yükseltme olmadan bile çalışmaya devam edecektir. Gelişmiş Biçim genel kullanıma sunulduğunda yükseltilir.
- Rapor sunucusu için Power BI Desktop, var olan bir veri kümesini sizin için otomatik olarak gelişmiş biçime yükseltecektir. Önceki biçime geri dönmek istemeniz durumunda, bu yükseltilen sürümdeki rapor sunucusu üzerindeki mevcut raporların üzerine yazılmasını öneririz.
- Bu önizlemeye katılmak isteğe bağlıdır, ancak bize geri bildirimde bulunun. Gelişmiş biçimi rapor sunucusu 'nun bir sonraki sürümünde tek seçenek olarak genel kullanıma sunarız.
 
Yönetici olarak, bu önizlemeyi devre dışı bırakabilir, v3 'yi zorlayabilir ve önizleme özelliğini gizleyebilirsiniz onay kutusunu kapatabilirsiniz. Kayıt defterinde şu DWORD değerini 0 olarak ayarlayın: AllowV3Models:

```
[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop SSRS]
"AllowV3Models"=dword:00000000
```

veya

```
[HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop SSRS]
"AllowV3Models"=dword:00000000
```

Daha fazla bilgi için bkz. [Gelişmiş veri kümesi meta verileri kullanma](../connect-data/desktop-enhanced-dataset-metadata.md) .

### <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu

**Tarayıcı desteği kullanımdan kaldırılıyor**

Eski sürüm veya Internet Explorer 11 kullanıyorsanız, tarayıcınızı yükseltmeniz zaman vardır. Edge eski tarayıcı desteği 9 Mart 2021 ' den itibaren sona eriyor. Internet Explorer 11 için destek 17 Ağustos 2021 tarihinden itibaren sona erer. 

Internet Explorer 11 ' in kullanım dışı olduğunu Power BI Rapor Sunucusu Web portalında bir uyarı görürsünüz. Yükseltme zamanı! Ayrıntılar için bkz. [Power BI rapor sunucusu Için tarayıcı desteği](browser-support.md) .

**Yeni ürün simgesi**

Power BI Rapor Sunucusu, tüm Microsoft ürünlerinde kullanıma hazır yeni simgelerle birlikte yeni bir ürün simgesine sahiptir.

:::image type="content" source="media/whats-new/power-bi-report-server-new-logo.png" alt-text="Yeni logo Power BI Rapor Sunucusu.":::

## <a name="october-2020"></a>Ekim 2020

Aşağıda yeni ve güncelleştirilmiş özelliklerin tamamı listelenmiştir. Ayrıntılar için bkz. [Power BI Rapor Sunucusu Ekim 2020 blog gönderisi](https://powerbi.microsoft.com/blog/power-bi-report-server-october-2020-feature-summary/). 

### <a name="power-bi-desktop-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için Power BI Desktop

Öne çıkan yeni özelliklerden bazıları aşağıda verilmiştir.

**Modern şerit**  

Modern şerit, Power BI Rapor Sunucusu için Power BI Desktop gelir. Şeride daha fazla özellik eklemeye devam edeceğiz. Değişiklikler ve avantajlar hakkında daha fazla bilgi edinmek için [Power BI Desktop’taki güncelleştirilmiş şeridi kullanma](../create-reports/desktop-ribbon.md) başlıklı makaleye göz atın.

:::image type="content" source="media/whats-new/report-server-new-ribbon.png" alt-text="Power BI Rapor Sunucusu için Power BI Desktop yeni şeridin ekran görüntüsü.":::

**Hiyerarşi dilimleyicileri**

Birden çok ilgili alanı tek bir dilimleyicide filtrelemek için *hiyerarşi dilimleyicisi* oluşturabilirsiniz. Bu özellik genel kullanıma sunulduğundan, şu ek işlevlerden de yararlanır:

- Genişlet/daralt simgeleri için yeni seçenekler.
- Simgeler şimdi yazı tipi boyutuyla ölçeklendiriliyor.
- Alt öğeler için özelleştirilebilir girintileme.
- Dilimleyici üst bilgi metni için daha fazla özelleştirme.

:::image type="content" source="media/whats-new/report-server-slicer-hierarchy.png" alt-text="Power BI Rapor Sunucusu için Power BI Desktop hiyerarşi dilimleyicisi.":::

Ayrıntılar için belgelerdeki [Power BI’daki dilimleyiciler](../visuals/power-bi-visualization-slicers.md) bölümünü inceleyin.

**Mobil yazma geliştirmeleri** 

Bu sürümde, geliştirilmiş bir mobil düzen yazma deneyimi ve daha fazla mobil düzen özelliği sunuyoruz. Power BI mobil uygulamaları benimseyen daha fazla kuruluş, mobil yazma deneyimi için daha fazla özellik ve iyileştirmeler isteyen bir geri bildirim aldık. Bu sürümdeki geliştirmeler, mobil cihazlar için iyileştirilmiş ilgi çekici ve etkileşimli raporları daha kolay bir biçimde hazırlamanıza yardımcı olacak.

Mobil cihazlar için iyileştirilmiş raporlar oluşturmaya yönelik yeni deneyim ve özellikler aşağıda verilmiştir:  

- Yeni telefon öykünücüsü  
- Güncelleştirilmiş görselleştirme bölmesi  
- Yer paylaşımlı görsellere yönelik destek  
- Yer işaretleri mobil düzen görünümünde kullanılabilir  
- Kılavuz çizgilerini ve kılavuza yaslama işlevini kapatma  

:::image type="content" source="media/whats-new/report-server-mobile-layout.png" alt-text="Power BI Rapor Sunucusu için Power BI Desktop gelişmiş mobil düzen.":::

Ayrıntılar için [Mobil düzende yapılan geliştirmeler](https://powerbi.microsoft.com/blog/power-bi-desktop-june-2020-feature-summary/#_mobile) başlıklı blog gönderisine bakın.

**Veri Hazırlama: Excel dosyalarından otomatik tablo algılama**

Excel bağlayıcısının bu yeni özelliği, tabloya ayıklamak üzere Excel elektronik tablolarının her bir bölümünü otomatik olarak tespit eder. Bunlar, Gezgin’deki “Önerilen Tablolar” grubunda gösterilir. Önceden, verilerin Excel’de tablo veya adlandırılmış aralık olarak biçimlendirilmesi gerekiyordu. Aksi takdirde çalışma sayfası nesnelerinden satırları atlama ve sütunları kaldırma gibi, belirli dönüşümler içeren ilgili satırları/sütunları kazımanız gerekirdi. Buna ilişkin aşağıdaki örnekte yer alan Sayfa1’e göz atabilirsiniz. Bu özelliği kullanmak için **Ayarlar** iletişim kutusundan etkinleştirmeniz gerekir.

:::image type="content" source="media/whats-new/report-server-excel-table.png" alt-text="Power BI Rapor Sunucusu için Power BI Desktop bir Excel tablosu tanıyor.":::

**Modelleme: Gelişmiş Veri Kümesi Meta Verileri**

Geçmişte, yalnızca Power Query’de oluşturulmuş yüklenebilir sorgular veri modeline eşlenirdi. Şimdi tüm sorgular veri modelindeki nesnelere eşleniyor. Söz konusu PBIX dosyasını açtığınızda, sorgular veri modeli temel alınarak yeniden oluşturulur.

Bu arka uç güncelleştirmesi ile gelecekte daha fazla iyileştirme yapma olanağı elde ettik ve bunu sürdüreceğiz. 

Örneğin:

- Power BI Desktop’a dış araçların (şu anda önizleme aşamasında) eklenmesiyle birlikte, bu dış araçlardan yararlanarak eklediğiniz tablolar raporunuzu yeniden açtığınızda sorgu olarak görüntülenir.
- Bir PBIT dosyasını dışarı aktarıp bu dosyanın sıkıştırmasını kaldırmayı denediğinizde, modeli JSON biçiminde görürsünüz ve bozuk dosyalarla ilgili hatalar almazsınız. 

Otomatik olarak güncelleştireılamayan eski bir PBIX 'niz varsa, başka bir modelleme değişikliği yapmadan önce modelinizi başarıyla yükseltmeniz gerekir. 

**Windows 7 desteği sona erdi**

10 yılın ardından, Windows 7 desteği 14 Ocak 2020’de sona erdi. Bu değişikliği içeren satırda, 31 Ocak 2021 tarihinde Windows 7 ' de Power BI Desktop desteğini durduracağız. Bu tarihten sonra, Power BI Desktop yalnızca Windows 8 ve üzeri sürümlerde desteklenecek. Rapor Sunucusu için iyileştirilmiş Power BI Desktop’ın Ocak 2021 sürümü, Modern Yaşam Döngüsü İlkesi uyarınca desteklenecek. Başka bir deyişle, sonraki sürüme (şimdilik 31 Mayıs 2021 için zamanlandı) kadar tam olarak desteklenecek. Mayıs 2021’den sonra, Ocak 2022’ye kadar yalnızca güvenlik güncelleştirmeleri alacak. Desteğin tamamı Ocak 2022’den sonra sona erecek. Ayrıntılar için bkz. [Power BI Rapor Sunucusu için destek zaman çizelgesi](support-timeline.md). 

**Güncelleştirmelerin eksiksiz listesi**

Power BI Rapor Sunucusu için Power BI Desktop Ekim sürümündeki güncelleştirmelerin tüm listesi aşağıda verilmiştir. 

**Raporlama**

- Modern şerit
- Tuval filigranları
- Yığılmış görseller için toplam etiketleri
- Katman sırasını korumak için genel görsel seçeneği eklendi
- Gradyan göstergesi
- Göreli zaman filtresi
- Dilimleyici üst bilgi metnini daha fazla özelleştirme imkanı
- Hiyerarşik dilimleyiciyle ilgili iyileştirmeler

    - Simgeleri enişlet/daralt simgeleri için yeni seçenekler
    - Simgeler şimdi yazı tipi boyutuyla ölçeklendiriliyor
    - Alt öğeler için özelleştirilebilir girintileme imkanı

- Mobil yazma geliştirmeleri

    - Yeni telefon öykünücüsü
    - Güncelleştirilmiş görselleştirme bölmesi
    - Yer paylaşımlı görsellere yönelik destek
    - Yer işaretleri mobil düzen görünümünde kullanılabilir
    - Kılavuz çizgilerini ve kılavuza yaslama işlevini kapatma  

**Görselleştirmeler**

- Çizgi grafik nokta biçimlendirme seçenekleri 

**Modelleme**

- Gelişmiş Veri Kümesi Meta Verileri
- IF ve SWITCH işlevleri için performans iyileştirmeleri
- Excel finansal işlevleri için destek
- Model görünümü canlı bağlantı için etkinleştirildi
- Model görünümündeki güncelleştirmeler 

**Veri hazırlama**

- Excel dosyalarından Otomatik Tablo Algılama  
- JSON dosyalarından Otomatik Tablo Algılama  
- Otomatik tür algılamayı devre dışı bırakma genel seçeneği 

**Diğer**  

- Power BI Desktop'ta veri kaynağını PBIDS olarak dışarı aktarma
- Masaüstü karşılama ekranını kapatma özelliği 

### <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu

**PowerShell ile Power BI raporlarını kullanarak veri kaynağı bağlantı dizelerini değiştirme**

Power BI Rapor Sunucusu’nun Ekim sürümünde, DirectQuery ve Refresh için Power BI raporlarına yönelik bağlantıları güncelleştirme özelliğini kullanıma sunuyoruz. Bu özellik ayrıca önceki sürümlerde nasıl ayarlansağlayabilmeniz için de önemli bir değişiklik olabilir. Daha fazla bilgi için bkz. [PowerShell - Power BI Rapor Sunucusu ile Power BI raporlarını kullanarak veri kaynağı bağlantı dizelerini değiştirme](connect-data-source-apis.md). 

## <a name="may-2020"></a>Mayıs 2020

### <a name="power-bi-desktop-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için Power BI Desktop

Bu güncelleştirmenin öne çıkan kısımları arasında hiyerarşik dilimleyici, ayrıştırma ağacı görselleri ve sorgu tanılamaları yer alır. Aşağıda yeni ve güncelleştirilmiş özelliklerin tamamı listelenmiştir. Ayrıntılar için bkz. [Power BI Rapor Sunucusu Mayıs 2020 blog gönderisi](https://powerbi.microsoft.com/blog/power-bi-report-server-may-2020-feature-summary/). 

#### <a name="reporting"></a>Raporlama

- Hiyerarşik dilimleyici
- Düğmeler için yeni eylem türleri:

    - Sayfa gezintisi
    - Detaylandırma

- Düğmeler artık dolgu resimlerini destekliyor
- Tablolar için çok sütunlu sıralama
- Çizgi grafik için çift eksen
- Görseller için dikdörtgen seçimi
- Tablo ve matrislerde toplamlar ve alt toplamlar için koşullu biçimlendirme
- Temayı özelleştirme iletişim kutusu
- Koşullu biçimlendirme bulunabilirliği
- Ayrıştırma ağacı
- Filtre bölmesi güncelleştirmeleri:

    - Yeni filtre bölmesi deneyimi
    - Filtre bölmesi araması
    
#### <a name="modeling"></a>Modelleme

- Yeni DAX işlevleri:

    - FirstNonBlankValue
    - LastNonBlankValue
    - Coalesce

- Standart DAX ayırıcıları

#### <a name="visualizations"></a>Görselleştirmeler

- Yeni görselleştirme simgeleri
- Görsel gölge katmanları

#### <a name="data-preparation"></a>Veri Hazırlama

- Sorgu tanılamaları

#### <a name="other"></a>Diğer

- Web proxy için varsayılan sistem kimlik bilgilerini kullanma

### <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu

#### <a name="power-bi-visuals-api"></a>Power BI görselleri API’si

Bu sürümle gönderilen API sürümü 3.2’dir.

## <a name="january-2020"></a>Ocak 2020

Diğer ayrıntılar için Power BI Rapor Sunucusu Ocak 2020 blog gönderisine bakın.

### <a name="power-bi-desktop-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için Power BI Desktop

Bu sürüm düğmeler için koşullu biçimlendirme, veri profili iyileştirmeleri ve KPI’lerle tablo görselleri için diğer biçimlendirme ayarları gibi birçok yeni özellik getiriyor. İşte güncelleştirmelerin özetlenmiş bir listesi:

**Raporlama**

- Tablo sütunu veya matris değerini özel bir URL olarak ayarlama
- KPI görsel biçimlendirme ayarları
- Filtre bölmesi deneyimi güncelleştirmeleri

**Analiz**

- Koşullu biçimlendirilen düğmeler
- İçgörüleri analiz etmek için daha fazlasını yükleme
- Yeni DAX işlevi: Çeyrek

**Veri hazırlama**

- Veri profili oluşturma geliştirmeleri

**Diğer**

- Yeni dosya biçimi: .pbids
- Modelleme işlemleri için performans artışları

**Raporlama**

*Tablo sütunu veya matris değerini özel bir URL olarak ayarlama*

Tablo sütunu veya matris değerini özel bir URL olarak ayarlayabilirsiniz. Bu yeni seçeneği biçimlendirme bölmesindeki koşullu biçimlendirme kartı altında bulabilirsiniz.

*KPI görsel biçimlendirme ayarları*

Bu ayın sürümüyle birlikte KPI’lerin artık yeni biçimlendirme seçenekleri var:

- Gösterge metin biçimlendirmesi (yazı tipi ailesi, rengi ve hizalama)
- Eğilim ekseni saydamlığı
- Hedef ve uzaklık metin biçimlendirmesi (etiket metni, yazı tipi ailesi, rengi ve boyutu)
- Uzaklık metin biçimlendirmesi (etiket metni, pozitif yön, yazı tipi ailesi, rengi ve boyutu)
- Biçimlendirmesi olan bir tarih etiketi ekleme (yazı tipi ailesi, rengi ve boyutu)

Bu yeni biçimlendirme seçeneklerinin bir bölümünü koşullu olarak biçimlendirebilirsiniz:

- Gösterge yazı tipi rengi
- Hedef yazı tipi rengi ve Hedef Uzaklık yazı tipi rengi
- İyi/kötü/nötr durum renkleri
- Tarih yazı tipi rengi

*Filtre bölmesi deneyimi güncelleştirmeleri*

[Son sürümdeki](https://powerbi.microsoft.com/blog/power-bi-report-server-september-2019-feature-summary/#filterPane) yeni filtre deneyiminin genel kullanılabilirliği kapsamında, geçerli raporların yeni bölmeye geçişini düzenledik. Power BI Rapor Sunucusu’nu ilk kez açtığınızda bir filtre panosunu otomatik güncelleştirme iletişim kutusu görürsünüz. Bu güncelleştirmeler arasında, raporların yeni deneyime geçirilmesi gerektiğinde Rapor Sunucusu’nda gösterilen başlıklar da vardır.

**Analiz**

*Düğmeler için koşullu biçimlendirme*

Bu koşullu biçimlendirme güncelleştirmelerinin tümü düğmelerle ilgilidir. Artık aşağıdaki özellikler için biçimlendirmeyi dinamik olarak ayarlayabilirsiniz:

- Düğme metni yazı tipi rengi
- Düğme metni
- Simge çizgisi rengi
- Ana hat rengi
- Dolgu Rengi
- Araç ipucu (eylem kartının altında)

*İçgörüleri analiz etmek için daha fazlasını yükleme*

Verilerinizdeki içgörüleri bulmak, örneğin artışı açıklamak için Analiz özelliğini çalıştırdığınızda, içgörüleri zamanında size göstermek için makine öğrenmesi modellerini yalnızca ayarlanmış bir süre çalıştırırız. Analiz edilecek çok fazla veri varsa artık ilk zaman aşımından sonra analizi çalıştırmaya devam etmeyi seçebilirsiniz.

*Yeni DAX işlevi: Quarter*

Bu ay yeni bir DAX işlevimiz var: Quarter. Quarter işlevi belirtilen tarihe karşılık gelen çeyreği döndürür.

**Veri hazırlama**

*Veri profili oluşturma geliştirmeleri*

Bu ay Power Query Düzenleyicisi’ndeki Veri Profili Oluşturma özelliklerimizde bir dizi önemli geliştirme yaptık. Bunlar:

- Sütun Profili bölmesi değer dağılım görselinde mevcut “Değere Göre” ölçütüne ek olarak sütun türüne göre belirtilen birden çok Gruplandırma seçeneği.
- Metin: Metne Göre Uzunluk (karakter sayısı).
- Sayı: İşarete (pozitif/negatif) ve Eşliğe Göre (çift/tek).
- Tarih/TarihSaat: Yıla, Aya, Güne, Yılın Haftasına, Haftanın Gününe, AM/PM Saatine ve Günün saatine göre.
- Diğer veri türleri için de fazlası var, örneğin Mantıksal Doğru/Yanlış.

*Filtre seçenekleri*

Sütun Profilleri dağılım bölmesindeki türe özgü birkaç gruplandırma ölçütünden zaten yararlanabiliyordunuz. Şimdi gruplandırma ölçütleri uygulandığında dağılım grafiğindeki değerlerin her biri için belirtme çizgileri içinden de filtre uygulayabilirsiniz. Örneğin Tarih/TarihSaat sütunu için Veri Profilleri bölmesinden belirli bir Aya denk gelen tüm değerleri dışlayabilirsiniz.

**Diğer**

*Yeni dosya biçimi: .pbids*

Kuruluşunuzda rapor oluşturanlara yönelik “Veri Al” deneyimini kolaylaştırmak için bu ay yeni bir dosya biçimini kullanıma sunuyoruz: .pbids. Yöneticiler sık kullanılan bağlantılar için bu dosyaları oluşturmasını öneririz.

Rapor oluşturucusu .pbids dosyasını açtığında Power BI Desktop kimlik doğrulaması için dosyada belirtilen veri kaynağına bağlanmanızı ister. Ardından kullanıcı modele yüklenecek tabloları seçer. Dosyada veritabanı belirtilmemişse, veritabanını da seçmesi gerekebilir. Oradan, rapor oluşturucusu görselleştirmeleri oluşturmaya başlayabilir.

“Power BI Desktop’ta veri kaynakları” makalesinin [Verileri almak için .pbids dosyalarını kullanma](../connect-data/desktop-data-sources.md#using-pbids-files-to-get-data) bölümünde konunun ayrıntılarını ve örneklerini bulabilirsiniz.

*Modelleme işlemleri için performans artışları*

Ölçüleri veya hesaplanmış alanları ekleme ve ilişkileri oluşturma gibi modelleme işlemlerine hız kazandırmak için Analysis Services altyapısında performans geliştirmesi yaptık. Göreceğiniz geliştirme miktarı modele bağlıdır ama bazı müşterilerin dosya açma ve ölçü ekleme gibi eylemlerinde 20 kat performans artışı olduğunu gördük.

Bunların hepsi Power BI Rapor Sunucusu’nun Ocak 2020 sürümünde. Geri bildirimlerinizi göndermeye devam edin ve [Power BI’da görmek istediğiniz özellikler için oy vermeyi](https://ideas.powerbi.com/forums/265200-power-bi) unutmayın.

### <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu

#### <a name="export-to-excel-from-power-bi-reports"></a>Power BI raporlarından Excel’e aktarma

Power BI Rapor Sunucusu’nda bir Power BI raporundan Excel’e dışarı aktarma işlemi şimdi Power BI hizmetinde bir Power BI raporundan Excel’e dışarı aktarma işlemiyle aynı şekilde çalışıyor. Doğrudan Excel .xlsx biçimine aktarabilirsiniz ve dışarı aktarma sınırı 150.000 satırdır.

#### <a name="azure-sql-managed-instance-support"></a>Azure SQL Yönetilen Örneği desteği

Artık Power BI Rapor Sunucusu tarafından kullanılan veritabanı kataloğunu bir VM’de veya veri merkezinizde barındırılan Azure SQL Yönetilen Örneğinde (MI) barındırabilirsiniz. Bu destek SQL MI bağlantısı için veritabanı kimlik bilgilerini kullanmakla sınırlandırılmıştır.

#### <a name="power-bi-premium-dataset-support"></a>Power BI Premium veri kümesi desteği

Power BI veri kümelerine bağlanmak için Microsoft Rapor Oluşturucusu’nu veya SQL Server Veri Araçları’nı (SSDT) kullanabilirsiniz. Ardından SQL Server Analysis Services bağlantısını kullanarak söz konusu raporları Power BI Rapor Sunucusu’nda yayımlayabilirsiniz. Kullanıcıların bu senaryoyu etkinleştirebilmek için depolanmış Windows kullanıcı adı ve parolası kullanması gerekir.

#### <a name="alttext-alternative-text-support-for-report-elements"></a>Rapor öğeleri için AltText (alternatif metin) desteği

Raporları yazarken, rapordaki her öğenin metnini belirtmek için araç ipuçlarını kullanabilirsiniz. Ekran okuyucu teknolojileri bu ipuçlarını kullanacaktır.

#### <a name="azure-active-directory-application-proxy-support"></a>Azure Active Directory Uygulama Ara Sunucusu desteği

Azure Active Directory Uygulama Ara Sunucusu ile artık web veya mobil uygulamalar üzerinden güvenli erişime izin vermek için kendi web uygulaması ara sunucunuzu yönetmeniz gerekmez. Daha fazla bilgi için bkz. [Azure Active Directory'nin Uygulama Ara Sunucusu aracılığıyla şirket içi uygulamalarına uzaktan erişim](/azure/active-directory/manage-apps/application-proxy).

#### <a name="custom-headers"></a>Özel üst bilgiler

Belirtilen regex desenine uyan tüm URL’ler için üst bilgi değerleri ayarlar. Kullanıcılar seçilen istek URL’lerinin üst bilgi değerlerini ayarlamak için özel üst bilgi değerini geçerli bir XML ile güncelleştirebilir. Yöneticiler XML’de istedikleri sayıda üst bilgi ekleyebilir. Ayrıntılar için **Reporting Services Sunucusu Özellikleri Gelişmiş Sayfası** makalesindeki [CustomHeaders](/sql/reporting-services/tools/server-properties-advanced-page-reporting-services#customheaders) bölümüne bakın.

#### <a name="transparent-database-encryption"></a>Saydam Veritabanı Şifrelemesi

Power BI Rapor Sunucusu artık Enterprise ve Standard sürümleri için Reporting Services Sunucusu katalog veritabanında Saydam Veritabanı Şifrelemesi’ni destekliyor.

#### <a name="power-bi-visuals-api"></a>Power BI görselleri API’si

Bu sürümle gönderilen API sürümü 2.6.0’dır.

#### <a name="microsoft-report-builder-update"></a>Microsoft Rapor Oluşturucusu güncelleştirmesi

Rapor Oluşturucusu’nun yeni kullanıma sunulan sürümü Reporting Services’in 2016, 2017 ve 2019 sürümleriyle tam olarak uyumludur. Ayrıca Power BI Rapor Sunucusu’nun kullanıma sunulmuş ve desteklenen tüm sürümleriyle uyumludur.

## <a name="september-2019"></a>Eylül 2019

Tüm yeni özellikler hakkında ayrıntılı bilgi için [Power BI Rapor Sunucusu Eylül 2019](https://powerbi.microsoft.com/blog/power-bi-report-server-september-2019-feature-summary/) blog gönderisine bakın.

Power BI Rapor Sunucusu Eylül 2019 güncelleştirmesi, çok sayıda Power BI rapor özelliği içermektedir. Öne çıkanlardan bazıları:

- **Dilimleyiciler için görsel düzeyinde filtreler** Dilimleyicilere görsel düzeyinde filtre ekleyebilirsiniz. Diğer görsel düzeyindeki filtreler gibi sadece dilimleyiciyi filtreleyip başka bir görseli filtrelemeden çalışır. Bu filtre, boşlukları filtrelemek veya ölçüm filtreleri kullanmak istiyorsanız yararlıdır.
- **Tablo ve matris için simge kümeleri** KPI simgeleriyle, Excel’deki simge kümelerine benzer şekilde tablonuzda ve matrisinizde farklı simge kümelerini görüntülemeye yönelik kurallar oluşturabilirsiniz.
- **Görselleri gruplandırma** Şimdi görselleri, şekilleri, metin kutularını, görüntüleri ve düğmeleri tıpkı PowerPoint’te yaptığınız gibi bir rapor sayfasında birlikte gruplandırabilirsiniz. Nesneleri birlikte gruplandırdığınızda hep birlikte taşıyabilir ve yeniden boyutlandırabilirsiniz. Gruplandırma, her sayfada çok fazla nesnenin katmanlandığı raporlarda çalışmayı kolaylaştırır.
- **Yeni varsayılan temalar** Yeni tema JSON seçeneklerini desteklemek amacıyla, raporlar için kullanılabilen temaları güncelleştiriyor ve yeni raporlar için varsayılan temayı değiştiriyoruz. Yeni varsayılan tema hem Microsoft’un tasarım diline daha uygundur hem de görseller için en iyi tasarım uygulamalarını izler. 
- **Güncelleştirilmiş bölme tasarımı** Arabirimimizin büyük bölümünü yeniledik. Tüm bölmeleri, alt bilgiyi ve görünüm değiştiricisini daha açık bir renkle güncelleştirdik, aralığı güncelleştirdik ve yeni simgeler oluşturduk. Yeni tasarım, tüm arabirimi yenilemeye yönelik birinci adımdır.

Özelliklerin tam listesi aşağıda verilmiştir. 

### <a name="reporting"></a>Raporlama

- Güncelleştirilmiş bölme tasarımı
- Dilimleyiciler için görsel düzeyinde filtreler
- Performans analizi bölmesi için sıralama
- Görsel üst bilgisi araç ipuçları
- Tablo ve matris toplam etiketi özelleştirmesi
- Hiyerarşi dilimleyicisi için dilimleyiciyi eşitleme desteği
- Görsellerde tutarlı yazı tipi boyutları
- Tablo ve matrisler için simge kümeleri
- Kurallara göre koşullu biçimlendirme için yüzde desteği
- Yeni filtre bölmesi genel kullanıma sunuldu
- Dağılım grafiklerinde yürütme ekseni kullanılırken veri renkleri desteği
- Göreli tarih ve açılan dilimleyiciler kullanılırken performans iyileştirmeleri
- Görselleri gruplandırma
- Temalardaki renk ve metin sınıfları
- Yeni varsayılan temalar

### <a name="analytics"></a>Analiz

- Özel biçim dizeleri
- Biçimlendirme seçenekleri için koşullu biçimlendirme güncelleştirmeleri

    - Görsel arka plan ve başlık renkleri
    - Kart renkleri
    - Ölçer dolgusu ve renkleri
    - Alternatif metin
    - Kenarlık rengi

- Koşullu biçimlendirme uyarıları
- Detaylandırma bulunabilirlik geliştirmesi
- Yeni DAX ifadeleri: REMOVEFILTERS ve CONVERT
- Yeni DAX karşılaştırma işleci: ==

### <a name="data-preparation"></a>Veri hazırlama

- M Intellisense geliştirmeleri
- Yeni Dönüşüm: Sütunu konumlara göre bölme
- Veri profilinizden panoya kopyalama


## <a name="may-2019"></a>Mayıs 2019

### <a name="power-bi-desktop-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için Power BI Desktop

Tüm yeni özellikler hakkında ayrıntılı bilgi için [Power BI Rapor Sunucusu Mayıs 2019](https://powerbi.microsoft.com/blog/power-bi-report-server-update-may-2019/) blog gönderisine bakın.

Yayının öne çıkan bazı konuları:

#### <a name="performance-analyzer"></a>Performans çözümleyici 

Raporunuz beklediğinizden daha yavaş çalışıyorsa Power BI Desktop’ta Performans Analizi’ni deneyin. Bunu başlattığınızda, raporda yaptığınız her işlemle ilgili bilgileri içeren bir günlük dosyası oluşturur. [Performans Analizi](../create-reports/desktop-performance-analyzer.md) hakkında daha fazla bilgi edinin.

#### <a name="new-modeling-view"></a>Yeni modelleme görünümü

Power BI Desktop’taki yeni Modelleme görünümü ile, birçok tablo içeren karmaşık veri kümelerini görüntüleyebilir ve bunlarla çalışabilirsiniz. Öne çıkanlar arasında birden çok diyagram düzeni ile sütun, ölçüm ve tabloların toplu olarak düzenlenmesi bulunur. [Modelleme görünümü](../transform-model/desktop-modeling-view.md) hakkında daha fazla bilgi edinin.

#### <a name="accessible-visual-interaction"></a>Erişilebilir görsel etkileşimi

Şimdi klavye gezintisini kullanarak yerleşik görsellerin birçoğunda bulunan veri noktalarına erişebilirsiniz. [Power BI raporlarında erişilebilirlik](../create-reports/desktop-accessibility-overview.md) hakkında daha fazla bilgi edinin.

#### <a name="conditional-formatting-titles-and-web-url-actions"></a>Koşullu biçimlendirme başlıkları ve web URL’si eylemleri

Power BI raporları etkileşimlidir. Raporun geçerli durumunu yansıtmak için bir rapordaki başlıkların dinamik olması anlamlıdır. Düğme, şekil ve görüntülerinizin URL’lerini dinamik hale getirmek için ifadeye bağlı biçimlendirmenin aynısını kullanabilirsiniz. [İfade temelli başlıklar](../create-reports/desktop-conditional-format-visual-titles.md) hakkında daha fazla bilgi edinin.

#### <a name="cross-highlight-by-axis-labels"></a>Eksen etiketlerine göre çapraz vurgulama

Bir görseldeki veri noktalarını seçerken olduğu gibi, bir sayfadaki diğer öğeleri çapraz vurgulamak için görseldeki eksen kategorisi etiketlerini seçin. [Çapraz vurgulama](../create-reports/power-bi-reports-filters-and-highlighting.md#cross-filter-and-cross-highlight-visuals) hakkında daha fazla bilgi edinin.

#### <a name="all-the-new-features"></a>Tüm yeni özellikler

Tüm yeni özelliklerin listesi aşağıda verilmiştir:

#### <a name="reporting"></a>Raporlama

- Çizgi grafiklerde tek noktada çapraz vurgulama 
- Başlıklarda sözcük kaydırma 
- Varsayılan görsel etkileşimi çapraz filtreye güncelleştirme
- Görsellerin kenarlıkları için yuvarlak köşeler 
- Tekli seçim dilimleyicisi  
- Bing haritalarında ısı haritası desteği  
- Eksen etiketlerine göre çapraz vurgulama  
- Varsayılan araç ipucu biçimlendirmesi  
- Düğmeler, şekiller ve görüntüler için statik web URL’si desteği  
- Sayfa hizalama seçenekleri   
- Seçim bölmesi geliştirmeleri  
- Erişilebilir görsel etkileşimi  
- Görsel başlıkları için koşullu biçimlendirme  
- Düğme, şekil ve görüntülerde web URL eylemleri için koşullu biçimlendirme
- Performans analizi bölmesi
- Tablo ve matriste klavye ile gezinme
- Satır veri etiketi konum denetimi
- KPI görseli Gösterge metin boyutu denetimi

#### <a name="analytics"></a>Analiz

- Tarihleri hiyerarşi olarak gösterme özelliği artık genel kullanıma sunuldu  

#### <a name="modeling"></a>Modelleme

- Yeni modelleme görünümü artık genel kullanıma sunuldu
- Yeni DAX işlevleri
- ALLSELECTED DAX işlevine güncelleştirme
- Yeni raporlarda tablolara otomatik tarih eklemeyi devre dışı bırakma

### <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu

#### <a name="support-for-trusted-visuals"></a>Güvenilen görseller için destek

Power BI Rapor Sunucusu için Güvenilen Görsellere yönelik destek ekledik. Şu anda Mapbox ve PowerOn görsellerini destekliyoruz. ESRI, Visio ve PowerApps bu sürümde desteklenmemektedir.)

#### <a name="improved-security-features"></a>İyileştirilmiş güvenlik özellikleri

Yöneticilerin, engellenen mime türlerinin virgülle ayrılmış bir listesini belirtmek için kullanabileceği **RestrictedResourceMimeTypeForUpload**.

## <a name="january-2019"></a>Ocak 2019

Power BI raporlarında bu özellikler için destek:

[**Satır düzeyi güvenlik**](row-level-security-report-server.md) Power BI Rapor Sunucusu ile satır düzeyi güvenlik (RLS) ayarlandığında, belirli kullanıcıların veri erişimi kısıtlanabilir. Filtreler, veri erişimini satır düzeyinde sınırlar ve rollerin içinde filtre tanımlayabilirsiniz.

[**Matris satır üst bilgilerini genişletme ve daraltma**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#expandCollapse) Tek tek satır üst bilgilerini genişletebilme ve daraltabilme özelliği ekledik. Bu, en çok istenen görsel özelliklerden biriydi.

[ **.pbix dosyaları arasında kopyalama ve yapıştırma**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#copyPaste) Görselin bağlam menüsünden veya standart Ctrl+C klavye kısayoluyla görselleri .pbix dosyaları arasında kopyalayabilir ve Ctrl+V ile başka bir rapora yapıştırabilirsiniz.

[**Akıllı hizalama kılavuzları**](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#smartGuides) Rapor sayfanızdaki her şeyi hizalamanıza yardımcı olması için, sayfanızda nesneleri taşırken PowerPoint'teki gibi akıllı hizalama kılavuzları görürsünüz. Sayfanızdaki bir nesneyi her sürüklediğinizde veya yeniden boyutlandırdığınızda akıllı kılavuzları görürsünüz. Bir nesneyi başka bir nesnenin yakınına taşıdığınızda, taşınan nesne diğeriyle hizalı bir konuma yerleştirilir.

**Erişilebilirlik özellikleri** Listelenemeyecek kadar çok erişilebilirlik özelliği var: örneğin, [alan listesi bölmesi erişilebilirlik desteği](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#fieldList). Alan listesi bölmesi tümüyle erişilebilirdir. Yalnızca klavyenizi ve ekran okuyucuyu kullanarak bölmede gezinebilir ve bağlam menüsünü kullanarak rapor sayfanıza alanlar ekleyebilirsiniz.

#### <a name="power-bi-visuals"></a>Power BI görselleri

- Bu sürümle gönderilen API sürümü 2.3.0’dır.

### <a name="administrator-settings"></a>Yönetici ayarları

Yöneticiler sunucu grubunun SSMS Gelişmiş Özellikleri bölümünde aşağıdaki ayarları yapabilir:

**AllowedResourceExtensionsForUpload** Rapor sunucusuna yüklenebilecek kaynakların uzantılarını ayarlayın. Yerleşik dosya türlerinin uzantılarını (&ast;.rdl ve &ast;.pbix gibi) eklemek gerekmez. Varsayılan uzantılar “&ast;, &ast;.xml, &ast;.xsd, &ast;.xsl, &ast;.png, &ast;.gif, &ast;.jpg, &ast;.tif, &ast;.jpeg, &ast;.tiff, &ast;.bmp, &ast;.pdf, &ast;.svg, &ast;.rtf, &ast;.txt, &ast;.doc, &ast;.docx, &ast;.pps, &ast;.ppt, &ast;.pptx” uzantılarıdır. 

**SupportedHyperlinkSchemes** İşlenmesine izin verilen Köprü eylemlerinde tanımlanmasına izin verilen URI şemalarının virgülle ayrılmış listesini ayarlar veya tüm köprü şemalarına izin vermek için “&ast;” kullanılır. Örneğin, “http,https” ayarlandığında “https://www olabilir. contoso.com” köprülerine izin verilir ama “mailto:bill@contoso.com” veya “javascript:window.open(‘ www.contoso.com’, ‘_blank’)” köprülerine izin verilmez. Varsayılan değer “&ast;” ayarıdır.

## <a name="august-2018"></a>Ağustos 2018

Ağustos 2018, Power BI Rapor Sunucusu için Power BI Desktop sürümüne eklenen birçok yeni özelliği görür. Alana göre ayrıştırılmış şekilde bu yenilikler aşağıdaki gibidir:

- [Raporlama](#reporting)
- [Analiz](#analytics)
- [Modelleme](#modeling)

### <a name="highlights-of-the-august-2018-release"></a>Ağustos 2018 yayının öne çıkan özellikleri

Yeni özelliklerin uzun listesinde öne çıkan ilginç özellikler şunlardır. Daha fazla bilgi için [blog gönderimize](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/) bakın.

#### <a name="report-theming"></a>Rapor teması oluşturma

Raporunuzun tamamını belirli bir tema veya kurumsal kimlikle eşleştirecek şekilde hızlıca renklendirmenizi sağlayan rapor teması oluşturma özelliği, Power BI Rapor Sunucusu'nun Ağustos 2018 yayınına eklenmiştir. Bir temayı içeri aktardığınızda tüm grafikleriniz tema renklerini kullanacak şekilde otomatik olarak güncelleştirilir ve tema renklerine renk paletinden erişebilirsiniz. Tema dosyasını yüklemek için **Temayı Değiştir** düğmesinin altındaki **Temayı İçeri Aktar** seçeneğini kullanabilirsiniz.

Tema dosyası, raporunuzda kullanmak istediğiniz tüm renklere ek olarak görsellere uygulamak istediğiniz varsayılan biçimlendirmeyi içeren bir JSON dosyasıdır.
Raporun varsayılan renklerini güncelleştiren örnek bir JSON teması aşağıda verilmiştir:

```json
{
"name": "waveform",
"dataColors": [ "#31B6FD", "#4584D3", "#5BD078", "#A5D028", "#F5C040", "#05E0DB", "#3153FD", "#4C45D3", "#5BD0B0", "#54D028", "#D0F540", "#057BE0" ],
"background":"#FFFFFF",
"foreground": "#F2F2F2",
"tableAccent":"#5BD078"
}
```

#### <a name="conditional-formatting-by-a-different-field"></a>Farklı bir alan ile koşullu biçimlendirme

Bir sütunu modelinizdeki farklı bir alana göre biçimlendirme özelliği, koşullu biçimlendirmede yapılan önemli geliştirmelerden biridir.

#### <a name="conditional-formatting-by-values"></a>Değerlere göre koşullu biçimlendirme

Yeni eklenen koşullu biçimlendirme türlerinden biri de **Alana göre biçimlendir** değeridir. Alana göre biçimlendir değeri, onaltılık kod veya ad ile renk belirten bir ölçüyü veya sütunu kullanmanızı ve bu rengi arka plana veya yazı tipi rengine uygulamanızı sağlar.

#### <a name="report-page-tooltips"></a>Rapor sayfası araç ipuçları

Rapor sayfası araç ipuçları özelliği, Power BI Rapor Sunucusu'nun Ağustos 2018 güncelleştirmesine eklenmiştir. Bu özellik, raporunuzdaki diğer görseller için özel araç ipucu olarak kullanılacak bir rapor sayfası tasarlamanızı sağlar.

#### <a name="log-axis-improvements"></a>Günlük ekseni iyileştirmeleri

Kartezyen grafiklerinizdeki günlük ekseninde önemli geliştirmeler yaptık. Artık verileriniz tamamen pozitif veya tamamen negatif olduğunda birleşik harita dahil olmak üzere tüm kartezyen grafiklerin sayısal ekseni için günlük eksenini seçebilirsiniz.

#### <a name="sap-hana-sso-direct-query"></a>SAP HANA SSO Doğrudan Sorgu

Power BI Raporlarında artık Kerberos ile SAP HANA SSO Doğrudan Sorgu desteği sunulmaktadır.

>[!Note]
>Bu senaryo yalnızca SAP HANA, Power BI'da oluşturduğunuz raporlarla ilişkisel veri kaynağı olarak kullanıldığında desteklenir.  Bu özelliği Power BI Desktop uygulamasında etkinleştirmek için DirectQuery menüsünün Seçenekler bölümünden “SAP HANA’ya bir ilişkisel kaynak olarak davranma” seçeneğini işaretleyin ve Tamam'a tıklayın.

#### <a name="power-bi-visuals"></a>Power BI görselleri

- Bu yayınla birlikte 1.13.0 API sürümü kullanılmıştır.

- Artık Power BI görselleri sunucu API’sinin geçerli sürümüyle uyumlu eski bir sürüme geri dönebilir (varsa).

### <a name="reporting"></a>Raporlama 

- [Rapor Teması Oluşturma](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#theming)
- [Eylem tetikleme düğmeleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#buttons)
- [Birleşik grafik çizgisi stilleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLines)
- [Görseller için varsayılan sıralama iyileştirildi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sort)
- [Sayısal dilimleyici](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#numericSlicer)
- [Gelişmiş dilimleyici eşitleme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerSync)
- [Günlük ekseni iyileştirmeleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#logAxis)
- [Huni grafiği için veri etiketi seçenekleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#funnelChart)
- [Çizgi darbe genişliğini sıfıra ayarlama](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#lineStroke)
- [Raporlar için yüksek karşıtlık desteği](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#highContrast)
- [Halka yarıçap denetimi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#donutRadius)
- [Pasta ve halka ayrıntı etiketleri konumlandırma denetimi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#detailLabels)
- [Bir birleşik haritadaki her ölçüm için veri etiketlerini ayrı ayrı biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLabels)
- [Daha fazla esneklik ve biçimlendirmeyle yeni görsel üst bilgi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#visualHeader)
- [Duvar kağıdı biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#wallpaper)
- [Tablo ve matris için araç ipuçları](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tableTooltips)
- [Görsellerde araç ipuçlarını kapatma](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tooltips)
- [Dilimleyici erişilebilirliği](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerAccessibility)
- [Biçimlendirme bölmesi geliştirmeleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#formattingPane)
- [Çizgi grafikler ve bileşik haritalar için basamaklı çizgi desteği](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#steppedLine)
- [Sıralama deneyimi geliştirmesi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sorting)
- [PDF'ye dışarı aktar özelliğiyle rapor yazdırma (Power BI Desktop uygulamasında)](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#print)
- [Yer işareti grubu oluşturma](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#bookmarks)
- [Dilimleyici yeniden belirleme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicer)
- [Rapor sayfası araç ipuçları](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#reportPageTooltips)

### <a name="analytics"></a>Analiz

- [Yeni DAX işlevi: COMBINEVALUES()](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#combineValues)
- [Ölçü detaylandırma](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#measureDrillthrough)
- [Farklı bir alan ile koşullu biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingField)
- [Değerlere göre koşullu biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingValue)

### <a name="modeling"></a>Modelleme

- [Veri görünümünde filtreleme ve sıralama](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#filterAndSort)
- [Geliştirilmiş yerel ayar biçimlendirmesi](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#locale)
- [Ölçüler için veri kategorileri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dataCategory)
- [İstatistiksel DAX işlevleri](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dax)

## <a name="may-2018"></a>Mayıs 2018

### <a name="configure-power-bi-ios-mobile-apps-for-report-servers-remotely"></a>Uzaktan rapor sunucuları için Power BI iOS mobil uygulamalarını yapılandırma

BT yöneticisi olarak artık kuruluşunuzun MDM aracını kullanarak bir rapor sunucusuna Power BI iOS mobil uygulama erişimini uzaktan yapılandırabilirsiniz. Ayrıntılı bilgi için bkz. [Uzaktan bir rapor sunucusuna Power BI iOS mobil uygulama erişimini yapılandırma](configure-powerbi-mobile-apps-remote.md).

## <a name="march-2018"></a>Mart 2018

Mart 2018, Power BI Rapor Sunucusu için Power BI Desktop sürümüne eklenen birçok yeni özelliği görür. Alana göre ayrıştırılmış şekilde bu yenilikler aşağıdaki gibidir:

- [Görseller](#visuals-updates)
- [Raporlama](#reporting)
- [Analiz](#analytics)
- [Performans](#performance)
- [Rapor sunucusu](#report-server)
- [Diğerleri](#other-improvements)

### <a name="highlights-of-the-march-2018-release"></a>Mart 2018 yayının öne çıkan özellikleri

Yeni özelliklerin uzun listesinde öne çıkan ilginç özellikler şunlardır.

#### <a name="rule-based-conditional-formatting-for-table-and-matrix"></a>[Tablo ve matris için kural tabanlı koşullu biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)

Tablo veya matrisinizdeki özel iş mantığına dayalı bir sütunun yazı tipi rengini veya arka planı koşullu olarak renklendirmek için kurallar oluşturun.

#### <a name="show-and-hide-pages"></a>[Sayfaları gösterme ve gizleme](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

Okuyucuların raporunuza erişmesini istiyorsunuz, ancak bazı sayfalar bitmedi. Artık hazır oluncaya kadar bunları gizleyebilirsiniz. Alternatif olarak, sayfaları normal gezintiden gizleyebilirsiniz ve okuyucular yer işaretlerini veya detaylandırmayı kullanarak sayfaya erişebilir.

#### <a name="bookmarking"></a>[Yer işareti ekleme](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

Yer işareti demişken, raporunuzdaki verilerle bir hikaye anlatmak için yer işaretleri oluşturabilirsiniz.

- [Yer işaretleri için çapraz vurgulama](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): Yer işaretleri, yer işaretini oluşturduğunuz anda rapor sayfasının çapraz vurgulanan durumunu korur ve görüntüler.
- [Daha fazla yer işareti esnekliği](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): Yer işaretleri, raporunuzda ayarladığınız özellikleri yansıtır ve yalnızca seçtiğiniz görselleri etkiler.

#### <a name="multi-select-data-points-across-multiple-charts"></a>[Birden çok grafikte çoklu seçim noktaları](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

Birden çok grafikte çoklu veri noktası seçip sayfanın tamamına çapraz filtreleme uygulayabilirsiniz.

#### <a name="sync-slicers-across-multiple-pages-of-your-report"></a>[Raporunuzun birden çok sayfasında dilimleyicileri eşitleme](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

Dilimleyici, bir rapordaki bir, iki veya daha fazla sayfaya uygulanabilir.

#### <a name="quick-measures"></a>[Hızlı ölçümler](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

Bir tablodaki mevcut ölçümlere ve sayısal sütunlara dayalı yeni ölçümler oluşturabilirsiniz.

#### <a name="drilling-down-filters-other-visuals"></a>[Detaya gidildiğinde diğer görselleri de filtreleme](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

Bir görselde belirtilen bir kategoride detaya gittiğinizde, sayfadaki tüm görselleri aynı kategoriye göre filtreleyebilirsiniz.

### <a name="visuals-updates"></a>Görsellerin güncelleştirmeleri

- [Tablo ve matris için hücre hizalaması](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [Tablo ve matris sütunları için birimleri ve duyarlık denetimini görüntüleme](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [Çubuk ve sütun grafikleri için taşma veri etiketleri](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [Kartezyen ve eşleme görselleri için veri etiketi arka plan rengini denetleme](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [Çubuk/sütun doldurma denetimi](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [Grafiklerde eksen etiketleri için kullanılan alanı artırma](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [x ve y eksen gruplandırmalarıyla dağılım görseli](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [Enlem ve boylam temelli haritalar için yüksek yoğunluklu örnekleme](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [Esnek dilimleyiciler](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [Göreli tarih dilimleyici için yer işareti tarihi ekleme](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>Raporlama

- [Rapor için okuma modunda görsel üst bilgiyi kapatma](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [Yavaş veri kaynakları için rapor seçenekleri](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [Gelişmiş varsayılan görsel yerleşimi](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [Seçim bölmesi aracılığıyla görsel sıralamasını denetleme](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [Raporunuzdaki nesneleri kilitleme](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [Biçimlendirme ve analiz bölmelerinde arama](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [Alan özellikleri bölmesi ve alan açıklamaları](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>Analiz

- [UTCNOW() ve UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [Özel tarih tablosu işaretleme](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [Detaya gidildiğinde diğer görselleri de filtreleme](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [Çok satırlı kart için çok boyutlu AS modellerini hücre düzeyinde biçimlendirme](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)

### <a name="performance"></a>Performans

- [Filtrelemeye ilişkin performans iyileştirmeleri](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [DirectQuery’ye ilişkin performans iyileştirmeleri](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [Açma ve kaydetmeye ilişkin performans iyileştirmeleri](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [“Veri içermeyen öğeleri göstermeye” ilişkin iyileştirmeler](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)

### <a name="report-server"></a>Rapor sunucusu

#### <a name="export-to-accessible-pdf"></a>Erişilebilir PDF'ye dışa aktarma

Sayfalandırılmış (RDL) raporu PDF’ye dışarı aktardığınızda artık erişilebilir/etiketlenmiş bir PDF dosyası elde edebilirsiniz. Boyutu daha büyüktür, ancak ekran okuyucularının ve diğer yardımcı teknolojilerin okuması ve gezinmesi daha kolaydır. **AccessiblePDF** cihaz bilgileri ayarını **True** olarak belirleyerek erişilebilir PDF’yi etkinleştirebilirsiniz. Bkz. [PDF Cihaz Bilgileri Ayarları](/sql/reporting-services/pdf-device-information-settings) ve [Cihaz Bilgileri Ayarlarını Değiştirme](/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings).

### <a name="other-improvements"></a>Diğer iyileştirmeler

- [Örneklerden Sütun Eklemeye ilişkin iyileştirmeler](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [Danışmanlık Hizmetleri hızlı bağlantısı](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [Gelişmiş hata raporlama](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [Daha önce karşılaştığınız hataları görüntüleme](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

## <a name="october-2017"></a>Ekim 2017

### <a name="power-bi-report-data-sources"></a>Power BI raporu veri kaynakları

Power BI Rapor Sunucusu'ndaki Power BI raporları çeşitli veri kaynaklarına bağlanabilir. Verileri içeri aktarabilir, veri yenileme zamanlayabilir veya DirectQuery ya da SQL Server Analysis Services canlı bağlantısı kullanarak doğrudan sorgulayabilirsiniz. Zamanlanmış yenileme ve DirectQuery desteği sunan veri kaynaklarının listesi için bkz. "Power BI Rapor Sunucusu'ndaki Power BI raporu veri kaynakları".

### <a name="scheduled-data-refresh-for-imported-data"></a>İçeri aktarılan veriler için zamanlanmış veri yenileme

Power BI Rapor Sunucusu'nda canlı bağlantı veya DirectQuery yerine ekli bir model kullanarak Power BI raporlarındaki verileri güncel tutmak için zamanlanmış veri yenileme özelliğini kullanabilirsiniz. Ekli bir model ile verileri içeri aktarırsınız ve verilerin özgün veri kaynağıyla bağlantısı kesilir. Verilerin güncel tutulması için güncelleştirilmesi gerekir ve bunu zamanlamış yenileme ile gerçekleştirebilirsiniz. "Power BI Rapor Sunucusu'ndaki Power BI raporları için zamanlanmış yenileme" hakkında daha fazla bilgi edinin.

### <a name="editing-power-bi-reports-from-the-server"></a>Power BI raporlarını sunucuda düzenleme

Power BI raporu (.pbix) dosyalarını sunucuda açıp düzenleyebilirsiniz ancak bu durumda, karşıya yüklediğiniz özgün dosyaya dönersiniz. **Veriler sunucu tarafından yenilenmişse dosyayı ilk açtığınızda veriler yenilenmez**. Değişiklikleri görmek için dosyayı el ile yenilemeniz gerekir.

### <a name="large-file-uploaddownload"></a>Büyük dosyaları karşıya yükleme/indirme

SQL Server Management Studio'daki (SSMS) Rapor Sunucusu ayarlarında sınır 1 GB olarak belirtilmiş olsa da en fazla 2 GB boyutundaki dosyaları karşıya yükleyebilirsiniz.  Bu dosyalar veritabanında SharePoint'te olduğu gibi depolanır ve SQL Server kataloğu için özel bir yapılandırma gerekmez.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Paylaşılan veri kümelerine OData akışı olarak erişme

Paylaşılan veri kümelerine Power BI Desktop'tan OData akışı ile erişebilirsiniz. Daha fazla bilgi için bkz. [Power BI Rapor Sunucusu'nda, paylaşılan veri kümelerine OData akışları olarak erişme](access-dataset-odata.md).

### <a name="scale-out"></a>Ölçeği genişletme

Bu sürüm, ölçeği genişletme desteği sunmaktadır. En iyi deneyim için yük dengeleyici kullanın ve sunucu benzeşimi oluşturun. Senaryo henüz ölçeği genişletme için en iyi duruma getirilmemiştir. Bu nedenle, modellerin birden fazla düğümde çoğaltıldığını görebilirsiniz. Bu senaryo Ağ Yükü Dengeleyici ve kalıcı oturum desteği olmadan çalışacaktır. Ancak, bu durumda model N kez yüklendiği için düğümler arasında fazla bellek kullanımının yanı sıra model, istekler arasında yeni bir düğümle karşılaştığında akış yapılacağından bağlantılar arası performans düşüklüğü yaşanır.  

### <a name="administrator-settings"></a>Yönetici ayarları

Yöneticiler sunucu grubunun SSMS Gelişmiş Özellikleri bölümünde aşağıdaki ayarları yapabilir:

- EnableCustomVisuals: True/False
- EnablePowerBIReportEmbeddedModels: True/False
- EnablePowerBIReportExportData: True/False
- MaxFileSizeMb: Varsayılan değer şimdi 1000'dir
- ModelCleanupCycleMinutes: Bellekteki modelleri çıkarmak için denetleme sıklığı
- ModelExpirationMinutes: Son kullanılma zamanına bağlı olarak modelin süresinin dolması ve çıkarılması için beklenecek süre
- ScheduleRefreshTimeoutMinutes: Modelde veri yenilemenin ne kadar sürebileceği. Varsayılan değeri iki saattir.  Kesin bir üst sınır yoktur.

**rsreportserver.config yapılandırma dosyası**

```xml
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>Geliştirici API'si

SSRS 2017 için yayımlanmış olan geliştirici API'si (REST API), Power BI Rapor Sunucusu için genişletilerek hem Excel dosyaları hem de .pbix dosyalarıyla çalışacak şekilde geliştirilmiştir. Olası kullanım senaryolarından biri sunucudaki dosyaları programlama yoluyla indirmek, yenilemek ve yeniden yayımlamaktır. Örneğin, bu, PowerPivot modellerine sahip Excel çalışma kitaplarını yenilemenin tek yoludur.

Daha büyük dosyalar için yeni bir API vardır ve bu Swagger'ın Power BI Rapor Sunucusu sürümünde güncelleştirilecektir. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SQL Server Analysis Services (SSAS) ve Power BI Rapor Sunucusu bellek ayak izi

SQL Server Analysis Services (SSAS) artık Power BI Rapor Sunucusu içinde barındırılmaktadır. Bu durum zamanlanmış yenilemeye özgü değildir. SSAS hizmetinin barındırılması sayesinde rapor sunucusu bellek ayak izi önemli ölçüde genişletilebilir. AS.ini yapılandırma dosyası sunucu düğümleri üzerinde mevcuttur. Bu nedenle SSAS konusunda bilgi sahibiyseniz maksimum bellek sınırı ve diski önbelleğe alma gibi özellikler de dahil olmak üzere bu ayarları güncelleştirebilirsiniz. Ayrıntılar için bkz. [Analysis Services'deki sunucu özellikleri](/sql/analysis-services/server-properties/server-properties-in-analysis-services).

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Excel çalışma kitaplarını görüntüleme ve bunlarla etkileşim kurma

Excel ve Power BI, sektörde benzeri olmayan bir araç portföyü sunabilir. Bu iki uygulama bir arada kullanıldığında iş analistlerine verileri toplama, şekillendirme, çözümleme ve görsel olarak inceleme konusunda kolaylık sunar. İş kullanıcıları, Power BI raporlarını web portalında görüntülemenin yanı sıra Power BI Rapor Sunucusu'nda Excel çalışma kitaplarını görüntüleyerek tek noktadan kendilerine ait Microsoft BI içeriğini yayımlayabilir ve görüntüleyebilir.

[Power BI Rapor Sunucusu önizleme ortamınıza Office Online Server (OOS) eklemeye ilişkin adım adım yönergelerin sağlandığı bir kılavuz](excel-oos.md) yayımladık. Toplu Lisanslama hesabına sahip müşteriler OOS uygulamasını Toplu Lisanslama Hizmeti Merkezi'nden ücretsiz indirerek yalnızca görüntüleme işlevini kullanabilir. Kullanıcılar, yapılandırmanın ardından aşağıdaki koşulları karşılayan Excel çalışma kitaplarını görüntüleyebilir ve bunlarla etkileşim kurabilir:

- Dış veri kaynağı bağımlılıklarına sahip olmayan
- Dış SQL Server Analysis Services veri kaynağına yönelik bir canlı bağlantıya sahip olan
- PowerPivot veri modeline sahip olan

### <a name="support-for-new-table-and-matrix-visuals"></a>Yeni tablo ve matris görselleri için destek

Power BI Rapor Sunucusu artık yeni Power BI tablo ve matris görsellerini desteklemektedir. Bu görsellerle rapor oluşturmak için Power BI Desktop uygulamasının Ekim 2017 sürümünü kullanmanız gerekir. Bu sürümü Power BI Desktop (Haziran 2017) yan yana yükleyebilirsiniz. Power BI Desktop uygulamasının en güncel sürümü için [Power BI Rapor Sunucusu indirme sayfasında](https://powerbi.microsoft.com/report-server/)**Gelişmiş indirme seçenekleri**'ne tıklayın.

## <a name="june-2017"></a>Haziran 2017

- Power BI Rapor Sunucusu genel kullanıma (GA) sunuldu.

## <a name="may-2017"></a>Mayıs 2017

- Power BI Rapor Sunucusu Önizleme kullanıma sunuldu
- Power BI raporlarını şirket içi ortamda yayımlama olanağı
  - Power BI görselleri desteği
  - Daha fazla veri kaynağı için **Analysis Services canlı bağlantı*- desteği yakında kullanıma sunulacaktır.
  - Power BI Mobil uygulaması Power BI Rapor Sunucusu'nda barındırılan Power BI raporlarını görüntüleyecek şekilde güncelleştirildi
- Yorumlar eklenerek raporlardaki işbirliği özellikleri geliştirildi

## <a name="next-steps"></a>Sonraki adımlar

Power BI Rapor Sunucusu'ndaki yeni özelliklerden sürekli olarak haberdar olmak için bu kaynakları kontrol edin.

- [Microsoft Power BI blogu](https://powerbi.microsoft.com/blog/)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
