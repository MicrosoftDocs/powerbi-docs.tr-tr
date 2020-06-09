---
title: Geliştirilmiş işlem altyapısını veri akışları ile kullanma
description: Power BI Premium'daki geliştirilmiş işlem altyapısını veri akışları ile birlikte kullanmayı öğrenin
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/01/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: ec0d12ddf91b04654b90c5a3e7cdfda24bc04604
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315914"
---
# <a name="the-enhanced-compute-engine"></a>Geliştirilmiş işlem altyapısı

Power BI geliştirilmiş işlem altyapısı, Power BI Premium abonelerinin kapasitelerini kullanarak veri akışlarının kullanımını iyileştirmelerini sağlar. Geliştirilmiş işlem altyapısını kullanmak şu avantajları sunar:

* *Birleştirme*, *benzersiz*, *filtre* ve *gruplama* gibi işlemleri gibi hesaplanan varlıklar üzerinde gerçekleştirilen uzun süreli ETL adımları için gerekli olan yenileme süresini önemli ölçüde azaltır.
* Varlıklar üzerinde DirectQuery sorgusu gerçekleştirme (Şubat 2020'de)

Aşağıdaki bölümlerde geliştirilmiş işlem altyapısını etkinleştirme adımları anlatılmakta ve sık sorulan sorulara yanıt verilmektedir.


## <a name="using-the-enhanced-compute-engine"></a>Geliştirilmiş işlem altyapısını kullanma

Geliştirilmiş işlem altyapısı, Power BI hizmetinin **Kapasite Ayarları** sayfasının **veri akışları** bölümünden etkinleştirilir. Geliştirilmiş işlem altyapısı varsayılan olarak **Kapalı** durumdadır. Etkinleştirmek için aşağıdaki görüntüde gösterildiği gibi **Açık** duruma getirin ve yaptığınız değişikliği kaydedin. 

![Geliştirilmiş işlem altyapısını açın](media/service-dataflows-enhanced-compute-engine/enhanced-compute-engine-01.png)

> [!IMPORTANT]
> Geliştirilmiş işlem altyapısı yalnızca A3 ve üzeri Power BI kapasitelerinde çalışır.

Geliştirilmiş işlem altyapısı açtıktan sonra veri akışlarına döndüğünüzde, aynı kapasitedeki var olan bağlantılı varlıklardan oluşan veri akışları için *birleşim* veya *gruplama* gibi karmaşık işlemler gerçekleştirilen hesaplanan varlıklarda performans artışı görmeniz gerekir. 

İşlem altyapısını en verimli şekilde kullanmak için ETL aşamasını şu şekilde iki ayrı veri akışına ayırmanız gerekir:

* **Veri akışı 1**: Bu veri akışı yalnızca veri kaynağındaki gerekli verileri almalı ve veri akışı 2 içine yerleştirmelidir.
* **Veri akışı 2**: Tüm ETL işlemlerini bu ikinci veri akışında gerçekleştirin ancak aynı kapasite üzerinde yer alan Veri akışı 1'e başvurduğunuzdan emin olun. Ayrıca işlem altyapısının kullanıldığından emin olmak için diğer işlemlerden önce katlanabilecek (filtre, gruplama, benzersiz, birleşim) işlemler gerçekleştirdiğinizden emin olun.

## <a name="common-questions-and-answers"></a>Sık sorulan sorular ve yanıtları

**Soru:** Geliştirilmiş işlem altyapısını etkinleştirdim ancak veriler daha yavaş yenileniyor. Neden mi?

**Cevap:** Geliştirilmiş işlem altyapısını etkinleştirmenize rağmen verilerin yavaş yenilenmesinin iki nedeni olabilir:

 - Geliştirilmiş işlem altyapısı etkinleştirildikten sonra düzgün çalışmak için bir miktar belleğe ihtiyaç duyar. Bu nedenle yenileme gerçekleştirme için ayrılan bellek miktarı azalır ve bunun sonucunda yenileme işlemleri kuyruğa alınır ve eşzamanlı olarak yenilenebilecek iş akışı sayısı azalır. Bu sorunu çözmek için geliştirilmiş işlemi etkinleştirdiğinizde veri akışlarına ayrılan belleği artırarak eşzamanlı veri akışı yenileme işlemleri için gerekli belleği aynı düzeyde kalmasını sağlayın.

 - Yenileme işlemlerinin yavaş olmasının bir diğer nedeni de işlem altyapısının yalnızca var olan varlıklarla birlikte çalışmasıdır. İş akışınızın, iş akışı olmayan bir veri kaynağına başvurması durumunda geliştirme göremezsiniz. Bazı büyük veri senaryolarında verilerin geliştirilmiş işlem altyapısına geçirilmesi gerektiğinden veri kaynağından gerçekleştirilen ilk okuma işlemi daha yavaş olacağından performans artışı yaşanmayacaktır.  

**Soru:** Geliştirilmiş işlem altyapısını açma veya kapatma seçeneğini göremiyorum. Neden mi?

**Cevap:** Geliştirilmiş işlem altyapısı, dünyanın farklı yerlerindeki bölgelerde aşamalı olarak kullanıma sunulmaktadır. Bu desteğin 2020'nin sonuna kadar tüm bölgelere yayılmış olmasını planlıyoruz.

**Soru:** İşlem altyapısı için desteklenen veri türleri nelerdir?

**Cevap:** Geliştirilmiş işlem altyapısı ve veri akışları şu anda aşağıdaki veri türlerini desteklemektedir. Veri akışınız aşağıdaki veri türlerinden birini kullanmıyorsa yenileme sırasında hata oluşur:

* Tarih/Saat
* Ondalık Sayı
* Metin
* Tam sayı
* Tarih/Saat/Bölge
* True/False
* Tarih
* Saat

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede veri akışları için geliştirilmiş işlem altyapısını kullanmaya yönelik bilgiler sağlanmıştır. Aşağıdaki makaleler de yardımcı olabilir:

* [Veri akışları ile self servis veri hazırlığı](service-dataflows-overview.md)
* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Power BI Premium'da hesaplanan varlıkları kullanma](service-dataflows-computed-entities-premium.md)
* [Power BI veri akışları için geliştirici kaynakları](service-dataflows-developer-resources.md)

Power Query ve zamanlanmış yenileme hakkında daha fazla bilgi için şu makaleleri okuyabilirsiniz:
* [Power BI Desktop'ta sorgulara genel bakış](desktop-query-overview.md)
* [Zamanlanmış yenileme yapılandırma](../connect-data/refresh-scheduled-refresh.md)

Ortak Veri Modeli hakkında daha fazla bilgi için genel bakış makalesini okuyabilirsiniz:
* [Ortak Veri Modeli - genel bakış ](https://docs.microsoft.com/powerapps/common-data-model/overview)
