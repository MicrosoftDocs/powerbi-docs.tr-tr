---
title: "Power BI'daki özel görselleştirmeler"
description: "Power BI'daki özel görselleştirmeler"
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/06/2018
ms.author: maghan
ms.openlocfilehash: 72c4c0e3a177f83582677113b1c349a6ae295428
ms.sourcegitcommit: ad9bd4e52471b1179f46f847960d5ed79c0c0761
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2018
---
# <a name="custom-visuals-in-power-bi"></a>Power BI'daki özel görseller
Bir Power BI raporu oluştururken veya düzenlerken kullanabileceğiniz çok çeşitli türden görseller bulunmaktadır. Bu görseller, **Görsel Öğeler** bölmesinde sunulur. Bu görseller dizisi, Power BI Desktop'ı indirdiğinizde veya Power BI hizmetini (app.powerbi.com) açtığınızda hazır olarak sunulur.

![](media/power-bi-custom-visuals/power-bi-visualizations.png)

Ancak, kullanabileceğiniz görseller bu görsel dizisiyle sınırlı değildir. Üç nokta simgesini seçtiğinizde başka bir rapor görseli kaynağı daha sunulur: *özel görseller*.

Geliştiriciler, iş kullanıcılarının verilerini işletme için en uygun şekilde görmesine imkan sağlamak için özel görseller SDK’sını kullanarak özel görseller oluşturur. Daha sonra, rapor yazarları bu özel görsel dosyalarını diğer Power BI görselleri gibi kendi raporlarında içeri aktarabilir. Özel görseller Power BI’da 1. sınıf öğelerdir ve filtrelenebilir, vurgulanabilir, düzenlenebilir, paylaşılabilir, vb.

Özel görseller 3 dağıtım kanalı biçiminde olabilir:
* Özel görsel dosyaları
* Kuruluş görselleri
* Market görselleri

## <a name="custom-visual-files"></a>Özel görsel dosyaları

Özel görseller, kendisine sunulan verileri işlemeye yönelik kod içeren paketlerdir. Herkes özel bir görsel oluşturup bunu bir Power BI raporunda içeri aktarılabilen tek bir .pbiviz dosyası olarak paketleyebilir.

> [!WARNING]
> Özel görseller güvenlik veya gizlilik riski taşıyan kodlar içerebilir. Özel görseli raporunuzda içeri aktarmadan önce görselin yazarına ve kaynağına güvendiğinizden emin olun.
> 
> 

## <a name="organization-visuals-preview"></a>Kuruluş görselleri (Önizleme)

Power BI yöneticileri, kuruluş içinde kullanılmasına onay verdikleri özel görselleri rapor yazarlarının kolayca keşfedip kullanabilmesi için kuruluşlarına özel görseller dağıtabilir. Bu sayede, yönetici kuruluşta dağıtmak üzere belirli özel görselleri seçme konusunda denetimin yanı sıra bu görselleri yönetmenin (örn. sürümü güncelleştirme, devre dışı bırakma/etkinleştirme) kolay bir yoluna sahip olur. Rapor yazarı için kuruluşa özgü görselleri keşfetme ve bu görsellerin güncelleştirilmesi için sorunsuz destek almanın kolay bir yolunu sağlar.

Özel kuruluş görselleri hakkında daha fazla bilgi edinmek için lütfen [kuruluş görselleri hakkında daha fazla bilgi edinin](power-bi-custom-visuals-organization.md).

## <a name="marketplace-visuals"></a>Market görselleri

Topluluk üyelerinin yanı sıra Microsoft tarafından genel kamu yararına yönelik olarak özel görsel katkısında bulunulmuş ve bu görseller [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals) markette yayımlanmıştır. Bu görseller indirilerek Power BI raporlarına eklenebilir. Bu özel görsellerin tümü, Microsoft tarafından işlevsellik ve kalite testinden geçirilip onaylanmıştır.

