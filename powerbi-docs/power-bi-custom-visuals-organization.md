---
title: "Power BI’da özel kuruluş görsellerini kullanma"
description: "Power BI'da özel kuruluş görsellerini kullanma, yönetme ve oluşturma"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 02/06/2018
ms.author: maghan
ms.openlocfilehash: 2c90ea4a7e95c354b6dfaec04cff7e5e4009b55f
ms.sourcegitcommit: db37f5cef31808e7882bbb1e9157adb973c2cdbc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="using-organization-custom-visuals-in-power-bi-preview"></a>Power BI’da özel kuruluş görsellerini kullanma (Önizleme)

Power BI'da özel görselleri kullanarak size veya aktarmaya çalıştığınız veri bilgilerine göre uyarlanmış, benzersiz türde bir görsel oluşturabilirsiniz. Bu özel görseller genellikle geliştiriciler tarafından, Power BI’daki birçok görselin gereksinimlerini tam olarak karşılamadığı durumlarda oluşturulur. 

Bazı kuruluşlarda özel görseller daha da önemlidir ve bunlar kuruluşa özgü verilerin ya da bilgilerin aktarılması için gerekli olabilir, özel veri gereksinimlerine sahip olabilir ya da özel iş yöntemlerini vurgulayabilir. Bu durumdaki kuruluşların özel görseller geliştirmesi, kuruluş genelinde paylaşması ve bakımlarının düzgün yapıldığından emin olması gerekir. Power BI özel görselleri (şimdi önizlemede), kuruluşların tam olarak bunu yapmasına olanak sağlar. 

Aşağıdaki resimde, Power BI’daki özel kuruluş görsellerinin (önizleme) yöneticiden başlayıp geliştirme ve bakım aşamalarından geçerek veri analistinde sonlanan akış süreci gösterilmektedir.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

## <a name="how-to-enable-organizational-custom-visuals-preview"></a>Özel kuruluş görsellerini (önizleme) etkinleştirme

Özel kuruluş görselleri şu an Önizlemede olduğundan, Power BI Desktop’ta bu özelliği etkinleştirmeniz gerekir. Bu önizleme özelliğini etkinleştirmek için aşağıdaki resimde gösterildiği gibi şeritten Dosya > Seçenekler ve ayarlar > Seçenekler’i seçin, sonra sol bölmeden Önizleme özellikleri’ni seçip Kuruluşuma özel görseller’in yanındaki onay kutusunu seçin.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-02.jpg)

Kuruluş görselleri, Power BI yöneticisi tarafından Yönetim portalından dağıtılır ve yönetilir. Görsel kuruluş deposuna dağıtıldıktan sonra kuruluştaki kullanıcılar bunları doğrudan Power BI Desktop’tan kolayca keşfedebilir ve özel kuruluş görsellerini raporlarında içeri aktarabilir.

## <a name="using-organizational-custom-visuals"></a>Özel kuruluş görsellerini kullanma

Oluşturduğunuz raporlarda özel kuruluş görsellerini kullanma hakkında daha fazla bilgi için şu makaleye bakın: [Kuruluş görsellerini raporlarınızda içeri aktarma hakkında daha fazla bilgi edinin](power-bi-custom-visuals.md).
 
## <a name="administering-organizational-custom-visuals"></a>Özel kuruluş görsellerini yönetme

Kuruluşunuzda özel kuruluş görsellerini yönetme, dağıtma ve yönetme hakkında daha fazla bilgi edinmek için şu makaleye bakın: [Özel kuruluş görsellerinin dağıtımı ve yönetimi hakkında daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> Özel bir görsel, güvenlik veya gizlilik riski taşıyan kod içerebilir. Bir özel görseli kuruluş deposuna dağıtmadan önce görselin yazarına ve kaynağına güvendiğinizden emin olun. 
> 

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar
 
Özel kuruluş görselleri önizlemede olduğundan, dikkat etmeniz ve göz önünde bulundurmanız gereken birkaç önemli nokta ve sınırlama vardır.
 
Yönetici:

* Eski özel görseller (sürümü tutulan yeni API'leri temel almayan özel görseller gibi) desteklenmez

* Yerinde güncelleştirme henüz desteklenmemektedir. Bir görseli güncelleştirmek için kuruluş deposuna görselin yeni bir sürümünü yüklemeniz gerekir (ayrıca, PBIVIZ dosyasındaki Görsel Kimliğiyle aynı kimliğe sahip olduğundan emin olun). Daha sonra rapor yazarları yeni sürümü kendi raporlarında içeri aktarabilir ve rapordaki görselin geçerli sürümünü yerinde değiştirebilir.

* Özel bir görsel depodan silinirse, silinen görseli kullanan tüm mevcut raporlar işlenmeyi durdurur. Depodan silme işlemi geri alınamaz.
 
Son kullanıcı:

* Ortak marketten (AppSource) ve kuruluş depodan aynı görselin (aynı Görsel Kimliği) kullanılması desteklenmez. Bu durumda, içeri aktarılan en son görsel kullanılır.

* Pano ve raporlardaki kuruluş görsellerinin kuruluş dışıyla paylaşılması desteklenmez. Özel bir kuruluş görseli içeren bir panoyu görüntüleyen kuruluş dışı kullanıcılar boş bir görsel görür. 

* Kuruluş görselleri için Power BI Çalışma Alanı Koleksiyonu desteklenmez

* Web’de yayımlanan raporlardaki özel kuruluş görselleri gösterilmez

* AppSource marketten edinilen Visio görseli, PowerApps görseli ve GlobeMap görseli kuruluş deposu aracılığıyla dağıtılırsa gösterilmez

* Yönetici özel bir görseli depodan silerse ve bu görsel bir raporda kullanılıyorsa görsel artık gösterilmez ve raporun kurtarılması için rapordan kaldırılır