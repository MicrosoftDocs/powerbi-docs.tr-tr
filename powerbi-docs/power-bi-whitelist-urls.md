---
title: Power BI URL'leri
description: Uç noktaların Power BI kullanan müşteriler tarafından erişilebilir durumda olması gerekir
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/13/2018
ms.openlocfilehash: 8e29fa0c9471bb865619102247f38776208c3d87
ms.sourcegitcommit: 8990028a348b642ba5c96f001fe3a4280f0166ee
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "40101151"
---
# <a name="power-bi-urls"></a>Power BI URL'leri

Power BI SaaS (Hizmet Olarak Yazılım) uygulaması olarak da bilinen **Power BI çevrimiçi hizmeti** için İnternet bağlantısı gerekir. Power BI çevrimiçi hizmetini kullanan müşterilerin aşağıdaki uç noktalara erişebiliyor olması gerekir.

Power BI çevrimiçi hizmetini kullanmak için aşağıdaki tabloda **gerekli** olarak işaretlenen uç noktalara ve bağlantılı sitelerde **gerekli** olarak işaretlenen uç noktalarına erişim sahibi olmanız gerekir. Dış site bağlantısı belirli bir bölüme başvuruyorsa yalnızca bu bölümdeki uç noktalarını gözden geçirmeniz gerekir.

**İsteğe bağlı** olarak işaretlenen uç noktalar, belirli işlevlerin çalışması için **izin verilenler listesine eklenebilir**.

Power BI çevrimiçi hizmetlerinin listelenen uç noktaları için yalnızca 443 numaralı TCP bağlantı noktasının açılması gerekir.

Joker karakterler (*) kök etki alanı altındaki tüm düzeyleri temsil eder ve bilgi bulunmayan alanlar Yok ifadesiyle belirtilmiştir. **Hedefler** sütununda FQDN/etki alanları ve uç noktalarıyla ilgili daha fazla bilginin bulunduğu dış sitelerin bağlantıları yer almaktadır.

>[!Important]
>Aşağıdaki tabloda yer alan bilgiler **ABD Kamu bulutu**, **Almanya bulutu** ve **Çin bulutu** için geçerli değildir.

## <a name="authentication"></a>Kimlik Doğrulama

Power BI, Office 365 kimlik doğrulama ve kimlik bölümündeki gerekli uç noktaları kullanır. Power BI'ı kullanmak için aşağıdaki bağlantıdan ulaşabileceğiniz sitede yer alan uç noktalara bağlanabiliyor olmanız gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Gerekli:** Kimlik doğrulama ve kimlik | Office 365 izin verilenler sitesindeki [Office 365 kimlik doğrulama ve kimlik bölümüne](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_identity) bakın | YOK |

## <a name="general-site-usage"></a>Genel site kullanımı

Genel Power BI kullanımı için aşağıdaki tabloda ve bağlantılı sitelerde belirtilen uç noktalara bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Gerekli:** Arka uç API'leri | *.analysis.windows.net | TCP 443 |
| 2 | **Gerekli:** Office 365 tümleştirmesi | Office 365 izin verilenler sitesindeki [Office 365 portal ve paylaşma bölümüne](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity) bakın | YOK |
| 3 | **Gerekli:** Portal | app.powerbi.com | TCP 443 |
| 4 | **Gerekli:** Hizmet telemetrisi | dc.services.visualstudio.com | TCP 443 |
| 5 | **İsteğe bağlı:** Bilgilendirme iletileri | dynmsg.modpim.com | TCP 443 |
| 6 | **İsteğe bağlı:** NPS anketleri | nps.onyx.azure.net | TCP 443 |

## <a name="administration"></a>Yönetim

Power BI'da yönetim işlevleri gerçekleştirmek için aşağıda bağlantısı verilen sitelerde yer alan uç noktalara bağlanabiliyor olmanız gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Gerekli:** Kullanıcıları yönetmek ve denetim günlüklerini görüntülemek için | Office 365 izin verilenler sitesindeki [Office 365 portal ve paylaşma bölümüne](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_portal-identity) bakın | YOK |

## <a name="get-data"></a>Veri Al

OneDrive gibi belirli veri kaynaklarından veri almak için aşağıdaki tabloda yer alan uç noktalarına bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Gerekli:** AppSource (Power BI'ın içindeki veya dışındaki uygulamalar) | appsource.microsoft.com | TCP 443 |
| 2 | **İsteğe bağlı:** Kişisel OneDrive hesabınızdaki dosyaları içeri aktarma | [OneDrive sitesindeki gerekli URL'ler ve bağlantı noktalarına](https://support.office.com/en-ie/article/required-urls-and-ports-for-onedrive-ce15d2cc-52ef-42cd-b738-d9c6f9b03f3a) bakın | YOK |
| 3 | **İsteğe bağlı:** 60 saniyede Power BI eğitim videosu | *.doubleclick.net </br> *.ggpht.com </br> *.google.com </br> *.googlevideo.com </br> *.youtube.com </br> *.ytimg.com </br> fonts.gstatic.com | TCP 443 |
| 4 | **İsteğe bağlı:** PubNub akış verisi kaynakları | [PubNub belgelerine](https://support.pubnub.com/support/solutions/articles/14000043522) bakın | YOK |

## <a name="dashboard-and-report-integration"></a>Pano ve Rapor tümleştirmesi 

Power BI, panolarınızı ve raporlarınızı desteklemek için belirli uç noktaları kullanır. Aşağıdaki tabloda ve bağlantılı sitelerde belirtilen uç noktalara bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Gerekli:** Excel tümleştirmesi | Office 365 izin verilenler sitesindeki [Office Online bölümüne](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline) bakın | YOK |

## <a name="custom-visuals"></a>Özel görseller

Power BI, özel görselleri görüntülemek ve onlara erişim sağlamak için belirli uç noktalarını kullanır. Aşağıdaki tabloda ve bağlantılı sitelerde belirtilen uç noktalara bağlanabilmeniz gerekir.

| Satır | Amaç | Hedefler | Bağlantı noktaları |
|-----|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|---------------------------------------------|
| 1 | **Gerekli:** Market arabiriminden ve dosyadan özel görsel içeri aktarma | *.microsoft.com </br> *.bing.com </br> *.msecnd.net </br> *.osi.office.net </br> *.azureedge.net </br> ajax.aspnetcdn.com </br> nexus.ensighten.com </br> store.office.com | TCP 443 |
| 2 | **İsteğe bağlı:** Bing Haritalar | bing.com </br> platform.bing.com </br> *.dynamic.tiles.virtualearth.net </br> *.virtualearth.net | TCP 443 |
| 3 | **İsteğe bağlı:** PowerApps | PowerApps sistem gereksinimleri sitesinin [Gerekli hizmetler bölümüne](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) bakın | YOK |
| 4 | **İsteğe bağlı:** Visio | Office 365 izin verilenler sitesindeki [Office Online bölümüne](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_officeonline) bakın | YOK |