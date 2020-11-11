---
title: Veri akışı sınırlamaları, kısıtlamaları ve desteklenen bağlayıcılar ve özellikler
description: Veri akışlarının özelliklerine genel bakış
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 10/01/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 89de77e65d8eb675d9e80c3b2497f39af7c32d33
ms.sourcegitcommit: 37bd34053557089c4fbf0e05f78e959609966561
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94396599"
---
# <a name="dataflows-limitations-and-considerations"></a>Veri akışı sınırlamaları ve önemli noktalar

Veri akışı yazma, yenileme ve kapasite yönetimi konularında kullanıcıların dikkat etmesi gereken birkaç sınırlama vardır. Bu sınırlamalar aşağıdaki bölümlerde açıklanmıştır.

## <a name="dataflow-authoring"></a>Veri akışı yazma

Veri akışı yazan kullanıcıların aşağıdaki noktalara dikkat etmesi gerekir:

* Veri akışlarında yazma işlemi Power Query Online (PQO) ortamında gerçekleştirilir. [Power Query sınırları](/power-query/power-query-online-limits) sayfasında belirtilen sınırlamaları inceleyin.
Veri akışı yazma işlemi Power Query Online (PQO) ortamında gerçekleştirildiğinden veri akışı iş yükü yapılandırmalarında gerçekleştirilen güncelleştirmeler yalnızca yenilemeleri etkiler; yazma deneyimini etkilemez

* Veri akışları yalnızca sahipleri tarafından değiştirilebilir

* Veri akışları, *Çalışma Alanım* sayfasında kullanılamaz

* Ağ geçidi veri kaynaklarını kullanan veri akışları, aynı veri kaynağı için birden çok kimlik bilgisini desteklemez

* Web.Page bağlayıcısını kullanmak için bir ağ geçidi gerekir

## <a name="api-considerations"></a>API'lerde dikkat edilmesi gerekenler

Desteklenen veri akışları REST API'leri hakkında daha fazla bilgi için bkz. [REST API başvurusu](/rest/api/power-bi/dataflows). Dikkat etmeniz gereken noktalardan bazıları şunlardır:

* Bir veri akışı dışarı ve içeri aktarıldığında yeni bir kimliğe sahip olur

* Bağlantılı varlıkların bulunduğu veri akışlarını içeri aktarmak, veri akışı içindeki mevcut başvuruları düzeltmez (bu sorgular veri akışı içeri aktarılmadan önce el ile düzeltilmelidir)

* *CreateOrOverwrite* ile başlangıçta içeri aktarma API'si kullanılarak oluşturulmuş olan veri akışlarının üzerine yazılabilir

## <a name="dataflows-in-shared"></a>Paylaşılan kapasitelerdeki veri akışları

Paylaşılan kapasitelerde veri akışları için bazı sınırlamalar vardır:

* Veri akışlarını yenileme sırasında paylaşılan kapasitelerdeki zaman akışları varlık başına 2 saat, veri akışı başına ise 3 saat olarak belirlenmiştir
* Paylaşılan veri akışlarında bağlantılı varlık oluşturulamaz; bu varlıklar sorgudaki *Load Enabled* özelliği devre dışı bırakıldığı sürece veri akışında mevcut olabilir
* Paylaşılan veri akışlarında hesaplanan varlık oluşturulamaz
* Paylaşılan veri akışlarında AutoML ve Bilişsel Hizmetler kullanılamaz
* Paylaşılan veri akışlarında artımlı yenileme çalışmaz

## <a name="dataflows-in-premium"></a>Premium kapasitelerdeki veri akışları

Premium kapasitelerdeki veri akışları aşağıdaki sınırlamalara ve dikkat edilmesi gereken noktalara sahiptir.

**Yenilemeler ve verilerle ilgili dikkat edilecek konular:**

* Veri akışları yenilenirken zaman aşımı 24 saattir (varlıklar ve/veya veri akışları için ayrım yoktur)

