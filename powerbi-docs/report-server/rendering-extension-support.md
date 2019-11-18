---
title: PDF İşleme Uzantısı ISO 14289-1 uyumluluğu - Power BI Rapor Sunucusu
description: Bu belgede Power BI Rapor Sunucusu ile SQL Reporting Services PDF İşleme Uzantısı'nın ISO 14289-1 (PDF/UA) belirtimlerine uyumluluğu açıklanmaktadır.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/04/2019
ms.author: maggies
ms.openlocfilehash: c800ee995bc3c03b3cbcda91503e6dea9495f6b5
ms.sourcegitcommit: 721cf375627b010e8ad12c4c668295f38d450a17
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73638092"
---
# <a name="pdf-rendering-extension-conformance-to-iso-14289-1---power-bi-report-server"></a>PDF İşleme Uzantısı ISO 14289-1 uyumluluğu - Power BI Rapor Sunucusu 

Aşağıdakiler cihazlar için geçerlidir: Power BI Rapor Sunucusu ve SQL Reporting Services

Bu belgede Power BI Rapor Sunucusu ile SQL Reporting Services PDF İşleme Uzantısı'nın [ISO 14289-1 (PDF/UA)](https://www.pdfa.org/publication/pdfua-in-a-nutshell/) belirtimlerine uyumluluğu açıklanmaktadır.

> [!NOTE]
> Tarayıcınızdan **Yazdır**’ı ve ardından **PDF olarak kaydet**’i seçerek bu teknik incelemeyi yazdırabilir veya kaydedebilirsiniz.

## <a name="1--scope"></a>1.  Kapsam

Uygulanamaz

## <a name="2--normative-references"></a>2.  Normatif başvurular

Uygulanamaz

## <a name="3--terms-and-definitions"></a>3.  Terimler ve tanımlar

Uygulanamaz

## <a name="4--notation"></a>4.  Gösterim

Uygulanamaz

## <a name="5-version-identification"></a>5. Sürüm Tanımlama

PDF İşleme Uzantısı, bu belgede açıklanan şekilde PDF/UA desteği sunar. Aşağıda belirtilen bazı durumlarda, PDF dosyasının PDF/UA ile tam uyumlu olması için kullanıcının gerçekleştirmesi gereken bazı adımlar vardır.  Kullanıcının bu sürecin son adımı olarak uygun PDF/UA sürümünü ve uyumluluk tanımlayıcılarını ekleyerek PDF dosyasını PDF/UA ile tam olarak uyumlu hale getirmek için gerekli işlemlerin yapıldığını belirtmesini bekliyoruz.

Bu belgede belirtilen tüm bilgiler, PDF belgesi işleme sırasında AccessiblePdf cihaz bilgileri ayarının `true` olarak ayarlanmasına dayanmaktadır. Bazı durumlarda Rapor Tanımlama Dili (RDL) kısıtlamalarından kaynaklı uyumluluk sınırlamaları mevcuttur.

## <a name="6--conformance-requirements"></a>6.  Uyumluluk gereksinimleri

|     Ölçütler     |     Destekleyici Özellik     |     Açıklamalar      |
|----|--------|--------|
|    6.1 Genel    |                 Destekleniyor    |    PDF İşleme Uzantısı, PDF sürüm 1.7 belgeleri oluşturur.    |
|    6.2 Uyumlu dosyalar    |                 Destekleniyor, özel durumlar mevcut    |    Dosya biçimi gereksinimleri başlıklı 7. bölümdeki açıklamalara bakın.    |
|    6.3 Uyumlu okuyucu    |     Uygulanamaz     |         |
|    6.4 Uyumlu yardımcı teknoloji    |     Uygulanamaz     |         |

## <a name="7--file-format-requirements"></a>7.  Dosya biçimi gereksinimleri

