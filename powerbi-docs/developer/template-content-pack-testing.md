---
title: "Power BI şablon içerik paketlerini test etme"
description: "Şablon İçerik Paketi Testi"
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
ms.date: 10/09/2017
ms.author: maghan
ms.openlocfilehash: d777dcf1b10f45a000819445e65a557be7cdd28f
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="testing-template-content-packs-for-power-bi"></a>Power BI şablon içerik paketlerini test etme
İçerik paketinizi yayımlanmak üzere göndermeden önce test edebileceğiniz birden fazla yöntem vardır.  

> [!NOTE]
> İçerik paketinizde kendi geliştirdiğiniz özel bir [Veri Bağlayıcı](https://aka.ms/DataConnectors) kullanılıyorsa veri yenileme özelliklerini veya şablon içerik paketini aşağıdaki şekilde test edemezsiniz. Bu durumda lütfen içerik paketinizi [gönderin](#submission). Power BI ekibi içerik paketinizin test edilmesi konusunda sizinle birlikte çalışacaktır.
> 
> 

## <a name="testing-scheduled-data-refresh"></a>Zamanlanmış Veri Yenileme Testi
Şablon içerik paketleri bağlantı kurulduğunda müşteri verileriyle içerik paketinin örneğini oluşturmak için PowerBI.com'daki Yenileme özelliğini kullanır. İçerik paketi genel kullanıma sunulmadan önce bu akışı, oluşturduğunuz Desktop dosyasıyla test edebilirsiniz.

Dosyayı karşıya yükledikten sonra veri kümesinin yanındaki "…" simgesini ve Yenilemeyi Zamanla'yı seçin. Kaynağın kimlik bilgilerini yapılandırın. Veri kümesinin başarıyla yenilendiğinden emin olmak için "Şimdi Yenile" ve "Zamanlanmış Yenile" seçeneklerini kullanın. Yenileme işleminde hata olursa hata iletisini kontrol edip sorgularınızı ve uç sisteminizi doğrulayın.

### <a name="additional-refresh-tips"></a>Yenilemeye ilişkin ek ipuçları
* Yenilemeyi zamanlama sırasında yalnızca bir veri kaynağı algılanmalıdır  
* Test bağlantısı, kullanıcınızın içerik paketini yükleyebildiğini belirtmelidir. Aksi durumda sorgularınızın ek hata durumlarını işleyebildiğinden emin olun.  
* Yenilemenin yaklaşık 5 dakika gibi makul bir süre içinde tamamlanması gerekir  

![ayarlar](media/template-content-pack-testing/scheduledrefresh.png)

<a name="templates"></a>

## <a name="testing-templates"></a>Şablonları test etme
Şablon içerik paketi, veri kümesinde gerçek veriler içermemesi durumu haricinde mevcut çözümlere benzerdir. Bunun yerine kullanıcılar bir şablonu kullandığında veya bir şablon örneği oluşturduğunda bağlantı kurmak için parametreler ve kimlik bilgileri istenir. Bağlantı kurulduktan sonra kullanıcılar panoda, raporda ve veri kümelerinde kendi verilerini görür. 

Kullanıcının erişimi olan içerik paketini zamanlanmış yenileme dahil olmak üzere veri kümesi ayarlarına uygulaması halinde veri kümesindeki RLS ayarları içerik paketiyle birlikte **yayımlanmaz**.  

> [!NOTE]
> Şablon içerik paketlerinde yalnızca 1 pano, 1 rapor ve 1 veri kümesi bulunabilir. Lütfen [yazma](template-content-pack-authoring.md#restrictions) sayfasındaki kısıtlama listesine bakın. 
> 
> 

Kiracınız için şablon oluşturmayı etkinleştirmek üzere lütfen Power BI yöneticinizle birlikte çalışarak aşağıdaki özellik anahtarını etkinleştirin. 

![özellik anahtarı](media/template-content-pack-testing/featureswitch.png)

Bu özellik anahtarı etkinleştirildikten sonra ["İçerik paketi oluştur"](https://app.powerbi.com/groups/me/publish-content/) bölümünün en altında kuruluşunuz için şablon içerik paketi yayımlama seçeneğini göreceksiniz. 

![onay kutusu](media/template-content-pack-testing/checkbox.png)

### <a name="naming"></a>Adlandırma
Panonuzu, raporunuzu ve veri kümenizi içerik paketinin tamamında tutarlı bir şekilde adlandırmanızı öneriyoruz. Adlar sabittir ve tüm kullanıcılar için aynı olacaktır. Bu sayede ürün/senaryo adınızı kullanarak müşterilerinizin daha kolay bulmasını sağlayabilirsiniz.

### <a name="additional-template-tips"></a>Ek şablon ipuçları
* Sorgularda belirttiğiniz parametrelerin son kullanıcılarınız açısından anlamlı olduğundan emin olun
* Son kullanıcınızın zamanlanmış yenilemenin tamamlanması için bekleyeceği süreye dikkat edin

![oluştur](media/template-content-pack-testing/createtemplate.png)

<a name="submission"></a>

## <a name="submission"></a>Gönderme
[Microsoft AppSource](https://appsource.microsoft.com/en-us/partners/list-an-app) üzerinden gerçekleştirilen gönderme işlemi, şablon içerik paketinizin PowerBI.com üzerindeki hizmet içerik paketleri galerisinde yayımlanmasının yanı sıra içerik paketinizin [Microsoft AppSource](http://appsource.microsoft.com)'ta listelenmesini sağlayacaktır.

### <a name="before-submission"></a>Göndermeden önce
* İçerik paketi içindeki tüm öğelerle ilgili içerik oluşturma ipuçlarını gözden geçirin
* Çeşitli hesaplar ve veri koşullarıyla test ve bağlantı gerçekleştirin. (Kendi özel [Veri Bağlayıcınızı](https://aka.ms/DataConnectors) geliştirdiyseniz bu adımı atlayın)
* Tüm görselleri gözden geçirin, yazım hatalarına dikkat edin ve bulduklarınızı düzeltin
* İçerik paketinin Soru-Cevap özelliğine düzgün cevaplar verdiğinden emin olun. Veri modelinde en az 30 farklı soruyu test etmenizi öneririz. (Kendi özel [Veri Bağlayıcınızı](https://aka.ms/DataConnectors) geliştirdiyseniz bu adımı atlayın)

### <a name="submission"></a>Gönderme
Göndermeye hazır olduğunuzda AppSource'taki [Uygulama gönderme sayfasını](https://appsource.microsoft.com/en-us/partners/list-an-app) ziyaret edin ve bilgilerinizi gönderin. Kullanılabilir ürün listesinden Power BI'ı seçtiğinizden emin olun

Power BI ekibi gönderinizi inceleyecek ve tüm öğelerin gereksinimlere uygun olduğundan emin olmak için sizinle iletişime geçecektir. Paketin eksiksiz olmasının yanı sıra sağlanan panonun ve raporların kalite düzeyini de doğrulayarak uygulamada anlatılan iş senaryosuna uygun olduğundan emin olacağız.

### <a name="updates"></a>Güncelleştirmeler
İçerik paketinizin güncelleştirilme işlemi, ilk gönderme sürecine benzerdir. 

