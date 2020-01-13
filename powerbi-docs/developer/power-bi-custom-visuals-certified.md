---
title: Sertifikalı Power BI görselleri
description: Sertifika için özel görsel gönderme işlemi ve gereksinimleri. Sertifikalanan Power BI görselleri listesi.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 12/02/2019
ms.openlocfilehash: c39b96122016746905ea09c0983adf50356f0c77
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2020
ms.locfileid: "75221977"
---
# <a name="get-a-power-bi-visual-certified"></a>Power BI görseli için sertifika alın

Sertifikalı Power BI görselleri, *Markette* bulunan ve *Microsoft Power BI ekibinin* test ettiği ve onayladığı *belirli kod* gereksinimlerini karşılayan görsellerdir. Testler görselin dış hizmetlere veya kaynaklara erişmediğini denetleyecek şekilde tasarlanmıştır.

Sertifikalı Power BI görselleri ve [standart Power BI görselleri](power-bi-custom-visuals.md) aynı şekilde kullanılır. Bunlar [Power BI Desktop](../desktop-what-is-desktop.md)'a ve [Power BI hizmetine](../power-bi-service-overview.md) eklenebilir; [Power BI Mobil](../consumer/mobile/mobile-apps-for-mobile-devices.md) ve [Power BI Embedded](embedding.md) ile görüntülenebilir.