|     Ölçütler     |     Destekleyici Özellik     |     Açıklamalar      |
|-----|-------|------------------------|
|    7.1 Genel    |                 Destekleniyor, özel durumlar mevcut    |    Tüm gerçek içerikler ISO 32000-1:2008, 14.8 ile belirtilen şekilde etiketlenmelidir. Yapıtlar (ISO 32000-1:2008, 14.8.2.2.2), yapı ağacında etiketlenmemelidir. <li> PDF İşleme Uzantısı, belirli öğelerin yapıt olarak işaretlenmesini desteklemediğinden ISO 32000-1:2008, 14.8.2.2.2 ölçütlerine uyan her şeyi yapıt olarak işaretleyecektir.<br>İçerik, yapı ağacında semantik açıdan uygun etiketlerle ve mantıksal okuma sırasına göre işaretlenmelidir. <br> **Not** 4: WCAG 2.0, Yönerge 1.4 içinde karşıtlık, renk ve diğer erişilebilirlik biçimlendirmeleriyle ilgili sorunlar açıklanmıştır. <br><li> Belgenin bu sorunlardan arındırılmış olmasını sağlamak, kullanıcının sorumluluğundadır. <br>ISO 32000-1:2008, 14.8.4 ile tanımlanmış olan standart etiketler yeniden eşlenmemelidir. <li> PDF İşleme Uzantısı, standart etiketleri yeniden eşlemez. Belgeler, "Document" kök öğesiyle başlar. <br>Bu Uluslararası Standart ile uyumlu olduğunu beyan eden dosyaların "Suspects" değeri "false" (ISO 32000-1:2008, Tablo 321) olmalıdır. <li> PDF İşleme Uzantısında "Suspects" girişi yoktur. Bu özellik isteğe bağlıdır.    |
|    7.2 Metin    |                 Destekleniyor, özel durumlar mevcut    |    İçerik, mantıksal okuma sırasına göre etiketlenmelidir. Belge içeriğindeki her bir mantıksal öğe için semantik açıdan en uygun etiket kullanılmalıdır. <br><li> PDF İşleme Uzantısı, içeriği mümkün olduğunca mantıksal okuma sırasında etiketler.<br>Karakter kodları, ISO 32000-1:2008, 14.8.2.4.2 ile tanımlanan Unicode değerleriyle eşleşmelidir. Unicode belirtiminde yer almayan karakterler, Unicode özel kullanım alanını kullanabilir veya farklı bir karakter kodlaması bildirebilir. <br>Doğal dil, ISO 32000-1:2008, 14.9.2 ve/veya ISO 32000-1:2008, 7.9.2 ile anlatıldığı gibi bildirilmelidir. Doğal dildeki değişiklikler bildirilmelidir. Metin dizelerinin (alternatif açıklamalar gibi) içindeki doğal dil değişiklikleri, ISO 32000-1:2008, 14.9.2.2 ile tanımlanan dil tanımlayıcıları kullanılarak bildirilmelidir. <br><li> PDF İşleme Uzantısı, yalnızca belge düzeyinde doğal dil bildirimi gerçekleştirir    |
|    7.3 Grafikler    |                 Destekleniyor, özel durumlar mevcut    |    Metin nesneleri dışındaki grafik nesneleri, ISO 32000-1:2008, 14.8.4.5, Tablo 340 ile belirtilen şekilde "Figure" olarak etiketlenmelidir. Aşağıdaki özel durumlardan herhangi birinin geçerli olması halinde grafik bir yapıt olarak etiketlenmelidir: <br><li> Grafikte anlamlı içerik mevcut değilse veya <li>  Grafik bir bağlantı ek açıklamasının arka planında görünüyorsa. Bu durumda bağlantının alternatif metni hem grafiği hem de bağlantıyı açıklamalıdır. <li> PDF İşleme Uzantısı, grafik nesnelerini "Figure" olarak etiketler. <br>Şeklin resim yazısı, "Caption" etiketiyle etiketlenmelidir. <li> PDF İşleme Uzantısı, şu an için resim yazılarını şekillerin üzerine "Caption" etiketiyle eklememektedir. <br>"Figure" etiketleri, ISO 32000-1:2008, 14.7.2, Tablo 323 ile belirtildiği üzere "Figure" etiketiyle işaretlenmiş olan içeriği temsil eden alternatif bir belirtim veya metin içermelidir. <br>**Not** 1: Ayrıca bkz. WCAG 2.0, Yönerge 1.1. <br>Bir grafikte belirtilen metnin, insan olan okuyucular tarafından okunması beklenen doğal dilde bir metin olmaması durumunda grafiğin doğasını veya amacını belirten alternatif metin sağlanmalıdır. <br>**Not** 2: Bir dil tarafından kullanılan örnek harfleri veya yazı sistemini içeren metin, doğal dil olmayan metinlere örnek verilebilir.   PDF İşleme Uzantısı, şekiller üzerindeki alternatif metinleri destekler ancak alternatif metin ekleme kararı kullanıcıya aittir. <br>"BBox" özniteliğiyle ilgili ek not: <br><li> PDF İşleme Uzantısı şu anda "BBox" özniteliğini yazmamaktadır. <li> Geçici çözüm olarak çizimleri yeni "Figure" öğeleri veya yapıtlar olarak el ile yeniden etiketleyebilirsiniz.    |
|    7.4 Başlıklar    |                 Uygulanamaz    |    RDL, başlıkların herhangi bir şekilde işaretlenmesini desteklemez. Bunları uygun şekilde etiketlemek kullanıcının sorumluluğundadır.    |
|    7.5 Tablolar    |                 Destekleniyor, özel durumlar mevcut    |    Tablolar, üst bilgileri içermelidir. Tablo üst bilgileri, ISO 32000-1:2008, Tablo 337 ve Tablo 349 ile belirtilen şekilde etiketlenmelidir. <br>**Not** 1: Tablolarda sütun üst bilgileri, satır üst bilgileri veya ikisi birden kullanılabilir. <br>**Not** 2: Yardımcı teknolojilerin kullanıldığı durumlarda tabloların yapısıyla ilgili mümkün olan en fazla bilginin sunulması gerekir. Üst bilgiler, yapısal bilgilerin sunulması konusunda oldukça önemli bir role sahiptir. <br><li> Tabloya üst bilgi ekleyip eklememek kullanıcının tercihidir. RDL ve PDF İşleme Uzantısı, satır üst bilgilerini destekler. <br>  TH türündeki yapı öğelerinde "Scope" özniteliği bulunmalıdır.   <li> PDF İşleme Uzantısı, TH öğelerinde "Column" ve "Row" üyeleri için "Scope" özniteliğine sahiptir ancak "Corner" hücreleri için destek sunmaz.<br>Tablo etiketleme yapıları yalnızca mantıksal satır ve/veya sütun ilişkileri kapsamında sunulan içeriğin etiketlenmesi için kullanılmalıdır.   <li> Bu durum, kullanıcının RDL içinde tabloları ne şekilde kullanmayı seçtiğine göre değişir.    |
|    7.6 Listeler    |                 Uygulanamaz    |    RDL, listelerin işaretlemesini desteklemez. RDL'de listeler yapısal açıdan tek bir tablo hücresine sahip tablolar gibidir. <br>Bunları uygun şekilde yeniden etiketlemek kullanıcının sorumluluğundadır.    |
|    7.7 Matematiksel ifadeler    |                 Destekleniyor, özel durumlar mevcut    |    Tüm matematiksel ifadeler, ISO 32000-1:2008, 14.8.4.5 ile belirtilen şekilde bir "Formula" etiketi içinde sunulmalı ve bir "Alt" özniteliğine sahip olmalıdır. <br><li> PDF İşleme Uzantısı şu an için matematiksel ifadeleri "Formula" etiketine almamaktadır. <br>Karakterlerin ISO 32000-1:2008, 9.10.2 ve 14.8.2.4 ile belirtilen şekilde Unicode olarak eşlenmesi, matematiksel ifadeler için de geçerlidir. <br><li> Bu özellik PDF İşleme Uzantısı tarafından desteklenir.    |
|    7.8 Sayfa üst bilgileri ve alt bilgileri    |                 Destekleniyor    |    Sürekli üst bilgiler ve alt bilgiler, "Pagination" yapıtları olarak tanımlanmalı ve ISO 32000-1:2008, 14.8.2.2.2, Tablo 330 uyarınca "Header" veya "Footer" alt türleri olarak sınıflandırılmalıdır. <br><li> Üst Bilgiler veya Alt Bilgiler, yapıt olarak etiketlenir ve o şekilde işlenir.    |
|    7.9 Notlar ve başvurular    |                 Uygulanamaz    |    PDF İşleme Uzantısı, notların ve başvuruların işaretlenmesini desteklemez. <br>Bunları uygun şekilde etiketlemek kullanıcının sorumluluğundadır.    |
|    7.10 İsteğe bağlı içerik    |                 Uygulanamaz    |         |
|    7.11 Eklenmiş dosyalar    |                 Uygulanamaz    |         |
|    7.12 Makale parçacıkları    |                 Uygulanamaz    |         |
|    7.13 Dijital imzalar    |                 Uygulanamaz    |         |
|    7.14 Etkileşimli olmayan formlar    |                 Uygulanamaz    |         |
|    7.15 XFA    |                 Uygulanamaz    |         |
|    7.16 Güvenlik    |                 Uygulanamaz    |         |
|    7.17 Gezinti    |                 Destekleniyor    |    Bir belgede okuma sırası ve gezinti hedeflerinin düzeyiyle eşleşen bir belge ana hattı olmalıdır (ISO 32000-1:2008, 12.3.3). <br><li> RDL, rapor öğesi için yer işaretlerini destekler ancak bu seçenek kullanıcı tarafından seçilmelidir. Daha sonra bu yer işaretleri, PDF İşleme Uzantısı tarafından belge ana hattı olarak işlenir. <br>Varsa "PageLabels" numara ağacındaki (ISO 32000-1:2008, 7.7.2, Tablo 28) girişler de semantik açıdan uygun olmalıdır. <br><li> PDF İşleme Uzantısı, "PageLabels" numara ağacı eklemez.    |
|    7.18 Ek Açıklamalar    |                 Uygulanamaz    |    RDL, ek açıklamaları desteklemez    |
|    7.21 Yazı tipleri    |                 Destekleniyor    |         |
|    7.21.1 Genel    |                 Destekleniyor    |         |
|    7.21.2 Yazı tipi türleri    |                 Destekleniyor    |         |
|    7.21.3 Bileşik yazı tipleri    |                 Destekleniyor    |         |
|    7.21.3.1 Genel    |                 Destekleniyor    |         |
|    7.21 3.2 CIDFonts    |                 Destekleniyor    |         |
|    7.21.3.3 CMaps    |                 Destekleniyor    |         |
|    7.21.4 Ekleme    |                 Destekleniyor    |         |
|    7.21.4.1 Genel    |                 Destekleniyor    |         |
|    7.21.4.2 Alt küme ekleme    |                 Destekleniyor    |         |
|    7.21.5 Yazı tipi ölçümleri    |                 Destekleniyor    |         |
|    7.21.6 Karakter kodlamaları    |                 Destekleniyor    |         |
|    7.21.7 Unicode karakter eşlemeleri    |                 Destekleniyor    |         |
|    7.21.8 .notdef karakterinin kullanımı    |                 Destekleniyor    |         |

