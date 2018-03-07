---
title: "Power BI Desktop raporlarında kılavuz çizgilerini ve kılavuza yaslama işlevini kullanma"
description: "Power BI Desktop raporlarında kılavuz çizgilerini, kılavuza yaslama işlevini, z düzenini, hizalamayı ve dağıtımı kullanma"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1b6b1a3ecda7d3f827975da8fcfec5d9d5b67023
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="use-gridlines-and-snap-to-grid-in-power-bi-desktop-reports"></a>Power BI Desktop raporlarında kılavuz çizgilerini ve kılavuza yaslama işlevini kullanma
**Power BI Desktop** rapor tuvali, görselleri rapor sayfasında düzgünce hizalamanızı sağlayan kılavuz çizgileri ve raporunuzdaki görsellerin temiz, hizalı ve eşit aralıklı görünmesi için kılavuza yaslama özelliği sunar.

**Power BI Desktop**'ta bir rapordaki nesnelerin z düzenini ayarlayabilir (bir öne getirme, bir arkaya gönderme) ve tuvalde seçili görselleri hizalayabilir veya eşit bir şekilde dağıtabilirsiniz.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_0.png)

### <a name="enabling-gridlines-and-snap-to-grid"></a>Kılavuz çizgilerini ve kılavuza yaslama işlevini etkinleştirme
Kılavuz çizgileri ve kılavuza yaslama işlevini etkinleştirmek için **Görünüm** şeridini seçin, sonra **Kılavuz çizgilerini göster** ve **Nesneleri kılavuza yasla** onay kutularını etkinleştirin. Kutulardan birini veya ikisini seçebilirsiniz; bunlar birbirinden bağımsız olarak çalışır.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_1.png)

> [!NOTE]
> **Kılavuz çizgilerini göster** ve **Nesneleri kılavuza yasla** devre dışıysa herhangi bir veri kaynağına bağlandığınızda etkinleşirler.
> 
> 

### <a name="using-gridlines"></a>Kılavuz çizgilerini kullanma
Kılavuz çizgileri, iki veya daha fazla görselin düzgünce hizalı olup olmadığını görmenize yardım eden görsel kılavuzlardır. İki (veya daha fazla) görselin yatay ya da dikey hizalı olup olmadığını anlamak için kılavuz çizgilerini kullanarak kenarlıklarının hizalı olup olmadığını görebilirsiniz.

*CTRL tuşuna basıp tıklayarak* birden fazla görseli aynı anda seçebilirsiniz. Böylece seçili tüm görsellerin kenarlıkları belirir ve görsellerin düzgün bir şekilde hizalı olup olmadığını kolayca anlamanıza yardımcı olur.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_2.png)

#### <a name="using-gridlines-inside-visuals"></a>Kılavuz çizgileri görsellerin içinde kullanma
Power BI'da kılavuz çizgileri görsellerin içinde de görülebilir. Bunlar veri noktalarını ve değerleri karşılaştırmak için görsel kılavuzlar sağlar. **Power BI Desktop**'ın Eylül 2017 sürümünden itibaren **Görsel Öğeler** bölmesinin **Biçim** bölümündeki **X Ekseni** ve **Y Ekseni** kartlarını (görsel türüne göre) kullanarak görsellerin içindeki kılavuz çizgilerini yönetebilirsiniz. Bir görselin içindeki kılavuz çizgilerinin aşağıdaki öğelerini yönetebilirsiniz:

* Kılavuz çizgileri etkinleştirme veya devre dışı bırakma
* Kılavuz çizgilerinin rengini değiştirme
* Kılavuz çizgilerinin darbe genişliğini ayarlama
* Görseldeki kılavuz çizgilerinin stilini düz, kesik çizgili, veya noktalı olarak seçme

Kılavuz çizgilerinin belirli öğelerini değiştirmek, özellikle görsellerinde koyu renkli arka planlar olan raporlarda kullanışlıdır. Aşağıdaki görüntüde **X Ekseni** kartındaki *Kılavuz çizgileri* bölümü gösterilmektedir.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_9.png)

### <a name="using-snap-to-grid"></a>Kılavuza yaslama işlevini kullanma
**Nesneleri kılavuza yasla** etkinleştirildiğinde, **Power BI Desktop** tuvalinde taşıyacağınız (veya yeniden boyutlandıracağınız) tüm görseller otomatik olarak en yakındaki kılavuz eksenine hizalanır. Böylece iki ya da daha fazla görselin aynı yatay veya dikey konuma ya da aynı boyuta hizalandığından emin olmak çok daha kolaylaşır.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_3.png)

Raporlarınızdaki görsellerin düzgünce hizalandığından emin olmak için **kılavuz çizgileri** ve **kılavuza yaslama işlevini** kullanmak işte bu kadar kolay.

### <a name="using-z-order-align-and-distribute"></a>Z düzenini, hizalamayı ve dağıtımı kullanma
Bir rapordaki görsellerin önden arkaya sırasını yönetebilirsiniz. Buna genellikle öğelerin *z düzeni* denir. Böylece görselleri istediğiniz biçimde üst üste getirebilir ve her görselin önden arkaya sırasını ayarlayabilirsiniz. Bu sıralama, **Bir Öne Getir** ve **Bir Arkaya Gönder** düğmeleriyle yapılır. Bu düğmeler **Biçim** şeridinin **Düzenle** bölümünde bulunur ve bir veya daha fazla görsel seçildiğinde belirir (seçili görsel yoksa kullanılamaz).

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_4.png)

**Biçim** şeridi ayrıca görsellerinizi pek çok farklı şekilde hizalamanızı sağlar. Böylece görselleriniz sayfada sizin en iyi görünüm ve işleve sahip olduğuna inandığınız hizalamayla görünür.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_5.png)

Aşağıdaki görüntüde görüldüğü gibi bir görsel seçilir ve **Hizala** düğmesine tıklanırsa o görsel, rapor tuvalinin kenarına (veya merkezine) hizalanır.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_6.png)

İki veya daha fazla görsel seçildiğinde, zaten hizalı olan sınırlara göre birlikte hizalanır. Örneğin, iki görsel seçip *Sola Hizala* düğmesine tıklarsanız görsellerin hizalanması, seçili tüm görsellerin en soldaki sınırına göre gerçekleştirilir.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_7.png)

Ayrıca, görsellerinizi yatay veya dikey olarak rapor tuvaline eşit dağıtabilirsiniz. **Biçim** şeridindeki **Dağıt** düğmesine tıklamanız yeterlidir.

![](media/desktop-gridlines-snap-to-grid/snap-to-grid_8.png)

Bu kılavuz çizgisi, hizalama ve dağıtım araçlarında yapacağınız birkaç seçimle, raporlarınız tam olarak istediğiniz gibi görünecektir.

