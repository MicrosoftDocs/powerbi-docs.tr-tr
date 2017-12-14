---
title: "Power BI Embedded hakkında sık sorulan sorular"
description: "Power BI Embedded hakkında sık sorulan sorular ve cevaplar listesini inceleyin."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/27/2017
ms.author: asaxton
ms.openlocfilehash: 5f884c9c45627ee3c129daca77e38d17f1223909
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2017
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Power BI Embedded hakkında sık sorulan sorular

* Başka sorularınız varsa [Power BI Topluluğu'na sorun](http://community.powerbi.com/).
* Sorununuz hâlâ çözülmedi mi? Lütfen [Power BI destek sayfasını](https://powerbi.microsoft.com/support/) ziyaret edin.

## <a name="general"></a>Genel

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded nedir?

Microsoft Power BI Embedded uygulama geliştiricilerin, kendi veri görselleştirmelerini ve kontrollerini sıfırdan oluşturmak için zaman ve para harcamadan nefes kesen, tam etkileşimli raporları, panoları ve kutucukları uygulamalarına ekleyebilmelerini sağlar.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Power BI Embedded kimler içindir?

Kendi uygulamalarını yapan, bağımsız yazılım satıcıları (ISV'ler) olarak bilinen yazılım şirketleri ve geliştiriciler içindir.

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded hangi açıdan Power BI hizmetinden farklıdır?

Power BI Embedded, kendi uygulamalarını oluşturan ve sıfırdan bir analiz çözümü yaratmadan müşterilerinin karar almasını kolaylaştırmak üzere görsel öğeler eklemek isteyen geliştiriciler veya ISV'ler için tasarlanmıştır. Katıştırılmış analiz, iş kullanıcılarının iş verilerine erişebilmesini ve uygulama içerisinde bu verileri kullanarak öngörüler oluşturmak üzere sorgulama yapabilmesini sağlar.

Power BI ise kuruluşlara en kritik iş verilerini tek bir görünümde sunan hizmet olarak yazılım analiz çözümüdür.

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Power BI Premium ve Power BI Embedded arasındaki fark nedir?

Power BI Premium, kuruluşu, iş ortaklarını, müşterilerini ve sağlayıcılarını tek bir görünümde sunan eksiksiz bir İş Zekası çözümü isteyen kuruluşlar için kapasiteye göre tasarlanmıştır. Power BI Premium kuruluşların karar almasına yardımcı olur. Power BI Premium, bir SaaS ürünüdür ve kullanıcıların Power BI portal, mobil uygulama ile ve şirket içinde geliştirilen uygulamalar ile içeriği kullanabilmesini sağlar.

Power BI Embedded, uygulama oluşturan ve bu uygulamalara görseller eklemek isteyen geliştiriciler veya ISV'lere yöneliktir. Power BI Embedded, uygulama geliştiricilerine yönelik olduğundan ve kuruluş içindekiler veya dışındakiler dahil olmak üzere tüm uygulama kullanıcıları Power BI Embedded kapsamında depolanan içerikleri kullanabildiğinden Power BI Embedded müşterilerinizin karar almasına yardımcı olur. Power BI Embedded kapsamındaki içerik, tek tıkla Web'de veya SharePoint'te yayımlanamaz ve SSRS raporlarını desteklemez.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Microsoft bir müşterinin hangi durumlarda Power BI Premium ve hangi durumlarda Power BI Embedded satın almasını önerir?

Microsoft, kuruluşların kurumsal sınıf, self servis bulut İş Zekası çözümü olarak Power BI Premium satın almasını ve ISV'lerin bulut destekli katıştırılmış analiz bileşenleri olarak Power BI Embedded satın almasını önerir. Ancak, müşterilerin satın alabileceği ürünlere ilişkin herhangi bir sınırlama yoktur.

Bir ISV (tipik olarak büyük), kuruluşunda önceden paketlenmiş Power BI hizmetinin ek avantajlarından yararlanmak ve uygulamalarına eklemek üzere P SKU kullanmak isteyebilir. Ayrıca bazı Kuruluşlar, yalnızca iş uygulamaları oluşturmak ve bunlara analiz eklemek istediklerinde ve önceden paketlenmiş Power BI hizmetini kullanmak istemediklerinde Azure'da A SKU kullanabilir.

### <a name="when-will-power-bi-embedded-be-available-in-azure"></a>Power BI Embedded ne zaman Azure'da sunulacak?

Power BI Embedded kullanıma sunulmuştur.

## <a name="technical"></a>Teknik

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-em-skus-in-office-365"></a>Azure'da A SKU ile Office 365'te EM SKU arasındaki fark nedir?

PowerBI.com bir Hizmet olarak Yazılım teklifinde sosyal iş birliği, e-posta aboneliği ve benzeri pek çok özelliği içeren kurumsal bir çözümdür

Power BI Embedded ise bir Hizmet olarak Platform teklifinde katıştırılmış analiz çözümü oluşturmak üzere geliştiriciler tarafından kullanılabilen bir dizi API'dir. Katıştırılmış analiz senaryosunda PowerBI.com, ISV'lerin ve geliştiricilerin analiz çözümü içeriklerini ve kiracı düzeyi ayarlarını yönetmesine yardımcı olmak üzere kullanılmalıdır.

Her bir seçenek ile kullanabileceğiniz farklılıklara ilişkin kısmi bir liste sunulmaktadır.

|Özellik  |Power BI Embedded<br>(A SKU'lar) |Power BI Premium Kapasitesi<br>(EM SKU'lar)  |
|---------|---------|---------|
|Power BI Uygulaması çalışma alanlarından yapıtları ekleme     |Azure kapasitesi |Office 365 kapasitesi |
|Raporların kullanılabilmesi için Power BI lisansı gereklidir |Hayır  |Evet |
|Katıştırılmış uygulamada Power BI raporlarını kullanma |Evet  |Evet |
|Power BI raporlarını SharePoint'te kullanma |Hayır |Evet |
|Power BI raporlarını Teams'de kullanma |Hayır |Evet |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI artık katıştırma için üç SKU sunar: A SKU, EM SKU ve P SKU. Benim durumumda hangisini satın almalıyım?

|  |A SKU (Power BI Embedded)  |EM SKU (Power BI Premium)  |P SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|Satın alma     |Azure portalı |Office |Office |
|Kullanım örnekleri |* Kendi uygulamanıza içerik ekleme |* Kendi uygulamanıza içerik ekleme<br>* PowerBI.com dışında ÜCRETSİZ Power BI kullanıcıları ile içerik paylaşma ve diğer SaaS uygulamalarına (SharePoint, Ekipler) ekleme |* Kendi uygulamanıza içerik ekleme<br>* PowerBI.com dışında ÜCRETSİZ Power BI kullanıcıları ile içerik paylaşma ve diğer SaaS uygulamalarına (SharePoint, Ekipler) ekleme<br>* PowerBI.com aracılığıyla ÜCRETSİZ Power BI kullanıcıları ile içerik paylaşma  |
|Faturalama |Saatlik |Aylık |Aylık |
|Taahhüt  |Taahhütsüz |Yıllık  |Aylık/Yıllık |
|Ayrım |Tam esneklik; Azure portalında veya API'ler ile kaynaklar duraklatılabilir/sürdürülebilir, ölçek artırılabilir/azaltılabilir  |SharePoint Online ve Microsoft Teams'de içerik eklemek için kullanılabilir |Uygulamalarda katıştırma birleştirilebilir ve Power BI Hizmeti aynı kapasitede kullanılabilir |

### <a name="how-can-i-monitor-capacity-consumption"></a>Kapasite tüketimini nasıl izleyebilirim?

Yakın zamanda Azure üzerinden izleyebileceksiniz. Azure kaynağı, Power BI Embedded, sistem durumu ve kullanımı gösterecek şekilde KPI'leri izleme olanağı sağlayacaktır.

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>Kapasitem, uygulamamın kullanımına göre otomatik olarak ölçekleme sağlayacak mı?

Şu anda otomatik ölçekleme olanağı olmasa da tüm API'leri kullanarak dilediğiniz zaman ölçekleme yapabilirsiniz.

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>Power BI Embedded kimlik doğrulama modeli nedir?

Power BI Embedded, Power BI'da uygulama kimliğini doğrulayarak ana kullanıcının (belirli bir Power BI Pro lisanslı kullanıcısı) kimliğini doğrulamak için Azure AD'den yararlanmaya devam edecektir.

Uygulama kullanıcılarının kimliklerini doğrulama ve yetkilendirme işlemleri, ISV tarafından gerçekleştirilecektir ve ISV, uygulamaları için kendi kimlik doğrulama modelini uygulayabilir.

Zaten bir Azure AD kiracınız varsa mevcut dizininizi kullanabilir veya katıştırılmış uygulama içeriğinizin güvenliği için yeni bir Azure AD kiracısı oluşturabilirsiniz.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded hangi açıdan diğer Azure hizmetlerinden farklıdır?

ISV/geliştiricinin, Azure'da Power BI Embedded'ı satın almadan önce bir Power BI hesabı olmalıdır. Power BI Embedded dağıtım bölgeniz, Power BI hesabınıza göre belirlenir. Azure'da Power BI Embedded kaynağınızı yöneterek:

* Ölçeği artırın/azaltın
* Kapasite yöneticileri ekleyin
* Hizmeti duraklatın/sürdürün

Power BI Embedded kapasitenize çalışma alanları atamak/çalışma alanının atamasını kaldırmak için PowerBI.com'u kullanın.

### <a name="what-deploy-regions-are-supported"></a>Hangi dağıtım bölgeleri desteklenir?

Avustralya Güneydoğu, Batı ABD, Batı ABD 2, Batı Avrupa, Birleşik Krallık Güney, Brezilya Güney, Doğu ABD 2, Güneydoğu Asya, Hindistan Batı, Japonya Doğu, Kuzey Avrupa, Kuzey Orta ABD, Orta Güney ABD, Orta Kanada.

## <a name="licensing"></a>Lisanslama

### <a name="how-do-i-purchase-power-bi-embedded"></a>Power BI Embedded'ı nasıl satın alabilirim?

Power BI Embedded Azure üzerinden sunulmaktadır.

### <a name="how-power-bi-embedded-be-metered"></a>Power BI Embedded kullanımı nasıl ölçülür?

Power BI Embedded kullanımı saatlik olarak ölçülür.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Power BI Embedded kullanımı faturamda nasıl gösterilir?

Power BI Embedded dağıtılan düğüm türlerine dayalı tahmini bir saatlik ücrete göre faturalandırılır.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>Power BI Premium'u satın aldıysam ve Azure'da Power BI Embedded avantajlarının bazılarından yararlanmak istiyorsam ne yapmalıyım?

Müşteriler, geçerli sözleşme döneminin sonuna dek tüm mevcut Power BI Premium satın alma işlemleri için ödemelerine devam edecektir. Daha sonra gerektiği şekilde Power BI Premium ürünlerinde değişiklik yapabilirler.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Power BI Embedded'a erişmek için yine de Power BI Premium satın almam gerekiyor mu?

Hayır; Power BI Embedded, müşterilerinize çözümünüzü sunmak ve dağıtmak üzere ihtiyaç duyduğunuz Azure tabanlı kapasiteyi içermektedir.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Power BI Embedded için kimlerin Power BI Pro lisansı alması gerekir ve bunun nedeni nedir?

Bir Power BI çalışma alanına rapor eklemesi gereken tüm analistlerin, REST API'leri kullanılmasını gerektiren tüm geliştiricilerin, Power BI kiracısını ve kapasitesini yönetmesi gereken tüm kiracı yöneticilerinin bir Power BI Pro lisansı alması gerekir.

Power BI Embedded katıştırılan içeriği yönetmek ve doğrulamak için Power BI kullanılmasına olanak tanıdığından doğru depolarda raporlara erişmek üzere PowerBI.com'da Uygulama kimliğini doğrulamak için Power BI Pro lisansı gereklidir.

### <a name="can-i-get-started-for-free"></a>Ücretsiz olarak başlayabilir miyim?

Evet, Power BI Embedded için [Azure kredilerinizi](https://azure.microsoft.com/free/) kullanabilirsiniz.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Azure'da Power BI Embedded için bir deneme sürümü alabilir miyim?

Power BI Embedded Azure kapsamında yer aldığından hizmeti [Azure'a kaydolurken tanınan 200 $ kredi](https://azure.microsoft.com/free/) ile kullanabilirsiniz.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Power BI Embedded satın alma taahhüdü nedir? 

Müşteriler kullanımlarını saatlik olarak değiştirebilir. Power BI Embedded hizmeti için aylık veya yıllık taahhüt yoktur.

### <a name="where-is-power-bi-embedded-available-us-government-germany-china-what-is-the-timing"></a>Power BI Embedded nerede kullanılabilir? ABD Kamu? Almanya? Çin? Zamanlama nedir?

Power BI Embedded, GA'daki Azure ticari bulutlarında kullanıma sunulacaktır.  Bağımsız bulut seçeneği gelecekte eklenecektir.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Power BI Embedded kâr amacı gütmeyen ve eğitim kuruluşları için kullanılabilir mi?

Kâr amacı gütmeyen kuruluşlar ve eğitim kurumları Azure'ı satın alabilir. Azure'da bu tür müşteriler için özel fiyatlandırma yoktur.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)