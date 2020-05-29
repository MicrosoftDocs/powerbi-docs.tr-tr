---
title: Dağıtım işlem hatları süreci
description: Power BI dağıtım işlem hattı sürecini anlama
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.date: 05/06/2020
ms.openlocfilehash: c4a823b0b41def6c10cd8f932bb97e91eb977ecb
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83148613"
---
# <a name="understand-the-deployment-process-preview"></a>Dağıtım sürecini anlama (önizleme)

Dağıtım süreci, içeriği işlem hattındaki bir aşamadan diğerine (genellikle geliştirmeden teste ve testten üretime) kopyalamanıza olanak verir.

Dağıtım sırasında Power BI, içeriği geçerli aşamadan hedef aşamaya kopyalar. Kopyalanan öğeler arasındaki bağlantılar kopyalama işlemi sırasında korunur. Ayrıca Power BI, hedef aşamadaki güncelleştirilmiş içeriğe yapılandırılmış veri kümesi kuralları uygular. İçeriği dağıtmak, dağıtılacak öğe sayısına bağlı olarak biraz zaman alabilir. Bu süre boyunca, Power BI portalındaki diğer sayfalarda gezinebilirsiniz ancak hedef aşamadaki içeriği kullanamazsınız.

## <a name="deploying-content-to-an-empty-stage"></a>Boş bir aşamaya içerik dağıtma

İçeriği boş bir aşamaya dağıttığınızda, çalışma alanındaki raporların, panoların ve veri kümelerinin meta verileri dağıtım yapılan aşamaya kopyalanır. Dağıtım yaptığınız aşamaya yönelik yeni çalışma alanı bir Premium kapasitede oluşturulur.

