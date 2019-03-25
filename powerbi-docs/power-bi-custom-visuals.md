---
title: Power BI'daki özel görseller
description: Power BI'daki özel görselleştirmeler
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/18/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: ed61d865756748ccd4e60f54de4a4b1b9adcef8d
ms.sourcegitcommit: ac63b08a4085de35e1968fa90f2f49ea001b50c5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/18/2019
ms.locfileid: "57980347"
---
# <a name="custom-visuals-in-power-bi"></a>Power BI'daki özel görseller

Bir Power BI raporu oluştururken veya düzenlerken kullanabileceğiniz çok çeşitli türden görseller bulunmaktadır. Bu görseller, **Görsel Öğeler** bölmesinde sunulur. Bu görseller dizisi, [Power BI Desktop](https://powerbi.microsoft.com/desktop/)'ı indirdiğinizde veya [Power BI hizmetini](https://app.powerbi.com) açtığınızda "önceden paketlenmiş" olarak sunulur.

![görselleştirmeler](media/power-bi-custom-visuals/power-bi-visualizations.png)

Ancak, kullanabileceğiniz görseller bu görsel dizisiyle sınırlı değildir. Üç nokta simgesini seçtiğinizde başka bir rapor görseli kaynağı daha sunulur: *özel görseller*.

Geliştiriciler, iş kullanıcılarının verilerini işletme için en uygun şekilde görmesine imkan sağlamak için özel görseller SDK’sını kullanarak özel görseller oluşturur. Daha sonra, rapor yazarları bu özel görsel dosyalarını diğer Power BI görselleri gibi kendi raporlarında içeri aktarabilir. Özel görseller Power BI’da birinci sınıf öğelerdir ve filtrelenebilir, vurgulanabilir, düzenlenebilir, paylaşılabilir, vb.

Özel görseller üç dağıtım kanalı biçiminde olabilir:

* Özel görsel dosyaları
* Kuruluş görselleri
* Market görselleri

## <a name="custom-visual-files"></a>Özel görsel dosyaları

Özel görseller, kendisine sunulan verileri işlemeye yönelik kod içeren paketlerdir. Herkes özel bir görsel oluşturup bunu bir Power BI raporunda içeri aktarılabilen tek bir `.pbiviz` dosyası olarak paketleyebilir.

> [!WARNING]
> Özel görseller güvenlik veya gizlilik riski taşıyan kodlar içerebilir. Özel görseli raporunuzda içeri aktarmadan önce görselin yazarına ve kaynağına güvendiğinizden emin olun.

## <a name="organizational-visuals"></a>Kuruluş görselleri

Power BI yöneticileri, kuruluş içinde kullanılmasına onay verdikleri özel görselleri rapor yazarlarının kolayca keşfedip kullanabilmesi için kuruluşlarına özel görseller dağıtabilir. Bu sayede, yönetici kuruluşta dağıtmak üzere belirli özel görselleri seçme konusunda denetimin yanı sıra bu görselleri yönetmenin (örneğin sürümü güncelleştirme, devre dışı bırakma/etkinleştirme) kolay bir yoluna sahip olur. Rapor yazarı için kuruluşa özgü görselleri keşfetme ve bu görsellerin güncelleştirilmesi için sorunsuz destek almanın kolay bir yolunu sağlar.

Özel kuruluş görselleri hakkında daha fazla bilgi edinmek için [kuruluş görselleri hakkında daha fazla makale okuyun](power-bi-custom-visuals-organization.md).

## <a name="marketplace-visuals"></a>Market görselleri

Topluluk üyelerinin yanı sıra Microsoft tarafından genel kamu yararına yönelik olarak özel görsel katkısında bulunulmuş ve bu görseller [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) markette yayımlanmıştır. Bu görseller indirilerek Power BI raporlarına eklenebilir. Bu özel görsellerin tümü, Microsoft tarafından işlevsellik ve kalite testinden geçirilip onaylanmıştır.

[AppSource](developer/office-store.md) nedir? Şöyle açıklanabilir; Microsoft yazılımınıza yönelik uygulamaları, eklentileri ve uzantıları bulabileceğiniz yerdir. [AppSource](https://appsource.microsoft.com/); Power BI, Office 365, Azure, Dynamics 365 ve Cortana gibi ürünlerin milyonlarca kullanıcısının, işlerini hiç olmadığı kadar verimli, bilinçli ve etkileyici bir şekilde gerçekleştirmelerine yardımcı olacak çözümlere bağlanmasını sağlar.

### <a name="certified-visuals"></a>Sertifikalı görseller

Power BI sertifikalı görseller, kalite konusunda ek olarak sıkı testlerden geçirilmiş olan market görselleridir. Bu görsellerin, [e-posta abonelikleri](https://docs.microsoft.com/power-bi/service-report-subscribe) ve [PowerPoint'e aktarma](https://docs.microsoft.com/power-bi/service-publish-to-powerpoint) gibi ek senaryolardaki kullanımları desteklenir.
Sertifikalı özel görsellerin listesini görmek veya kendi özel görselinizi göndermek için bkz. [Sertifikalı özel görseller](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified).

Bir Web geliştiricisi olarak kendi görselleştirmelerinizi oluşturmak ve bunları AppSource'a eklemek mi istiyorsunuz? [Power BI özel görseli geliştirme](developer/custom-visual-develop-tutorial.md) makalesini inceleyin ve [AppSource'ta özel görseller yayımlamayı](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) öğrenin.

### <a name="import-a-custom-visual-from-a-file"></a>Bir dosyadan özel bir görseli içeri aktarma

1. Görsel Öğeler bölmesinin alt kısmındaki üç nokta simgesini seçin.

    ![görselleştirme2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Açılan menüden **Dosyadan içeri aktar** seçeneğini belirleyin.

    ![dosyadan içeri aktar](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. Dosyayı aç menüsünden içeri aktarmak istediğiniz `.pbiviz` dosyasını seçip Aç'ı seçin. Özel görselin simgesi, Görsel Öğeler bölmenizin alt kısmına eklenir ve bu özel görsel artık raporunuzda kullanılmaya hazırdır.

    ![içeri aktarılan cv](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organizational-visuals"></a>Kuruluş görsellerini içeri aktarma

1. Görsel Öğeler bölmesinin alt kısmındaki üç nokta simgesini seçin.

    ![görsel kuruluş 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. Açılan menüden Marketten içeri aktarın seçeneğini belirleyin.

    ![görsel kuruluş 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Üst sekme menüsünde **KURULUŞUM**’u seçin.

    ![görsel kuruluş 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. İçeri aktaracağınız görseli bulmak için sayfayı aşağı kaydırın.

    ![görsel kuruluş 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. **Ekle** düğmesini seçerek özel görseli içeri aktarın. Özel görselin simgesi, Görsel Öğeler bölmenizin alt kısmına eklenir ve bu özel görsel artık raporunuzda kullanılmaya hazırdır.

    ![görsel kuruluş 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource'tan özel görsel indirme veya içeri aktarma

Power BI'dan ve AppSource web sitesinden olmak üzere, özel görselleri indirmenin ve içeri aktarmanın iki yolu vardır.

### <a name="import-custom-visuals-from-within-power-bi"></a>Özel görselleri Power BI'dan içeri aktarma

1. Görsel Öğeler bölmesinin alt kısmındaki üç nokta simgesini seçin.

    ![görselleştirmeler 2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Açılan menüden **Marketten içeri aktarın** seçeneğini belirleyin.

    ![görsel kuruluş 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. İçeri aktaracağınız görseli bulmak için sayfayı aşağı kaydırın.

    ![görseli içeri aktar](media/power-bi-custom-visuals/power-bi-import-visual.png)

4. Özel görsellerden biri hakkında daha fazla bilgi edinmek için ilgili özel görseli seçip vurgulayın.

    ![Seç](media/power-bi-custom-visuals/power-bi-select.png)

5. Ayrıntılar sayfasında ekran görüntülerini, videoları, ayrıntılı açıklamaları ve daha fazlasını görüntüleyebilirsiniz.

    ![Özet](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. İncelemeleri görmek için sayfanın en altına gidin.

    ![Gözden Geçirmeler](media/power-bi-custom-visuals/power-bi-reviews.png)

7. Ekle düğmesini seçerek özel görseli içeri aktarın. Özel görselin simgesi, Görsel Öğeler bölmenizin alt kısmına eklenir ve bu özel görsel artık raporunuzda kullanılmaya hazırdır.

    ![içeri aktarılan görsel](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource'tan özel görsel indirme ve içeri aktarma

1. [Microsoft AppSource](https://appsource.microsoft.com)'a gidin ve **Uygulamalar** sekmesini seçin.

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. *Power BI Uygulamaları* da dahil olmak üzere her kategoride sık kullanılan uygulamaları görüntüleyebileceğiniz [Uygulama sonuçları sayfasına](https://appsource.microsoft.com/marketplace/apps) gidin. Ancak, aradığımız şey özel görseller olduğu için sol gezinti listesinden **Power BI visuals** seçeneğini belirleyerek sonuçları daraltalım.

    ![AppSource görselleri](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource, her özel görsel için bir kutucuk görüntüler.  Her kutucuk, özel görselin bir anlık görüntüsünü içerir ve özel görsele ilişkin kısa bir açıklamayla indirme bağlantısı sunar. Daha fazla ayrıntı görmek için kutucuğu seçin.

    ![Özel Seçilen Görsel](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. Ayrıntılar sayfasında ekran görüntülerini, videoları, ayrıntılı açıklamaları ve daha fazlasını görüntüleyebilirsiniz. **Şimdi edinin** düğmesini seçip Kullanım koşullarını kabul ederek özel görseli indirin.

    ![AppSource Alma](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. Özel görseli indirmek için bağlantıyı seçin.

    ![İndir](media/power-bi-custom-visuals/powerbi-custom-download.png)

    İndirme sayfası aynı zamanda özel görselin Power BI Desktop'a ve Power BI hizmetine nasıl aktarılacağını anlatan yönergeler de içerir.

    Ayrıca özel görseli içeren ve görselin özelliklerinin sergilendiği örnek bir raporu da indirebilirsiniz.

    ![Örneği Deneyin](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. '.pbiviz' dosyasını kaydedin ve Power BI'ı açın.

7. '.pbiviz' dosyasını raporunuza aktarın. (Yukarıdaki [Bir dosyadan özel bir görseli içeri aktarma](#import-a-custom-visual-from-a-file) bölümüne bakın.)

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Özel görseller içeri aktarıldığında belirli bir rapora eklenir. Başka bir raporda kullanmak istiyorsanız görseli bu rapora da aktarmanız gerekir. Bir rapor, **Farklı Kaydet** seçeneği kullanılarak özel bir görselle kaydedildiğinde, özel görselin bir kopyası yeni raporla kaydedilir.

* **Görsel Öğeler** bölmesini görmüyorsanız bu, raporu düzenleme izninizin olmadığı anlamına gelir.  Sizinle paylaşılan raporlara değil, yalnızca düzenleyebildiğiniz raporlara özel görsel ekleyebilirsiniz.

## <a name="troubleshoot"></a>Sorun giderme

Sorun giderme hakkında bilgi için [Power BI özel görsellerinizin sorunlarını giderme](power-bi-custom-visuals-troubleshoot.md) bağlantısını ziyaret edin.

## <a name="faq"></a>SSS

Daha fazla bilgi edinmek ve sorularınıza yanıt bulmak için [Power BI özel görselleri hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#organizational-custom-visuals) bağlantısını ziyaret edin.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI'daki Görselleştirmeler](visuals/power-bi-report-visualizations.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/).
