---
title: İzin verilenler listesine Power BI URL’lerini ekleme
description: Bu makalede, Power BI’a bağlanmak için izin verilenler listenize eklenecek URL uç noktaları ve bağlantı noktaları listelenir.
author: kfollis
ms.author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/25/2020
ms.custom: seodec18
ms.openlocfilehash: 38e6668c0fb15d1279923b77042cdedebe6dd139
ms.sourcegitcommit: a453ba52aafa012896f665660df7df7bc117ade5
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2020
ms.locfileid: "85485082"
---
# <a name="add-power-bi-urls-to-your-allow-list"></a>Power BI URL’lerini izin verilenler listenize ekleme
[//]: # "suparnap, miwehnia ve natham bu listeyi korumaya yönelik ilgili kişilerdir"

Power BI hizmeti için internet bağlantısı gerekir. Bu makaledeki tablolarda listelenen uç noktaların, Power BI hizmetini kullanan müşteriler tarafından ulaşılabilir olması gerekir.

Power BI hizmetini kullanmak için aşağıdaki tabloda **gerekli** olarak işaretlenen uç noktalara ve bağlantılı sitelerde **gerekli** olarak işaretlenen uç noktalarına bağlanabilmeniz gerekir. Dış site bağlantısı belirli bir bölüme başvuruyorsa yalnızca bu bölümdeki uç noktalarını gözden geçirmeniz gerekir.

**İsteğe bağlı** olarak işaretlenen uç noktalar, belirli işlevlerin çalışması için izin verilenler listesine eklenebilir.

Power BI hizmetlerinin listelenen uç noktaları için yalnızca 443 numaralı TCP bağlantı noktasının açılması gerekir.

Joker karakterler (*) kök etki alanı altındaki tüm düzeyleri temsil eder ve bilgi bulunmayan alanlar Yok ifadesiyle belirtilmiştir. **Hedefler** sütununda uç noktalarla ilgili daha fazla bilginin bulunduğu dış sitelerin etki alanları ve bağlantıları listelenmektedir.

>[!Important]
>Aşağıdaki tablolarda yer alan bilgiler Power BI Germany, 21Vianet tarafından işletilen Power BI China veya Power BI for US Government için geçerli değildir. Bulut hizmetleri arasında bağlantı hakkında daha fazla bilgi için [Kamuya özgü ve genel Azure bulut hizmetleri arasında bağlantı kurma](service-govus-overview.md#connect-government-and-global-azure-cloud-services) makalesini okuyun.

## <a name="authentication"></a>Kimlik Doğrulama

Power BI, Microsoft 365 kimlik doğrulaması ve kimlik bölümlerindeki gerekli uç noktaları kullanır. Power BI'ı kullanmak için aşağıdaki bağlantıdan ulaşabileceğiniz sitede yer alan uç noktalara bağlanabiliyor olmanız gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Kimlik doğrulaması ve kimlik | [Microsoft 365 Ortak ve Office Online URL’leri](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) ile ilgili belgelere bakın  | YOK |

## <a name="general-site-usage"></a>Genel site kullanımı

Genel Power BI kullanımı için aşağıdaki tabloda ve bağlantılı sitelerde belirtilen uç noktalara bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Arka uç API’leri | api.powerbi.com | TCP 443 |
| 2 | **Gerekli:** Arka uç API’leri | *.analysis.windows.net | TCP 443 |
| 3 | **Gerekli:** Arka uç API’leri | *.pbidedicated.windows.net | TCP 443 |
| 4 | **Gerekli:** Content Delivery Network (CDN) | content.powerapps.com | TCP 443 |
| 5 | **Gerekli:** Microsoft 365 tümleştirmesi | [Microsoft 365 Ortak ve Office Online URL’leri](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) ile ilgili belgelere bakın | YOK |
| 6 | **Gerekli:** Portal | *.powerbi.com | TCP 443 |
| 7 | **Gerekli:** Hizmet telemetrisi | dc.services.visualstudio.com | TCP 443 |
| 8 | **İsteğe bağlı:** Bilgilendirme iletileri | dynmsg.modpim.com | TCP 443 |
| 9 | **İsteğe bağlı:** NPS anketleri | nps.onyx.azure.net | TCP 443 |
| | | |

## <a name="administration"></a>Yönetim

Power BI'da yönetim işlevleri gerçekleştirmek için aşağıda bağlantısı verilen sitelerde yer alan uç noktalara bağlanabiliyor olmanız gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Kullanıcıları yönetmek ve denetim günlüklerini görüntülemek için | [Microsoft 365 Ortak ve Office Online URL’leri](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) ile ilgili belgelere bakın | YOK |
| | | |

## <a name="getting-data"></a>Veri alma

OneDrive gibi belirli veri kaynaklarından veri almak için aşağıdaki tabloda yer alan uç noktalarına bağlanabilmeniz gerekir. Kuruluşunuzda kullanılan belirli veri kaynakları için ek internet etki alanlarına ve URL'lere erişim gerekli olabilir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** AppSource (Power BI’ın içindeki veya dışındaki uygulamalar) | appsource.microsoft.com <br> *.s-microsoft.com  | TCP 443 |
| 2 | **İsteğe bağlı:** Oturum açma ve içerik paketleri için veri alma | Kullanılan içerik paketlerine bağlıdır | Kullanılan içerik paketlerine bağlıdır |
| 3 | **İsteğe bağlı:** Kişisel OneDrive hesabınızdaki dosyaları içeri aktarma | [OneDrive sitesindeki gerekli URL'ler ve bağlantı noktalarına](https://docs.microsoft.com/onedrive/required-urls-and-ports) bakın | YOK |
| 4 | **İsteğe bağlı:** 60 saniyede Power BI öğretici videosu | *.doubleclick.net <br> *.ggpht.com <br> *.google.com <br> *.googlevideo.com <br> *.youtube.com <br> *.ytimg.com <br> fonts.gstatic.com | TCP 443 |
| 5 | **İsteğe bağlı:** PubNub akış verisi kaynakları | [PubNub belgelerine](https://support.pubnub.com/support/solutions/articles/14000043522) bakın | YOK |
| | | |

## <a name="dashboard-and-report-integration"></a>Pano ve rapor tümleştirmesi

Power BI, panolarınızı ve raporlarınızı desteklemek için belirli uç noktaları kullanır. Aşağıdaki tabloda ve bağlantılı sitelerde belirtilen uç noktalara bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Excel tümleştirmesi | [Microsoft 365 Ortak ve Office Online URL’leri](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) ile ilgili belgelere bakın | YOK |
| | | |

## <a name="power-bi-visuals"></a>Power BI görselleri

Power BI, Power BI görsellerini görüntülemek ve onlara erişim sağlamak için belirli uç noktaları kullanır. Aşağıdaki tabloda ve bağlantılı sitelerde belirtilen uç noktalara bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Market arabiriminden veya dosyadan özel görsel içeri aktarma | *.azureedge.net <br> *.blob.core.windows.net <br> *.osi.office.net <br> *.msecnd.net <br> store.office.com <br> web.vortex.data.microsoft.com <br> store-images.s-microsoft.com | TCP 443 |
| 2 | **İsteğe bağlı:** Bing Haritalar | bing.com <br> platform.bing.com <br> *.virtualearth.net | TCP 443 |
| 3 | **İsteğe bağlı:** PowerApps | PowerApps sistem gereksinimleri sitesinin [Gerekli hizmetler bölümüne](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) bakın | YOK |
| 4 | **İsteğe bağlı:** Visio | [Microsoft 365 Ortak ve Office Online URL'leri](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) ile [SharePoint Online ve OneDrive İş](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business) ile ilgili belgelere bakın. | YOK |
| | | |

## <a name="related-external-sites"></a>İlgili dış siteler

Diğer ilgili siteler için Power BI bağlantıları. Bu siteler belgeleri, destek bilgilerini, yeni özellik isteklerini ve daha fazlasını barındırır. İzin verilenler listesine ekleme isteğe bağlı olduğundan, bu sitelere erişim Power BI’ın işlevselliğini etkilemez.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **İsteğe bağlı:** Topluluk sitesi | community.powerbi.com <br> oxcrx34285.i.lithium.com | TCP 443 |
| 2 | **İsteğe bağlı:** Belgeler sitesi | docs.microsoft.com <br> img-prod-cms-rt-microsoft-com.akamaized.net <br> statics-uhf-eas.akamaized.net <br> cdnssl.clicktale.net <br> ing-district.clicktale.net | TCP 443 |
| 3 | **İsteğe bağlı:** İndirme sitesi (Power BI Desktop vb. için) | download.microsoft.com | TCP 443 |
| 4 | **İsteğe bağlı:** Dış yönlendirme siteleri | aka.ms <br> go.microsoft.com | TCP 443 |
| 5 | **İsteğe bağlı:** Fikir geri bildirim sitesi| ideas.powerbi.com <br> powerbi.uservoice.com | TCP 443 |
| 6 | **İsteğe bağlı:** Power BI sitesi - giriş sayfası, daha fazla bilgi edinme bağlantıları, destek sitesi, indirme bağlantıları, iş ortağı gösterimi vb. | powerbi.microsoft.com | TCP 443 |
| 7 | **İsteğe bağlı:** Power BI Geliştirici Merkezi | dev.powerbi.com | TCP 443 |
| 8 | **İsteğe bağlı:** Destek sitesi | support.powerbi.com <br> s3.amazonaws.com <br> *.olark.com <br> logx.optimizely.com <br> mscom.demdex.net <br> tags.tiqcdn.com | TCP 443 |
| | | |