AppSource nedir? Basit bir şekilde açıklamak gerekirse, Microsoft yazılımınıza yönelik uygulamaları, eklentileri ve uzantıları bulabileceğiniz yerdir. [AppSource](https://appsource.microsoft.com/en-us/); Power BI, Office 365, Azure, Dynamics 365 ve Cortana gibi ürünlerin milyonlarca kullanıcısının, işlerini hiç olmadığı kadar verimli, bilinçli ve etkileyici bir şekilde gerçekleştirmelerine yardımcı olacak çözümlere bağlanmasını sağlar.

### <a name="certified-visuals"></a>Sertifikalı görseller

Power BI sertifikalı görseller, kalite konusunda ek olarak sıkı testlerden geçirilmiş olan market görselleridir. Bu görsellerin, [e-posta abonelikleri](https://docs.microsoft.com/en-us/power-bi/service-report-subscribe) ve [PowerPoint'e aktarma](https://docs.microsoft.com/en-us/power-bi/service-publish-to-powerpoint) gibi ek senaryolardaki kullanımları desteklenir.
Sertifikalı özel görsellerin listesini görmek veya kendi özel görselinizi göndermek için bkz. [Sertifikalı özel görseller](https://docs.microsoft.com/en-us/power-bi/power-bi-custom-visuals-certified).

Bir Web geliştiricisi olarak kendi görselleştirmelerinizi oluşturmak ve bunları AppSource'a eklemek mi istiyorsunuz? [Geliştirici Araçlarıyla çalışmaya başlama](https://docs.microsoft.com/en-us/power-bi/service-custom-visuals-getting-started-with-developer-tools) makalesini inceleyin ve [AppSource'ta özel görseller yayımlamayı](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals) öğrenin.

### <a name="import-a-custom-visuals-from-a-file"></a>Bir dosyadan özel bir görseli içeri aktarın

1. Görsel Öğeler bölmesinin alt kısmındaki üç nokta simgesini seçin.

    ![](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Açılan menüden **Dosyadan içeri aktar** seçeneğini belirleyin.

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. Dosyayı aç menüsünden içeri aktarmak istediğiniz .pbiviz dosyasını seçip Aç'ı seçin. Özel görselin simgesi, Görsel Öğeler bölmenizin alt kısmına eklenir ve bu özel görsel artık raporunuzda kullanılmaya hazırdır.

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organization-visuals"></a>Kuruluş görsellerini içeri aktarma

1. Görsel Öğeler bölmesinin alt kısmındaki üç nokta simgesini seçin.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. Açılan menüden Marketten içeri aktarın seçeneğini belirleyin.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Üst sekme menüsünde **KURULUŞUM**’u seçin.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. İçeri aktaracağınız görseli bulmak için sayfayı aşağı kaydırın.
    
    ![](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. **Ekle** düğmesini seçerek özel görseli içeri aktarın. Özel görselin simgesi, Görsel Öğeler bölmenizin alt kısmına eklenir ve bu özel görsel artık raporunuzda kullanılmaya hazırdır.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-05.png)
 
## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource'tan özel görsel indirme veya içeri aktarma
Power BI'dan ve AppSource web sitesinden olmak üzere, özel görselleri indirmenin ve içeri aktarmanın iki yolu vardır.

### <a name="import-custom-visuals-from-within-power-bi"></a>Özel görselleri Power BI'dan içeri aktarma

1. Görsel Öğeler bölmesinin alt kısmındaki üç nokta simgesini seçin.

    ![](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Açılan menüden **Marketten içeri aktarın** seçeneğini belirleyin.

    ![](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. İçeri aktaracağınız görseli bulmak için sayfayı aşağı kaydırın.

    ![](media/power-bi-custom-visuals/power-bi-import-visual.png)

4. Özel görsellerden biri hakkında daha fazla bilgi edinmek için ilgili özel görseli seçip vurgulayın.

    ![](media/power-bi-custom-visuals/power-bi-select.png)

5. Ayrıntılar sayfasında ekran görüntülerini, videoları, ayrıntılı açıklamaları ve daha fazlasını görüntüleyebilirsiniz.

    ![](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. İncelemeleri görmek için sayfanın en altına gidin.

    ![](media/power-bi-custom-visuals/power-bi-reviews.png)

7. Ekle düğmesini seçerek özel görseli içeri aktarın. Özel görselin simgesi, Görsel Öğeler bölmenizin alt kısmına eklenir ve bu özel görsel artık raporunuzda kullanılmaya hazırdır.

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource'tan özel görsel indirme ve içeri aktarma

1. [Microsoft AppSource](https://appsource.microsoft.com)'a gidin ve **Uygulamalar** sekmesini seçin. 

    ![](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. Böylece, *Power BI Uygulamaları* da dahil olmak üzere her bir kategorideki sık kullanılan uygulamaları görüntüleyebileceğiniz [Uygulama sonuçları sayfası](https://appsource.microsoft.com/en-us/marketplace/apps) açılır. Ancak, aradığımız şey özel görseller olduğu için sol gezinti listesinden **Power BI visuals** seçeneğini belirleyerek sonuçları daraltalım.

    ![](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource, her özel görsel için bir kutucuk görüntüler.  Her kutucuk, özel görselin bir anlık görüntüsünü içerir ve özel görsele ilişkin kısa bir açıklamayla indirme bağlantısı sunar. Daha fazla ayrıntı görmek için kutucuğu seçin. 

    ![](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. Ayrıntılar sayfasında ekran görüntülerini, videoları, ayrıntılı açıklamaları ve daha fazlasını görüntüleyebilirsiniz. **Şimdi edinin** düğmesini seçip Kullanım koşullarını kabul ederek özel görseli indirin. 

    ![](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. Özel görseli indirmek için bağlantıyı seçin.

    ![](media/power-bi-custom-visuals/powerbi-custom-download.png)

    İndirme sayfası aynı zamanda özel görselin Power BI Desktop'a ve Power BI hizmetine nasıl aktarılacağını anlatan yönergeler de içerir.

    Ayrıca özel görseli içeren ve görselin özelliklerinin sergilendiği örnek bir raporu da indirebilirsiniz.

    ![](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. .pbiviz dosyasını kaydedin ve Power BI'ı açın.

7. Raporunuzda .pbiviz dosyasını içeri aktarın (Yukarıdaki [Bir dosyadan özel bir görseli içeri aktarın](#import-a-custom-visuals-from-a-file) bölümüne bakın)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

- Özel görseller içeri aktarıldığında belirli bir rapora eklenir. Başka bir raporda kullanmak istiyorsanız görseli bu rapora da aktarmanız gerekir. Bir rapor, **Farklı Kaydet** seçeneği kullanılarak özel bir görselle kaydedildiğinde, özel görselin bir kopyası yeni raporla kaydedilir.

- **Görsel Öğeler** bölmesini görmüyorsanız bu, raporu düzenleme izninizin olmadığı anlamına gelir.  Sizinle paylaşılan raporlara değil, yalnızca düzenleyebildiğiniz raporlara özel görsel ekleyebilirsiniz.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)