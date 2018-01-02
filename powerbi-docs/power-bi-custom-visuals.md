---
title: "Power BI'daki özel görselleştirmeler"
description: "Power BI'daki özel görselleştirmeler"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 11/20/2017
ms.author: mihart
ms.openlocfilehash: c50b984cd8babc845dbe0223613e463a7a8ee76d
ms.sourcegitcommit: 12236d08c27c7ee3fabb7ef9d767e9dee693f8aa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="custom-visuals-in-power-bi"></a>Power BI'daki özel görseller
Bir Power BI raporu oluştururken veya düzenlerken kullanabileceğiniz çok çeşitli türden görseller bulunmaktadır. Bu görseller, **Görsel Öğeler** bölmesinde sunulur. Bu görseller dizisi, Power BI Desktop'ı indirdiğinizde veya Power BI hizmetini (app.powerbi.com) açtığınızda hazır olarak sunulur. 

![](media/power-bi-custom-visuals/power-bi-visualizations.png)

Ancak, kullanabileceğiniz görseller bu görsel dizisiyle sınırlı değildir. Üç nokta simgesini seçtiğinizde başka bir rapor görseli kaynağı daha sunulur: *özel görseller*.

Topluluk üyeleri ve Microsoft tarafından oluşturulan bu özel görseller [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals)'ta barındırılır. Bu görseller indirilerek Power BI raporlarına eklenebilir. Özel görsellerin tümü Microsoft tarafından onaylanmıştır ve Power BI'daki hazır görselleştirmeler gibi çalışır. Başka bir deyişle, filtrelenebilir, vurgulanabilir, düzenlenebilir ve paylaşılabilirler. 

AppSource nedir? Basit bir şekilde açıklamak gerekirse, Microsoft yazılımınıza yönelik uygulamaları, eklentileri ve uzantıları bulabileceğiniz yerdir. [AppSource](https://appsource.microsoft.com); Power BI, Office 365, Azure, Dynamics 365 ve Cortana gibi ürünlerin milyonlarca kullanıcısının, işlerini hiç olmadığı kadar verimli, bilinçli ve etkileyici bir şekilde gerçekleştirmelerine yardımcı olacak çözümlere bağlanmasını sağlar.

## <a name="two-types-of-custom-visuals"></a>Özel görsellerin iki türü

AppSource'ta sunulan Power BI özel görselleri 2 kategoriye ayrılır: **onaylı** ve **sertifikalı**. *AppSource onaylı* görseller tarayıcılarda, raporlarda ve panolarda çalıştırılabilir.  *Power BI sertifikalı* görseller sıkı testlerden geçmiştir. Bu görsellerin, [e-posta abonelikleri](service-report-subscribe.md) ve [PowerPoint'e aktarma](service-publish-to-powerpoint.md) gibi ek senaryolardaki kullanımları desteklenir.

Sertifikalı özel görsellerin listesini görmek veya kendi özel görselinizi göndermek için bkz. [Sertifikalı özel görseller](power-bi-custom-visuals-certified.md).

Bir Web geliştiricisi olarak kendi görselleştirmelerinizi oluşturmak ve bunları AppSource'a eklemek mi istiyorsunuz?  [Geliştirici Araçlarıyla çalışmaya başlama](service-custom-visuals-getting-started-with-developer-tools.md) makalesini inceleyin ve [AppSource'ta özel görseller yayımlamayı](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) öğrenin.

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource'tan özel görsel indirme veya içeri aktarma
Power BI'dan ve AppSource web sitesinden olmak üzere, özel görselleri indirmenin ve içeri aktarmanın iki yolu vardır. 

###    <a name="import-custom-visuals-from-within-power-bi"></a>Özel görselleri Power BI'dan içeri aktarma
1. Görsel Öğeler bölmesinin alt kısmındaki üç nokta simgesini seçin. 

    ![](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. Açılan menüden **Mağazadan al** seçeneğini belirleyin.

    ![](media/power-bi-custom-visuals/power-bi-custom-visual-import.png)

3. İçeri aktaracağınız görseli bulmak için sayfayı aşağı kaydırın. 

    ![](media/power-bi-custom-visuals/power-bi-import-visual.png)

4.  Özel görsellerden biri hakkında daha fazla bilgi edinmek için ilgili özel görseli seçip vurgulayın.

    ![](media/power-bi-custom-visuals/power-bi-select.png)

5.  Ayrıntılar sayfasında ekran görüntülerini, videoları, ayrıntılı açıklamaları ve daha fazlasını görüntüleyebilirsiniz. 

    ![](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. İncelemeleri görmek için sayfanın en altına gidin.

    ![](media/power-bi-custom-visuals/power-bi-reviews.png)

7.    **Ekle** düğmesini seçerek özel görseli içeri aktarın. Özel görselin simgesi, Görsel Öğeler bölmenizin alt kısmına eklenir ve bu özel görsel artık raporunuzda kullanılmaya hazırdır.

       ![](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)


###    <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>Microsoft AppSource'tan özel görsel indirme ve içeri aktarma

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
7. Özel görseli eklemek istediğiniz raporu açtıktan sonra **Görsel Öğeler** bölmesinden üç nokta simgesini seçip **Dosyadan içeri aktar** seçeneğini belirleyin.  

      ![](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

8. Bu özel görselin simgesini **Görsel Öğeler** bölmenizin altına eklemek için özel görsel dosyasını seçin. Özel görsel artık raporunuzda kullanılmaya hazırdır.

    ![](media/power-bi-custom-visuals/power-bi-chord.png)
    
##    <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme


- Özel görseller içeri aktarıldığında belirli bir rapora eklenir. Başka bir raporda kullanmak istiyorsanız görseli bu rapora da aktarmanız gerekir. Bir rapor, **Farklı Kaydet** seçeneği kullanılarak özel bir görselle kaydedildiğinde, özel görselin bir kopyası yeni raporla kaydedilir.

- **Görsel Öğeler** bölmesini görmüyorsanız bu, raporu düzenleme izninizin olmadığı anlamına gelir.  Sizinle paylaşılan raporlara değil, yalnızca düzenleyebildiğiniz raporlara özel görsel ekleyebilirsiniz.


Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

