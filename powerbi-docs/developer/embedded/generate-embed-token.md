---
title: Power BI ekli analizinde bir ekleme belirteci oluşturma konusuyla ilgili önemli noktalar
description: Ekleme belirteci oluşturmak için dikkat edilmesi gerekenler, sınırlamalar ve gerekli izinler hakkında bilgi edinin
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.custom: ''
ms.date: 10/15/2020
ms.openlocfilehash: 45a88d93e7ac5a63b269350451f39991ba153dd5
ms.sourcegitcommit: bbf7e9341a4e1cc96c969e24318c8605440282a5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97098042"
---
# <a name="considerations-when-generating-an-embed-token"></a>Ekleme belirteci oluştururken dikkate alınması gerekenler

[Belirteç oluşturma](/rest/api/power-bi/embedtoken), bir Power BI öğesini web uygulamasına veya portala ekleme amacıyla bir belirteç oluşturmanızı sağlayan bir REST API'sidir. Bu belirteç, isteğinizi Power BI hizmetinde yetkilendirmek için kullanılır.

Belirteç oluşturma API'si, tek bir kimlik (ana kullanıcı veya hizmet sorumlusu) kullanarak kullanıcının uygulamadaki kimlik bilgilerini (geçerli kimlik) temel alan bir belirteç oluşturur.

Kimlik doğrulaması başarılı olduktan sonra ilgili verilere erişim sağlanır.

>[!NOTE]
>Belirteç oluşturmayı yalnızca [*müşterileriniz için içerik eklediğinizde*](embed-sample-for-customers.md) (*veriler uygulamaya aittir* senaryosu olarak da bilinir) kullanılabilir.

Belirteç oluşturmak için aşağıdaki API'leri kullanabilirsiniz:

* [Panolar](/rest/api/power-bi/embedtoken/dashboards_generatetokeningroup)

* [Veri kümeleri](/rest/api/power-bi/embedtoken/datasets_generatetokeningroup)

* [Birden çok rapor için belirteç oluşturma](/rest/api/power-bi/embedtoken/generatetoken)


* [Rapor oluşturma](/rest/api/power-bi/embedtoken/reports_generatetokenforcreateingroup)

* [Raporlar](/rest/api/power-bi/embedtoken/reports_generatetokeningroup)

* [Kutucuklar](/rest/api/power-bi/embedtoken/tiles_generatetokeningroup)

## <a name="workspace-versions"></a>Çalışma alanı sürümleri

Power BI'da *klasik* çalışma alanı ve *yeni* çalışma alanı olmak üzere iki çalışma alanı sürümü vardır. Bu çalışma alanları arasındaki farklar hakkında daha fazla bilgi edinmek için bkz. [Yeni ve klasik çalışma alanları arasındaki farklar](../../collaborate-share/service-new-workspaces.md#new-and-classic-workspace-differences).

Ekleme belirteci oluştururken dikkat etmeniz gereken noktalar ve izinler seçtiğiniz çalışma alanına göre farklılık gösterebilir.

|                  |*Klasik* çalışma alanı |*Yeni* çalışma alanı|
|------------------|---------|--------|
|**Dikkat edilmesi gerekenler**|<li>Veri kümesi ve öğe aynı çalışma alanında olmalıdır</li><li>Hizmet sorumlusu kullanılamaz</li>  |Veri kümesi ve öğe iki farklı *yeni* çalışma alanında olabilir |
|**Çalışma alanı izinleri**|Ana kullanıcının çalışma alanının yöneticisi olması gerekir  |Hizmet sorumlusu veya ana kullanıcı iki çalışma alanında da en azından üye olmalıdır |

