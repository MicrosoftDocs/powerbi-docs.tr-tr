---
title: Sertifikalı Power BI görselleri
description: Sertifika için özel görsel gönderme işlemi ve gereksinimleri. Daha önce sertifikalanan Power BI görselleri listesi.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 12/02/2019
ms.openlocfilehash: 0a39496ade27cd45fae116eea92ef4b472e04582
ms.sourcegitcommit: 5bb62c630e592af561173e449fc113efd7f84808
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2019
ms.locfileid: "74999756"
---
# <a name="get-a-power-bi-visual-certified"></a>Power BI görseli için sertifika alın

Sertifikalı Power BI görselleri, *Markette* bulunan ve *Microsoft Power BI ekibinin* test ettiği ve onayladığı *belirli kod* gereksinimlerini karşılayan görsellerdir. Testler görselin dış hizmetlere veya kaynaklara erişmediğini denetleyecek şekilde tasarlanmıştır.

Sertifikalı Power BI görselleri ve [standart Power BI görselleri](power-bi-custom-visuals.md) aynı şekilde kullanılır. Bunlar [Power BI Desktop](../desktop-what-is-desktop.md)'a ve [Power BI hizmetine](../power-bi-service-overview.md) eklenebilir; [Power BI Mobil](../consumer/mobile/mobile-apps-for-mobile-devices.md) ve [Power BI Embedded](embedding.md) ile görüntülenebilir.

