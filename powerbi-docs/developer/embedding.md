---
title: Power BI ile ekleme
description: "Power BI, panolarınızı ve raporlarınızı uygulamalara eklemek için kullanabileceğiniz API'ler sunar."
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
ms.date: 10/05/2017
ms.author: asaxton
ms.openlocfilehash: 36eb4231b6b3d3278d571722bde731051ffdf05e
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="embedding-with-power-bi"></a>Power BI ile ekleme
Power BI, panolarınızı ve raporlarınızı uygulamalara eklemek için kullanabileceğiniz API'ler sunar. Power BI API'leri içeriğinizi eklerken kullanabileceğiniz tutarlı özellik kümesi ve panolar, ağ geçitleri ve uygulama çalışma alanları gibi en yeni Power BI özeliklerine erişim sunar.

## <a name="a-single-api"></a>Tek bir API
Power BI içeriğini eklerken kullanılabilecek iki ana senaryo vardır. Kuruluşunuz için ekleme ve müşterileriniz için ekleme. Power BI REST API'si iki senaryo için de kullanılabilir. Bu sayede panoları ve raporları özel uygulamanıza ekleyebilir, aynı API'yi kullanarak kuruluşunuz veya müşterilerinizle paylaşabilirsiniz. İçerik eklerken JavaScript ve REST API'lerinin tüm özelliklerini kullanabilirsiniz.

İçerik eklemenin nasıl gerçekleştirildiğini gösteren bir örnek için bkz. [JavaScript ekleme örneği](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Kuruluşunuz için içerik ekleme
Kuruluşunuz için içerik ekleyerek Power BI hizmetinin kapsamını genişletebilirsiniz. Bunun için uygulamanızın son kullanıcısının içeriğinizi görüntülemek istediğinde Power BI hizmetinde oturum açması gerekir. Kuruluşunuzdaki kullanıcılar oturum açtığında yalnızca kendileriyle Power BI hizmetinden paylaşılmış olan panolara ve raporlara erişebilir. 

*Kuruluşunuz için içerik ekleme örnekleri arasında şirket içi web uygulaması, SharePoint Online web bölümü ve Microsoft Teams tümleştirmesi bulunur.*

Kuruluşunuz için içerik ekleme konusunda bilgiye aşağıdaki sayfalardan ulaşabilirsiniz:

* [Panoları uygulamalarla tümleştirme](integrate-dashboard.md)
* [Kutucukları uygulamalarla tümleştirme](integrate-tile.md)
* [Raporları uygulamalarla tümleştirme](integrate-report.md)

Düzenleme ve kaydetme gibi self servis özellikleri Power BI kullanıcıları için ekleme yaparken [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)'si aracılığıyla kullanılabilir.

## <a name="embedding-for-your-customers"></a>Müşterileriniz için içerik ekleme
Müşterileriniz için içerik ekleme, panoları ve raporları Power BI hesabı olmayan müşterilerle paylaşma olanağı sunar. Müşterilerinizin Power BI'dan haberdar olmalarına gerek yoktur. En az bir Power BI Pro hesabı gerekir. Power BI Pro hesabı, uygulamanız için ana hesap olarak kullanılır. Bunu bir yetkili hesap olarak düşünün. Power BI Pro hesabı ayrıca Power BI hizmetindeki panolara ve raporlara erişim sağlayan ekleme belirteçlerini oluşturmanızı da sağlar. 

*Müşterileriniz için içerik ekleme örneklerinden biri, diğer şirketlere sunulan bir ISV uygulamasıdır.*

![Müşterileriniz için içerik ekleme akışı](media/embedding/powerbi-embed-flow.png)

Panoları, raporları ve kutucukları eklemek için kuruluşunuz için içerik ekleme amacıyla kullandığınız API'leri kullanmanız gerekir.

> [!IMPORTANT]
> Ekleme işlemi, Power BI hizmetine bağlı olsa da müşterileriniz için Power BI hizmeti bağımlılığı söz konusu değildir. Müşterilerinizin uygulamanıza eklenmiş içeriği görüntülemek için Power BI'a kaydolması gerekmez.
> 
> 

Üretim aşamasına geçmeye hazır olduğunuzda uygulama çalışma alanınızın bir kapasiteye atanması gerekir. Microsoft Azure içindeki Power BI Embedded çözümü, uygulamalarınızla kullanılabilecek kapasiteyi sunar.

Ekleme hakkında ayrıntılı bilgi için bkz. [Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](embedding-content.md).

Azure'daki Power BI Çalışma Alanı Koleksiyonları'nı kullanıyorsanız içeriğinizi taşıma hakkında bilgi almak için bkz. [Power BI Çalışma Alanı Koleksiyonları Azure hizmetindeki içeriği taşıma](migrate-from-powerbi-embedded.md).

## <a name="next-steps"></a>Sonraki adımlar
[Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](embedding-content.md)  
[Power BI Embedded çalışma alanı koleksiyon içeriğini Power BI'a taşıma](migrate-from-powerbi-embedded.md)  
[Power BI Premium nedir?](../service-premium.md)  
[JavaScript API'si Git deposu](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git deposu](https://github.com/Microsoft/PowerBI-CSharp)  
[JavaScript ekleme örneği](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Embedded analytics capacity planning (Katıştırılmış analiz kapasite planlaması) teknik incelemesi](https://aka.ms/pbiewhitepaper)  
[Power BI Premium teknik incelemesi](https://aka.ms/pbipremiumwhitepaper)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

