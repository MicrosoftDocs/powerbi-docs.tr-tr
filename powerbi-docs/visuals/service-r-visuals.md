---
title: R betiklerini kullanarak gelişmiş analizler ve görselleştirmeler oluşturma
description: Gelişmiş analizler ve görselleştirmeler oluşturmak için Power BI Desktop'ta R betiklerini kullanma
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/14/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 9f9b0ec77d0273374d940332abd5d186c2604866
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "80979834"
---
# <a name="create-and-use-r-visuals-in-power-bi"></a>Power BI'da R görselleri oluşturma ve kullanma
R görselleri şu anda yalnızca **Power BI Desktop**'ta oluşturulabilir ve ardından Power BI hizmetinde yayımlanabilir. R görselleri oluşturma hakkında daha fazla bilgi için bkz. [R kullanarak Power BI görselleri oluşturma ](../desktop-r-visuals.md).

## <a name="viewing-r-visuals-in-the-power-bi-service"></a>Power BI hizmetinde R görselleri görüntüleme
Power BI hizmeti, R betikleriyle oluşturulan görselleri görüntülemeyi ve bu görsellerle etkileşim kurmayı destekler. R betikleriyle oluşturulan ve genellikle *R görselleri* olarak adlandırılan görseller, R'ın zengin analizlerini ve görselleştirme gücünü kullanarak tahmin etme özelliği gibi gelişmiş veri şekillendirme özellikleri ve analizler sunabilir.