## <a name="8--conforming-reader-requirements"></a>8.  Uyumlu okuyucu gereksinimleri

Uygulanamaz

## <a name="9--at-requirements"></a>9.  AT gereksinimleri

Uygulanamaz

## <a name="disclaimer"></a>Sorumluluk Reddi

© 2017 Microsoft Corporation. Tüm hakları saklıdır. Burada adı geçen gerçek şirket ve ürünlerin adları, ilgili sahiplerinin ticari markaları olabilir. Bu belgede yer alan bilgiler, yayın tarihi itibarıyla Microsoft Corporation'ın söz konusu durumlarla ilgili geçerli görüşlerini temsil etmektedir. Microsoft, sunulan bilgilerin yayın tarihinden sonra doğru olduğunu garanti edemez. Microsoft, web sitelerini ürünlerin erişilebilirliği konusunda elde edilen yeni bilgilerle düzenli olarak güncelleştirmektedir.

Ürünün özelleştirilmesi, Microsoft tarafından sunulan bu uyumluluk bildirimini geçersiz kılacaktır. Belirli Yardımcı Teknoloji (AT) ürünleri hakkında uyumluluk bilgileri için lütfen AT ürünü satıcılarıyla iletişime geçin.

Bu belge yalnızca bilgilendirme amaçlıdır. MICROSOFT BURADA SAĞLANAN BİLGİLER KONUSUNDA AÇIK VEYA ÖRTÜLÜ HİÇBİR GARANTİ VERMEZ.


## <a name="next-steps"></a>Sonraki adımlar
[Yönetici genel bakışı](admin-handbook-overview.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

