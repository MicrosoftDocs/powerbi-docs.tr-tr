---
title: Beyaz listeye ekleme için Power BI URL’si
description: Bu makalede Power BI’a bağlantıda güvenilir listeye alınacak URL uç noktaları ve bağlantı noktaları listelenir.
author: kfollis
ms.author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/29/2020
ms.custom: seodec18
ms.openlocfilehash: f74bfb92508564a01422729eefc251acc124baea
ms.sourcegitcommit: 250242fd6346b60b0eda7a314944363c0bacaca8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692735"
---
# <a name="power-bi-urls-for-whitelisting"></a>Beyaz listeye ekleme için Power BI URL’si
[//]: # "suparnap, miwehnia bu listeyi korumaya yönelik ilgili kişilerdir"

Power BI SaaS (Hizmet Olarak Yazılım) uygulaması olarak da bilinen **Power BI çevrimiçi hizmeti** için internet bağlantısı gerekir. Power BI çevrimiçi hizmetini kullanan müşterilerin aşağıdaki uç noktalara erişebiliyor olması gerekir.

Power BI çevrimiçi hizmetini kullanmak için aşağıdaki tabloda **gerekli** olarak işaretlenen uç noktalara ve bağlantılı sitelerde **gerekli** olarak işaretlenen uç noktalarına bağlanabilmeniz gerekir. Dış site bağlantısı belirli bir bölüme başvuruyorsa yalnızca bu bölümdeki uç noktalarını gözden geçirmeniz gerekir.

**İsteğe bağlı** olarak işaretlenen uç noktalar, belirli işlevlerin çalışması için **izin verilenler listesine eklenebilir**.

Power BI çevrimiçi hizmetlerinin listelenen uç noktaları için yalnızca 443 numaralı TCP bağlantı noktasının açılması gerekir.

Joker karakterler (*) kök etki alanı altındaki tüm düzeyleri temsil eder ve bilgi bulunmayan alanlar Yok ifadesiyle belirtilmiştir. **Hedefler** sütununda FQDN/etki alanları ve uç noktalarıyla ilgili daha fazla bilginin bulunduğu dış sitelerin bağlantıları yer almaktadır.

>[!Important]
>Aşağıdaki tabloda yer alan bilgiler **ABD Kamu bulutu**, **Almanya bulutu** veya **Çin bulutu** için geçerli değildir.

## <a name="authentication"></a>Kimlik Doğrulama

Power BI, Microsoft 365 kimlik doğrulaması ve kimlik bölümlerindeki gerekli uç noktaları kullanır. Power BI'ı kullanmak için aşağıdaki bağlantıdan ulaşabileceğiniz sitede yer alan uç noktalara bağlanabiliyor olmanız gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Kimlik doğrulaması ve kimlik | [Microsoft 365 Ortak ve Office Online URL’leri](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) ile ilgili belgelere bakın  | YOK |

## <a name="general-site-usage"></a>Genel site kullanımı

Genel Power BI kullanımı için aşağıdaki tabloda ve bağlantılı sitelerde belirtilen uç noktalara bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Arka uç API’leri | *.analysis.windows.net | TCP 443 |
| 2 | **Gerekli:** Arka uç API’leri | *.pbidedicated.windows.net | TCP 443 |
| 3 | **Gerekli:** Content Delivery Network (CDN) | content.powerapps.com | TCP 443 |
| 4 | **Gerekli:** Microsoft 365 tümleştirmesi | [Microsoft 365 Ortak ve Office Online URL’leri](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) ile ilgili belgelere bakın | YOK |
| 5 | **Gerekli:** Portal | app.powerbi.com | TCP 443 |
| 6 | **Gerekli:** Hizmet telemetrisi | dc.services.visualstudio.com | TCP 443 |
| 7 | **İsteğe bağlı:** Bilgilendirme iletileri | dynmsg.modpim.com | TCP 443 |
| 8 | **İsteğe bağlı:** NPS anketleri | nps.onyx.azure.net | TCP 443 |
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

Diğer ilgili siteler için Power BI bağlantıları. Bu siteler belgeleri, destek bilgilerini, yeni özellik isteklerini ve daha fazlasını barındırır. Beyaz liste isteğe bağlı olduğundan, bu sitelere erişim Power BI’ın işlevselliğini etkilemez.

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