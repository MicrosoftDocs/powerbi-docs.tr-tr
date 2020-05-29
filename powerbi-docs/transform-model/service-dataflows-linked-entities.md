---
title: Power BI’da veri akışları arasındaki varlıkları ilişkilendirme
description: Power BI'daki veri akışlarındaki varlıkları ilişkilendirme hakkında bilgi edinin
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/08/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 8326d68408b083a606730355538d2aae7fe2ad4c
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83322758"
---
# <a name="link-entities-between-dataflows-in-power-bi"></a>Power BI’da veri akışları arasındaki varlıkları ilişkilendirme

Power BI’daki veri akışları sayesinde, iş analizi uzmanlarının verileri bir kez hazırlayıp yönetebileceği ve sonra kuruluştaki farklı analiz uygulamaları arasında yeniden kullanabildiği tek bir kurumsal veri depolama kaynağına sahip olabilirsiniz. 

Veri akışları arasındaki varlıkları ilişkilendirdiğinizde, bu verileri sürdürme gereksinimi olmadan, başkalarının sahip olduğu diğer veri akışları tarafından zaten alınmış, temizlenmiş ve dönüştürülmüş varlıkları yeniden kullanabilirsiniz. Bağlantılı varlıklar diğer veri akışlarındaki varlıkları işaret eder ve verileri *kopyalamaz* veya yinelemez.

![Power BI’daki bağlantılı varlıklar](media/service-dataflows-linked-entities/linked-entities_00.png)

Bağlantılı varlıklar **salt okunur** özelliktedir. Bağlantılı bir varlık için dönüşümler oluşturmak istiyorsanız, bağlantılı varlığa başvuru ile birlikte yeni bir hesaplanmış varlık oluşturmanız gerekir.

## <a name="linked-entity-availability"></a>Bağlantılı varlığın kullanılabilirliği

Bağlantılı varlıkların yenilenmesi için bir [Power BI Premium](../admin/service-premium-what-is.md) aboneliği gerekir. Bağlantılı varlıklar, Power BI Premium kapasitesinde barındırılan bir çalışma alanı üzerindeki herhangi bir veri akışında kullanılabilir. Kaynak veri akışı ile ilgili bir sınırlama yoktur.

Bağlantılı varlıklar yalnızca yeni Power BI çalışma alanlarında düzgün çalışır. [Yeni Power BI çalışma alanları](../collaborate-share/service-create-the-new-workspaces.md) hakkında daha fazla bilgi edinebilirsiniz. Tüm bağlı veri akışlarının düzgün çalışması için yeni çalışma alanlarına yerleştirilmesi gerekir.

> [!NOTE]
> Varlıklar, standart varlıklar mı hesaplanan varlıklar mı olduğuna göre farklılık gösterir. Standart varlıklar (genellikle yalnızca varlıklar olarak adlandırılır), SQL veritabanı gibi bir dış veri kaynağını sorgular. Hesaplanan varlıklar, Power BI’da Premium kapasite gerektirir ve Power BI depolamada bulunmakta olan veriler üzerinde dönüştürmeler çalıştırır. 
>
>Veri akışınız Premium kapasite çalışma alanında değilse, yine de tek bir sorguya başvurabilir veya depolama dönüştürmelerinde dönüştürmeler tanımlanmadığı sürece iki ya da daha fazla sorguyu birleştirebilirsiniz. Böyle başvurular standart varlıklar olarak değerlendirilir. Bunu yapmak için **Yüklemeyi etkinleştir** seçeneğini kapatarak, başvurulan sorguların verilerin gerçekleştirilmesini ve depolama alanına alınmasını engellemesini sağlayın. Buradan, **Yüklemeyi etkinleştir = false** sorgularına başvurabilir ve yalnızca gerçekleştirmek istediğiniz sonuçta elde edilen sorgular için **Yüklemeyi etkinleştir** seçeneğini **Açık** olarak ayarlayın.


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
* Veri akışı [yeni bir Power BI çalışma alanı](../collaborate-share/service-create-the-new-workspaces.md) içinde bulunmalıdır
* Bağlantılı bir varlık, verilerinin şirket içi veri kaynağından alan normal bir varlıkla birleştirilemez
* Veri akışlarında bir sorgu (örneğin, A sorgusu), başka bir sorgunun (B sorgusu) hesaplanması için kullanıldığında B sorgusu hesaplanmış bir varlık olur. Hesaplanmış varlıklar, şirket içi kaynaklara başvuramaz.


## <a name="next-steps"></a>Sonraki Adımlar

Veri akışı oluştururken veya veri akışları ile çalışırken aşağıdaki makaleler yararlı olabilir. 

* [Power BI’da self servis veri hazırlığı](service-dataflows-overview.md)
* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Power BI Premium'da hesaplanan varlıkları kullanma](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışları için geliştirici kaynakları](service-dataflows-developer-resources.md)

Power Query ve zamanlanmış yenileme hakkında daha fazla bilgi için şu makaleleri okuyabilirsiniz:
* [Power BI Desktop'ta sorgulara genel bakış](desktop-query-overview.md)
* [Zamanlanmış yenileme yapılandırma](../connect-data/refresh-scheduled-refresh.md)

Ortak Veri Modeli hakkında daha fazla bilgi için genel bakış makalesini okuyabilirsiniz:
* [Ortak Veri Modeli - genel bakış ](https://docs.microsoft.com/powerapps/common-data-model/overview)