> [!NOTE]
> [R programlama dili](https://www.r-project.org/); istatistikçiler, veri bilimciler ve iş analistleri arasında en yaygın kullanılan programlama dilleri arasındadır. R dili, yaygın olarak kullanılan R Kullanıcı Grupları'nın yanı sıra 7.000'den fazla eklenti paketi sunan bir açık kaynak topluluğuna sahiptir. Power BI hizmetinde dağıtılan R sürümü *Microsoft R 3.4.4.* sürümüdür.
> 
> 

Aşağıdaki görüntüde, gelişmiş analizler için kullanılan bir R görseli koleksiyonu içeren bir Power BI panosu gösterilmektedir.

![Power BI hizmeti rapor tuvalinin ekran görüntüsü](media/service-r-visuals/power-bi-r-visuals.png)

R görselleri, aşağıdaki görüntüde gösterilen rapora benzer bir [Power BI Desktop raporunda](../desktop-get-the-desktop.md) oluşturulur.

![İki görsele sahip Desktop raporu](media/service-r-visuals/power-bi-r-visual-desktop.png)

Rapor **Power BI Desktop**'ta oluşturulduktan sonra, bir veya daha fazla R görseli içeren raporunuzu Power BI hizmetinde yayımlayabilirsiniz. 

 Hizmette R paketlerinin tümü desteklenmiyor. Şu anda Power BI hizmetinde desteklenen paketlerin listesi için, bu makalenin sonunda bulunan desteklenen paketler bölümüne bakın.

Nasıl çalıştığını görmek ve kullanmayı denemek için birkaç R görseli içeren bu [örnek Power BI Desktop dosyasını](https://download.microsoft.com/download/D/9/A/D9A65269-D1FC-49F8-8EC3-1217E3A4390F/RVisual_correlation_plot_sample%20SL.pbix) (.pbix dosyası) indirebilirsiniz.

**Power BI Desktop**'ta oluşturulan ve ardından Power BI hizmetinde yayımlanan R görselleri çoğunlukla Power BI hizmetindeki diğer görseller gibi çalışır; R görselleri ile etkileşim kurabilir, bu görsellere filtre uygulayabilir, görselleri bir panoya sabitleyebilir veya başkalarıyla paylaşabilirsiniz. Pano ve görsel paylaşma hakkında daha fazla bilgi için bkz. [panoları iş arkadaşlarınızla ve diğer kişilerle paylaşma](../service-share-dashboards.md). R görsellerinin diğer görsellerden farkı, araç ipuçlarını gösterememesi ve diğer görsellere filtre uygulamak için kullanılamamasıdır.

Aşağıdaki görüntüde görebileceğiniz gibi, Power BI hizmetindeki R görselleri, hem panolarda hem de raporlarda büyük ölçüde diğer görseller gibi görünüp bu şekilde davranır ve kullanıcıların, görseli oluşturan, temel alınan R betiğini bilmeleri gerekmez.

![Power BI hizmetindeki rapor sayfasının ekran görüntüsü](media/service-r-visuals/power-bi-r-visual.png)

## <a name="r-scripts-security"></a>R betiklerinin güvenliği
R görselleri, güvenlik veya gizlilik riskleri taşıyan kodlar içerebilecek R betiklerinden oluşturulur.

Bu risklerle en çok, yazarın betiği kendi bilgisayarında çalıştırdığı yazma aşamasında karşılaşılır.

Power BI hizmeti, kullanıcıları ve hizmeti güvenlik risklerine karşı korumak için bir *korumalı alan* teknolojisi uygular.

Bu *korumalı alan* yaklaşımı, Power BI hizmetinde çalıştırılan R betiklerine, İnternet'e veya R görselini oluşturmak için gerekli olmayan diğer kaynaklara erişme gibi konularda bazı kısıtlamalar getirir.

## <a name="r-scripts-error-experience"></a>R betik hatası deneyimi
Bir R betiği hatayla karşılaştığında R görseli çizilmez ve bir hata iletisi görüntülenir. Hata hakkında ayrıntılı bilgi için, aşağıdaki görüntüde gösterilen şekilde, tuvaldeki R görseli hatasında **Ayrıntılara göz atın** seçeneğini belirleyin.

![hata iletisi](media/service-r-visuals/r-visuals-service-4.png)

Başka bir örnek olarak, aşağıdaki görüntüde, Azure'da bir R paketinin eksik olması nedeniyle R betiği çalıştırılamadığında görünen hata iletisi gösterilmektedir.

![Çalışma zamanı hatasını gösteren ekran görüntüsü](media/service-r-visuals/r-visuals-service-5.png)

## <a name="licensing"></a>Lisanslama
R görselleri, raporlarda işleme, yenileme, filtreleme ve çapraz filtreleme yapmak için [Power BI Pro](../service-self-service-signup-for-power-bi.md) lisansı gerektirir. Power BI Pro lisansları ve bunların ücretsiz lisanslardan farkı hakkında daha fazla bilgi edinmek için bkz. [Power BI Pro içeriği nedir?](../service-admin-purchasing-power-bi-pro.md)

Power BI’ın ücretsiz kullanıcıları, Premium çalışma alanlarında yalnızca kendileriyle paylaşılan kutucukları kullanabilir. Daha fazla bilgi için bkz. [Power BI Pro'yu satın alma](../service-admin-purchasing-power-bi-pro.md).

Aşağıdaki tabloda, lisanslama türüne göre R görseli özellikleri açıklanmaktadır.


|  |Power BI Desktop’ta R görselleri oluşturma  | R görselleri ile PBI hizmet raporları oluşturma |Raporlarda R görsellerini görüntüleme  | Panolarda R kutucuklarını görüntüleme |
|---------|---------|---------|---------|--------|
|**Konuk** (Power BI embedded)     |  Destekleniyor|  Desteklenmiyor      | Yalnızca Premium/Azure kapasitesinde desteklenir  | Yalnızca Premium/Azure kapasitesinde desteklenir |
|**Yönetilmeyen kiracı** (etki alanı doğrulanmadı) | Destekleniyor | Desteklenmiyor |  Desteklenmiyor |Desteklenen (B2B senaryosu) |
|Ücretsiz lisans ile **yönetilen kiracı**    |  Destekleniyor       |  Desteklenmiyor       |    Yalnızca Premium kapasitede desteklenir    | Destekleniyor |
Pro lisansı ile **yönetilen kiracı**     |   Destekleniyor      | Destekleniyor      | Destekleniyor    |Destekleniyor|



## <a name="known-limitations"></a>Bilinen Sınırlamalar
Power BI hizmetindeki R görselleri için bazı sınırlamalar söz konusudur:

* R görselleri desteği, [Hangi R paketlerinin desteklendiğini öğrenin](../service-r-packages-support.md) konusunda tanımlanan paketlerle sınırlıdır. Şu anda özel paketler için destek bulunmamaktadır.
* Veri boyutu sınırlamaları: R görseli tarafından çizim için kullanılan veri 150.000 satırla sınırlıdır. 150.000'den fazla satır seçilirse yalnızca ilk 150.000 satır kullanılır ve görüntünün üzerinde bir ileti görüntülenir. Bunun yanı sıra, giriş verileri için 250 MB sınırı vardır.
* Çözünürlük: Tüm R görselleri 72 DPI çözünürlükte görüntülenir.
* Çizim cihazı: Yalnızca varsayılan cihazla çizim yapma desteklenir. 
* Hesaplama süresi sınırlaması: Bir R görseli hesaplaması 60 saniyeden uzun sürerse betik zaman aşımına uğrar ve bir hata oluşur.
* R görselleri veri güncelleştirme, filtreleme ve vurgulama işlemlerinden sonra yenilenir. Ancak, görüntünün kendisi etkileşimli değildir ve araç ipuçlarını desteklemez.
* R görselleri, diğer görselleri vurgulama işlemine yanıt verir ancak diğer öğelere çapraz filtreleme uygulamak için R görsellerindeki öğelere tıklayamazsınız.
* R görselleri şu anda *Saat* veri türü için desteklenmemektedir. Bunun yerine lütfen Tarih/Saat veri türünü kullanın.
* R görselleri **Web’de yayımla** özelliği kullanılırken görüntülenmez.
* R görselleri, giriş sütunlarının yeniden adlandırılmasını desteklemez. Betik yürütme sırasında sütunlara özgün adlarıyla başvurulur.
* R görselleri şu anda pano ve rapor yazdırma özelliğiyle yazdırılamaz
* R görselleri şu anda Analysis Services'in DirectQuery modunda desteklenmemektedir
* R görsellerinin metin etiketlerini grafik öğelerine dönüştürebilme özelliği vardır. Power BI hizmetinde bunu yapabilmek için aşağıdaki ek adımlar gerekir:
  
  * R betiğinin başına şu satırı ekleyin:
    
        powerbi_rEnableShowText =  1
* Çince, Japonca ve Korece yazı tiplerinin Power BI hizmetinde düzgün çalışması için şu ek adımların tümünü izlemeniz gerekir:
  
  * İlk olarak, *showtext* R paketini ve tüm bağımlılıklarını yükleyin. Bunu, şu betiği çalıştırarak da yapabilirsiniz:
    
        *install.packages("showtext")*
  * Ardından, R betiğinin başına şu satırı ekleyin:
    
        powerbi_rEnableShowTextForCJKLanguages =  1

## <a name="overview-of-r-packages"></a>R paketlerine genel bakış
R paketleri, iyi tanımlanmış bir biçimde bir araya getirilen R işlevlerinden, verilerden ve derlenmiş kodlardan oluşan koleksiyonlardır. R yüklendiğinde, standart bir paket kümesi ile birlikte gelir. Diğer paketleri ise ayrı olarak indirebilir ve yükleyebilirsiniz. Yükleme işleminin ardından kullanılabilmesi için R paketleri oturuma yüklenmelidir. Ücretsiz R paketlerinin birincil kaynağı, açılımı [Comprehensive R Archive Network](https://cran.r-project.org/web/packages/available_packages_by_name.html) olan CRAN'dir.

**Power BI Desktop** her tür R paketini sınırlama olmaksızın kullanabilir. R paketlerini **Power BI Desktop**'ta kullanmak üzere kendiniz yükleyebilirsiniz (örneğin, [RStudio IDE](https://www.rstudio.com/) kullanarak).

**Power BI hizmetindeki** R görselleri, **bu makalede** bulunan [Desteklenen Paketler](../service-r-packages-support.md) bölümündeki paketler tarafından desteklenmektedir. Desteklenen paketler listesinde ilginizi çeken bir paket bulamazsanız seçtiğiniz paket için destek isteyebilirsiniz. Destek isteme hakkında daha fazla bilgi için bkz. [Power BI hizmetindeki R paketleri](../service-r-packages-support.md).

### <a name="requirements-and-limitations-of-r-packages"></a>R paketleri Gereksinimleri ve Sınırlamaları
R paketlerine yönelik birçok gereksinim ve sınırlama bulunmaktadır:

* Power BI hizmeti, R paketlerini çoğunlukla GPL-2, GPL-3, MIT+ ve bu tür ücretsiz ve açık kaynaklı yazılım lisanslarıyla destekler.
* Power BI hizmeti, CRAN'de yayımlanan paketleri destekler. Hizmet, kişisel veya özel R paketlerini desteklemez. Kullanıcılarımıza, kişisel paketlerinin Power BI hizmetinde kullanılması isteğinde bulunmadan önce bu paketlerini CRAN'de kullanılabilir hale getirmelerini öneririz.
* **Power BI Desktop**, R paketlerine yönelik iki çeşitlemeye sahiptir:
  
  * R görselleri için, özel R paketleri de dahil olmak üzere herhangi bir paket yükleyebilirsiniz
  * Özel R görselleri içinse otomatik paket yüklemesinde yalnızca genel CRAN paketleri desteklenir.
* Güvenlik ve gizlilik nedenleriyle, World-Wide Web üzerinden istemci-sunucu sorguları sağlayan R paketleri (RgoogleMaps gibi) şu anda hizmette desteklenmez. Bu tür denemeler yapıldığında ağ engellenir. Desteklenen ve desteklenmeyen R paketlerinin listesi için bkz. [Power BI hizmetindeki R paketleri](../service-r-packages-support.md).
* Yeni bir R paketi eklemeye yönelik onay süreci birçok bağımlılık gerektirir; hizmete yüklenmesi gereken bazı bağımlılıklar desteklenmemektedir.

### <a name="supported-packages"></a>Desteklenen Paketler:
Desteklenen R paketlerinin uzun listesi (ve desteklenmeyen paketlerin kısa listesi) için şu makaleye bakın:

* [Power BI hizmetindeki R paketleri](../service-r-packages-support.md)

