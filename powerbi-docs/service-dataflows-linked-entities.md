---
title: Power BI’da veri akışları arasındaki varlıkları ilişkilendirme
description: Power BI'daki veri akışlarındaki varlıkları ilişkilendirme hakkında bilgi edinin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/06/2018
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: b69b84c7c61227ef7a827722c86f54100bd2f3b7
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51268881"
---
# <a name="link-entities-between-dataflows-in-power-bi-preview"></a>Power BI’da veri akışları arasındaki varlıkları ilişkilendirme (Önizleme)

Power BI’daki veri akışları sayesinde, iş analizi uzmanlarının verileri bir kez hazırlayıp yönetebileceği ve sonra kuruluştaki farklı analiz uygulamaları arasında yeniden kullanabildiği tek bir kurumsal veri depolama kaynağına sahip olabilirsiniz. 

Veri akışları arasındaki varlıkları ilişkilendirdiğinizde, bu verileri sürdürme gereksinimi olmadan, başkalarının sahip olduğu diğer veri akışları tarafından zaten alınmış, temizlenmiş ve dönüştürülmüş varlıkları yeniden kullanabilirsiniz. Bağlantılı varlıklar diğer veri akışlarındaki varlıkları işaret eder ve verileri *kopyalamaz* veya yinelemez.

![Power BI’daki bağlantılı varlıklar](media/service-dataflows-linked-entities/linked-entities_00.png)

Bağlantılı varlıklar **salt okunur** özelliktedir. Bağlantılı bir varlık için dönüşümler oluşturmak istiyorsanız, bağlantılı varlığa başvuru ile birlikte yeni bir hesaplanmış varlık oluşturmanız gerekir.

## <a name="linked-entity-availability"></a>Bağlantılı varlığın kullanılabilirliği

Bağlantılı varlıkların yenilenmesi için bir [Power BI Premium](service-premium.md) aboneliği gerekir. Bağlantılı varlıklar, Power BI Premium kapasitesinde barındırılan bir çalışma alanı üzerindeki herhangi bir veri akışında kullanılabilir. Kaynak veri akışı ile ilgili bir sınırlama yoktur.

Bağlantılı varlıklar yalnızca yeni Power BI çalışma alanlarında düzgün çalışır. [Yeni Power BI çalışma alanları](service-create-the-new-workspaces.md) hakkında daha fazla bilgi edinebilirsiniz. Tüm bağlı veri akışlarının düzgün çalışması için yeni çalışma alanlarına yerleştirilmesi gerekir.

## <a name="how-to-link-entities-between-dataflows"></a>Veri akışları arasındaki varlıkları ilişkilendirme

Power BI’da veri akışları arasındaki varlıkları birkaç şekilde ilişkilendirebilirsiniz. Aşağıdaki görüntüde gösterildiği gibi Veri Akışları yazma aracından **Bağlantılı varlıkları ekle**’yi seçebilirsiniz. 

![Power BI’daki bağlantılı varlıklar](media/service-dataflows-linked-entities/linked-entities_00.png)

Ayrıca, Power BI hizmetindeki **Varlık ekle** menü öğesinden **Bağlantılı varlıkları ekle**’yi seçebilirsiniz.

![Power BI’daki bağlantılı varlıklar](media/service-dataflows-linked-entities/linked-entities_01.png)

Varlıkları ilişkilendirmek için Power BI kimlik bilgilerinizle oturum açmanız gerekir.

Bir **Gezgin** penceresi açılır ve bağlanabileceğiniz bir varlık kümesi seçmenize olanak tanır. Görüntülenen varlıklar, Power BI kiracınızdaki tüm çalışma alanlarında izinlerine sahip olduğunuz varlıklardır. 

Bağlantılı varlıklarınız seçildikten sonra, onları Bağlantılı varlık olarak tanımlayan özel bir simge ile birlikte yazma aracında veri akışınızın varlık listesinde görünür.

Kaynak veri akışını, bağlantılı varlığınızın veri akışı ayarlarından da görüntüleyebilirsiniz.

## <a name="refresh-logic-of-linked-entities"></a>Bağlantılı varlıkların yenileme mantığı
Bağlantılı varlıkların varsayılan yenileme mantığı, kaynak veri akışının hedef veri akışı ile aynı çalışma alanında bulunup bulunmadığına bağlı olarak değişir. Aşağıdaki bölümlerde her birinin davranışı açıklanmıştır.

### <a name="links-between-workspaces"></a>Çalışma alanları arasındaki bağlantılar

Farklı çalışma alanlarındaki varlıkların bağlantıları için yenileme işlemi, bir dış veri kaynağı gibi davranır. Veri akışı yenilendiğinde kaynak veri akışından varlığın en son verilerini alır. Kaynak veri akışı yenilenirse hedef veri akışındaki verileri otomatik olarak etkilemez.

### <a name="links-in-the-same-workspace"></a>Aynı çalışma alanındaki bağlantılar

Bir kaynak veri akışının verileri yenilendiğinde, bu olay aynı çalışma alanındaki tüm hedef veri akışlarında bağımlı varlıklar ve bunları temel alan tüm hesaplanmış varlıklar için bir yenileme işlemini tetikler. Hedef veri akışındaki diğer tüm varlıklar, veri akışı zamanlamasına göre yenilenir. Birden fazla kaynağa bağlı olan varlıklar, kaynakları başarıyla güncelleştirildiğinde verilerini güncelleştirir.

Tüm yenileme işleminin tek seferde yürütülmesinin yararlı olduğunu unutmayın. Bu nedenle, hedef veri akışı yenilenemezse kaynak veri akışında da yenileme işlemi başarısız olur.

## <a name="permissions-when-viewing-reports-from-dataflows"></a>Veri akışlarından raporları görüntülerken gereken izinler

Kullanıcılar, bir veri akışını temel alan veriler içeren Power BI raporu oluştururken yalnızca kullanıcının kaynak veri akışına erişimi olması durumunda bağlantılı varlıkları görebilir.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

Bağlantılı varlıklarla çalışırken göz önünde bulundurulması gereken birkaç sınırlama vardır:

* En fazla beş başvuran atlama vardır
* Bağlantılı varlıkların döngüsel bağımlılıklarına izin verilmez
* Veri akışı [yeni bir Power BI çalışma alanı](service-create-the-new-workspaces.md) içinde bulunmalıdır


## <a name="next-steps"></a>Sonraki Adımlar

Veri akışı oluştururken veya veri akışları ile çalışırken aşağıdaki makaleler yararlı olabilir. 

* [Power BI’da self servis veri hazırlığı (Önizleme)](service-dataflows-overview.md)
* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Power BI Premium’da hesaplanan varlıkları kullanma (Önizleme)](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma (Önizleme)](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışları için geliştirici kaynakları (Önizleme)](service-dataflows-developer-resources.md)

Power Query ve zamanlanmış yenileme hakkında daha fazla bilgi için şu makaleleri okuyabilirsiniz:
* [Power BI Desktop'ta sorgulara genel bakış](desktop-query-overview.md)
* [Zamanlanmış yenileme yapılandırma](refresh-scheduled-refresh.md)

Ortak Veri Modeli hakkında daha fazla bilgi için genel bakış makalesini okuyabilirsiniz:
* [Ortak Veri Modeli - genel bakış ](https://docs.microsoft.com/powerapps/common-data-model/overview)
