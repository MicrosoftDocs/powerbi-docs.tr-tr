---
title: Onay - Power BI içeriklerini yükseltme ve onaylama
description: Kaliteli içeriği yükselterek veya onaylayarak daha kolay bulunmasını sağlamayı öğrenin
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: conceptual
ms.date: 10/26/2020
LocalizationGroup: Share your work
ms.openlocfilehash: 2389290fedd26c9e88af614e1fbf6afb29c02d35
ms.sourcegitcommit: 932f6856849c39e34229dc9a49fb9379c56a888a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97926810"
---
# <a name="endorsement---promoting-and-certifying-power-bi-content"></a>Onay - Power BI içeriklerini yükseltme ve onaylama

## <a name="endorsement-overview"></a>Onaya genel bakış

Kuruluşlarda genellikle Power BI kullanıcılarının paylaşmasına ve yeniden kullanmasına yönelik çok fazla içerik bulunur. Güvenilir ve yetkili kişilerin onayladığı içerikleri bulmak zor olabilir. Onay, kullanıcıların ihtiyaç duyduğu yüksek kaliteli içeriğe daha kolay erişmelerini sağlar. Onaylanan içerikler etiketleri sayesinde hem Power BI'da hem de kullanıcıların Power BI içeriği aradığı ortamlarda (Excel gibi) kolayca ayırt edilebilir. Ayrıca bu içeriklere aramalarda öncelik verilir ve bazı listelerde arama ölçütü olarak kullanılabilir.

İki tür onay vardır: **yükseltme** ve **onaylama**.

* **Yükseltme**: Yükseltme, kullanıcıların değerli olduğunu ve başkalarının da kullanabileceğini düşündüğü içerikleri vurgulamasına olanak tanır. İçeriklerin kuruluş içinde işbirliğine dayalı bir şekilde yayılmasını teşvik eder.

    Tüm içerik sahipleri veya içeriğin bulunduğu çalışma alanı üzerinde yazma izinleri olan tüm üyeler, paylaşım için yeterince iyi olduğunu düşündükleri içerikleri kolayca yükseltebilir.

    [İçeriğinizi öne çıkarma hakkında bilgi edinin](service-endorse-content.md#promote-content).

* **Onaylama**: Onaylama içeriğin kuruluş kalite standartlarını karşıladığı ve kuruluş genelinde kullanılmaya hazır, güvenilir ve yetkilendirilmiş olarak kabul edilebileceği anlamına gelir.

    Yalnızca [seçili (Power BI yöneticisi tarafından tanımlanmış) bir grup inceleyicinin ](../admin/service-admin-setup-certification.md) içerik onaylama yetkisi vardır. İçeriklerinin onaylanmasını isteyen ancak bunu kendileri yapamayan içerik sahiplerinin gerekli onay işlemleri için kuruluşa özgü yönergeleri izlemesi gerekir.

    [İçerik onaylama](service-endorse-content.md#certify-content) veya [onay isteme](service-endorse-content.md#request-content-certification) hakkında bilgi edinin.

    **Onaylama seçeneği, yalnızca bir Power BI yöneticisi bunu kuruluşunuzda [etkinleştirip yapılandırdıysa](../admin/service-admin-setup-certification.md) bulunur**.

Aşağıdaki görüntüde rapor oluşturmak için kullanacağınız bir veri kümesini ararken onaylı içeriğin (yükseltilmiş ve onaylanmış) nasıl belirtildiği gösterilmiştir.

![Onaylı veri akışları Power Query'de vurgulanır.](media/service-endorsement-overview/power-bi-content-endorsement-dataset-select.png)

## <a name="content-types-that-can-be-endorsed"></a>Onaylanabilecek içerik türleri
Power BI şu an için aşağıdaki içeriklere yönelik onay desteği sunmaktadır:
* Veri kümeleri
* Veri akışları (önizleme)
* Raporlar (önizleme)
* Uygulamalar (önizleme)

## <a name="identifying-endorsed-content"></a>Onaylanmış içeriği tanımlama

Onaylanmış içerikler hem Power BI'da hem de Power BI içeriğinin bulunabileceği Excel gibi ortamlarda yer alan listelerde, kartlarda ve diğer yerlerde rozetler ve simgelerle etiketlenir. Onaylı içerikler aşağıdaki rozetler ve simgelerle gösterilir.

|Rozet|Simge|
|---------|---------|
|![Onay rozetinin ekran görüntüsü.](media/service-endorsement-overview/certified-badge.png)|![Onay simgesinin ekran görüntüsü.](media/service-endorsement-overview/certified-icon.png)|
|![Yükseltme rozetinin ekran görüntüsü.](media/service-endorsement-overview/promoted-badge.png)|![Yükseltme simgesinin ekran görüntüsü.](media/service-endorsement-overview/promoted-icon.png)|
|||

Ayrıca açık raporların veya uygulamaların onay durumunu üst bilgiden görebilirsiniz.
* Onay durumu hem üst bilgide hem de onayı veren kullanıcıyı görebileceğiniz üst bilgi açılan menüsünde gösterilir.

    ![Rapor üst bilgisindeki onay rozetini gösteren ekran görüntüsü.](media/service-endorsement-overview/certification-report-header.png)

* Yükseltme durumu yalnızca üst bilgi açılan menüsünde gösterilir.
 
    ![Rapor üst bilgisindeki yükseltme rozetini gösteren ekran görüntüsü.](media/service-endorsement-overview/promotion-report-header.png)

## <a name="deciding-whether-to-endorse-an-app-or-a-report"></a>Bir uygulamayı veya raporu onaylama kararını verme

Onaylama seçeneğini kullanıcıların bulmasını, kullanmasını ve gerekirse yeniden paylaşmasını istediğiniz içerik öğeleri (uygulamalar, raporlar, veri kümeleri ve veri akışları) için kullanmanız gerekir.

Power BI'da geniş bir hedef kitleyle paylaşmak istediğiniz verileri bir uygulama aracılığıyla paylaşmanız önerilir. Bu en iyi deneyimi uygularsanız kullanıcılar ilgili uygulamayı kolayca bulabilir. Bu gibi durumlarda uygulamayı onaylamanız gerekir. 

Raporları doğrudan paylaşmayı tercih ederseniz raporun kendisini onaylamanız gerekecektir. 

Rapor veya uygulama paylaşırken temel alınan veri kümelerinin temiz ve paylaşılmaya hazır olması durumunda ilgili veri kümelerini onaylamak da iyi bir fikirdir. Aynı şey veri akışları için de geçerlidir.  

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI içeriklerini yükseltme veya onaylama](service-endorse-content.md)
* [Kuruluşunuz için onayı etkinleştirme](../admin/service-admin-setup-certification.md) (Power BI yöneticileri)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)