>[!NOTE]
>* [Çalışma alanım](../../consumer/end-user-workspaces.md#types-of-workspaces) için ekleme belirteci oluşturamazsınız.
>* *Öğe* sözcüğü pano, kutucuk, Soru-Cevap veya rapor gibi Power BI öğelerini ifade eder.

## <a name="securing-your-data"></a>Verilerinizin güvenliğini sağlama

Çözümünüzü oluştururken verilerinizi güvenliğini sağlayacak şu iki yaklaşımı inceleyin:

* [Çalışma alanı tabanlı yalıtım](embed-multi-tenancy.md#power-bi-workspace-based-isolation)

* [Satır düzeyi güvenlik tabanlı yalıtım](embed-multi-tenancy.md#row-level-security-based-isolation)

RLS yaklaşımını kullanacaksanız bu makalenin sonundaki [RLS ile ilgili önemli noktalar ve sınırlamalar](generate-embed-token.md#row-level-security) bölümünü inceleyin.

## <a name="token-permissions"></a>Belirteç izinleri

Belirteç oluşturma API'lerinin *GenerateTokenRequest* bölümünde belirteç izinleri anlatılmıştır.

>[!NOTE]
>Bu bölümde listelenen belirteç izinleri, [Birden çok rapor için belirteç oluşturma](/rest/api/power-bi/embedtoken/generatetoken) API'si için geçerli değildir.

### <a name="access-level"></a>Erişim düzeyi

Kullanıcının erişim düzeyini belirlemek için *accessLevel* parametresini kullanın.

* **View**: Kullanıcıya görüntüleme izni verin.

* **Edit**: Kullanıcıya görüntüleme ve düzenleme izni verin (yalnızca rapor için ekleme belirteci oluşturulurken geçerlidir).

    [Birden çok rapor için belirteç oluşturma](/rest/api/power-bi/embedtoken/generatetoken) API'sini kullanıyorsanız, kullanıcıya görüntüleme ve düzenleme izni vermek için *allowEdit* parametresini kullanın.

* **Create**: Kullanıcıya rapor oluşturma izni verin (yalnızca rapor oluşturma için ekleme belirteci oluştururken geçerlidir).

    Rapor oluşturmak için *datasetId* parametresini de sağlamanız gerekir.

### <a name="saving-a-copy-of-the-report"></a>Raporun kopyasını kaydetme

Kullanıcıların raporu yeni bir rapor olarak kaydetmesine izin vermek için *allowSaveAs* Boole değerini kullanın. Bu ayar varsayılan olarak *false* şeklinde ayarlanmıştır.

Bu parametre yalnızca rapor için ekleme belirteci oluştururken geçerlidir.

### <a name="row-level-security"></a>Satır Düzeyi Güvenlik

[Satır Düzeyi Güvenlik (RLS)](embedded-row-level-security.md) sayesinde belirteci oluşturduğunuz hizmet sorumlusu veya ana kullanıcı kimliği yerine farklı bir kimlik kullanmayı tercih edebilirsiniz. Bu seçeneği kullanarak eklenen bilgileri hedeflediğiniz kullanıcıya göre görüntüleyebilirsiniz. Örneğin uygulamanızda kullanıcılardan oturum açmasını isteyip satış bilgilerini içeren bir raporun yalnızca oturum açmış olan kullanıcının satış ekibine ait olması durumunda görüntülenmesini sağlayabilirsiniz.

RLS kullandığınızda bazı durumlarda kullanıcı kimliğini (*EffectiveIdentity* parametresi) dışarıda bırakabilirsiniz. Bu sayede belirteç, veritabanının tamamına erişim sağlayabilir. Bu yöntem, veri kümesinin tamamını görüntüleme iznine sahip olan yöneticiler ve idareciler gibi kullanıcılara erişim vermek için kullanılabilir. Ancak bu yöntemi her senaryoda kullanamazsınız. Aşağıdaki tabloda farklı RLS türleri listelenmiş ve kullanıcı kimliği belirtilmeden kullanılabilecek kimlik doğrulama yöntemleri gösterilmiştir.

Tabloda ayrıca her bir RLS türüyle ilgili önemli noktalar ve sınırlamalar da yer almaktadır.

|RLS türü  |Geçerli kullanıcı kimliğini belirtmeden ekleme belirteci oluşturabilir miyim?  |Önemli noktalar ve sınırlamalar  |
|---------|---------|---------|
|Bulut Satır Düzeyi Güvenlik (Bulut RLS)      |✔ Ana kullanıcı<br/>✖ Hizmet sorumlusu          |         |
|RDL (sayfalandırılmış raporlar)     |✖ Ana kullanıcı<br/>✔ Hizmet sorumlusu        |RDL için ekleme belirteci oluşturmak üzere ana kullanıcı kullanamazsınız.         |
|Analysis Services (AS) şirket içi canlı bağlantısı    |✔ Ana kullanıcı<br/>✖ Hizmet sorumlusu         |Ekleme belirtecini oluşturan kullanıcının aşağıdaki izinlerden birine de sahip olması gerekir:<li>Ağ geçidi yöneticisi izinleri</li><li>Veri kaynağının kimliğine bürünme izni (*ReadOverrideEffectiveIdentity*)</li>         |
|Analysis Services (AS) Azure canlı bağlantısı    |✔ Ana kullanıcı<br/>✖ Hizmet sorumlusu         |Ekleme belirtecini oluşturan kullanıcının kimliği geçersiz kılınamaz. Dinamik RLS veya güvenli filtreleme sağlamak için özel veriler kullanılabilir.<br/><br/>**Not:** Hizmet sorumlusu, geçerli kimlik (RLS kullanıcı adı) olarak nesne kimliğini sağlamalıdır.         |
|Çoklu Oturum Açma (SSO)     |✔ Ana kullanıcı<br/>✖ Hizmet sorumlusu         |Geçerli kimlik nesnesinde kimlik blob özelliği kullanılarak açık (SSO) kimlik sağlanabilir         |
|SSO ve bulut RLS     |✔ Ana kullanıcı<br/>✖ Hizmet sorumlusu         |Şunları sağlamanız gerekir:<li>Geçerli kimlik nesnesindeki kimlik blob özelliğinde açık (SSO) kimliği</li><li>Geçerli (RLS) kimliği (kullanıcı adı)</li>         |

>[!NOTE]
>Hizmet sorumlusunun her zaman şunları sağlaması gerekir:
>* RLS veri kümesindeki bir öğe için kimlik.
>* SSO veri kümesi için kullanıcı adı özelliği tanımlanmış geçerli bir RLS kimliği.

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Uygulamayı kaydetme](register-app.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için Power BI Embedded](embed-sample-for-customers.md)

>[!div class="nextstepaction"]
>[Azure Active Directory'deki uygulama ve hizmet sorumlusu nesneleri](/azure/active-directory/develop/app-objects-and-service-principals)

>[!div class="nextstepaction"]
>[Hizmet sorumlusuyla şirket içi veri ağ geçidinde satır düzeyi güvenlik kullanma](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal)

>[!div class="nextstepaction"]
>[Hizmet sorumlusuyla Power BI içeriği ekleme](embed-service-principal.md)