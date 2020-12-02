---
title: Sertifikalı Power BI görselleri
description: Sertifika için özel görsel gönderme işlemi ve gereksinimleri, ayrıca sertifikalı Power BI görsellerinin listesi.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 03/08/2020
ms.openlocfilehash: bbca1802b1136c4e9e16e70ab87ab7554612c037
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96386721"
---
# <a name="get-a-power-bi-visual-certified"></a>Power BI görseli için sertifika alın

Sertifikalı Power BI görselleri, [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals)’ta yer alan ve Microsoft Power BI ekibinin [kod gereksinimlerini](#certification-requirements) karşılayan görsellerdir. Bu görseller test edilmiş ve dış hizmetlere veya kaynaklara erişmedikleri, güvenli kodlama desenlerine ve yönergelerine uydukları doğrulanmıştır.

Power BI görseli sertifikalandığında, daha fazla özellik sunar. Örneğin görseli [PowerPoint'e aktarabilirsiniz](../../consumer/end-user-powerpoint.md) veya bir kullanıcı [rapor sayfalarına abone olduğunda](../../consumer/end-user-subscribe.md) alınan e-postalarda görüntüleyebilirsiniz.

Sertifikasyon işlemi isteğe bağlıdır. Sertifikalı olmayan Power BI görsellerinin güvenli olmaması gerekmez. Bazı Power BI görselleri sertifikalı değildir çünkü bunlar [sertifikasyon gereksinimlerinin](power-bi-custom-visuals-certified.md#certification-requirements) biriyle veya birden çoğuyla uyumlu değildir. Örneğin dış hizmete bağlanan bir harita Power BI görseli veya ticari kitaplıkları kullanan Power BI görseli.

> [!NOTE]
> Üçüncü taraf Power BI görsellerinin yazarı Microsoft değildir. Üçüncü taraf görsellerinin işlevselliğini doğrulamak için doğrudan görselin yazarına başvurun.

## <a name="certification-requirements"></a>Sertifikasyon gereksinimleri

Power BI görselinizin [sertifikalı](#get-a-power-bi-visual-certified) olmasını sağlamak için, Power BI görseliniz bu bölümde listelenen gereksinimleri karşılamalıdır. 

### <a name="general-requirements"></a>Genel gereksinimler

Power BI görselinizin İş Ortağı Merkezi tarafından onaylanması gerekir. Power BI görselinizin zaten [AppSource](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)’ta bulunmasını öneririz. Power BI görselini AppSource’ta yayımlamayı öğrenmek için bkz. [Power BI görsellerini İş Ortağı Merkezi’nde yayımlama](office-store.md).

Power BI görselinizi sertifikalanmak üzere göndermeden önce bu görselin [Power BI görsellerine ilişkin yönergelere](guidelines-powerbi-visuals.md) uyduğunu doğrulayın.

Power BI görselini gönderirken derlenen paketin gönderilen paketle tam olarak eşleştiğinden emin olun.

### <a name="code-repository-requirements"></a>Kod deposu gereksinimleri

Kodunuzu GitHub’da herkese açık bir şekilde paylaşmanız gerekmese de, kod deposunun Power BI ekibinin gözden geçirmesine açık olması gerekir. Bunu yapmanın en iyi yolu GitHub’da kaynak kodu (JavaScript veya TypeScript) sağlamaktır.

Depo aşağıdakileri içermelidir:
* Tek bir Power BI görselinin kodu. Birden çok Power BI görselinin kodunu veya ilişkisiz bir kod içeremez.
* **certification** (küçük harf gereklidir) adlı bir dal. Bu daldaki kaynak kodun gönderilen paketle eşleşmesi gerekir. Power BI görselinizi yeniden gönderiyorsanız, bu kod ancak sonraki gönderim işlemi sırasında güncelleştirilebilir.

Power BI görseliniz özel npm paketleri veya git alt modülleri içeriyorsa, bu kodu içeren ek depolara erişim sağlamanız gerekir.

Power BI görsel deposunun nasıl göründüğünü anlamak için [Power BI görselleri örnek çubuk grafiği](https://github.com/microsoft/PowerBI-visuals-sampleBarChart) için GitHub deposunu gözden geçirin.

### <a name="file-requirements"></a>Dosya gereksinimleri

Power BI görselini yazmak için en son API sürümünü kullanın.

Depo aşağıdaki dosyaları içermelidir:
* **.gitignore** - Bu dosyaya `node_modules`, `.tmp` ve `dist` ekleyin. Kod *node_modules*, *.tmp* veya *dist* klasörleri içeremez.
* **capabilities.json** - Bu dosyalardaki özelliklerde değişiklikler yapılmış olarak Power BI görselinizin daha yeni bir sürümünü gönderiyorsanız, bunun mevcut kullanıcıların raporlarını bozmadığını doğrulayın.
* **pbiviz.json** 
* **package.json**. Görselde aşağıdaki paket yüklü olmalıdır:
   * ["tslint"](https://www.npmjs.com/package/tslint) - Sürüm 5.18.0 veya üzeri
   * ["typescript"](https://www.npmjs.com/package/typescript) - Sürüm 3.0.0 veya üzeri
   * ["tslint-microsoftcontrib"](https://www.npmjs.com/package/tslint-microsoft-contrib) - Sürüm 6.2.0 veya üzerin
   * Dosya linter çalıştırmak için bir komut içermelidir -  `"lint": "tslint -c tslint.json -p tsconfig.json"`
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

[Power BI görselleri ek sertifikasyonu](/legal/marketplace/certification-policies#1200-power-bi-visuals-additional-certification) ilke listesine uyduğunuzu doğrulayın. Gönderiminiz bu yönergelere uymuyorsa, İş Ortağı Merkezi’nden gelen reddetme e-postası bu bağlantıda listelenen ilke numaralarını içerir.

Kodunuzun Power BI sertifikasyon ilkelerine uygun olduğundan emin olmak için aşağıda listelenen kod gereksinimlerine uyun.  

**Gerekli**
* Yalnızca genel olarak gözden geçirilebilen genel JavaScript veya TypeScript kitaplıkları gibi OSS bileşenleri kullanın.
* Kodun [Olay İşleme API’sini](event-service.md) desteklemesi gerekir.
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

## <a name="certified-power-bi-visual-badges"></a>Sertifikalı Power BI görseli rozetleri

Power BI görseli sertifikalı olunca, sertifikalı olduğunu göstermek için belirlenmiş bir rozet alır.

### <a name="certified-power-bi-visuals-in-appsource"></a>AppSource’ta sertifikalı Power BI görselleri

* [AppSource’ta Power BI görselleri](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) için çevrimiçi arama yaparken, görselin kartındaki küçük sarı bir rozet bunun sertifikalı bir Power BI görseli olduğunu gösterir.

    ![AppSource sertifikalı Power BI görseli](media/power-bi-custom-visuals-certified/certified-visual-yellow-small.png)

* AppSource’ta Power BI görseli kartına tıkladıktan sonra *PBI Sertifikalı* başlıklı sarı rozet bu Power BI görselinin sertifikalandığını gösterir.

    ![Uygulama sayfası sertifikalı Power BI görseli](media/power-bi-custom-visuals-certified/certified-visual-yellow-big.png)

### <a name="certified-power-bi-visuals-in-the-power-bi-interface"></a>Power BI arabiriminde sertifikalı Power BI görselleri

* Power BI görselini Power BI’ın (Desktop veya hizmet) içinden içeri aktarırken, mavi bir rozet Power BI görselinin sertifikalı olduğunu gösterir.

    ![Power BI arabirimi sertifikalı Power BI görseli](media/power-bi-custom-visuals-certified/certified-visual-blue.png)

* *Power BI Sertifikalı* filtre seçeneğini kullanarak yalnızca sertifikalı Power BI görsellerinin görüntülenmesini sağlayabilirsiniz.

## <a name="publication-timeline"></a>Yayımlama zaman çizelgesi

AppSource’un dağıtımı biraz zaman alan bir işlemdir. Bu işlem tamamlandıktan sonra Power BI görseliniz AppSource’dan indirilebilir.

### <a name="when-will-users-be-able-to-download-my-visual"></a>Kullanıcılar görselimi ne zaman indirebilecek?

* Power BI görselini ilk kez gönderdiyseniz, siz AppSource’dan bir e-posta aldıktan birkaç saat sonra kullanıcılar görseli indirebilir.

* Mevcut Power BI görseline güncelleştirme gönderdiyseniz, kullanıcılar gönderiminizi izleyen ay içinde bunu indirebilir.

    >[!NOTE]
    > AppSource’daki *sürüm* alanı Power BI’ınızın AppSource tarafından onaylandığı gün ile güncelleştirilir. Bu, yaklaşık olarak görselinizi göndermenizden bir hafta sonrasına denk gelir. Kullanıcılar güncelleştirilmiş görseli indirebilir ama güncelleştirilmiş özellikler geçerlilik kazanmaz. Görselinizin yeni özellikleri yaklaşık bir ay sonra kullanıcının raporlarını etkileyecektir. 

### <a name="when-will-my-power-bi-visual-display-a-certification-badge"></a>Power BI görselim ne zaman bir sertifikasyon rozeti görüntüleyecek?

* Power BI görselini ilk kez gönderdiyseniz, AppSource’dan onay e-postası alındıktan sonraki gün içinde sertifikasyon rozeti görüntülenir.

* Mevcut Power BI görseli için sertifikasyon istiyorsanız, sertifikasyon rozeti gönderiminizi izleyen bir ay içinde görünecektir.

## <a name="next-steps"></a>Sonraki adımlar

* Bir web geliştiricisi olarak kendi Power BI görsellerinizi oluşturmakla ve  [Microsoft AppSource](https://appsource.microsoft.com)'a eklemekle ilgileniyorsanız,  [Power BI daire kartı görseli geliştirme](develop-circle-card.md) öğreticisiyle başlayın.

* Görseller hakkında daha fazla bilgi için bkz. [Sertifikalı görseller hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#certified-power-bi-visuals).

* [Microsoft’un YouTube’daki Power BI görseli oynatma listesi](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)

* [Power BI’daki görseller](power-bi-custom-visuals.md)

* [Microsoft AppSource’ta Power BI görselleri yayımlama](office-store.md)

* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)