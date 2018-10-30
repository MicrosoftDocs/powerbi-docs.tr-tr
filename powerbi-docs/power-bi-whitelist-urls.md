---
title: Power BI URL'leri
description: Bu makalede Power BI hizmetini kullanan müşteriler için erişilebilir durumda olması gereken uç noktalar anlatılmaktadır.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/22/2018
ms.openlocfilehash: cc7b24d273f8e83854f7e316f0c761e710e48160
ms.sourcegitcommit: a764e4b9d06b50d9b6173d0fbb7555e3babe6351
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2018
ms.locfileid: "49641977"
---
# <a name="power-bi-urls"></a>Power BI URL'leri

Power BI SaaS (Hizmet Olarak Yazılım) uygulaması olarak da bilinen **Power BI çevrimiçi hizmeti** için internet bağlantısı gerekir. Power BI çevrimiçi hizmetini kullanan müşterilerin aşağıdaki uç noktalara erişebiliyor olması gerekir.

Power BI çevrimiçi hizmetini kullanmak için aşağıdaki tabloda **gerekli** olarak işaretlenen uç noktalara ve bağlantılı sitelerde **gerekli** olarak işaretlenen uç noktalarına erişim sahibi olmanız gerekir. Dış site bağlantısı belirli bir bölüme başvuruyorsa yalnızca bu bölümdeki uç noktalarını gözden geçirmeniz gerekir.

**İsteğe bağlı** olarak işaretlenen uç noktalar, belirli işlevlerin çalışması için **izin verilenler listesine eklenebilir**.

Power BI çevrimiçi hizmetlerinin listelenen uç noktaları için yalnızca 443 numaralı TCP bağlantı noktasının açılması gerekir.

Joker karakterler (*) kök etki alanı altındaki tüm düzeyleri temsil eder ve bilgi bulunmayan alanlar Yok ifadesiyle belirtilmiştir. **Hedefler** sütununda FQDN/etki alanları ve uç noktalarıyla ilgili daha fazla bilginin bulunduğu dış sitelerin bağlantıları yer almaktadır.

>[!Important]
>Aşağıdaki tabloda yer alan bilgiler **ABD Kamu bulutu**, **Almanya bulutu** veya **Çin bulutu** için geçerli değildir.

## <a name="authentication"></a>Kimlik Doğrulama

Power BI, Office 365 kimlik doğrulama ve kimlik bölümündeki gerekli uç noktaları kullanır. Power BI'ı kullanmak için aşağıdaki bağlantıdan ulaşabileceğiniz sitede yer alan uç noktalara bağlanabiliyor olmanız gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Kimlik doğrulama ve kimlik | [Office Online ve ortak URL'ler](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) için Office 365 belgelerine bakın.  | YOK |

## <a name="general-site-usage"></a>Genel site kullanımı

Genel Power BI kullanımı için aşağıdaki tabloda ve bağlantılı sitelerde belirtilen uç noktalara bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Arka uç API'leri | *.analysis.windows.net | TCP 443 |
| 2 | **Gerekli:** Office 365 tümleştirmesi | [Office Online ve ortak URL'ler](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) için Office 365 belgelerine bakın. | YOK |
| 3 | **Gerekli:** Portal | app.powerbi.com | TCP 443 |
| 4 | **Gerekli:** Hizmet telemetrisi | dc.services.visualstudio.com | TCP 443 |
| 5 | **İsteğe bağlı:** Bilgilendirme iletileri | dynmsg.modpim.com | TCP 443 |
| 6 | **İsteğe bağlı:** NPS anketleri | nps.onyx.azure.net | TCP 443 |
| | | |

## <a name="administration"></a>Yönetim

Power BI'da yönetim işlevleri gerçekleştirmek için aşağıda bağlantısı verilen sitelerde yer alan uç noktalara bağlanabiliyor olmanız gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Kullanıcıları yönetmek ve denetim günlüklerini görüntülemek için | [Office Online ve ortak URL'ler](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) için Office 365 belgelerine bakın. | YOK |
| | | |

## <a name="getting-data"></a>Veri alma

