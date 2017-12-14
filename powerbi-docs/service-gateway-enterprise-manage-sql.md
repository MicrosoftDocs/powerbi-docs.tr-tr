---
title: "Manage your data source - SQL (Veri kaynağınızı yönetme - SQL)"
description: "Şirket içi veri ağ geçidini ve bu ağ geçidine ait veri kaynaklarını yönetme."
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 11/02/2017
ms.author: davidi
ms.openlocfilehash: 95fccd70b536a26baf93bf4735750e5599e3021f
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2017
---
# <a name="manage-your-data-source---sql-server"></a>Manage your data source - SQL Server (Veri kaynağınızı yönetme - SQL Server)
Şirket içi veri ağ geçidini yükledikten sonra ilgili ağ geçidi ile kullanılabilen veri kaynaklarını ekleyebilirsiniz. Bu makalede, ağ geçitleriyle ve veri kaynaklarıyla nasıl çalışıldığı anlatılmaktadır. SQL Server veri kaynağını zamanlanmış yenileme veya DirectQuery için kullanabilirsiniz.

## <a name="download-and-install-the-gateway"></a>Ağ geçidini indirme ve yükleme
Ağ geçidini Power BI hizmetinden indirebilirsiniz. **İndir** > **Data Gateway** seçeneğini belirleyin veya [ağ geçidi indirme sayfasına](https://go.microsoft.com/fwlink/?LinkId=698861) gidin.

![](media/service-gateway-enterprise-manage-sql/powerbi-download-data-gateway.png)

## <a name="add-a-gateway"></a>Ağ geçidi ekleme
Bir ağ geçidi eklemek için yalnızca ortamınızdaki bir sunucudan ağ geçidini [indirin](https://go.microsoft.com/fwlink/?LinkId=698861) ve yükleyin. Ağ geçidi, yüklendikten sonra **Ağ geçitlerini yönet** bölümündeki ağ geçidi listelerinde görünecektir.

> [!NOTE]
> **Ağ geçitlerini yönet** seçeneği en az bir ağ geçidinin yöneticisi olduğunuzda görünür. Bu durum, bir ağ geçidine yönetici olarak eklendiğinizde veya bir ağ geçidini kendiniz yükleyip yapılandırdığınızda gerçekleşir.
> 
> 

## <a name="remove-a-gateway"></a>Ağ geçitlerini kaldırma
Bir ağ geçidini kaldırmak, bu ağ geçidi altındaki tüm veri kaynaklarının da silinmesine neden olur.  Bu işlem ayrıca ilgili veri kaynağını kullanan panoların ve raporların tümünü bozar.

1. Sağ üst köşedeki dişli simgesi ![](media/service-gateway-enterprise-manage-sql/pbi_gearicon.png) > **Ağ geçitlerini yönet** seçeneğini belirleyin.
2. Ağ geçidi > **Kaldır**
   
   ![](media/service-gateway-enterprise-manage-sql/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Veri kaynağı ekleme
Bir veri kaynağını, bir ağ geçidi seçip **Veri kaynağı ekle**'ye tıklayarak veya Ağ geçidi > **Veri kaynağı ekle**'ye giderek ekleyebilirsiniz.

![](media/service-gateway-enterprise-manage-sql/datasourcesettings1.png)

Ardından **Veri Kaynağı Türü**'nü listeden seçebilirsiniz.

![](media/service-gateway-enterprise-manage-sql/datasourcesettings2.png)

> [!NOTE]
> DirectQuery kullanırken, ağ geçidi yalnızca **SQL Server 2012 SP1** ve sonraki sürümlerini destekler.
> 
> 

Ardından, **Sunucu** ve **Veritabanı**'nı içeren veri kaynağı bilgilerini doldurmak isteyebilirsiniz.  

Ayrıca bir **Kimlik Doğrulama Yöntemi** seçmeniz gerekecektir.  Bu yöntem **Windows** veya **Temel** seçeneklerinden biri olabilir.  Windows Kimlik Doğrulaması yerine SQL Kimlik Doğrulaması kullanacaksanız **Temel**'i seçmeyi tercih edebilirsiniz. Ardından, bu veri kaynağı için kullanılacak kimlik bilgilerini girin.

> [!NOTE]
> Kerberos Çoklu Oturum Açma (SSO) özelliği, veri kaynağı için yapılandırılmadığı ve etkinleştirilmediği sürece veri kaynağına yönelik tüm sorgular bu kimlik bilgileri kullanılarak çalıştırılır. SSO ile oturum açıldığında, içeri aktarılan veri kümeleri için, depolanan kimlik bilgilerini kullanır ancak DirectQuery veri kümeleri, SSO ile sorgu yürütmek için geçerli Power BI kullanıcısını kullanır. Daha fazla bilgi edinmek için, [kimlik bilgilerinin](service-gateway-onprem.md#credentials) nasıl depolandığını anlatan ana şirket içi veri geçidi makalesine veya [Power BI ve şirket içi veri kaynakları arasında SSO (çoklu oturum açma) gerçekleştirmek için Kerberos'u kullanmayı](service-gateway-kerberos-for-sso-pbi-to-on-premises-data.md) anlatan makaleye göz atın.
> 
> 

![](media/service-gateway-enterprise-manage-sql/datasourcesettings3.png)

Her yeri doldurduktan sonra **Ekle**'ye tıklayabilirsiniz.  Artık bu veri kaynağını bir şirket içi SQL Server'da zamanlanmış yenileme veya DirectQuery için kullanabilirsiniz. İşlem başarılı olduğunda *Bağlantı Başarılı* iletisi göreceksiniz.

![](media/service-gateway-enterprise-manage-sql/datasourcesettings4.png)

### <a name="advanced-settings"></a>Gelişmiş ayarlar
Veri kaynağınızın gizlilik düzeyini yapılandırabilirsiniz. Bu işlem verilerin nasıl bir araya getirileceğini denetler. Bu işlem yalnızca zamanlanmış yenileme için kullanılır. DirectQuery için geçerli değildir. [Daha fazla bilgi](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-sql/datasourcesettings9.png)

## <a name="remove-a-data-source"></a>Veri kaynaklarını kaldırma
Bir veri kaynağını kaldırma, ilgili veri kaynağını kullanan panoların ve raporların tümünü bozar.  

Bir Veri Kaynağını kaldırmak için, Veri Kaynağı > **Kaldır** seçeneğine gidin.

![](media/service-gateway-enterprise-manage-sql/datasourcesettings6.png)

## <a name="manage-administrators"></a>Yöneticileri yönetme
Ağ geçidinin Yöneticiler sekmesinde, ağ geçidini yönetebilen kullanıcılar (veya güvenlik grupları) ekleyebilir ve kaldırabilirsiniz.

![](media/service-gateway-enterprise-manage-sql/datasourcesettings8.png)

## <a name="manage-users"></a>Kullanıcıları yönetme
Veri kaynakları için, kullanıcılar sekmesinde ilgili veri kaynağını kullanabilen kullanıcılar veya güvenlik grupları ekleyebilir ve kaldırabilirsiniz.

> [!NOTE]
> Kullanıcılar listesi yalnızca kimlerin rapor yayımlayabildiğini denetler. Rapor sahipleri panolar veya içerik paketleri oluşturabilir ve bunları diğer kullanıcılarla paylaşabilir.
> 
> 

![](media/service-gateway-enterprise-manage-sql/datasourcesettings5.png)

## <a name="using-the-data-source"></a>Veri kaynağını kullanma
Veri kaynağı, oluşturulduktan sonra DirectQuery bağlantılarıyla veya zamanlanmış yenileme yoluyla kullanılabilir.

> [!NOTE]
> Şirket içi veri ağ geçidinde bulunan veri kaynağındaki ve Power BI Desktop'taki sunucu ve veritabanı adı eşleşmelidir!
> 
> 

Ağ geçidindeki veri kaynağı ve veri kümeniz arasındaki bağlantı, sunucu ve veritabanı adınızı temel alır. Bunlar eşleşmelidir. Örneğin, **Power BI Desktop** içinde sunucu adı için bir IP Adresi sağlarsanız bu IP Adresini ağ geçidi yapılandırması içindeki veri kaynağında da kullanmanız gerekir. Power BI Desktop'ta *SERVER\INSTANCE* (SUNUCU\ÖRNEK) seçeneğini kullanırsanız ağ geçidi için yapılandırılan veri kaynağında da aynısını kullanmanız gerekir.

Bu durum hem DirectQuery hem de zamanlanmış yenileme için geçerlidir.

### <a name="using-the-data-source-with-directquery-connections"></a>Veri kaynağını DirectQuery bağlantılarıyla kullanma
Sunucu ve veritabanı adının **Power BI Desktop**'ta ve ağ geçidinin yapılandırılmış veri kaynağında eşleştiğinden emin olmanız gerekir. Ayrıca, DirectQuery veri kümelerini yayımlamak için kullanıcınızın, veri kaynağının **Kullanıcılar** sekmesinde listelendiğinden emin olmanız gerekir. DirectQuery'ye yönelik seçim, verileri ilk kez içeri aktardığınızda Power BI Desktop'ta gerçekleşir. [Daha fazla bilgi](desktop-use-directquery.md)

Power BI Desktop veya **Veri Al** seçeneğinden yayımladığınızda, raporlarınızın çalışmaya başlaması gerekir. Ağ geçidinde veri kaynağını oluşturduktan sonra bağlantının kullanılır hale gelmesi, birkaç dakika alabilir.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Veri kaynağını zamanlanmış yenileme ile kullanma
Ağ geçidinde yapılandırılan veri kaynağının **Kullanıcılar** sekmesinde listeleniyorsanız ve sunucu ile veritabanı adı eşleşiyorsa ağ geçidini zamanlanmış yenileme ile kullanılabilen bir seçenek olarak görürsünüz.

![](media/service-gateway-enterprise-manage-sql/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Şirket içi veri ağ geçidi](service-gateway-onprem.md)  
* [Şirket içi veri ağ geçidi ayrıntıları](service-gateway-onprem-indepth.md)  
* [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)
* [Use Kerberos for SSO (single sign-on) from Power BI to on-premises data sources (Power BI ve şirket içi veri kaynakları arasında SSO (çoklu oturum açma) gerçekleştirmek için Kerberos'u kullanma)](service-gateway-kerberos-for-sso-pbi-to-on-premises-data.md). 
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

