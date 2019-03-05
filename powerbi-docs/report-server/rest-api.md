---
title: Power BI Rapor Sunucusu için REST API'lerle içerik geliştirme
description: REST API, bir Power BI Rapor Sunucusu kataloğundaki nesnelere program aracılığıyla erişim sağlar.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/25/2018
ms.openlocfilehash: 154415f3662aebaa086d3452eb84e589333ecd28
ms.sourcegitcommit: e9c45d6d983e8cd4cb5af938f838968db35be0ee
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57327861"
---
# <a name="develop-with-the-rest-apis-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için REST API'lerle içerik geliştirme

Power BI Rapor Sunucusu, Temsili Durum Aktarımı (REST) API'leri destekler. REST API'ler, bir rapor sunucusu içindeki kaynaklar için oluşturma, alma, güncelleştirme veya silme erişimi sunan bir dizi HTTP işlemini (yöntemini) destekleyen hizmet uç noktalarıdır.

REST API, bir Power BI Rapor Sunucusu kataloğundaki nesnelere program aracılığıyla erişim sağlar. Nesnelere örnek olarak klasörler, raporlar, KPI'ler, veri kaynakları, veri kümeleri, yenileme planları, abonelikler ve diğerleri verilebilir. Örneğin REST API'yi kullanarak klasör hiyerarşisinde gezinebilir, bir klasörün içeriğini keşfedebilir veya bir rapor tanımını indirebilirsiniz. Ayrıca nesne oluşturabilir, güncelleştirebilir ve silebilirsiniz. Nesnelerle çalışmaya örnek olarak rapor yükleme, yenileme planı çalıştırma, klasör silme gibi işlevler verilebilir.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-hybrid-note.md)]

## <a name="components-of-a-rest-api-requestresponse"></a>REST API istek/yanıt bileşenleri

REST API istek/yanıt çifti beş bileşene ayrılabilir:

* **İstek URI'si**, şu şekildedir: `{URI-scheme} :// {URI-host} / {resource-path} ? {query-string}`. İstek URI'si istek iletisi üst bilgilerinde yer alsa da birçok dil veya çerçeve için bunu istek iletisinden ayrı bir şekilde iletmeniz gerektiğinden burada ayrı ele alıyoruz.
  
  * URI şeması: İsteği iletmek için kullanılan protokolü belirtir. Örneğin `http` veya `https` olabilir.
  * URI ana bilgisayarı: REST hizmeti uç noktasının barındırıldığı sunucunun etki alanı adını veya IP adresini belirtir, örneğin: `myserver.contoso.com`.
  * Kaynak yolu: Kaynağı veya hizmetin kaynak seçimine karar vermek için kullandığı birden fazla bölüm içerebilen kaynak koleksiyonunu belirtir. Örneğin: `CatalogItems(01234567-89ab-cdef-0123-456789abcdef)/Properties`, CatalogItem için belirli özellikleri alma amacıyla kullanılabilir.
  * Sorgu dizesi (isteğe bağlı): API sürümü veya kaynak seçim ölçütü gibi basit ek parametreler sunar.
* HTTP isteği iletisi üst bilgi alanları:
  
  * Hizmete istediğiniz işlem türünü belirten bir [HTTP yöntemi](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) (işlem veya eylem olarak da bilinir). Reporting Services REST API'leri DELETE, GET, HEAD, PUT, POST ve PATCH yöntemlerini destekler.
  * Belirtilen URI ve HTTP yöntemi için gerekli olan isteğe bağlı üst bilgi alanları.
* URI ve HTTP işlemini destekleyecek isteğe bağlı HTTP **istek iletisi gövdesi** alanları. Örneğin POST işlemleri, karmaşık parametreler olarak iletilen MIME kodlamalı nesneler içerir. POST veya PUT işlemleri için gövde MIME kodlama türü de `Content-type` istek üst bilgisinde belirtilmelidir. Bazı hizmetlerde `application/json` gibi belirli bir MIME türü kullanılması gerekir.
* HTTP **yanıt iletisi üst bilgi** alanları:
  
  * 2xx başarı kodlarından 4xx veya 5xx hata kodlarına kadar değişebilen bir [HTTP durum kodu](http://www.w3.org/Protocols/HTTP/HTRESP.html). Alternatif olarak API belgelerinde belirtildiği şekilde hizmet tarafından tanımlanan bir durum kodu da döndürülebilir.
  * İsteğin yanıtını desteklemek için `Content-type` yanıt üst bilgisi gibi isteğe bağlı ek üst bilgi alanları.
* İsteğe bağlı HTTP **yanıt iletisi gövdesi** alanları:
  
  * Veri döndüren GET yöntemi yanıtı gibi MIME kodlamalı yanıt nesneleri, HTTP yanıt gövdesinde döndürülür. Bu nesneler genellikle JSON veya XML gibi yapılandırılmış biçimde döndürülür ve bu durum `Content-type` yanıt üst bilgisi ile belirtilir.

## <a name="api-documentation"></a>API belgeleri

Modern bir REST API'si için modern API belgeleri gerekir. REST API'si, OpenAPI belirtimi (başka bir deyişle swagger belirtimi) üzerine kurulmuştur ve belgelere [SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0) sayfasından ulaşmanız mümkündür. SwaggerHub, API belgelerini barındırmanın yanı sıra istediğiniz dilde bir istemci kitaplığı oluşturmanıza yardımcı olur: JavaScript, TypeScript, C#, Java, Python, Ruby ve diğerleri.

## <a name="testing-api-calls"></a>API çağrılarını test etme

HTTP istek/yanıt iletilerini test etmek için kullanabileceğiniz araçlardan biri [Fiddler](http://www.telerik.com/fiddler) aracıdır. Fiddler, REST isteklerinizi keserek HTTP istek/yanıt iletilerini tanılamayı kolaylaştıran ücretsiz bir web tabanlı hata ayıklama ara sunucusudur.

## <a name="next-steps"></a>Sonraki adımlar

[SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0)'daki API'leri inceleyin.

[GitHub](https://github.com/Microsoft/Reporting-Services)'da örnekler mevcuttur. TypeScript, React ve web paketi üzerinde kurulmuş bir örnek HTML5 uygulamasının yanı sıra PowerShell örneğini de inceleyebilirsiniz.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)