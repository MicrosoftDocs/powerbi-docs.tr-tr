---
title: Çalışma alanlarında içeriği düzenleme
description: Çalışma alanları ve çalışma alanı rolleri hakkında bilgi edinin
author: mihart
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/22/2020
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: 801b5cf5400bbe1cc0487eef596ea3d1cdc5fb1e
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82120217"
---
# <a name="collaborate-in-workspaces"></a>Çalışma alanında işbirliği yapma

 *Çalışma alanları* iş arkadaşlarınızla belirli bir içerik üzerinde işbirliği yaptığınız yerlerdir. Çalışma alanları Power BI *tasarımcıları* tarafından pano ve rapor koleksiyonlarını barındırmak için oluşturulur. Sonra, tasarımcı bu koleksiyonları bir *uygulamanın* içinde paketleyebilir ve kuruluşun tamamına veya belirli kişi veya gruplara dağıtabilir. 

 Power BI hizmetini kullanan herkes **Çalışma alanıma** sahiptir.  Çalışma alanım, kendiniz için içerik oluşturabileceğiniz kişisel korumalı alanınızdır.

 Çalışma alanlarınızı Power BI **Giriş** ekranından veya sol gezinti bölmenizdeki **Çalışma alanı** veya **Çalışma alanımı** seçerek görüntüleyebilirsiniz.

 ![iki tür çalışma alanı gösteren gezinti bölmesi](media/end-user-workspaces/power-bi-home.png)

## <a name="types-of-workspaces"></a>Çalışma alanlarının türleri
**Çalışma Alanım**, size ait olan ve sizin oluşturduğunuz tüm içeriği depolar. Bunu kişisel koruma alanınız veya kendi içeriğinize yönelik bir çalışma alanı gibi düşünün. Yeni içerik oluşturmak çoğu Power BI *tüketicisinin* işinin bir parçası olmadığından birçok kullanıcının **Çalışma alanım** bölümü boş gözükür. Tanım gereği *tüketiciler*, diğer kişiler tarafından oluşturulan verileri kullanır ve iş kararları alırken bu verilerden faydalanır. İçerik oluşturuyorsanız, [Tasarımcılara yönelik Power BI makalelerini](../create-reports/index.yml) okuyabilirsiniz.

**Uygulama çalışma alanlarında** belirli bir uygulamaya yönelik içeriğin tamamı yer alır. Bir *tasarımcı* uygulama oluşturduğunda, uygulamanın kullanılması için gereken tüm içeriği paket haline getirir. İçerikte panolar, raporlar ve veri kümeleri bulunabilir. Her uygulama bu üç içerik türünü içermeyebilir. Bir uygulama yalnızca bir panoyu, her içerik türünden üçer tane öğeyi veya yirmi tane raporu içerebilir. Bu tamamen *tasarımcının* uygulamaya neleri eklediğine bağlıdır. Genelde, *tüketicilere* yönelik uygulama çalışma alanları veri kümelerini içermez.

Aşağıdaki Fig satış uygulaması çalışma alanı, üç rapor ve bir pano içerir. 

![iki tür çalışma alanı gösteren gezinti bölmesi](media/end-user-workspaces/power-bi-app-workspace.png)

## <a name="roles-in-the-workspaces"></a>Çalışma alanlarındaki roller

Roller çalışma alanında neler yapabileceğinizi belirler ve bu sayede ekipler işbirliği yapabilir.  Yeni çalışma alanına erişim verirken, *tasarımcılar* kullanıcıları veya grupları çalışma alanı rollerinden birine ekler: **Görüntüleyici**, **Üye**, **Katkıda Bulunan** veya **Yönetici**. 


Power BI *tüketicisi* olarak çalışma alanlarında genellikle **Görüntüleyici** rolünü kullanarak etkileşim kurarsınız. Ancak bir *tasarımcı*, sizi **Üye** veya **Katılımcı** rolüne atayabilir. Görüntüleyici rolü, başkaları tarafından oluşturulup sizinle paylaşılan içeriği (panolar, raporlar, uygulamalar) görüntülemenizi ve içerikle etkileşim kurmanızı sağlar. Görüntüleyici rolü temeldeki veri kümesine erişemediğinden, içerikle etkileşim kurmak güvenli bir yoldur ve temeldeki veriye zarar verme konusunda endişe duymanıza gerek yoktur.