Sertifikasyon işlemi isteğe bağlı bir işlemdir. Power BI görsellerini Markette sertifikalama kararı tamamen geliştiricilere aittir. Power BI görseli sertifikalandığında, daha fazla özellik sunar. Örneğin görseli [PowerPoint'e aktarabilirsiniz](../consumer/end-user-powerpoint.md) veya bir kullanıcı [rapor sayfalarına abone olduğunda](../consumer/end-user-subscribe.md) alınan e-postalarda görüntüleyebilirsiniz.

Sertifikalı olmayan Power BI görsellerinin, güvenli olmayan görseller olması şart değildir. Bazı görseller sertifikalanmamıştır çünkü [sertifikasyon gereksinimlerinin](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) biriyle veya birden çoğuyla uyumlu değildir. Örneğin, harita görselleri gibi dış hizmetlere bağlanan veya ticari kitaplıkları kullanan görseller böyledir.

Bir web geliştiricisi olarak kendi Power BI görsellerinizi oluşturmakla ve  [Microsoft AppSource](https://appsource.microsoft.com)'a eklemekle ilgileniyorsanız,  [Power BI görseli oluşturma](visuals/custom-visual-develop-tutorial.md) öğreticisiyle başlayın.

> [!NOTE]
> Üçüncü taraf Power BI görsellerinin yazarı **Microsoft***değildir*. Üçüncü taraf görsellerinin işlevselliğini doğrulamak için doğrudan görselin yazarına başvurmasını öneririz.

> [!IMPORTANT]
> Microsoft kendi takdirine bağlı olarak, bir Power BI görselini [Sertifikalı Power BI görselleri](#certified-power-bi-visuals) listesinden kaldırabilir.

## <a name="certification-requirements"></a>Sertifikasyon gereksinimleri

Power BI görselinizin [sertifikalı](#get-a-power-bi-visual-certified) olmasını sağlamak için, Power BI görselinizin bu bölümde listelenen gereksinimleri karşıladığından emin olun. 

> [!TIP]
> Göndermeden önce kodunuzu doğrulamak için varsayılan güvenlik kuralı setiyle EsLint'i kullanmanızı öneririz.

* Microsoft Satıcı Panosu ve İş Ortağı Merkezi onaylıdır. Power BI görselinizin [Marketimizde](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) bulunması gerekir.
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
   * Power BI görselinin derlenen paketinin gönderilen paketle eşleşmesi gerekir.
* Kaynak Kodu gereksinimleri:
   * Power BI görselinin [Olay İşleme API’sini](./visuals/event-service.md) desteklemesi gerekir.
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

## <a name="certified-power-bi-visuals"></a>Sertifikalı Power BI görselleri

Sertifikalı Power BI görselleri aşağıda listelenmiştir. Power BI görselini AppSource'ta açmak için bağlantıya tıklayın. Video kullanılabiliyorsa, video bağlantısına tıklayarak videoyu izleyebilirsiniz.

* [3AG Systems - Bar Chart With Absolute Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381802)
*  [3AG Systems - Bar Chart With Relative Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381912)
*  [3AG Systems - Column Chart With Relative Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803)
*  [3AG Systems - Column Chart with Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381724)
* [Advanced Donut Visual (Tam Sürüm)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941)
*  [Advanced Donut Visual (Basit Sürüm)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858)
*  [Gelişmiş Grafik Görseli](https://appsource.microsoft.com/product/power-bi-visuals/WA104382086)
*  [Gelişmiş Ağ Görselleştirmesi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942)
*  [Advanced TimeSeries Visual (Tam Sürüm)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943)
*  [Aster Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759)
*  [Beyondsoft Calendar](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096)
*  [MAQ Software Bowtie Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838)
*  [Kutu ve Çizgi grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831)
* [MAQ Software Box and Whisker Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351)
*  [MAQ Software Brick Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836)
*  [Akvelon Bubble Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340)
*  [Bullet Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755),  **[video bağlantısı](https://youtu.be/AOlsFYkfkcw)**
* [Bullet Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755)
*  [Bullet Chart by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953), **[video bağlantısı](https://youtu.be/mtvUNl9bMjA)**
* [Calendar by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381844)
*  [Calendar by Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146)
*  [Candlestick by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952), **[video bağlantısı](https://youtu.be/nT_18gyRxPo)**
*  [OKViz Card with States](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967)
*  [Chiclet Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756)
*  [Chord](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761), **[video bağlantısı](https://youtu.be/AQvd2FhRyCI)**
*  [MAQ Software Circular Gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837)
*  [Küme Eşleme](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806)
* [Custom Calendar by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381179)
* [MAQ Software Cylindrical Gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874)
*  [Dial Gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184)
[Dot Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760)
*  [Dot Plot by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949), **[video bağlantısı](https://youtu.be/By16pX9KT40)**
*  [Ayrıntılı Kartogram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045)
*  [Ayrıntılı Koroplet](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044)
*  [Ayrıntılı sütun grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857), **[video bağlantısı](https://youtu.be/lBy2gQQ5YsQ)**
*  [Zamana bağlı veriler için ayrıntılı sütun grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881), **[video bağlantısı](https://youtu.be/T_mRou18vx0)**
*  [Ayrıntılı halka grafik](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858), **[video bağlantısı](https://youtu.be/AUVFrSHmPeo)**
*  [Dual KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774)
*  [MAQ Software Dynamic Tooltip](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983)
*  [Gelişmiş Dağılım](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762), **[video bağlantısı](https://youtu.be/xCfM0cjM4do)**
*  [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112)
*  [Enlighten Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960)
*  [Enlighten Stack Shuffle](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849)
*  [Enlighten Waffle Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850)
*  [Filter by List by Devscope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413), **[video bağlantısı](https://youtu.be/RetEWGwBu0I)**
*  [Zorla Yönlendirilmiş Grafik](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764), **[video bağlantısı](https://youtu.be/YsTa7uyJ4sg)**
*  [MAQ Software Funnel with Source](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334)
*  [Gantt](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765), **[video bağlantısı](https://youtu.be/qJ7s_KrGiUU)**
* [MAQ Software Gantt Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364)
*  [Yerküre Veri Çubukları](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344)
*  [MAQ Software kılavuz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825)
*  [Hierarchy Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333), **[video bağlantısı](https://youtu.be/0ZGzJaq_KT4)**
*  [Çubuk Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776)
*  [MAQ Software Histogram with points](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032)
* [Yatay çubuk grafik](https://appsource.microsoft.com/product/power-bi-visuals/WA104381230)
*  [MAQ Software Horizontal Funnel](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846)
*  [CloudScope Image](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297)
*  [Görüntü Kılavuzu](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355)
*  [Bilgi Grafiği Tasarımcısı](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898)
*  [Akvelon KPI Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432)
*  [MAQ Software KPI Sütunu](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996)
*  [MAQ Software KPI Kılavuzu](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947)
*  [KPI Indicator](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832)
*  [MAQ Software KPI Bandı](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946)
* [MAQ Software Linear Gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821)
*  [LineDot Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766)
*  [Mekko Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785), **[video bağlantısı](https://youtu.be/90FLCKpgicA)**
*  [Çoklu KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763)
*  [CloudScope Genel Bakışı](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477)
*  [Play Axis (Dynamic Slicer)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981)
*  [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083), [video bağlantısı](https://youtu.be/IvfIP3E6-1Q)
*  [Power KPI Matrisi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299), **[video bağlantısı](https://youtu.be/1enze8pcGzY)**
*  [Pulse Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006), **[video bağlantısı](https://youtu.be/DQWdcQtjDVw)**
*  [MAQ Software Quadrant Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011)
*  [Radar Grafik](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771)
*  [MAQ Software Ring Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824)
*  [MAQ Software Rotating Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007)
*  [Sankey Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777), **[video bağlantısı](https://youtu.be/WWP9wVUHGaA)**
*  [Akvelon Scatter Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703)
*  [Scroller](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018)
*  [Smart Filter by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859), **[video bağlantısı](https://youtu.be/gcJsDDRQq28)**
*  [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910), **[video bağlantısı](https://youtu.be/0m3Vnvso9tY)**
*  [Akış Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772)
*  [Güneş ışığı](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767)
*  [OKViz Genel Bakış Paneli](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873)
*  [Table Heatmap](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818)
*  [Tachometer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937), **[video bağlantısı](https://youtu.be/C3OXdETbS9o)**
*  [Metin Filtresi](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309)
*  [MAQ Software Text Wrapper](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826)
*  [MAQ Software Termometre](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847)
*  [Time Brush Dilimleyici](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798)
*  [Zaman Çizelgesi Dilimleyici](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786), **[video bağlantısı](https://youtu.be/ozMtZ4_NZ10)**
*  [Timeline by CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427), [video bağlantısı](https://youtu.be/szNi9YgXFJc)
*  [Tornado grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768), **[video bağlantısı](https://www.youtube.com/watch?v=AQvd2FhRyCI)**
*  [MAQ Software Trading Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823)
* [Ultimate KPI Card](https://appsource.microsoft.com/product/power-bi-visuals/WA104381977)
*  [Ultimate Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140), **[video bağlantısı](https://youtu.be/pDYF8iZxERs)**
*  [Ultimate Waterfall](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956), **[video bağlantısı](https://youtu.be/0BZsVCQdEkc)**
*  [CloudScope User List](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426)
*  [MAQ Software Venn Diyagramı](https://appsource.microsoft.com/product/power-bi-visuals/WA104381231)
*  [Violin Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104381947)
*  [Visio Görseli](https://appsource.microsoft.com/product/power-bi-visuals/WA104381132)
*  [Waffle Grafiği](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049), **[video bağlantısı](https://youtu.be/1vRqYUsm3Vk)**
*  [Word Cloud](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752), **[video bağlantısı](https://youtu.be/AblTenl9fqo)**

## <a name="faq"></a>SSS

Görseller hakkında daha fazla bilgi için bkz. [Sertifikalı görseller hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#certified-power-bi-visuals).

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI özel görseli geliştirme](../developer/custom-visual-develop-tutorial.md)
* [Microsoft'un YouTube'daki özel görsel oynatma listesi](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Power BI'daki Görselleştirmeler](../visuals/power-bi-report-visualizations.md)  
* [Power BI'daki Özel Görselleştirmeler](power-bi-custom-visuals.md)  
* [Microsoft AppSource’ta Power BI görselleri yayımlama](../developer/office-store.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