Sertifikasyon işlemi isteğe bağlı bir işlemdir. Power BI görsellerini markette sertifikalama kararı tamamen geliştiricilere aittir. Power BI görseli sertifikalandığında, daha fazla özellik sunar. Örneğin görseli [PowerPoint'e aktarabilirsiniz](../consumer/end-user-powerpoint.md) veya bir kullanıcı [rapor sayfalarına abone olduğunda](../consumer/end-user-subscribe.md) alınan e-postalarda görüntüleyebilirsiniz.

Sertifikalı olmayan Power BI görsellerinin, güvenli olmayan görseller olması şart değildir. Bazı görseller sertifikalanmamıştır çünkü [sertifikasyon gereksinimlerinin](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) biriyle veya birden çoğuyla uyumlu değildir. Örneğin, harita görselleri gibi dış hizmetlere bağlanan veya ticari kitaplıkları kullanan görseller böyledir.

Bir web geliştiricisi olarak kendi Power BI görsellerinizi oluşturmakla ve  [Microsoft AppSource](https://appsource.microsoft.com)'a eklemekle ilgileniyorsanız,  [Power BI görseli oluşturma](visuals/custom-visual-develop-tutorial.md) öğreticisiyle başlayın.

> [!NOTE]
> Üçüncü taraf Power BI görsellerinin yazarı **Microsoft** *değildir*. Üçüncü taraf görsellerinin işlevselliğini doğrulamak için doğrudan görselin yazarına başvurmasını öneririz.

> [!IMPORTANT]
> Microsoft kendi takdirine bağlı olarak, bir Power BI görselini [sertifikalı listesinden](#list-of-power-bi-visuals-that-have-been-certified) kaldırabilir.

## <a name="certification-requirements"></a>Sertifikasyon gereksinimleri

Power BI görselinizin [sertifikalı](#get-a-power-bi-visual-certified) olmasını sağlamak için, Power BI görselinizin bu bölümde listelenen gereksinimleri karşıladığından emin olun. 

> [!TIP]
> Göndermeden önce kodunuzu doğrulamak için varsayılan güvenlik kuralı setiyle EsLint'i kullanmanızı öneririz.

* Microsoft Satıcı Panosu ve İş Ortağı Merkezi onaylıdır. Power BI görselinizin [marketimizde](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) bulunması gerekir.
* Power BI görseli *API v2.5* veya sonraki bir sürümle yazılmıştır.
* Kod deposu Power BI ekibi tarafından gözden geçirilebilir. Örneğin kaynak kodun okunabilir bir biçimi (JavaScript veya TypeScript), GitHub aracılığıyla bize sağlanmıştır.

    >[!NOTE]
    > Kodunuzu Github'da genel paylaşıma açmanız gerekmez.

* Kod deposu gereksinimleri:
  * Şu dosyaları içermelidir:
    * .gitignore
    * capabilities.json
    * pbiviz.json
    * package.json
    * package-lock.json
    * tsconfig.json
  * *node_modules* klasörünü içermemelidir (*node_modules* klasörünü .gitingore* dosyasına ekleyin).
  * *npm install* komutu herhangi bir hata döndürmemelidir.
  * *npm audit* komutu yüksek veya orta düzeyde herhangi bir uyarı döndürmemelidir.
  * *pbiviz package* komutu herhangi bir hata döndürmemelidir.
  * Geçersiz kılma yapılandırmaları olmadan [Microsoft'tan TSlint](https://www.npmjs.com/package/tslint-microsoft-contrib)'i içermelidir. Bu komut hiçbir lint hatası döndürmemelidir.
   * Power BI görselinin derlenen paketinin gönderilen paketle eşleşmesi gerekir (her iki dosyanın da md5 karması eşit olmalıdır).
* Kaynak Kodu gereksinimleri:
   * Power BI görselinin [Olay İşleme API’sini](https://microsoft.github.io/PowerBI-visuals/docs/how-to-guide/rendering-events/) desteklemesi gerekir.
   * Herhangi bir rastgele/dinamik kodun çalıştırılmadığından emin olun (bad: eval(), unsafe to use of settimeout(), requestAnimationFrame(), setinterval(some function with user input), running user input/data).
   * DOM’nin güvenli bir şekilde yönlendirildiğinden emin olun (bad: innerHTML, D3.html(<some user/data input>), kullanıcı girişini/verilerini DOM’ye eklemeden önce temizleme yapın.
   * Herhangi bir giriş verisi için tarayıcı konsolunda javascript hataları veya özel durumları olmadığından emin olun. Kullanıcılar Power BI görselinizi farklı bir beklenmedik veri aralığıyla kullanabilir, bu yüzden görsel başarısız olmamalıdır. [Bu örnek raporu](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) test veri kümesi olarak kullanabilirsiniz.

* *Capabilities.json* dosyasındaki bir özellik değiştirilirse, mevcut kullanıcıların raporlarını bozmadığından emin olun.

* Power BI görselinin, [Power BI görsellerine ilişkin yönergelerle](./guidelines-powerbi-visuals.md) uyumlu olduğundan emin olun.
    
* Kodunuz yalnızca genel olarak gözden geçirilebilen genel JavaScript veya TypeScript kitaplıkları gibi bileşenleri kullanabilir. Kaynak kod gözden geçirilebilir olmalı ve bilinen güvenlik açıklarını içermemelidir. Ticari bir bileşen kullanarak özel görseli doğrulayamayız.

* Power BI görseli dış hizmetlere ya da kaynaklara erişmemelidir. Örneğin, Power BI'dan hizmetlere hiçbir HTTP/S veya WebSocket isteği gidemez. 

## <a name="submitting-a-power-bi-visual-for-certification"></a>Power BI görselini sertifikasyon için gönderme

İş Ortağı Merkezi üzerinden Power BI görselinizin Power BI ekibi tarafından sertifikalanmasını isteyebilirsiniz.

>[!TIP]
>Power BI sertifikasyon işlemi zaman alabilir. Yeni Power BI görseli oluşturuyorsanız, Power BI sertifikasyonu istemeden önce Power BI görselinizi İş Ortağı Merkezi'nde yayımlamanızı öneririz. Bu şekilde görselinizin yayımlanmasını geciktirmemiş olursunuz.

Power BI sertifikasyonu istemek için:

1. İş Ortağı Merkezi'nde oturum açın.
2. **Genel bakış sayfasında** Power BI görselinizi seçin ve **Ürün** kurulum sayfasına gidin.
3. **Power BI sertifikasyonu iste** onay kutusunu seçin.
4. **Gözden geçir ve yayımla** sayfasındaki **Sertifikasyon notları** onay kutusunda, kaynak kodun bağlantısını ve bu bağlantıya erişmek için gereken kimlik bilgilerini sağlayın.

>[!NOTE]
> Power BI görseli gönderim işleminin ortasındaysanız ve [Satıcı Panosu](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store)'nu (eski yönetim aracı) kullanmanız gerekirse, [Satıcı Panosu sertifikasyon gönderim işlemi](seller-dashboard.md#seller-dashboard-certification-submission-process) yönergelerini gözden geçirin.

## <a name="list-of-power-bi-visuals-that-have-been-certified"></a>Sertifikalanan Power BI görselleri listesi

| Bağlantı | Video |
| --- | --- |
| [3AG Systems - Bar Chart With Relative Variance](https://appsource.microsoft.com/en/product/power-bi-visuals/WA104381912) | |
| [3AG Systems - Column Chart With Relative Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803) | |
| [Gelişmiş Halka Görsel](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941) | |
| [Gelişmiş Ağ Görselleştirmesi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942) | |
| [Gelişmiş TimeSeries Görseli](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943) | |
| [Gelişmiş Birleşik Görsel](https://appsource.microsoft.com/product/power-bi-visuals/WA104381944) | |
| [Aster Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759) | |
| [Beyondsoft Calendar](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096) | |
| [MAQ Software Bowtie Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838) | [Video](https://youtu.be/So5xKMSpVJI) |
| [Kutu ve Çizgi grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831) | |
| [MAQ Software Box and Whisker Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351) | [Video](https://youtu.be/JoHaFLfhXdo) |
| [MAQ Software Brick Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836) | [Video](https://youtu.be/hA3DOsvn2xY) |
| [Akvelon Bubble Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340) | |
| [Bullet Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755) | [Video](https://youtu.be/AOlsFYkfkcw) |
| [Bullet Chart by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953) | [Video](https://youtu.be/mtvUNl9bMjA) |
| [Calendar by Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146) | |
| [OKViz Candlestick](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952) | [Video](https://youtu.be/nT_18gyRxPo) |
| [OKViz Card with States](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967) | |
| [Chiclet Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756) | |
| [Chord](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761) | [Video](https://youtu.be/AQvd2FhRyCI) |
| [MAQ Software Circular Gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837) | [Video](https://youtu.be/9NHXALkBXuY) |
| [Küme Eşleme](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806) | |
| [MAQ Software Cylindrical Gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | [Video](https://youtu.be/DgdoWi7Gcxo) |
| [Kadranlı Ölçer](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) | |
| [Noktalı Çizim](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760) | |
| [Dot Plot by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949) | [Video](https://youtu.be/By16pX9KT40) |
| [Ayrıntılı Kartogram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045) | |
| [Ayrıntılı Koroplet](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044) | |
| [Ayrıntılı sütun grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857) | [Video](https://youtu.be/lBy2gQQ5YsQ) |
| [Zamana bağlı veriler için ayrıntılı sütun grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881) | [Video](https://youtu.be/T_mRou18vx0) |
| [Ayrıntılı halka grafik](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | [Video](https://youtu.be/AUVFrSHmPeo) |
| [Dual KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774) | |
| [MAQ Software Dynamic Tooltip](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983) | [Video](https://youtu.be/Z-tl97BpEr0) |
| [Gelişmiş Dağılım](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762) | [Video](https://youtu.be/xCfM0cjM4do) |
| [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112) | |
| [Enlighten Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960) | |
| [Enlighten Stack Shuffle](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849) | |
| [Enlighten Waffle Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850) | |
| [Devscope Filter by List](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413) | [Video](https://youtu.be/RetEWGwBu0I) |
| [Zorla Yönlendirilmiş Grafik](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764) | [Video](https://youtu.be/YsTa7uyJ4sg) |
| [MAQ Software Funnel with Source](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334) | [Video](https://youtu.be/R_EcimsLI8U) |
| [Gantt](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765) | [Video](https://youtu.be/qJ7s_KrGiUU) |
| [MAQ Software Gantt Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364) | [Video](https://youtu.be/vJLV9JRCpI8) |
| [Yerküre Veri Çubukları](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344) | |
| [MAQ Software kılavuz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825) | [Video](https://youtu.be/VOPoDJgZfOY) |
| [Akvelon Hierarchy Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333) | [Video](https://youtu.be/0ZGzJaq_KT4) |
| [Çubuk Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776) | |
| [MAQ Software Histogram with points](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032) | [Video](https://youtu.be/-ILF--wExrw) |
| [MAQ Software Horizontal Funnel](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) | [Video](https://youtu.be/SudZei68PPo) |
| [CloudScope Image](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297) | |
| [Görüntü Kılavuzu](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355) | |
| [Bilgi Grafiği Tasarımcısı](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898) | |
| [Akvelon KPI Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432) | |
| [MAQ Software KPI Sütunu](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996) | [Video](https://youtu.be/rU0xoOlIq1U) |
| [MAQ Software KPI Kılavuzu](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947) | [Video](https://youtu.be/dM4PvZh71V0) |
| [KPI Indicator](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832) | |
| [MAQ Software KPI Bandı](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946) | [Video](https://youtu.be/cudG4gsZ2V8) |
| [MAQ Software Linear Gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821) | [Video](https://youtu.be/7_jFaM30dkc) |
| [LineDot Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766) | |
| [Mekko Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785) | [Video](https://youtu.be/90FLCKpgicA) |
| [Çoklu KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763) | |
| [CloudScope Genel Bakışı](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477) | |
| [Play Axis (Dynamic Slicer)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) | [Video](https://youtu.be/IvfIP3E6-1Q) |
| [Power KPI Matrix](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299) | [Video](https://youtu.be/1enze8pcGzY) |
| [Eğilim Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006) | [Video](https://youtu.be/DQWdcQtjDVw) |
| [MAQ Software Quadrant Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011) | [Video](https://youtu.be/ppBnyhqWNC0) |
| [Radar Grafik](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771) | |
| [MAQ Software Ring Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824) | [Video](https://youtu.be/pDToHDFHnq8) |
| [MAQ Software Rotating Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007) | [Video](https://youtu.be/d5xBCMmb3hU) |
| [Sankey Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777) | [Video](https://youtu.be/WWP9wVUHGaA) |
| [Akvelon Scatter Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703) | |
| [Scroller](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018) | |
| [OKViz Smart Filter](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859) | [Video](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910) | [Video](https://youtu.be/0m3Vnvso9tY) |
| [Akış Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772) | |
| [Güneş ışığı](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767) | |
| [OKViz Genel Bakış Paneli](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873) | |
| [Table Heatmap](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818) | |
| [Tachometer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937) | [Video](https://youtu.be/C3OXdETbS9o) |
| [Metin Filtresi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309) | |
| [MAQ Software Text Wrapper](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [MAQ Software Termometre](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847) | [Video](https://youtu.be/SPX9mgrAdBc) |
| [Time Brush Dilimleyici](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798) | |
| [Zaman Çizelgesi Dilimleyici](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786) | [Video](https://youtu.be/ozMtZ4_NZ10) |
| [CloudScope Zaman Çizelgesi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427) | [Video](https://youtu.be/szNi9YgXFJc) |
| [Tornado chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768) | [Video](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [MAQ Software Trading Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823) | [Video](https://youtu.be/xhTR6y6J9Ko) |
| [Ultimate Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140) | [Video](https://youtu.be/pDYF8iZxERs) |
| [Ultimate Waterfall](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956) | [Video](https://youtu.be/0BZsVCQdEkc) |
| [CloudScope User List](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426) | |
| [Waffle Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049) | [Video](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752) | [Video](https://youtu.be/AblTenl9fqo) |

## <a name="faq"></a>SSS

Görseller hakkında daha fazla bilgi için bkz. [Sertifikalı görseller hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#certified-power-bi-visuals).

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI özel görseli geliştirme](../developer/custom-visual-develop-tutorial.md)
* [Microsoft'un YouTube'daki özel görsel oynatma listesi](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Power BI'daki Görselleştirmeler](../visuals/power-bi-report-visualizations.md)  
* [Power BI'daki Özel Görselleştirmeler](power-bi-custom-visuals.md)  
* [Microsoft AppSource’ta Power BI görselleri yayımlama](../developer/office-store.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
