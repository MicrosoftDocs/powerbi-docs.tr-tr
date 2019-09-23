---
title: Power BI izinleri
description: Power BI izinleri
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 10/01/2018
ms.openlocfilehash: 8a48ec007f2d8c9c07de5cc0d51049e3dbf19662
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61269377"
---
# <a name="power-bi-permissions"></a>Power BI izinleri

## <a name="permission-scopes"></a>İzin kapsamları

Power BI izinleri, uygulamaya kullanıcı adına belirli eylemleri gerçekleştirme olanağı sunar. Tüm izinlerin geçerli olması için bir kullanıcı tarafından onaylanması gerekir.

| Görünen Ad | Açıklama | Kapsam Değeri |
| --- | --- | --- |
| Tüm Veri Kümelerini Görüntüleme |Uygulama oturum açmış olan kullanıcının veri kümelerinin yanı sıra kullanıcının erişimi olan veri kümelerini görüntüleyebilir. |Dataset.Read.All |
| Tüm Veri Kümelerini Okuma ve Yazma |Uygulama oturum açmış olan kullanıcının veri kümelerinin yanı sıra kullanıcının erişimi olan veri kümelerini görüntüleyebilir ve yazabilir. |Dataset.ReadWrite.All |
| Kullanıcının veri kümesine veri ekleme |Uygulamaya kullanıcının veri kümesi satırlarında ekleme veya silme gerçekleştirme erişimi verir. Bu izin uygulamaya kullanıcı verilerine erişim izni vermez. |Data.Alter_Any |
| İçerik oluşturma |Uygulama kullanıcı için otomatik olarak içerik ve veri kümesi oluşturabilir. |Content.Create |
| Kullanıcının Gruplarını Görüntüleme |Uygulama, oturum açmış olan kullanıcının üyesi olduğu tüm grupları görüntüleyebilir. |Group.Read |
| Tüm Grupları Görüntüleme |Uygulama, oturum açmış olan kullanıcının üyesi olduğu tüm grupları görüntüleyebilir. |Group.Read.All |
| Tüm Grupları okuma ve yazma |Uygulama oturum açmış olan kullanıcının gruplarının yanı sıra kullanıcının erişimi olan grupları görüntüleyebilir ve yazabilir. |Group.ReadWrite.All |
| Tüm Panoları görüntüleme |Uygulama oturum açmış olan kullanıcının panolarının yanı sıra kullanıcının erişimi olan panoları görüntüleyebilir. |Dashboard.Read.All |
| Tüm Raporları görüntüleme |Uygulama oturum açmış olan kullanıcının raporlarının yanı sıra kullanıcının erişimi olan raporları görüntüleyebilir. Uygulama ayrıca rapor içindeki verileri ve raporun yapısını da görebilir. |Report.Read.All |
| Tüm Raporları Okuma ve Yazma |Uygulama oturum açmış olan kullanıcının raporlarının yanı sıra kullanıcının erişimi olan raporları görüntüleyebilir ve yazabilir. Bu izin yeni rapor oluşturma hakkı vermez. |Report.ReadWrite.All |
| Tüm Kapasiteleri okuma ve yazma |Uygulama oturum açmış olan kullanıcının kapasitelerinin yanı sıra kullanıcının erişimi olan kapasiteleri görüntüleyebilir ve yazabilir. Bu izin yeni kapasite oluşturma hakkı vermez. |Capacities.ReadWrite.All |
| Tüm kapasiteler okuma |Uygulama oturum açmış olan kullanıcının kapasitelerinin yanı sıra kullanıcının erişimi olan kapasiteleri görüntüleyebilir ve yazabilir. Bu izin yeni kapasite oluşturma hakkı vermez. |Capacities.Read.All |
| Kiracıdaki tüm içeriği okuma ve yazma |Uygulama, Power BI’daki gruplar, raporlar, panolar ve veri kümeleri gibi tüm yapıları görüntüleyebilir ve bunlara yazabilir. Oturum açmış kullanıcının Power BI hizmet yöneticisi olması şartıyla. |Tenant.ReadWrite.All |
| Kiracıdaki tüm içeriği görüntüleme |Uygulama, Power BI’daki gruplar, raporlar, panolar ve veri kümeleri gibi tüm yapıtları görüntüleyebilir. Oturum açmış kullanıcının Power BI hizmet yöneticisi olması şartıyla. |Tenant.Read.All |

Uygulama, istenen izinleri çağrının kapsam parametresinde ileterek kullanıcı sayfasında ilk oturum açma girişiminde bulunduğunda izin isteyebilir. İzinler verildiğinde uygulamaya sonraki API çağrılarında kullanılabilecek bir erişim belirteci döndürülür. Erişim yalnızca belirli bir uygulama tarafından kullanılabilir.

> [!NOTE]
> Power BI API'lerde uygulama çalışma alanları hâlâ gruplar olarak adlandırılmaktadır. Gruplara yapılan başvurular, uygulama çalışma alanlarıyla çalıştığınızı gösterir.

## <a name="requesting-permissions"></a>İzin İsteme

Kullanıcı adı ve parolayla kimlik doğrulaması gerçekleştirmek için API çağrısı yapmaya ek olarak, başka bir kullanıcı adına eylem gerçekleştirmek isteyen uygulamaların izin istemesi, bu iznin kullanıcı tarafından onaylanması ve ardından sonraki çağrılarda kullanılmak üzere erişim belirtecinin gönderilmesi gerekir. Bu işlem için standart [OAuth 2.0](http://oauth.net/2/) protokolünü uygulayacağız. Gerçek uygulamalar farklılık gösterebilir ancak Power BI için OAuth akışı şu öğelere sahiptir:

* **Oturum açma kullanıcı arabirimi**: Geliştirici izin istemek için bu arabirimi çağırabilir. Kullanıcı oturum açmamışsa açması istenecektir. Kullanıcının ayrıca uygulamanın istediği izinleri de onaylaması gerekecektir. Oturum açma penceresi bir erişim kodu veya verilen yeniden yönlendirme URL'sine giden bir hata iletisi döndürecektir.
  * Yerel uygulamalar tarafından kullanılmak üzere Power BI tarafından standart bir yeniden yönlendirme URL'si iletilmelidir.
* **Yetkilendirme Kodu**: Yetkilendirme Kodları yeniden yönlendirme URL'sindeki URL parametreleri aracılığıyla oturum açma işlemi sonrasında web uygulamalarına döndürülür. Bunlar parametre içinde olduğu için bir miktar güvenlik riski söz konusudur. Web uygulamalarının yetkilendirme kodunu Yetkilendirme Belirteci ile değiştirmesi gerekir
* **Yetkilendirme Belirteci**: API çağrılarında kullanıcı adına kimlik doğrulaması gerçekleştirmek için kullanılır. Belirteçlerin kapsamı belirli bir uygulamayla sınırlı olacaktır. Belirteçlerin kullanım ömrü sınırlıdır ve bu süre dolduğunda yenilenmeleri gerekir.
* **Yenileme Belirteci**: Belirteçlerin süresi dolduğunda yenileme işlemi gerçekleştirilir.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)