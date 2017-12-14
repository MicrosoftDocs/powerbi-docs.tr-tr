---
title: "SAP HANA veri kaynağınızı yönetme"
description: "Şirket içi veri ağ geçitlerini ve bu ağ geçitlerine ait veri kaynaklarını yönetme. Bu makale SAP HANA'ya özeldir."
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
ms.date: 10/05/2017
ms.author: davidi
ms.openlocfilehash: d65bdf17997809cd4bcaa2718da42ba41398bcf4
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2017
---
# <a name="manage-your-sap-hana-data-source"></a>SAP HANA veri kaynağınızı yönetme
Şirket içi veri ağ geçidini yükledikten sonra ilgili ağ geçidi ile kullanılabilecek veri kaynaklarını eklemeniz gerekir. Bu makalede ağ geçitleriyle ve veri kaynaklarıyla nasıl çalışıldığı anlatılmaktadır. SAP HANA veri kaynağını zamanlanmış yenileme veya DirectQuery için kullanabilirsiniz.

## <a name="download-and-install-the-gateway"></a>Ağ geçidini indirme ve yükleme
Ağ geçidini Power BI hizmetinden indirebilirsiniz. **İndir** > **Data Gateway** seçeneğini belirleyin veya [ağ geçidi indirme sayfasına](https://go.microsoft.com/fwlink/?LinkId=698861) gidin.

![](media/service-gateway-enterprise-manage-sap/powerbi-download-data-gateway.png)

## <a name="add-a-gateway"></a>Ağ geçidi ekleme
Bir Ağ Geçidi eklemek için ortamınızdaki bir sunucuda ağ geçidini [indirin](https://go.microsoft.com/fwlink/?LinkId=698861) ve yükleyin. Ağ geçidi, yüklendikten sonra **Ağ geçitlerini yönet** bölümündeki ağ geçidi listelerinde görünecektir.

> [!NOTE]
> **Ağ geçitlerini yönet** seçeneği en az bir ağ geçidinin yöneticisi olduğunuzda görünür. Bunun için bir yönetici olarak eklenmeniz veya bir ağ geçidi yükleyip yapılandırmanız gerekir.
> 
> 

## <a name="remove-a-gateway"></a>Ağ geçitlerini kaldırma
Bir ağ geçidini kaldırmak, söz konusu ağ geçidi altındaki tüm veri kaynaklarının da silinmesine neden olur.  Ayrıca bu işlem, ilgili veri kaynaklarını kullanan panoların ve raporların tümünü bozar.

1. Sağ üst köşedeki dişli simgesi ![](media/service-gateway-enterprise-manage-sap/pbi_gearicon.png) > **Ağ geçitlerini yönet** seçeneğini belirleyin.
2. Ağ geçidi > **Kaldır**
   
   ![](media/service-gateway-enterprise-manage-sap/datasourcesettings7.png)

## <a name="add-a-data-source"></a>Veri kaynağı ekleme
Bir ağ geçidi seçip **Veri kaynağı ekle**'ye tıklayarak veya Ağ geçidi > **Veri kaynağı ekle** bölümüne giderek veri kaynağı ekleyebiliriz.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings1.png)

Ardından, listeden **Veri Kaynağı Türü**'nü seçebilirsiniz.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings2-sap.png)

Daha sonra, **Sunucu**, **Kullanıcı Adı** ve **Parola** gibi veri kaynağı bilgilerini doldurmanız gerekir.

> [!NOTE]
> Veri kaynağına yönelik tüm sorgular bu kimlik bilgileri kullanılarak çalıştırılır. [Kimlik bilgilerinin](service-gateway-onprem.md#credentials) nasıl depolandığı ile ilgili daha fazla bilgi için şirket içi veri ağ geçidi konusunun ele alındığı ana makaleye başvurun.
> 
> 

![](media/service-gateway-enterprise-manage-sap/datasourcesettings3-sap.png)

Tüm bilgileri doldurduktan sonra **Ekle**'ye tıklayabilirsiniz.  Artık bu veri kaynağını bir şirket içi SAP HANA sunucusunda zamanlanmış yenileme veya DirectQuery için kullanabilirsiniz. İşlem başarılı olduğunda *Bağlantı Başarılı* iletisi göreceksiniz.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings4.png)

### <a name="advanced-settings"></a>Gelişmiş ayarlar
Veri kaynağınızın gizlilik düzeyini yapılandırabilirsiniz. Bu işlem verilerin nasıl bir araya getirileceğini denetler. Bu işlem yalnızca zamanlanmış yenileme için kullanılır. DirectQuery için geçerli değildir. [Daha fazla bilgi](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![](media/service-gateway-enterprise-manage-sap/datasourcesettings9.png)

## <a name="remove-a-data-source"></a>Veri kaynaklarını kaldırma
Bir veri kaynağını kaldırmak, ilgili veri kaynağını kullanan panoların ve raporların tümünü bozar.  

Bir Veri Kaynağını kaldırmak için, Veri Kaynağı > **Kaldır** bölümüne gidin.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings6.png)

## <a name="manage-administrators"></a>Yöneticileri yönetme
Ağ geçidine ilişkin Yöneticiler sekmesinde, ağ geçidini yönetebilen kullanıcılar (veya güvenlik grupları) ekleyebilir ve kaldırabilirsiniz.

![](media/service-gateway-enterprise-manage-sap/datasourcesettings8.png)

## <a name="manage-users"></a>Kullanıcıları yönetme
Veri kaynağına ilişkin Kullanıcılar sekmesinde, veri kaynağını kullanabilen kullanıcılar veya güvenlik grupları ekleyebilir ve kaldırabilirsiniz.

> [!NOTE]
> Kullanıcılar listesi yalnızca kimlerin rapor yayımlayabildiğini denetler. Rapor sahipleri panolar veya içerik paketleri oluşturabilir ve bunları diğer kullanıcılarla paylaşabilir.
> 
> 

![](media/service-gateway-enterprise-manage-sap/datasourcesettings5.png)

## <a name="using-the-data-source"></a>Veri kaynağını kullanma
Veri kaynağı oluşturulduktan sonra, DirectQuery bağlantılarıyla veya zamanlanmış yenileme yoluyla kullanılabilir.

> [!NOTE]
> Şirket içi veri ağ geçidinde bulunan veri kaynağındaki ve Power BI Desktop'taki sunucu ve veritabanı adı eşleşmelidir!
> 
> 

Ağ geçidindeki veri kaynağı ve veri kümeniz arasındaki bağlantı sunucu ve veritabanı adınızı temel alır. Bunlar eşleşmelidir. Örneğin, Power BI Desktop içinde sunucu adı için bir IP Adresi sağlarsanız bu IP Adresini ağ geçidi yapılandırması içindeki veri kaynağında da kullanmanız gerekir. Power BI Desktop'ta *SUNUCU\ÖRNEK* yapılandırmasını kullanırsanız ağ geçidi için yapılandırılan veri kaynağında da aynısını kullanmanız gerekir.

Bu durum hem DirectQuery hem de zamanlanmış yenileme için geçerlidir.

### <a name="using-the-data-source-with-directquery-connections"></a>Veri kaynağını DirectQuery bağlantılarıyla kullanma
Sunucu ve veritabanı adının, Power BI Desktop'ta ve ağ geçidinin yapılandırılmış veri kaynağında eşleştiğinden emin olmanız gerekir. Ayrıca, DirectQuery veri kümelerini yayımlamak için kullanıcınızın, veri kaynağının **Kullanıcılar** sekmesinde listelendiğinden emin olmanız gerekir. DirectQuery'ye yönelik seçim, Power BI Desktop'ta verileri ilk kez içeri aktardığınız sırada gerçekleşir. [Daha fazla bilgi](desktop-use-directquery.md)

Power BI Desktop'ı veya **Veri Al** seçeneğini kullanarak yayımlama işlemini tamamladığınızda raporlarınız çalışmaya başlar. Ağ geçidinde veri kaynağı oluşturulduktan sonra bağlantının kullanılabilmesi için birkaç dakika beklemeniz gerekebilir.

### <a name="using-the-data-source-with-scheduled-refresh"></a>Zamanlanmış yenileme ile veri kaynağını kullanma
Ağ geçidinde yapılandırılan veri kaynağının **Kullanıcılar** sekmesinde yer alıyorsanız ve sunucu ile veritabanı adı eşleşiyorsa ağ geçidini, zamanlanmış yenileme ile kullanılabilen bir seçenek olarak görürsünüz.

![](media/service-gateway-enterprise-manage-sap/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidi](service-gateway-onprem.md)  
[Şirket içi veri ağ geçidi (ayrıntılı)](service-gateway-onprem-indepth.md)  
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

