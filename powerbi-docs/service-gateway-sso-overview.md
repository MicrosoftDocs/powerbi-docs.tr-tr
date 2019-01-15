---
title: Şirket içi veri kaynaklarında çoklu oturum açmayı (SSO) kullanma
description: Power BI'dan şirket içi veri kaynaklarına çoklu oturum açmayı (SSO) etkinleştirmek için ağ geçidinizi yapılandırın.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/15/2018
LocalizationGroup: Gateways
ms.openlocfilehash: bfd40c991f461e57f2f1d2de8a46b3627aa7fbc1
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54274226"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>Power BI'daki ağ geçitleri için çoklu oturum açmaya (SSO) genel bakış

Şirket içi veri ağ geçidinizi Kerberos kısıtlanmış temsil veya Security Assertion Markup Language (SAML) ile yapılandırıp Power BI raporlarının ve panoların şirket içi verilerle etkinleştirilmesini sağlayarak sorunsuz çoklu oturum açma bağlantısından yararlanabilirsiniz. Şirket içi veri ağ geçidi SSO bağlantılarını, şirket içi veri kaynaklarına bağlanmak için kullandığı DirectQuery’den yararlanarak kurar.

Şu an için aşağıdaki veri kaynakları desteklenmektedir:

* SQL Server ([Kerberos](service-gateway-sso-kerberos.md))
* SAP HANA ([Kerberos](service-gateway-sso-kerberos.md) ve [SAML](service-gateway-sso-saml.md))
* SAP BW ([Kerberos](service-gateway-sso-kerberos.md)
* Teradata ([Kerberos](service-gateway-sso-kerberos.md))
* Spark ([Kerberos](service-gateway-sso-kerberos.md))
* Impala ([Kerberos](service-gateway-sso-kerberos.md))

Bir kullanıcı Power BI Hizmeti'ndeki bir DirectQuery raporuyla etkileşime geçtiğinde; her bir çapraz filtreleme, dilimleme, sıralama ve rapor düzenleme işlemi, temel alınan şirket içi veri kaynağında canlı olarak sorgu yürütülmesine neden olabilir.  Veri kaynağı için SSO yapılandırıldığında, sorgular, Power BI ile etkileşime geçen kullanıcının kimliği altında (web deneyimi veya Power BI mobil uygulamaları aracılığıyla) yürütülür. Bu nedenle, her bir kullanıcı tam olarak, temel alınan veri kaynağında ilgili izinlere sahip olduğu verileri görür. Çoklu oturum açma yapılandırılmış olduğunda, paylaşılan verilerin farklı kullanıcılar için önbelleğe alınması söz konusu değildir.

## <a name="query-steps-when-running-sso"></a>SSO çalıştırırken gerçekleştirilen sorgu adımları

SSO ile çalıştırılan bir sorgu, aşağıdaki diyagramda da gösterildiği gibi üç adımdan oluşur.

![SSO sorgu adımları](media/service-gateway-sso-overview/sso-query-steps.png)

> [!NOTE]
> Oracle için SSO henüz mevcut olmasa da şu anda geliştirme aşamasındadır ve yakında kullanıma sunulacaktır.

Aşağıda, bu adımlara ilişkin ayrıntılar verilmiştir:

1. **Power BI hizmeti** yapılandırılmış ağ geçidine sorgu isteği gönderirken her bir sorguya *kullanıcı asıl adını* (UPN) ekler.

2. Ağ geçidinin Azure Active Directory UPN'sini yerel bir Active Directory kimliği ile eşlemesi gerekir.

   a.  Azure AD DirSync (*Azure AD Connect* olarak da bilinir) yapılandırılmışsa eşleme işlemi ağ geçidinde otomatik olarak gerçekleştirilir.

   b.  Aksi halde ağ geçidi, yerel Active Directory etki alanında arama gerçekleştirerek Azure AD UPN'sini bir yerel kullanıcı ile eşleyebilir.

3. Ağ geçidi hizmeti işlemi, eşlenen yerel kullanıcının kimliğine bürünür, temel alınan veritabanına yönelik bağlantıyı açar ve sorguyu gönderir. Ağ geçidinin veri kaynağının bulunduğu makineye yüklenmesi gerekmez.

## <a name="next-steps"></a>Sonraki adımlar

SSO ile ilgili temel bilgileri kavradığınıza göre Kerberos ve SAML hakkında daha ayrıntılı bilgilere göz atabilirsiniz:

* [Çoklu oturum açma (SSO) - Kerberos](service-gateway-sso-kerberos.md)
* [Çoklu oturum açma (SSO) - SAML](service-gateway-sso-saml.md)