* Bir veri akışının yenileme ilkesini artımlı yerine normal olarak değiştirmek veya bunun tersini yapmak tüm verilerin bırakılmasına neden olur

* Veri akışının şemasının değiştirilmesi tüm verilerin bırakılmasına neden olur

**Bağlantılı ve hesaplanan varlıklar:**

* Bağlantılı varlıklar en fazla 32 başvuru düzeyine sahip olabilir

* Bağlantılı varlıkların döngüsel bağımlılıklarına izin verilmez

* Bağlantılı bir varlık, verilerinin şirket içi veri kaynağından alan normal bir varlıkla birleştirilemez

* Veri akışlarında bir sorgu (örneğin, *A* sorgusu), başka bir sorgunun ( *B* sorgusu) hesaplanması için kullanıldığında *B* sorgusu hesaplanmış bir varlık olur. Hesaplanmış varlıklar, şirket içi kaynaklara başvuramaz.


**İşlem altyapısı:**

* İşlem altyapısı kullanıldığında veri alımı için başlangıçta yaklaşık olarak %10 ile %20 arasında süre artışı olur.

  1. Bu durum yalnızca işlem altyapısında bulunan ve veri kaynağında bulunan verileri okuyan ilk veri akışı için geçerlidir
  2. Kaynak veri akışını kullanan sonraki veri akışları aynı artışla karşılaşmaz

* İşlem altyapısı yalnızca belirli işlemler tarafından ve yalnızca bağlantılı varlık veya hesaplana varlık üzerinden kullanılır. Tüm işlemlerin yer aldığı listeye [bu blog gönderisinden](http://petcu40.blogspot.com/2019/06/m-folding-in-enhanced-engine-of-power.html) ulaşabilirsiniz.


**Kapasite Yönetimi:**

* Premium Power BI kapasiteleri tasarım gereği bellek azaldığında iş yüklerini farklı şekillerde kısıtlayan dahili bir kaynak yöneticisine sahiptir.

  1. Bu kısıtlama baskısı, veri akışları için kullanılabilir durumdaki M kapsayıcısı sayısını azaltır
  2. Verinizin boyutu için uygun boyuta sahip bir kapsayıcı kullanarak veri akışlarının belleğini %100 olarak ayarlayabilirsiniz; bu durumda iş yükü kapsayıcı sayısını uygun şekilde yönetir

* Yaklaşık kapsayıcı sayısını elde etmek için iş yüküne ayrılmış olan toplam belleği kapsayıcıya ayrılmış olan bellek miktarına bölebilirsiniz

## <a name="dataflow-usage-in-datasets"></a>Veri kümelerinde veri akışı kullanımı

* Power BI Desktop'ta oluşturduğunuz veri kümesini Power BI hizmetinde yayımlarken veri akışlarının veri kaynağı için Power BI Desktop uygulamasında kullanılan kimlik bilgilerinin veri kümesi hizmette yayımlandığında kullanılan kimlik bilgileriyle aynı olduğundan emin olun.
  1. Bu kimlik bilgilerinin farklı olması, veri kümesi yenilendiğinde *Anahtar bulunamadı* hatasına neden olur

## <a name="next-steps"></a>Sonraki adımlar
Aşağıdaki makaleler veri akışları ve Power BI hakkında daha fazla bilgi sunmaktadır:

* [Veri akışlarına giriş ve self servis veri hazırlığı](dataflows-introduction-self-service.md)
* [Veri akışı oluşturma](dataflows-create.md)
* [Veri akışı yapılandırma ve kullanma](dataflows-configure-consume.md)
* [Veri akışı depolama alanını Azure Data Lake 2. Nesil kullanacak şekilde yapılandırma](dataflows-azure-data-lake-storage-integration.md)
* [Veri akışlarının Premium özellikleri](dataflows-premium-features.md)
* [Veri akışları ve yapay zeka](dataflows-machine-learning-integration.md)