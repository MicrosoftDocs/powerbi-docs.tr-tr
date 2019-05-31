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
ms.date: 05/15/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: 3fd2f3e47c9b6dd2144ed5a66d45e65a00c5b92e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051252"
---
# <a name="custom-visuals-in-power-bi"></a>Power BI'daki özel görseller

Oluşturma veya Power BI raporu düzenlerken, birçok farklı türde görsel kullanabilirsiniz. Bu görseller için simgeler görünür **görselleştirmeler** bölmesi. Bu görseller, yüklediğinizde önceden paketlenmiş gelen [Power BI Desktop](https://powerbi.microsoft.com/desktop/) veya [Power BI hizmetinde](https://app.powerbi.com).

![görselleştirmeler](media/power-bi-custom-visuals/power-bi-visualizations.png)

Ancak, bu görsel dizisiyle sınırlı değildir. Alttaki üç nokta (...) seçin, başka bir rapor görseli kaynağı - kullanılabilir*özel görseller*.

Geliştiriciler, özel görseller SDK'sını kullanarak özel görseller oluşturun. Bu görseller, iş kullanıcılarının verilerini iş en iyi uyan bir şekilde görmek etkinleştirin. Rapor yazarlarının özel görsel dosyaları kendi raporlarında içeri ve bunlar herhangi bir Power BI görselleri gibi bunları kullanın. Özel görseller, Power bı'da birinci sınıf vatandaşlar olan ve vurgulanan, düzenlenen, paylaşılan ve bu şekilde filtrelenebilir.

Özel görseller, üç şekilde dağıtılır:

* Özel görsel dosyaları
* Kuruluş görselleri
* Market görselleri

## <a name="custom-visual-files"></a>Özel görsel dosyaları

Özel görseller, kendisine sunulan verileri işlemeye kod içeren paketlerdir. Herkes özel görsel oluşturma ve tek bir paket `.pbiviz` Power BI raporu aktarılabilen bir dosya.

> [!WARNING]
> Özel görseller güvenlik veya gizlilik riski taşıyan kod içerebilir. Raporunuzda içeri aktarmadan önce görselin yazarına ve özel görsel kaynağı güvendiğinizden emin olun.

## <a name="organizational-visuals"></a>Kuruluş görselleri

Power BI yöneticileri, onaylayabilir ve özel görselleri rapor yazarlarının kolayca keşfedin, güncelleştirme kullanın ve kendi kuruluş içinde dağıtabilirsiniz. Yöneticiler kolayca yönetebilir (örneğin, sürüm güncelleştirmesi, devre dışı bırakmanıza/etkinleştirmenize) bu görsellerin.

 [Kuruluş görselleri hakkında daha fazla bilgiyi](power-bi-custom-visuals-organization.md).

## <a name="marketplace-visuals"></a>Market görselleri

Topluluk üyeleri ve Microsoft ortak avantajı için özel görselleri katkıda bulunan ve kendilerine yayımlanan [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) Market. Bu indirebileceğiniz görselleri Power BI raporlarınızı ekleyin. Microsoft, test ve işlevsellik ve kalite için özel görsellerin onaylandı.

[AppSource](developer/office-store.md) nedir? Bu, Microsoft yazılımınıza yönelik uygulamaları, eklentileri ve uzantıları bulmak yerdir. [AppSource](https://appsource.microsoft.com/) milyonlarca kullanıcıya Office 365, Azure, Dynamics 365, Cortana ve Power BI'da, yardımcı olacak çözümlere daha verimli bir şekilde, insightfully, işlerinizi gibi ürünlerin ve içeriğinizin daha önce bağlanır.

### <a name="certified-visuals"></a>Sertifikalı görseller

Power BI sertifikalı görseller ek sıkı kalite testlerden geçmiştir ve gibi ek senaryolardaki desteklenen Market görsellerine [e-posta abonelikleri](https://docs.microsoft.com/power-bi/service-report-subscribe), ve [PowerPoint'e aktarma](https://docs.microsoft.com/power-bi/service-publish-to-powerpoint).
Sertifikalı özel görsellerin listesini görmek veya kendi özel görselinizi göndermek için bkz. [Sertifikalı özel görseller](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified).

Bir Web geliştiricisi olarak kendi görselleştirmelerinizi oluşturmak ve bunları AppSource'a eklemek mi istiyorsunuz? Bkz [Power BI özel görsel geliştirme](developer/custom-visual-develop-tutorial.md) ve bilgi edinmek için nasıl [Appsource'ta özel görseller yayımlama](https://docs.microsoft.com/power-bi/developer/office-store).

### <a name="import-a-custom-visual-from-a-file"></a>Bir dosyadan özel bir görseli içeri aktarma

1. Üç nokta simgesini seçin alt **görselleştirmeler** bölmesi.

    ![görselleştirme2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Açılan menüden **Dosyadan içeri aktar** seçeneğini belirleyin.

    ![dosyadan içeri aktar](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. Dosyayı Aç menüsünden seçin `.pbiviz` içeri aktarın ve ardından istediğiniz dosya **açık**. Özel görselin simgesi alt kısmına eklenir, **görselleştirmeler** bölmesi ve raporunuzdaki kullanıma sunulmuştur.

    ![içeri aktarılan cv](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organizational-visuals"></a>Kuruluş görsellerini içeri aktarma

1. Üç nokta simgesini seçin alt **görselleştirmeler** bölmesi.

    ![görsel kuruluş 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. Açılan menüden **Marketten içeri aktarın** seçeneğini belirleyin.

    ![görsel kuruluş 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. Üst sekme menüsünde **KURULUŞUM**’u seçin.

    ![görsel kuruluş 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. İçeri aktaracağınız görseli bulmak için sayfayı aşağı kaydırın.

    ![görsel kuruluş 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. Seçin **Ekle** özel görseli içeri aktarmak için. Simgesini alt kısmına eklenir, **görselleştirmeler** bölmesi ve raporunuzdaki kullanıma sunulmuştur.

    ![görsel kuruluş 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource'tan özel görsel indirme veya içeri aktarma

İndiriliyor ve özel görselleri içeri aktarma için iki seçeneğiniz vardır: öğesinden gelen ve giden Power bı'da [AppSource Web sitesi](https://appsource.microsoft.com/).

### <a name="import-custom-visuals-from-within-power-bi"></a>Özel görselleri Power BI'dan içeri aktarma

1. Üç nokta simgesini seçin alt **görselleştirmeler** bölmesi.

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

7. Seçin **Ekle** özel görseli içeri aktarmak için. Simgesini alt kısmına eklenir, **görselleştirmeler** bölmesi ve raporunuzdaki kullanıma sunulmuştur.

    ![içeri aktarılan görsel](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource'tan özel görsel indirme ve içeri aktarma

1. [Microsoft AppSource](https://appsource.microsoft.com)'a gidin ve **Uygulamalar** sekmesini seçin.

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. *Power BI Uygulamaları* da dahil olmak üzere her kategoride sık kullanılan uygulamaları görüntüleyebileceğiniz [Uygulama sonuçları sayfasına](https://appsource.microsoft.com/marketplace/apps) gidin. Özel görseller için bu nedenle şimdi seçin bekliyoruz **Power BI görselleri** sonuçları daraltmak için sol gezinti listesinde.

    ![AppSource görselleri](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource, her özel görsel için bir kutucuk görüntüler.  Her kutucuk özel görsel anlık görüntüsünü kısa bir açıklaması ve bir indirme bağlantısı vardır. Daha fazla ayrıntı görmek için kutucuğu seçin.

    ![Özel Seçilen Görsel](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. Ayrıntılar sayfasında ekran görüntülerini, videoları, ayrıntılı açıklamaları ve daha fazlasını görüntüleyebilirsiniz. Seçin **şimdi edinin** özel görseli indirmek ve kullanım koşullarını kabul etmiş olursunuz.

    ![AppSource Alma](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. Özel görseli indirmek için bağlantıyı seçin.

    ![İndir](media/power-bi-custom-visuals/powerbi-custom-download.png)

    İndirme sayfası aynı zamanda özel görselin Power BI Desktop ve Power BI hizmetinde içeri aktarma yönergeleri içerir.

    Ayrıca özel görseli içeren ve görselin özelliklerinin sergilendiği örnek bir raporu da indirebilirsiniz.

    ![Örneği Deneyin](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. Kaydet `.pbiviz` dosya ve Power BI'ı açın.

7. İçeri aktarma `.pbiviz` raporunuzu dosyasına. (Yukarıdaki [Bir dosyadan özel bir görseli içeri aktarma](#import-a-custom-visual-from-a-file) bölümüne bakın.)

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Özel görseller içeri aktarıldığında belirli bir rapora eklenir. Başka bir raporda kullanmak istiyorsanız görseli bu rapora da aktarmanız gerekir. Bir rapor, **Farklı Kaydet** seçeneği kullanılarak özel bir görselle kaydedildiğinde, özel görselin bir kopyası yeni raporla kaydedilir.

* Görmüyorsanız, bir **görselleştirmeler** bölmesinde rapor düzenleme izinleri yok demektir.  Sizinle paylaşılan raporlara değil, yalnızca düzenleyebildiğiniz raporlara özel görsel ekleyebilirsiniz.

## <a name="troubleshoot"></a>Sorun giderme

Sorun giderme için bkz: [Power BI özel görselleri sorun giderme](power-bi-custom-visuals-troubleshoot.md).

## <a name="faq"></a>SSS

Daha fazla bilgi edinmek ve sorularınıza yanıt bulmak için [Power BI özel görselleri hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#organizational-custom-visuals) bağlantısını ziyaret edin.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI raporlarındaki görselleştirmeler](visuals/power-bi-report-visualizations.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/).
