---
title: Power BI’daki görseller
description: Power BI'daki özel görselleştirmeler
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: 68048968bf6a3f85f2bc24e55fd1288073be1d56
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68415417"
---
# <a name="visuals-in-power-bi"></a>Power BI’daki görseller

Bir Power BI raporu oluştururken veya düzenlerken çok çeşitli türden görseller kullanabilirsiniz. Bu görsellerin simgeleri **Görselleştirmeler** bölmesinde görünür. Bu görseller, [Power BI Desktop](https://powerbi.microsoft.com/desktop/)’ı indirdiğinizde veya [Power BI hizmetini](https://app.powerbi.com) açtığınızda önceden paketlenmiş olarak sunulur.

![görselleştirmeler](media/power-bi-custom-visuals/power-bi-visualizations.png)

Ancak, bu görseller dizisiyle sınırlı değilsiniz. Alttaki üç noktayı (...) seçerseniz, farklı bir rapor görseli kaynağı olan *özel görseller* kullanılabilir hale gelir.

Geliştiriciler, özel görseller SDK’sını kullanarak özel görseller oluşturur. Bu görseller iş kullanıcılarının, verileri işlerine en uygun olan şekilde görüntülemelerine olanak tanır. Daha sonra, rapor yazarları bu özel görsel dosyalarını diğer Power BI görselleri gibi kendi raporlarında içeri aktarıp kullanabilir. Power BI’da birinci sınıf öğeler olan özel görseller filtrelenebilir, vurgulanabilir, düzenlenebilir, paylaşılabilir vb.

Özel görseller üç şekilde dağıtılır:

* Özel görsel dosyaları
* Kuruluş görselleri
* Market görselleri

## <a name="custom-visual-files"></a>Özel görsel dosyaları

Özel görseller, kendisine sunulan verileri işlemeye yönelik kod içeren paketlerdir. Herkes özel bir görsel oluşturup bunu bir Power BI raporunda içeri aktarılabilen tek bir `.pbiviz` dosyası olarak paketleyebilir.

> [!WARNING]
> Özel bir görsel, güvenlik veya gizlilik riski taşıyan kod içerebilir. Özel görseli raporunuza içeri aktarmadan önce özel görselin yazarına ve kaynağına güvendiğinizden emin olun.

## <a name="organizational-visuals"></a>Kuruluş görselleri

Power BI yöneticileri, rapor yazarlarının kolayca keşfedebildiği, güncelleştirebildiği ve kullanabildiği özel görselleri onaylar ve kuruluşlarında dağıtır. Yöneticiler bu görselleri kolayca yönetebilir (örneğin, sürümünü güncelleştirme, devre dışı bırakma/etkinleştirme).

 [Kurumsal görseller hakkında daha fazla bilgi edinin](power-bi-custom-visuals-organization.md).

## <a name="marketplace-visuals"></a>Market görselleri

Hem Topluluk üyeleri hem de Microsoft, genel kamu yararı için özel görsel katkısında bulunup bunları [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) markette yayımlamıştır. Bu görselleri indirip Power BI raporlarınıza ekleyebilirsiniz. Microsoft, bu özel görselleri işlevsellik ve kalite bakımından test etti ve onayladı.

[AppSource](developer/office-store.md) nedir? Microsoft yazılımınıza yönelik uygulamaları, eklentileri ve uzantıları bulabileceğiniz yerdir. AppSource; Power BI, Office 365, Azure, Dynamics 365 ve Cortana gibi ürünlerin milyonlarca kullanıcısının, işlerini hiç olmadığı kadar verimli, bilinçli ve etkileyici bir şekilde gerçekleştirmelerine yardımcı olacak çözümlere bağlanmasını sağlar.

### <a name="certified-visuals"></a>Sertifikalı görseller

Power BI sertifikalı görseller, kalite konusunda ek olarak sıkı testlerden geçirilmiş olan market görselleridir. Bu görsellerin, [e-posta abonelikleri](service-report-subscribe.md) ve [PowerPoint'e aktarma](service-publish-to-powerpoint.md) gibi ek senaryolardaki kullanımları desteklenir.
Sertifikalı özel görsellerin listesini görmek veya kendi özel görselinizi göndermek için bkz. [Sertifikalı özel görseller](power-bi-custom-visuals-certified.md).

Bir Web geliştiricisi olarak kendi görselleştirmelerinizi oluşturmak ve bunları AppSource'a eklemek mi istiyorsunuz? [Power BI özel görseli geliştirme](developer/custom-visual-develop-tutorial.md) makalesini inceleyin ve [AppSource'ta özel görseller yayımlamayı](developer/office-store.md) öğrenin.

### <a name="import-a-custom-visual-from-a-file"></a>Bir dosyadan özel bir görseli içeri aktarma

1. **Görselleştirmeler** bölmesinin alt kısmındaki üç nokta simgesini seçin.

    ![görselleştirme2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Açılan menüden **Dosyadan içeri aktar** seçeneğini belirleyin.

    ![dosyadan içeri aktar](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. Dosyayı **aç** menüsünden içeri aktarmak istediğiniz `.pbiviz` dosyasını seçip **Aç**'ı seçin. Özel görselin simgesi, **Görsel Öğeler** bölmenizin alt kısmına eklenir ve bu özel görsel artık raporunuzda kullanılmaya hazırdır.

    ![içeri aktarılan cv](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organizational-visuals"></a>Kuruluş görsellerini içeri aktarma

1. **Görselleştirmeler** bölmesinin alt kısmındaki üç nokta simgesini seçin.

    ![görsel kuruluş 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. Açılan menüden **Marketten içeri aktarın** seçeneğini belirleyin.

    ![görsel kuruluş 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Üst sekme menüsünde **KURULUŞUM**’u seçin.

    ![görsel kuruluş 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. İçeri aktaracağınız görseli bulmak için sayfayı aşağı kaydırın.

    ![görsel kuruluş 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. Özel görseli içeri aktarmak için **Ekle** düğmesini seçin. Özel görselin simgesi, **Görsel Öğeler** bölmenizin alt kısmına eklenir ve bu özel görsel artık raporunuzda kullanılmaya hazırdır.

    ![görsel kuruluş 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource'tan özel görsel indirme veya içeri aktarma

Power BI'dan ve [AppSource web sitesinden](https://appsource.microsoft.com/) olmak üzere, özel görselleri indirmenin ve içeri aktarmanın iki yolu vardır.

### <a name="import-custom-visuals-from-within-power-bi"></a>Özel görselleri Power BI'dan içeri aktarma

1. **Görselleştirmeler** bölmesinin alt kısmındaki üç nokta simgesini seçin.

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

7. Özel görseli içeri aktarmak için **Ekle** düğmesini seçin. Özel görselin simgesi, **Görsel Öğeler** bölmenizin alt kısmına eklenir ve bu özel görsel artık raporunuzda kullanılmaya hazırdır.

    ![içeri aktarılan görsel](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource'tan özel görsel indirme ve içeri aktarma

1. [Microsoft AppSource](https://appsource.microsoft.com)'a gidin ve **Uygulamalar** sekmesini seçin.

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. *Power BI Uygulamaları* da dahil olmak üzere her kategoride sık kullanılan uygulamaları görüntüleyebileceğiniz [Uygulama sonuçları sayfasına](https://appsource.microsoft.com/marketplace/apps) gidin. Aradığımız şey özel görseller olduğu için sonuçları daraltmak amacıyla sol gezinti listesinden **Power BI visuals** seçeneğini belirleyelim.

    ![AppSource görselleri](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource, her özel görsel için bir kutucuk görüntüler.  Her kutucuk, özel görselin bir anlık görüntüsünü içerir ve özel görsele ilişkin kısa bir açıklamayla indirme bağlantısı sunar. Daha fazla ayrıntı görmek için kutucuğu seçin.

    ![Özel Seçilen Görsel](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. Ayrıntılar sayfasında ekran görüntülerini, videoları, ayrıntılı açıklamaları ve daha fazlasını görüntüleyebilirsiniz. Özel görseli indirmek için **Şimdi edinin** düğmesini seçip Kullanım koşullarını kabul edin.

    ![AppSource Alma](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. Özel görseli indirmek için bağlantıyı seçin.

    ![İndir](media/power-bi-custom-visuals/powerbi-custom-download.png)

    İndirme sayfası aynı zamanda özel görselin Power BI Desktop'a ve Power BI hizmetine nasıl aktarılacağını anlatan yönergeler de içerir.

    Ayrıca özel görseli içeren ve görselin özelliklerinin sergilendiği örnek bir raporu da indirebilirsiniz.

    ![Örneği Deneyin](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. `.pbiviz` dosyasını kaydedin ve Power BI'ı açın.

7. `.pbiviz` dosyasını raporunuza aktarın. (Yukarıdaki [Bir dosyadan özel bir görseli içeri aktarma](#import-a-custom-visual-from-a-file) bölümüne bakın.)

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Özel görseller içeri aktarıldığında belirli bir rapora eklenir. Başka bir raporda kullanmak istiyorsanız görseli bu rapora da aktarmanız gerekir. Bir rapor, **Farklı Kaydet** seçeneği kullanılarak özel bir görselle kaydedildiğinde, özel görselin bir kopyası yeni raporla kaydedilir.

* **Görsel Öğeler** bölmesini görmüyorsanız bu, raporu düzenleme izninizin olmadığı anlamına gelir.  Sadece sizinle paylaşılan raporlara değil, yalnızca düzenleyebildiğiniz raporlara özel görsel ekleyebilirsiniz.

## <a name="troubleshoot"></a>Sorun giderme

Daha fazla bilgi için bkz. [Power BI özel görsellerinizin sorunlarını giderme](power-bi-custom-visuals-troubleshoot.md).

## <a name="faq"></a>SSS

Daha fazla bilgi edinmek ve sorularınıza yanıt bulmak için [Power BI özel görselleri hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#organizational-custom-visuals) bağlantısını ziyaret edin.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI raporlarındaki görselleştirmeler](visuals/power-bi-report-visualizations.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/).