Görüntüleyici rolüyle *tüketici* olarak yapabileceklerinizin ayrıntılı listesi için bkz. [Tüketiciler için Power BI özellikleri](end-user-features.md).


### <a name="workspace-roles"></a>Çalışma alanı rolleri
Dört rolün yetenekleri şunlardır: yöneticiler, üyeler, katkıda bulunanlar ve görüntüleyiciler. Görüntüleme ve etkileşim dışında bu özelliklerin tamamı için bir Power BI Pro lisansı gerekir.

|Özellik   | Yönetici  | Üye  | Katılımcı  | Görüntüleyici |
|---|---|---|---|---|
| Çalışma alanını güncelleştirebilir ve silebilir.  | X  |   |   |   | 
| Diğer yöneticiler de dahil olmak üzere kişileri ekleyebilir/kaldırabilir.  | X  |   |   |   |
| Üyeleri ve düşük izinlere sahip diğer kişileri ekleyebilir.  |  X | X  |   |   |
| Uygulama yayımlayabilir ve güncelleştirebilir. |  X | X  |   |   |
| Öğe veya uygulama paylaşabilir.<sup>1</sup> |  X | X  |   |   |
| Diğer kişilerin öğeleri yeniden paylaşmasına izin verebilir.<sup>1</sup> |  X | X  |   |   |
| İş arkadaşlarının Giriş Sayfasında uygulamaları öne çıkarabilir |  X | X  |   |   |
| İş arkadaşlarının Giriş Sayfasında panoları ve raporları öne çıkarabilir |  X | X  | X |   |
| Çalışma alanında içerik oluşturabilir, düzenleyebilir ve silebilir.  |  X | X  | X  |   |
| Çalışma alanında rapor yayımlayabilir, içeriği silebilir.  |  X | X  | X  |   |
| Başka bir çalışma alanında, bu çalışma alanındaki bir veri kümesini temel alan rapor oluşturun.<sup>1</sup> |  X | X  | X  |   |
| Bir raporu kopyalayın. | X | X | X |  |
| Öğeleri açın ve öğelerle etkileşim kurun.<sup>2</sup> |  X | X  | X  | X  |
| Çalışma alanı veri akışlarında depolanan verileri okuma | X | X | X | X |

1. Katkıda Bulunanlar ve Üyeler, bir çalışma alanındaki öğeleri ancak yeniden paylaşma izinleri varsa paylaşabilir.

2. Power BI Pro lisansınız olmasa bile, öğeler Premium kapasitedeki bir çalışma alanında yer alıyorsa Power BI hizmetinde öğeleri görüntüleyebilir ve bunlarla etkileşim kurabilirsiniz.

## <a name="licensing-workspaces-and-capacity"></a>Lisans, çalışma alanları ve kapasite
Çalışma alanında neleri yapabileceğinizin ve neleri yapamayacağınızın belirlenmesinde lisanslamanın da rolü vardır. Pek çok özellik için kullanıcının bir Power BI *Pro* lisansına sahip olması gerekir. Çoğu *tüketici* bir *ücretsiz* lisans ile çalışır. 

Ücretsiz lisansınız varsa ve çalışma alanı *Premium kapasitede* depolanıyorsa bu çalışma alanındaki içeriği görüntüleyebilir ve bu içerikle etkileşim kurabilirsiniz. Elmas simgesi, Premium kapasitede depolanan çalışma alanlarını ve uygulamaları belirtir.

![Seçili çalışma alanları](media/end-user-workspaces/power-bi-diamond.png) Daha fazla bilgi edinmek için bkz. [Hangi lisansa sahibim?](end-user-license.md).



## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'daki uygulamalar](end-user-apps.md)    

* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

