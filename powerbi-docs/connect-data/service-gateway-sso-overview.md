---
title: Power BI'daki ağ geçitleri için çoklu oturum açmaya (SSO) genel bakış
description: Power BI'dan şirket içi veri kaynaklarına çoklu oturum açmayı (SSO) etkinleştirmek için ağ geçidinizi yapılandırın.
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 5eab21418eb1028d94ba2e50ffd6e736e6226018
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83301805"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>Power BI'daki ağ geçitleri için çoklu oturum açmaya (SSO) genel bakış

Şirket içi veri ağ geçidinizi yapılandırıp Power BI raporlarının ve panoların şirket içi verilerle gerçek zamanlı olarak güncelleştirilmesini sağlayarak sorunsuz çoklu oturum açma bağlantısından yararlanabilirsiniz. Ağ geçidinizi [Kerberos](service-gateway-sso-kerberos.md) kısıtlanmış temsili veya Security Assertion Markup Language ([SAML](service-gateway-sso-saml.md)) ile yapılandırma seçeneğiniz vardır. Şirket içi veri ağ geçidi, şirket içi veri kaynaklarına bağlanan [DirectQuery](desktop-directquery-about.md) kullanarak veya Yenileme için SSO’yu destekler. 

Power BI aşağıdaki veri kaynaklarını destekler:

* SQL Server (Kerberos)
* SAP HANA (Kerberos ve SAML)
* SAP BW Uygulama Sunucusu (Kerberos)
* SAP BW İleti Sunucusu (Kerberos) 
* Oracle (Kerberos) 
* Teradata (Kerberos)
* Spark (Kerberos)
* Impala (Kerberos)

Şu anda [M uzantıları](https://github.com/microsoft/DataConnectors/blob/master/docs/m-extensions.md) için SSO desteklenmemektedir.

Bir kullanıcı Power BI Hizmeti'ndeki bir DirectQuery raporuyla etkileşime geçtiğinde; her bir çapraz filtreleme, dilimleme, sıralama ve rapor düzenleme işlemi, temel alınan şirket içi veri kaynağında sorguların canlı olarak yürütülmesine neden olabilir. Veri kaynağı için SSO’yu yapılandırdığınızda, sorgular, Power BI ile etkileşime geçen kullanıcının kimliği altında (web deneyimi veya Power BI mobil uygulamaları aracılığıyla) yürütülür. Bu nedenle, her kullanıcı temel alınan veri kaynağında izinli olduğu verileri tam olarak görür. 

Power BI hizmetinde yenileme için ayarlanmış bir raporu da SSO kullanacak şekilde yapılandırabilirsiniz. Bu veri kaynağı için SSO'yu yapılandırdığınızda sorgular Power BI içindeki veri kümesi sahibinin kimliği altında yürütülür. Bu nedenle yenileme işlemi, veri kümesi sahibinin temel alınan veri kaynağındaki izinlerine göre gerçekleşir. SSO kullanarak yenileme şu anda yalnızca [Kerberos](service-gateway-sso-kerberos.md) kısıtlanmış temsili kullanan veri kaynakları için etkinleştirilmiştir 

## <a name="query-steps-when-running-sso"></a>SSO çalıştırırken gerçekleştirilen sorgu adımları

SSO ile çalıştırılan bir sorgu, aşağıdaki diyagramda da gösterildiği gibi üç adımdan oluşur.

![SSO sorgu adımları](media/service-gateway-sso-overview/sso-query-steps.png)

Aşağıda, her adımla ilgili ayrıntılar verilmiştir:

1. Her sorgu için, Power BI hizmeti yapılandırılmış ağ geçidine sorgu isteği gönderirken, o anda Power BI hizmetinde oturum açmış olan kullanıcının tam kullanıcı adı olan *kullanıcı asıl adını (UPN)* içerir.

2. Ağ geçidinin Azure Active Directory UPN'sini yerel bir Active Directory kimliği ile eşlemesi gerekir:

   a. Azure AD DirSync (*Azure AD Connect* olarak da bilinir) yapılandırılmışsa eşleme işlemi ağ geçidinde otomatik olarak gerçekleştirilir.

   b.  Aksi halde ağ geçidi, yerel Active Directory etki alanında arama gerçekleştirerek Azure AD UPN'sini bir yerel AD kullanıcısıyla eşleyebilir.

3. Ağ geçidi hizmeti işlemi, eşlenen yerel kullanıcının kimliğine bürünür, temel alınan veritabanına yönelik bağlantıyı açar ve sonra sorguyu gönderir. Ağ geçidini veritabanıyla aynı makineye yüklemeniz gerekmez.

## <a name="next-steps"></a>Sonraki adımlar

Ağ geçidi aracılığıyla SSO etkinleştirme ile ilgili temel bilgileri kavradığınıza göre Kerberos ve SAML hakkında daha ayrıntılı bilgilere göz atabilirsiniz:

* [Çoklu oturum açma (SSO) - Kerberos](service-gateway-sso-kerberos.md)
* [Çoklu oturum açma (SSO) - SAML](service-gateway-sso-saml.md)
