---
title: "Power BI Güvenliği"
description: "Power BI Güvenliği. Power BI ile Azure Active Directory ve diğer Azure hizmetleri arasındaki ilişki. Bu konu başlığı altında, daha ayrıntılı bir teknik incelemenin bağlantısı da verilmiştir."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: erikri
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
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 2d780c04a207f67b4f0f7c06672f993df3818275
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2017
---
# <a name="power-bi-security"></a>Power BI Güvenliği
Power BI güvenlik özelliklerine ilişkin ayrıntılı bir açıklama için lütfen [Power BI Güvenliği teknik incelemesini indirin](http://go.microsoft.com/fwlink/?LinkId=829185):

[![](media/service-admin-power-bi-security/pbi_security_01.png)](http://go.microsoft.com/fwlink/?LinkId=829185)

Power BI hizmetinin temelini, Microsoft'un bulut bilgi işlem altyapısı ve platformu olan **Azure** oluşturmaktadır. Power BI hizmeti mimarisi, Web Ön Ucu (**WFE**) kümesi ve **Arka Uç** kümesi olmak üzere iki kümeyi temel alır. WFE kümesi, Power BI hizmetine yönelik ilk bağlantıdan ve kimlik doğrulamasından sorumludur. Kimlik doğrulaması yapıldıktan sonraki tüm kullanıcı etkileşimlerini Arka Uç üstlenir. Power BI, kullanıcı kimliklerini depolamak ve yönetmek için Azure Active Directory (AAD) hizmetini, verileri ve meta verileri depolamak ve yönetmek içinse Azure BLOB ve Azure SQL Veritabanı hizmetlerini kullanır.

## <a name="power-bi-architecture"></a>Power BI Mimarisi
Her Power BI dağıtımında iki küme (Web Ön Ucu (**WFE**) kümesi ve **Arka Uç** kümesi olmak üzere) bulunur.

**WFE** kümesi Power BI için ilk bağlantı ve kimlik doğrulaması işlemlerini yönetir. Bu küme, AAD hizmetini kullanarak istemcilerin kimliklerini doğrular ve Power BI hizmetiyle kurulacak sonraki istemci bağlantıları için belirteçler sağlar. Ayrıca Power BI, hem kimlik doğrulaması hem de statik içeriğin ve dosyaların indirilmesi için bağlantı kurmaya çalışan istemcinin DNS kaydına göre kullanıcı trafiğini en yakın veri merkezine yönlendirmek amacıyla **Azure Traffic Manager** (ATM) hizmetini kullanır. Power BI, statik içeriği ve dosyaları coğrafi yerel ayara göre kullanıcılara verimli bir şekilde dağıtmak için **Azure Content Delivery Network** (CDN) hizmetini kullanır.

![](media/service-admin-power-bi-security/pbi_security_v2_wfe.png)

**Arka Uç** kümesi, kimlik doğrulamasından geçen istemcilerin, Power BI hizmetiyle nasıl etkileşim kuracağını belirler. **Arka Uç** kümesi; görselleştirmeleri, kullanıcı panolarını, veri kümelerini, raporları, veri depolama alanlarını, veri bağlantılarını, veri yenileme özelliklerini ve Power BI hizmetiyle etkileşim kurarken kullanılan diğer öğeleri yönetir. **Ağ Geçidi Rolü** kullanıcı istekleriyle Power BI hizmeti arasında bir ağ geçidi işlevi görür. Kullanıcılar **Ağ Geçidi Rolü** haricindeki bir rolle doğrudan etkileşim kurmaz. **Ağ Geçidi Rolü**, **Azure API Management** tarafından yönetilir.

![](media/service-admin-power-bi-security/pbi_security_v2_backend_updated.png)

> [!IMPORTANT]
> Yalnızca **Azure API Management** (APIM) ve **Ağ Geçidi** (GW) rollerinin İnternet üzerinden herkesin erişimine açık olduğu unutulmamalıdır. Bu hizmetler kimlik doğrulaması, yetkilendirme, DDoS koruması, Azaltma, Yük Dengeleme, Yönlendirme gibi özellikler sunar.
> 
> 

## <a name="data-storage-security"></a>Veri Depolama Alanı Güvenliği
Power BI hizmetinin veri depolamak ve yönetmek için kullandığı iki ana depo vardır. Kullanıcılar tarafından karşıya yüklenen veriler genelde **Azure BLOB** depolama alanına gönderilirken sisteme ait meta veriler ve tüm yapıtlar **Azure SQL Veritabanı**'nda depolanır.

Yukarıdaki **Arka Uç** kümesi resminde yer alan kesik çizgi, kullanıcılar tarafından erişilebilen iki bileşen (kesik çizginin sol tarafı) ile yalnızca sistem tarafından erişilebilen roller arasındaki ayrımı göstermektedir. Kimliği doğrulanmış bir kullanıcı Power BI hizmetine bağlandığında bağlantı ve istemci istekleri **Ağ Geçidi Rolü** tarafından kabul edilip yönetilir (sonrasında **Azure API Management** tarafından işlenmek üzere) ve bu rol, Power BI hizmetinin geri kalan kısmında kullanıcının adına etkileşimde bulunur. Örneğin, bir istemci bir panoyu görüntülemek istediğinde **Ağ Geçidi Rolü** bu isteği kabul eder ve tarayıcının panoyu oluşturması için gerekli olan verileri almak için **Sunum Rolü**'ne ayrı bir istek gönderir.

## <a name="user-authentication"></a>Kullanıcı Kimlik Doğrulaması
Power BI, oturum açan kullanıcıların kimliğini doğrulamak için Azure Active Directory ([AAD](http://azure.microsoft.com/services/active-directory/)) hizmetini; kullanıcının, kimlik doğrulaması gerektiren kaynaklara erişmek istemesi halinde ise Power BI oturum açma kimlik bilgilerini kullanır. Power BI hizmetinde, Power BI hesabını oluşturmak için kullandığı e-posta adresiyle oturum açan kullanıcılar için Power BI, ilgili e-posta adresini *etkin kullanıcı adı* olarak kullanır ve kullanıcı verilere bağlanmaya çalıştığında kaynaklara bu bilgiyi iletir. Ardından *etkin kullanıcı adı* bir *Kullanıcı Asıl Adı* ([UPN](https://msdn.microsoft.com/library/windows/desktop/aa380525\(v=vs.85\).aspx)) ile eşlenerek ilişkili Windows etki alanı hesabı çözümlenir ve kimlik doğrulaması bu hesaba uygulanır.

Power BI oturumu açmak için iş e-postalarını kullanan kuruluşlarda (*david@contoso.com* gibi) *etkin kullanıcı adı* doğrudan UPN ile eşlenir. Power BI oturumu açmak için iş e-postalarını kullanmayan kuruluşlarda (*david@contoso.onmicrosoft.com* gibi) AAD ve şirket içi kimlik bilgileri arasında eşleme yapılabilmesi için [dizin eşitleme](https://technet.microsoft.com/library/jj573653.aspx) hizmetinin düzgün çalışması gerekir.

Power BI için platform güvenliği aynı zamanda çok kiracılı ortam güvenliğini, ağ güvenliğini ve AAD tabanlı ek güvenlik önlemleri ekleme olanağını da kapsar.

## <a name="data-and-service-security"></a>Veri ve Hizmet Güvenliği
Daha fazla bilgi için lütfen [Microsoft Güven Merkezi](https://www.microsoft.com/trustcenter)'ni ziyaret edin.

Bu makalenin yukarıdaki bölümlerinde açıklandığı üzere kullanıcının Power BI oturum açma bilgileri, şirket içi Active Directory sunucuları tarafından kullanılarak kimlik bilgilerine ilişkin bir UPN ile eşlenir. Ancak, kullanıcıların, paylaştıkları verilerin sorumluluğunu alması gerektiğini **unutmayın**. Bir kullanıcının kendi kimlik bilgilerini kullanarak bağlandığı veri kaynağındaki verileri kullanan bir raporu (veya panoyu ya da veri kümesini) paylaşması halinde, ilgili öğenin paylaşıldığı kullanıcıların kimliği, özgün veri kaynağı için doğrulanmaz ve bu kullanıcılara, rapora yönelik erişim izni verilir.

Bu durum, **şirket içi veri ağ geçidi** kullanılarak **SQL Server Analysis Services** ile kurulan bağlantılar için geçerli değildir. Panolar Power BI hizmetinde önbelleğe alınır ancak bağlantılı raporlara veya veri kümelerine erişim için rapora (veya veri kümesine) erişmek isteyen kullanıcıya yönelik olarak kimlik doğrulaması başlatılır ve yalnızca kullanıcının ilgili verilere erişmek için yeterli kimlik bilgilerine sahip olması durumunda erişim izni verilir. Daha fazla bilgi için bkz. [Şirket içi veri ağ geçidine yakından bakış](service-gateway-onprem-indepth.md).

