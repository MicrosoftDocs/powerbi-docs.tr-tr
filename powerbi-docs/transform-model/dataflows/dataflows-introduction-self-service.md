---
title: Veri akışlarına giriş ve self servis veri hazırlığı
description: Power BI veri akışlarına ve kullanım alanlarına genel bakış
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 10/01/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: b603c0a2ad300145db6342acac3473a2f4a567c6
ms.sourcegitcommit: be424c5b9659c96fc40bfbfbf04332b739063f9c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91638523"
---
# <a name="introduction-to-dataflows-and-self-service-data-prep"></a>Veri akışlarına giriş ve self servis veri hazırlığı

Veri hacmi artmaya devam ettikçe, bu verileri düzgün biçimlendirilmiş, eyleme geçirilebilir bilgilere dönüştürme güçlüğü de artar. Görselleri, raporları ve panoları doldurmak için analize hazır veriler isteriz, çünkü böylelikle veri hacimlerimizi kolayca eyleme dönüştürülebilir içgörüler haline getirebiliriz. Power BI'da büyük verilere yönelik self servis veri hazırlığı ile, yalnızca birkaç tıklamayla verilerden Power BI içgörülerine geçebilirsiniz.

![veri akışı](media/dataflows-introduction-self-service-flow.png)

## <a name="when-to-use-dataflows"></a>Veri akışlarının kullanım alanları

Veri akışları aşağıdaki senaryolarda kullanılmak üzere tasarlanmıştır:

* Power BI içindeki veri kümeleri ve raporları tarafından kullanılabilecek yeniden kullanılabilir dönüşüm mantığı oluşturma. Veri akışları, temel alınan veri öğelerinin yeniden kullanılmasını sağlayarak bulut veya şirket içi veri kaynakları için ayrı bağlantılar oluşturma ihtiyacını ortadan kaldırır.

* Azure Data Lake 2. Nesil depolama alanınızdaki verileri kullanıma sunarak farklı Azure hizmetlerini temel alınan ham verilere bağlama.

* Analistlerin temel alınan sistemlere bağlanmak yerine veri akışlarına bağlanmasını sağlayarak tek gerçeklik kaynağı oluşturup erişilen veriler ve bu verilerin rapor oluşturuculara sunulması üzerinde denetim sahibi olmasını sağlama. İsterseniz verileri sektör standardı tanımlarla eşleyerek Power Platform içindeki diğer hizmetlerde ve ürünlerde kullanılabilecek derli toplu görünümler oluşturabilirsiniz.

* Büyük hacimli verilerle çalışmak ve büyük ölçekte ETL gerçekleştirmek istiyorsanız Power BI Premium hizmetindeki veri akışları daha verimli bir şekilde ölçeklendirilir ve daha fazla esneklik sunar. Veri akışları birçok farklı bulut ve şirket içi kaynağı destekler. 

* Analistlerin temel alınan veri kaynağına doğrudan erişmesini engelleyin. Rapor oluşturucuları veri akışlarını kullanarak içerik geliştirebileceğinden yalnızca birkaç kişiye temel alınan veri kaynaklarına erişim izni vererek analistlerin veri akışlarına erişmesini sağlamak daha kullanışlı bir yöntem olabilir. Bu yaklaşım, temel alınan sistemlerin üzerindeki yükü azaltır ve yöneticilere yenileme sonrası yüklenen sistemler konusunda daha ayrıntılı denetim sunar.

Veri akışını oluşturduktan sonra, Power BI Desktop'ı veya Power BI hizmetini kullanarak Power BI veri akışlarına yerleştirdiğiniz verileri temel alan veri kümeleri, raporlar, panolar ve uygulamalar oluşturabilirsiniz. Bunlar, iş etkinliklerinize derin içgörüler eklemek için Common Data Model'den yararlanır. Veri akışı yenileme zamanlaması, aynı veri kümeleriniz gibi, doğrudan veri akışının oluşturulduğu çalışma alanından yönetilir.

## <a name="next-steps"></a>Sonraki adımlar
Bu makalede, Power BI'da büyük veriler için self servis veri hazırlığına ve bunu kullanmanın birçok yoluna genel bir bakış sağlanır. 

Aşağıdaki makaleler veri akışları ve Power BI hakkında daha fazla bilgi sunmaktadır:

* [Veri akışı oluşturma](dataflows-create.md)
* [Veri akışı yapılandırma ve kullanma](dataflows-configure-consume.md)
* [Veri akışı depolama alanını Azure Data Lake 2. Nesil kullanacak şekilde yapılandırma](dataflows-azure-data-lake-storage-integration.md)
* [Veri akışlarının Premium özellikleri](dataflows-premium-features.md)
* [Veri akışları ve yapay zeka](dataflows-machine-learning-integration.md)
* [Veri akışı sınırlamaları ve önemli noktalar](dataflows-features-limitations.md)


Ortak Veri Modeli hakkında daha fazla bilgi için genel bakış makalesini okuyabilirsiniz:
* [Common Data Model - genel bakış](https://docs.microsoft.com/powerapps/common-data-model/overview)