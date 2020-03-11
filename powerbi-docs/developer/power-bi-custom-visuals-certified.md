---
title: Sertifikalı Power BI görselleri
description: Sertifika için özel görsel gönderme işlemi ve gereksinimleri, ayrıca sertifikalı Power BI görsellerinin listesi.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 03/01/2020
ms.openlocfilehash: 8aea9041665de69b2c5be954dc8f13a6402a06e0
ms.sourcegitcommit: d55d3089fcb3e78930326975957c9940becf2e76
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260773"
---
# <a name="get-a-power-bi-visual-certified"></a>Power BI görseli için sertifika alın

Sertifikalı Power BI görselleri, [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals)’ta yer alan ve Microsoft Power BI ekibinin [kod gereksinimlerini](#certification-requirements) karşılayan görsellerdir. Bu görseller test edilmiş ve dış hizmetlere veya kaynaklara erişmedikleri, güvenli kodlama desenlerine ve yönergelerine uydukları doğrulanmıştır.

Power BI görseli sertifikalandığında, daha fazla özellik sunar. Örneğin görseli [PowerPoint'e aktarabilirsiniz](../consumer/end-user-powerpoint.md) veya bir kullanıcı [rapor sayfalarına abone olduğunda](../consumer/end-user-subscribe.md) alınan e-postalarda görüntüleyebilirsiniz.

Sertifikasyon işlemi isteğe bağlıdır. Sertifikalı olmayan Power BI görsellerinin güvenli olmaması gerekmez. Bazı Power BI görselleri sertifikalı değildir çünkü bunlar [sertifikasyon gereksinimlerinin](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) biriyle veya birden çoğuyla uyumlu değildir. Örneğin dış hizmete bağlanan bir harita Power BI görseli veya ticari kitaplıkları kullanan Power BI görseli.

> [!NOTE]
> Üçüncü taraf Power BI görsellerinin yazarı Microsoft değildir. Üçüncü taraf görsellerinin işlevselliğini doğrulamak için doğrudan görselin yazarına başvurun.

## <a name="certification-requirements"></a>Sertifikasyon gereksinimleri

Power BI görselinizin [sertifikalı](#get-a-power-bi-visual-certified) olmasını sağlamak için, Power BI görseliniz bu bölümde listelenen gereksinimleri karşılamalıdır. 

### <a name="general-requirements"></a>Genel gereksinimler

Power BI görselinizin Satıcı Panosu veya İş Ortağı Merkezi tarafından onaylanması gerekir. Power BI görselinizin zaten [AppSource](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)’ta bulunmasını öneririz. Power BI görselini AppSource’ta yayımlamayı öğrenmek için bkz. [Power BI görsellerini İş Ortağı Merkezi’nde yayımlama](office-store.md).

Power BI görselinizi sertifikalanmak üzere göndermeden önce bu görselin [Power BI görsellerine ilişkin yönergelere](./guidelines-powerbi-visuals.md) uyduğunu doğrulayın.

Power BI görselini gönderirken derlenen paketin gönderilen paketle tam olarak eşleştiğinden emin olun.

### <a name="code-repository-requirements"></a>Kod deposu gereksinimleri

Kodunuzu GitHub’da herkese açık bir şekilde paylaşmanız gerekmese de, kod deposunun Power BI ekibinin gözden geçirmesine açık olması gerekir. Bunu yapmanın en iyi yolu GitHub’da kaynak kodu (JavaScript veya TypeScript) sağlamaktır.

Depo aşağıdakileri içermelidir:
* Tek bir Power BI görselinin kodu. Birden çok Power BI görselinin kodunu veya ilişkisiz bir kod içeremez.
* **certification** (küçük harf gereklidir) adlı bir dal. Bu daldaki kaynak kodun gönderilen paketle eşleşmesi gerekir. Power BI görselinizi yeniden gönderiyorsanız, bu kod ancak sonraki gönderim işlemi sırasında güncelleştirilebilir.

Power BI görseliniz özel npm paketleri veya git alt modülleri içeriyorsa, bu kodu içeren ek depolara erişim sağlamanız gerekir.

Power BI görsel deposunun nasıl göründüğünü anlamak için [Power BI görselleri örnek çubuk grafiği](https://github.com/microsoft/PowerBI-visuals-sampleBarChartgi) için GitHub deposunu gözden geçirin.

### <a name="file-requirements"></a>Dosya gereksinimleri

Power BI görselini yazmak için en son API sürümünü kullanın.

Depo aşağıdaki dosyaları içermelidir:
* **.gitignore** - Bu dosyaya `node_modules`, `.tmp`, `dist` ekleyin. Kod *node_modules*, *.tmp* veya *dist* klasörleri içeremez.
* **capabilities.json** - Bu dosyalardaki özelliklerde değişiklikler yapılmış olarak Power BI görselinizin daha yeni bir sürümünü gönderiyorsanız, bunun mevcut kullanıcıların raporlarını bozmadığını doğrulayın.
* **pbiviz.json** 
* **package.json**. Görselde aşağıdaki paket yüklü olmalıdır:
   * ["tslint"](https://www.npmjs.com/package/tslint): "5.18.0" veya üzeri
   * ["typescript"](https://www.npmjs.com/package/typescript): "3.0.0" veya üzeri
   * ["tslint-microsoftcontrib"](https://www.npmjs.com/package/tslint-microsoft-contrib): "6.2.0" veya üzeri
   * Dosya linter çalıştırmak için komut içermelidir:  "lint": "tslint -c tslint.json -p tsconfig.json"
* **package-lock.json**
* **tsconfig.json**

### <a name="command-requirements"></a>Komut gereksinimleri

Aşağıdaki komutların hata döndürmediğinden emin olun.

* `npm install`
* `pbiviz package`
* `npm audit` - Yüksek veya orta düzeyde hiçbir uyarı döndürmemelidir.
* [Gerekli yapılandırmayla](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/master/tslint.json) [Microsoft’tan TSlint](https://www.npmjs.com/package/tslint-microsoft-contrib). Bu komut hiçbir lint hatası döndürmemelidir.

### <a name="compiling-requirements"></a>Derleme gereksinimleri

Power BI görselini yazmak için en son [powerbi-visuals-tools](https://www.npmjs.com/package/powerbi-visuals-tools) sürümünü kullanın.

Power BI görselinizi `pbiviz package` ile derlemelisiniz. Kendi derleme betiklerinizi kullanıyorsanız bir `npm run package` özel derleme komutu sağlayın.



### <a name="source-code-requirements"></a>Kaynak kod gereksinimleri

[Power BI görselleri ek sertifikasyonu](https://docs.microsoft.com/legal/marketplace/certification-policies#1200-power-bi-visuals-additional-certification) ilke listesine uyduğunuzu doğrulayın. Gönderiminiz bu yönergelere uymuyorsa, İş Ortağı Merkezi’nden gelen reddetme e-postası bu bağlantıda listelenen ilke numaralarını içerir.

Kodunuzun Power BI sertifikasyon ilkelerine uygun olduğundan emin olmak için aşağıda listelenen kod gereksinimlerine uyun.  

**Gerekli**
* Yalnızca genel olarak gözden geçirilebilen genel JavaScript veya TypeScript kitaplıkları gibi OSS bileşenleri kullanın.
* Kodun [Olay İşleme API’sini](./visuals/event-service.md) desteklemesi gerekir.
* DOM’nin güvenle işlendiğinden emin olun. Kullanıcı girişini veya kullanıcı verilerini DOM’ye eklemeden önce bu öğelerde temizleme işlemini kullanın.
* [Örnek raporu](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) test veri kümesi olarak kullanın.

**İzin verilmiyor**
* Dış hizmetlere ya da kaynaklara erişim. Örneğin, Power BI'dan hizmetlere hiçbir HTTP/S veya WebSocket isteği gidemez.
* `innerHTML` veya `D3.html(user data or user input)` kullanma.
* Herhangi bir giriş verisi için tarayıcı konsolunda JavaScript hataları veya özel durumlar.
* `eval()` gibi rasgele veya dinamik kod; `settimeout()`, `requestAnimationFrame()`, `setinterval(user input function)` ve kullanıcı girişi veya kullanıcı verilerinin güvenli olmayan kullanımı.
* Küçültülmüş JavaScript dosyaları veya projeleri.

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

### <a name="private-repository-submission-process"></a>Özel depo gönderim işlemi

Power BI görselinizi sertifikasyona göndermek için GitHub gibi bir özel depo kullanıyorsanız bu bölümdeki yönergeleri izleyin.
1. Doğrulama ekibi için yeni bir hesap oluşturun.
2. Hesabınızda [iki faktörlü kimlik doğrulamasını](https://help.github.com/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa) yapılandırın.
3. [Yeni bir kurtarma kodları kümesi oluşturun](https://help.github.com/github/authenticating-to-github/configuring-two-factor-authentication-recovery-methods#generating-a-new-set-of-recovery-codes).
4. Power BI görselinizi gönderirken aşağıdakileri sağlayın:
    * Deponun bağlantısı
    * Oturum açma kimlik bilgileri (parola dahil)
    * Kurtarma kodları
    * Hesabımıza salt okuma izinleri ([pbicvsupport](https://github.com/pbicvsupport))

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
* Bir web geliştiricisi olarak kendi Power BI görsellerinizi oluşturmakla ve  [Microsoft AppSource](https://appsource.microsoft.com)'a eklemekle ilgileniyorsanız,  [Power BI görseli oluşturma](visuals/custom-visual-develop-tutorial.md) öğreticisiyle başlayın. 

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