Bir aşamadan diğerine içerik dağıtmanın iki yolu vardır. İçeriğin tamamını dağıtabilirsiniz veya [dağıtılacak içerik öğelerini seçebilirsiniz](deployment-pipelines-get-started.md#selective-deployment).

Ayrıca içeriği, dağıtım işlem hattındaki sonraki bir aşamadan önceki bir aşamaya geriye dönük olarak dağıtabilirsiniz.

Dağıtım tamamlandıktan sonra, yeni kopyalanmış içeriği kullanabilmek için veri kümelerini yenileyin. Veriler bir aşamadan diğerine kopyalanmadığından, veri kümesini yenilemek gerekir. Dağıtım sürecinde hangi öğe özelliklerinin kopyalandığını ve hangilerinin kopyalanmadığını anlamak için [dağıtım sırasında kopyalanan öğe özellikleri](#item-properties-copied-during-deployment) bölümünü gözden geçirin.

### <a name="creating-a-premium-capacity-workspace"></a>Premium kapasite çalışma alanı oluşturma

İlk dağıtım sırasında, dağıtım işlem hatları Premium kapasite izinleriniz olup olmadığını denetler.  

Kapasite izinleriniz varsa çalışma alanının içeriği dağıtım yaptığınız aşamaya kopyalanır ve Premium kapasitede bu aşamaya yönelik yeni bir çalışma alanı oluşturulur.

Kapasite izinleriniz yoksa çalışma alanı oluşturulur ancak içerik kopyalanmaz. Bir kapasite yöneticisinin çalışma alanınızı kapasiteye eklemesini veya size kapasite için atama izinleri vermesini isteyebilirsiniz. Daha sonra, çalışma alanı kapasiteye atandığında içeriği bu çalışma alanına dağıtabilirsiniz.

### <a name="workspace-and-content-ownership"></a>Çalışma alanı ve içerik sahipliği

Dağıtım yapan kullanıcı otomatik olarak, kopyalanan veri kümelerinin veri kümesi sahibi ve çalışma alanının tek yöneticisi olur.

## <a name="deploy-content-to-an-existing-workspace"></a>İçeriği mevcut bir çalışma alanına dağıtma

Çalışan bir üretim işlem hattındaki içeriği, mevcut bir çalışma alanına sahip olan bir aşamaya dağıtma sürecine aşağıdakiler dahildir:

* Yeni içerik, zaten başka içeriğe sahip olan bir aşamaya ek olarak dağıtılır.

* Yeni içerik, çalışmakta olan geçerli aşamadaki eski içerikle değiştirilmek üzere dağıtılır.

### <a name="deployment-process"></a>Dağıtım süreci

Geçerli aşamadaki içerik, hedef aşamaya kopyalanır. Power BI, hedef aşamadaki mevcut içeriği tanımlar ve bu içeriğin üzerine yazar. Dağıtım işlem hatları, üzerine yazılması gereken içerik öğelerini belirlemek için üst öğe ve bu öğenin kopyaları arasındaki bağlantıyı kullanır. Yeni bir içerik oluşturulduğunda bu bağlantı korunur. Üzerine yazma işlemi, yalnızca öğenin içeriğinin üzerine yazar. Öğenin kimliği, URL’si ve izinleri değişmeden kalır.

Hedef aşamada [öğe özellikleri kopyalanmadan](deployment-pipelines-process.md#item-properties-that-are-not-copied), dağıtım öncesindeki haliyle aynı şekilde kalır. Yeni içerik ve yeni öğeler, geçerli aşamadan hedef aşamaya kopyalanır.

### <a name="refreshing-the-dataset"></a>Veri kümesini yenileme

Hedef veri kümesindeki veriler, mümkün olduğunda korunur. Veri kümesinde değişiklik yoksa veriler dağıtım öncesindeki haliyle korunur.

Tablo veya hesaplanmış ölçümler ekleme gibi küçük değişiklikler olduğunda Power BI özgün verileri korur, yenileme işlemi yalnızca gerekli öğeleri yenilemek üzere iyileştirilir. Yeni şema değişikliklerinde veya veri kaynağı bağlantısındaki değişikliklerde, tam yenileme gereklidir.

### <a name="requirements-for-deploying-to-a-stage-with-an-existing-workspace"></a>Mevcut bir çalışma alanına sahip olan bir aşamaya dağıtım gereksinimleri

Dağıtılan içerik bir [premium kapasitede](../admin/service-premium-what-is.md) olduğu sürece, aşağıdaki koşulları karşılayan bir kullanıcı mevcut çalışma alanına sahip bir aşamaya dağıtabilir:

* Hem hedef hem de kaynak dağıtım aşamalarındaki çalışma alanlarının her ikisinin de üyesi olan bir [Pro kullanıcı](../admin/service-admin-purchasing-power-bi-pro.md).

* Dağıtım yapılmak üzere olan hedef çalışma alanındaki tüm veri kümelerinin sahibi.

Daha fazla bilgi edinmek için [izinler](#permissions) bölümünü gözden geçirin.

## <a name="deployed-items"></a>Dağıtılan öğeler

Bir işlem hattından diğerine içerik dağıttığınızda, kopyalanan içerikte şu Power BI öğeleri yer alır:

* Veri kümeleri

* Raporlar

* Panolar

### <a name="unsupported-items"></a>Desteklenmeyen öğeler

Dağıtım işlem hatları aşağıdaki öğeleri desteklemez:

* Bir. pbix dosyasından oluşturulmayan veri kümeleri

* Desteklenmeyen veri kümelerini temel alan raporlar

* Çalışma alanı bir şablon uygulaması kullanamaz

* Sayfalandırılmış raporlar

* Veri akışları

* PUSH veri kümeleri

* Çalışma kitapları

## <a name="item-properties-copied-during-deployment"></a>Dağıtım sırasında kopyalanmış öğe özellikleri

Dağıtım sırasında, aşağıdaki öğe özellikleri kopyalanır ve hedef aşamadaki öğe özelliklerinin üzerine yazılır:

* Veri kaynakları ([veri kümesi kuralları](deployment-pipelines-get-started.md#step-4---create-dataset-rules) desteklenir)

* Parametreler ([veri kümesi kuralları](deployment-pipelines-get-started.md#step-4---create-dataset-rules) desteklenir)

* Rapor görselleri

* Rapor sayfaları

* Pano kutucukları

* Model meta verileri

* Veri ilişkileri

### <a name="item-properties-that-are-not-copied"></a>Kopyalanamayan öğe özellikleri

Dağıtım sırasında şu öğe özellikleri kopyalanmaz:

* Veri: Veriler kopyalanmaz, yalnızca meta veriler kopyalanır

* URL

* ID

* İzinler: Bir çalışma alanı veya belirli bir öğe için

* Çalışma alanı ayarları: Her aşamanın kendi çalışma alanı vardır

* Uygulama içeriği ve ayarlar: Uygulamalarınızı dağıtmak için bkz. [Power BI uygulamalarını dağıtma](#deploying-power-bi-apps)

Dağıtım sırasında şu veri kümesi özellikleri de kopyalanmaz:

* Rol ataması
    
* Yenileme zamanlaması
    
* Veri kaynağı kimlik bilgileri
    
* Sorgu önbelleğe alma ayarları (kapasiteden alınabilir)
    
* Onay ayarları

## <a name="deploying-power-bi-apps"></a>Power BI uygulamalarını dağıtma

[Power BI uygulamaları](../consumer/end-user-apps.md), ücretsiz Power BI kullanıcılarına içerik dağıtmak için önerilen yoldur. Uygulamanızın yaşam döngüsü söz konusu olduğunda daha fazla denetim ve esnekliğe sahip olabilmeniz için, dağıtım işlem hatlarını kullanarak dağıtım işlem hattındaki Power BI uygulamalarını yönetebilirsiniz.

Her dağıtım işlem hattı aşaması için bir uygulama oluşturun, böylece her uygulama güncelleştirmesini son kullanıcının bakış açısıyla test edebilirsiniz. Dağıtım işlem hattı, bu süreci kolayca yönetmenizi sağlar. Çalışma alanı kartındaki yayımla veya görüntüle düğmesini kullanarak uygulamayı yayımlayın veya belirli bir işlem hattı aşamasında görüntüleyin.

[![](media/deployment-pipelines-process/publish.png "Publish app")](media/deployment-pipelines-process/publish.png#lightbox)

Üretim aşamasında, sol alt köşedeki ana eylem düğmesi Power BI’da uygulama güncelleştirme sayfasını açar, böylece tüm içerik güncelleştirmeleri uygulama kullanıcılarının kullanımına sunulur.

[![](media/deployment-pipelines-process/update-app.png "Update app")](media/deployment-pipelines-process/update-app.png#lightbox)

>[!IMPORTANT]
>Dağıtım işlemi, uygulama içeriğinin veya ayarlarının güncelleştirilmesini içermez. İçerikte ve ayarlarda değişiklikler uygulamak için, uygulamayı gerekli işlem hattı aşamasında kendiniz güncelleştirmeniz gerekir.

## <a name="permissions"></a>İzinler

İşlem hattı izinleri ve çalışma alanı izinleri ayrı ayrı sağlanıp yönetilir. Örneğin, çalışma alanı izinleri olmayan bir işlem hattına erişimi olan bir kullanıcı, işlem hattını görüntüleyip başkalarıyla paylaşabilir. Ancak, bu kullanıcıyı işlem hattındaki çalışma alanının veya çalışma alanı sayfasının içeriğini görüntüleyemez ve dağıtım gerçekleştiremez.

### <a name="user-with-pipeline-access"></a>İşlem hattı erişimi olan kullanıcı

İşlem hattı erişimi olan kullanıcılar aşağıdaki izinlere sahiptir:

* İşlem hattını görüntüleme
    
* İşlem hattını başkalarıyla paylaşma
    
* İşlem hattını düzenleme ve silme

>[!NOTE]
>İşlem hattı erişimi, çalışma alanı içeriği üzerinde görüntüleme veya işlem yapma izni sağlamaz.

### <a name="workspace-viewer"></a>Çalışma Alanı Görüntüleyicisi

*İşlem hattı erişimi* olan çalışma alanı görüntüleyicileri şunları da yapabilir:

* İçerik tüketme

>[!NOTE]
>Çalışma alanı görüntüleyicileri veri kümesine erişemez veya çalışma alanı içeriğini düzenleyemez.

### <a name="workspace-contributor"></a>Çalışma alanı katkıda bulunanı

*İşlem hattı erişimi* olan çalışma alanı katkıda bulunanları şunları da  yapabilir:

* İçerik tüketme

* Aşamaları karşılaştırma

* Veri kümelerini görüntüleme

### <a name="workspace-member"></a>Çalışma alanı üyesi

*İşlem hattı erişimi* olan çalışma alanı üyeleri şunları da yapabilir:

* Çalışma alanı içeriğini görüntüleme
    
* Aşamaları karşılaştırma
    
* Raporları ve panoları dağıtma

* Çalışma alanlarını kaldırma

### <a name="workspace-admin"></a>Çalışma alanı yöneticisi

*İşlem hattı erişimi* olan çalışma alanı yöneticileri, *çalışma alanı üyesi* eylemlerini gerçekleştirmenin yanı sıra şunları da yapabilir:

* Çalışma alanları atama

* Çalışma alanlarını kaldırma

### <a name="dataset-owner"></a>Veri kümesi sahibi

Çalışma alanı üyesi veya yöneticisi olan veri kümesi sahipleri şunları da yapabilir:

* Veri kümelerini güncelleştirme
    
* Kuralları yapılandırma

>[!NOTE]
>Bu bölümde, dağıtım işlem hatlarındaki kullanıcı izinleri açıklanır. Bu bölümde listelenen izinler, diğer Power BI özelliklerindeki farklı uygulamalara sahip olabilir.

## <a name="limitations"></a>Sınırlamalar

Bu bölümde, dağıtım işlem hatlarındaki sınırlamaların çoğu listelenir.

* Çalışma alanının bir  [premium kapasitede](../admin/service-premium-what-is.md) bulunması gerekir.

* Raporlar ve panolar gibi Power BI [duyarlılık etiketlerine](../admin/service-security-data-protection-overview.md#sensitivity-labels-in-power-bi) sahip olan Power BI öğeleri dağıtılamaz.

* [Artımlı yineleme](../admin/service-premium-incremental-refresh.md) ile yapılandırılan veri kümeleri dağıtılamaz.

* Çalışma alanı sınırlamalarının listesi için bkz. [çalışma alanı atama sınırlamaları](deployment-pipelines-get-started.md#workspace-assignment-limitations).

* Veri kümesi kuralı sınırlamaları listesi için bkz. [veri kümesi kuralı sınırlamaları](deployment-pipelines-get-started.md#dataset-rule-limitations).

* Desteklenmeyen öğelerin listesi için bkz. [desteklenmeyen öğeler](#unsupported-items).

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Dağıtım işlem hatlarına giriş](deployment-pipelines-overview.md)

>[!div class="nextstepaction"]
>[Dağıtım işlem hatlarına yönelik en iyi yöntemler](deployment-pipelines-best-practices.md)

>[!div class="nextstepaction"]
>[Dağıtım işlem hatlarını kullanmaya başlama](deployment-pipelines-get-started.md)

>[!div class="nextstepaction"]
>[Dağıtım işlem hatlarıyla ilgili sorunları giderme](deployment-pipelines-troubleshooting.md)