---
title: Power BI’daki görseller
description: Bu makalede özel Power BI görselleri açıklanmaktadır
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: overview
ms.date: 07/14/2020
LocalizationGroup: Visualizations
ms.openlocfilehash: 91c9115f7d9ca0eb15606fcd77f99070e949842e
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96416773"
---
# <a name="visuals-in-power-bi"></a>Power BI’daki görseller

Power BI, kullanıma hazır birçok görselle birlikte gelir. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) ve [Power BI hizmetinin](https://app.powerbi.com) görselleştirme bölmesinden ulaşabileceğiniz bu görselleri Power BI içeriği oluşturmak ve düzenlemek için kullanabilirsiniz.

:::image type="content" source="media/power-bi-custom-visuals/power-bi-visualizations.png" alt-text="Power BI görselleştirme bölmesinin Power BI Desktop ve Power BI hizmetinde göründüğü halinin ekran görüntüsü.":::

Microsoft [AppSource](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fappsource.microsoft.com%2Fen-us%2Fmarketplace%2Fapps%3Fpage%3D1%26product%3Dpower-bi-visuals&data=02%7C01%7CKesem.Sharabi%40microsoft.com%7C6d9286afacb3468d4cde08d740b76694%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637049028749147718&sdata=igWm0e1vXdgGcbyvngQBrHQVAkahPnxPC1ZhUPntGI8%3D&reserved=0) veya Power BI üzerinden daha fazla Power BI görseline ulaşabilirsiniz. Microsoft ve Microsoft iş ortakları tarafından oluşturulan bu görseller, AppSource doğrulama ekibi tarafından test edilmekte ve doğrulanmaktadır.

Ayrıca kendi Power BI görselinizi geliştirebilir; kendi başınıza, kuruluşunuzla veya Power BI topluluğunun tamamıyla birlikte kullanabilirsiniz.

## <a name="default-power-bi-visuals"></a>Varsayılan Power BI görselleri

*Power BI Desktop* ve *Power BI hizmetindeki* görselleştirme bölmesinden ulaşabileceğiniz kullanıma hazır Power BI görselleri bunlardır.

Görselleştirme bölmesindeki bir Power BI görselini kaldırmak için sağ tıklayıp **kaldır**'ı seçin.

Varsayılan Power BI görsellerini görselleştirme bölmesine yeniden yüklemek için **Özel bir görseli içeri aktar**'a tıklayıp **Varsayılan görselleri geri yükle**'yi seçin. 

## <a name="appsource-power-bi-visuals"></a>AppSource Power BI görselleri

Hem Microsoft hem de topluluk üyeleri, genel kamu yararı için Power BI görseli katkısında bulunup bunları [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) üzerinde yayımlamaktadır. Bu görselleri indirip Power BI raporlarınıza ekleyebilirsiniz. Microsoft bu Power BI görsellerini işlevsellik ve kalite bakımından test edip onaylamıştır.

>[!NOTE]
>* SDK’mızla oluşturulan Power BI görsellerini kullanarak, Power BI kiracınızın coğrafi alanının, uyumluluk sınırının veya ulusal bulut örneğinin dışında bulunan diğer hizmetlere veya üçüncü taraflara veri gönderebilir ya da buralardan verileri içeri aktarabilirsiniz.
>* Power BI sertifikalı görseller, görselin dış hizmetlere veya kaynaklara erişmediğinden emin olmak için ek olarak test edilmiş olan, AppSource’daki görsellerdir.
>* AppSource’dan Power BI görselleri içeri aktarıldıktan sonra görseller ek bir bildirim olmadan otomatik olarak güncelleştirilebilir.

### <a name="what-is-appsource"></a>AppSource nedir?

[AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals); Microsoft yazılımınıza yönelik uygulamaları, eklentileri ve uzantıları bulabileceğiniz yerdir. AppSource; Microsoft 365, Azure, Dynamics 365, Cortana ve Power BI gibi ürünlerin milyonlarca kullanıcısının, işlerini hiç olmadığı kadar verimli ve bilinçli bir şekilde gerçekleştirmelerine yardımcı olacak çözümlere bağlanmasını sağlar.

### <a name="certified-power-bi-visuals"></a>Sertifikalı Power BI görselleri

Sertifikalı Power BI görselleri, [AppSource](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fappsource.microsoft.com%2Fen-us%2Fmarketplace%2Fapps%3Fpage%3D1%26product%3Dpower-bi-visuals&data=02%7C01%7CKesem.Sharabi%40microsoft.com%7C6d9286afacb3468d4cde08d740b76694%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637049028749147718&sdata=igWm0e1vXdgGcbyvngQBrHQVAkahPnxPC1ZhUPntGI8%3D&reserved=0) üzerinde bulunan ve Microsoft Power BI ekibinin test ettiği ve onayladığı belirli kod gereksinimlerini karşılayan görsellerdir. Testler görselin dış hizmetlere veya kaynaklara erişmediğini denetleyecek şekilde tasarlanmıştır.

Sertifikalı Power BI görsellerinin listesini görüntülemek veya kendi Power BI görselinizi göndermek için bkz. [Sertifikalı Power BI görselleri](power-bi-custom-visuals-certified.md).

### <a name="samples-for-power-bi-visuals"></a>Örnek Power BI görselleri

AppSource'taki her Power BI görseli, görselin nasıl çalıştığını gösteren örnek veriler içerir. Örneği indirmek için [AppSource](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fappsource.microsoft.com%2Fen-us%2Fmarketplace%2Fapps%3Fpage%3D1%26product%3Dpower-bi-visuals&data=02%7C01%7CKesem.Sharabi%40microsoft.com%7C6d9286afacb3468d4cde08d740b76694%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637049028749147718&sdata=igWm0e1vXdgGcbyvngQBrHQVAkahPnxPC1ZhUPntGI8%3D&reserved=0)'ta Power BI görselini seçin ve *Örnek deneyin* bölümünde **örnek rapor** bağlantısına tıklayın.

## <a name="organizational-store"></a>Kuruluş deposu

Power BI yöneticileri, kuruluşlarında kullanılmasını istedikleri Power BI görsellerini onaylayıp dağıtır. Bu sayede rapor yazarları bu Power BI görsellerini kolayca keşfedebilir, güncelleştirebilir ve kullanabilir. Yöneticiler, bu Power BI görsellerinde sürüm güncelleştirme, devre dışı bırakma ve etkinleştirme gibi eylemler gerçekleştirerek bunları kolayca yönetebilir.

Kuruluş deposuna erişmek için *Görselleştirme* bölmesinde **Özel bir görseli içeri aktar**'a tıklayın, **Marketten içeri aktar**'ı seçin ve *Power BI görselleri* penceresinin üst tarafından **Kuruluşum** sekmesini seçin.

[Kurumsal görseller hakkında daha fazla bilgi edinin](power-bi-custom-visuals-organization.md).

## <a name="visual-files"></a>Görsel dosyaları

Power BI görselleri, kendisine sunulan verileri işlemeye yönelik kod içeren paketlerdir. Herkes özel bir görsel oluşturup bunu bir Power BI raporunda içeri aktarılabilen tek bir `.pbiviz` dosyası olarak paketleyebilir.

Bir Power BI görselini içeri aktarmak için *Görselleştirme* bölmesinde **Özel bir görseli içeri aktar**'a tıklayıp **Dosyadan içeri aktar**'ı seçin.

Web geliştiricisiyseniz ve kendi görselinizi oluşturup AppSource'a eklemek istiyorsanız [Power BI daire kartı görseli geliştirme](develop-circle-card.md) ve [AppSource'ta Power BI görseli yayımlama](office-store.md) sayfalarını inceleyin.

> [!WARNING]
> Bir Power BI görsel, güvenlik veya gizlilik riski taşıyan kod içerebilir. Power BI görselini raporunuza içeri aktarmadan önce özel görselin yazarına ve kaynağına güvendiğinizden emin olun.

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Power BI daire kartı görseli geliştirme](develop-circle-card.md)

>[!div class="nextstepaction"]
>[Power BI görselleri proje yapısı](visual-project-structure.md)

>[!div class="nextstepaction"]
>[Power BI görselleri için yönergeler](guidelines-powerbi-visuals.md)

>[!div class="nextstepaction"]
>[Sık sorulan sorular](power-bi-custom-visuals-faq.md)

>[!div class="nextstepaction"]
>[Power BI Topluluğu](https://community.powerbi.com/)