OneDrive gibi belirli veri kaynaklarından veri almak için aşağıdaki tabloda yer alan uç noktalarına bağlanabilmeniz gerekir. Kuruluşunuzda kullanılan belirli veri kaynakları için ek internet etki alanlarına ve URL'lere erişim gerekli olabilir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** AppSource (Power BI'ın içindeki veya dışındaki uygulamalar) | appsource.microsoft.com </br> *.s-microsoft.com  | TCP 443 |
| 2 | **Gerekli:** Oturum açma ve içerik paketleri için veri alma | *.github.com  | TCP 443 |
| 3 | **İsteğe bağlı:** Kişisel OneDrive hesabınızdaki dosyaları içeri aktarma | [OneDrive sitesindeki gerekli URL'ler ve bağlantı noktalarına](https://docs.microsoft.com/en-us/onedrive/required-urls-and-ports) bakın | YOK |
| 4 | **İsteğe bağlı:** 60 saniyede Power BI eğitim videosu | *.doubleclick.net </br> *.ggpht.com </br> *.google.com </br> *.googlevideo.com </br> *.youtube.com </br> *.ytimg.com </br> fonts.gstatic.com | TCP 443 |
| 5 | **İsteğe bağlı:** PubNub akış verisi kaynakları | [PubNub belgelerine](https://support.pubnub.com/support/solutions/articles/14000043522) bakın | YOK |
| | | |

## <a name="dashboard-and-report-integration"></a>Pano ve rapor tümleştirmesi

Power BI, panolarınızı ve raporlarınızı desteklemek için belirli uç noktaları kullanır. Aşağıdaki tabloda ve bağlantılı sitelerde belirtilen uç noktalara bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Excel tümleştirmesi | [Office Online ve ortak URL'ler](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) için Office 365 belgelerine bakın. | YOK |
| | | |

## <a name="custom-visuals"></a>Özel görseller

Power BI, özel görselleri görüntülemek ve onlara erişim sağlamak için belirli uç noktalarını kullanır. Aşağıdaki tabloda ve bağlantılı sitelerde belirtilen uç noktalara bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **Gerekli:** Market arabiriminden veya dosyadan özel görsel içeri aktarma | *.azureedge.net </br> *.blob.core.windows.net </br> store.office.com | TCP 443 |
| 2 | **İsteğe bağlı:** Bing Haritalar | bing.com </br> platform.bing.com </br> *.dynamic.tiles.virtualearth.net </br> *.virtualearth.net | TCP 443 |
| 3 | **İsteğe bağlı:** PowerApps | PowerApps sistem gereksinimleri sitesinin [Gerekli hizmetler bölümüne](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) bakın | YOK |
| 4 | **İsteğe bağlı:** Visio | [Office Online ve ortak URL'ler](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) ile [SharePoint Online ve OneDrive İş](https://docs.microsoft.com/en-us/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business) için Office 365 belgelerine bakın. | YOK |
| | | |

## <a name="related-external-sites"></a>İlgili dış siteler

Diğer ilgili siteler için Power BI bağlantıları. Bu siteler belgeleri, destek bilgilerini, yeni özellik isteklerini ve daha fazlasını içerir. Bu siteler Power BI işlevlerini etkilemez, isteğe bağlı olarak izin verilenler listesine alınabilir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
| --- | --- | --- | --- |
| 1 | **İsteğe bağlı:** Topluluk sitesi | community.powerbi.com </br> oxcrx34285.i.lithium.com | TCP 443 |
| 2 | **İsteğe bağlı:** Belgeler sitesi | docs.microsoft.com </br> img-prod-cms-rt-microsoft-com.akamaized.net </br> statics-uhf-eas.akamaized.net </br> cdnssl.clicktale.neting-district.clicktale.net | TCP 443 |
| 3 | **İsteğe bağlı:** İndirme sitesi (Power BI Desktop vb.) | download.microsoft.com | TCP 443 |
| 4 | **İsteğe bağlı:** Dış yönlendirme siteleri | aka.ms </br> go.microsoft.com | TCP 443 |
| 5 | **İsteğe bağlı:** Fikir geri bildirim sitesi| ideas.powerbi.com </br> powerbi.uservoice.com | TCP 443 |
| 6 | **İsteğe bağlı:** Power BI sitesi - giriş sayfası, daha fazla bilgi edinme bağlantıları, destek sitesi, indirme bağlantıları, iş ortağı gösterimi vb. | powerbi.microsoft.com | TCP 443 |
| 7 | **İsteğe bağlı:** Power BI Geliştirici Merkezi | dev.powerbi.com | TCP 443 |
| 8 | **İsteğe bağlı:** Destek sitesi | support.powerbi.com </br> s3.amazonaws.com </br> *.olark.com </br> logx.optimizely.com </br> mscom.demdex.net </br> tags.tiqcdn.com | TCP 443 |
| | | |