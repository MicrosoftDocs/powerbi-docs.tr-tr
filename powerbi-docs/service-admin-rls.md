---
title: "Power BI ile satır düzeyi güvenlik (RLS)"
description: "Power BI hizmetinde, içeri aktarılan veri kümeleri ve DirectQuery için satır düzeyi güvenliği yapılandırma."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 11/29/2017
ms.author: asaxton
ms.openlocfilehash: 338921df57b77b1e79f9b71e814203734ab5971c
ms.sourcegitcommit: 7742f952c20695dfb475f74965c0065b02c01521
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/29/2017
---
# <a name="row-level-security-rls-with-power-bi"></a>Power BI ile satır düzeyi güvenlik (RLS)
<iframe width="560" height="315" src="https://www.youtube.com/embed/67fK0GoVQ80?showinfo=0" frameborder="0" allowfullscreen></iframe>

Power BI ile satır düzeyi güvenlik (RLS), belirli kullanıcıların veri erişimini kısıtlamak için kullanılabilir. Filtreler verileri satır düzeyinde kısıtlar. Rollerde filtre tanımlayabilirsiniz.

Power BI Desktop ile Power BI'a aktarılan veri modelleri için RLS'yi yapılandırabilirsiniz. Ayrıca DirectQuery'yi kullanan SQL Server gibi veri kümelerinde de RLS'yi yapılandırabilirsiniz. Önceden RLS'yi yalnızca Power BI dışındaki şirket içi Analysis Services modellerinde uygulayabiliyordunuz. Analysis Services canlı bağlantıları için Satır düzeyi güvenliği şirket içi model üzerinde yapılandırırsınız. Güvenlik seçeneği, canlı bağlantı veri kümeleri için gösterilmez.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

## <a name="manage-security-on-your-model"></a>Modelinizde güvenliği yönetme
Veri modelinizde güvenliği yönetmek için aşağıdakileri gerçekleştirmeniz gerekir.

1. Bir veri kümesine ilişkin **üç nokta (…)** simgesini seçin.
2. **Güvenlik** seçeneğini belirleyin.
   
   ![](media/service-admin-rls/rls-security.png)

Bu, Power BI Desktop'ta oluşturduğunuz bir role üye eklemeniz için sizi RLS sayfasına yönlendirir. Yalnızca veri kümesinin sahipleri Güvenlik seçeneğini görür. Veri kümesi bir Grupta yer alıyorsa yalnızca grup Yöneticileri güvenlik seçeneğini görür. 

Power BI Desktop'ta yalnızca rol oluşturabilir veya rolleri değiştirebilirsiniz.

## <a name="working-with-members"></a>Üyelerle çalışma
### <a name="add-members"></a>Üye ekleme
Eklemek istediğiniz kullanıcının, güvenlik grubunun veya dağıtım listesinin e-posta adresini ya da adını yazarak role üye ekleyebilirsiniz. Bu üyenin kuruluşunuzda olması gerekir. Power BI'da oluşturulan Grupları ekleyemezsiniz.

![](media/service-admin-rls/rls-add-member.png)

Rol adının veya Üyeler'in yanında parantez içinde gösterilen sayıya bakarak role kaç üyenin dahil olduğunu da görebilirsiniz.

![](media/service-admin-rls/rls-member-count.png)

### <a name="remove-members"></a>Üyeleri kaldırma
Üye adlarının yanındaki X işaretlerini seçerek üyeleri kaldırabilirsiniz. 

![](media/service-admin-rls/rls-remove-member.png)

## <a name="validating-the-role-within-the-power-bi-service"></a>Power BI hizmetinde rolü doğrulama
Tanımladığınız rolü test ederek rolün doğru şekilde çalışıp çalışmadığını doğrulayabilirsiniz. 

1. Rolün yanındaki **üç nokta (...)** simgesini seçin.
2. **Verileri role göre test et** seçeneğini belirleyin

![](media/service-admin-rls/rls-test-role.png)

Ardından, bu rol için kullanılabilen raporları görürsünüz. Panolar bu görünümde sunulmaz. Yukarıdaki mavi çubuk, hangi rolün filtrelendiğini gösterir.

![](media/service-admin-rls/rls-test-role2.png)

**Şu anda şu kişi olarak görüntülüyorsunuz** seçeneğini belirleyerek diğer rolleri veya rol birleşimlerini test edebilirsiniz.

![](media/service-admin-rls/rls-test-role3.png)

Verileri belirli bir kullanıcı olarak görüntülemeyi tercih edebilir veya kullanılabilir rollerin bir birleşimini seçerek çalışıp çalışmadıklarını doğrulayabilirsiniz. 

Normal görüntülemeye geri dönmek için **Satır Düzeyi Güvenliğe Geri Dön** seçeneğini belirleyin.

[!INCLUDE [include-short-name](./includes/rls-usernames.md)]

## <a name="using-rls-with-app-workspaces-in-power-bi"></a>Power BI'da uygulama çalışma alanlarıyla RLS'yi kullanma
Power BI Desktop raporunuzu Power BI hizmetindeki bir uygulama çalışma alanında yayımlarsanız roller salt okunur üyeler için geçerli olur. Uygulama çalışma alanı ayarlarında üyelerin Power BI içeriğini yalnızca görüntüleyebileceklerini belirtmeniz gerekir.

> [!WARNING]
> Uygulama çalışma alanını yapılandırırken üyelerin, düzenleme izinlerine sahip olacağını belirtirseniz RLS rolleri söz konusu üyeler için geçerli olmaz. Bu durumda, kullanıcılar tüm verileri görebilir.
> 
> 

![](media/service-admin-rls/rls-group-settings.png)

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Sonraki adımlar
[Row-level security (RLS) with Power BI Desktop (Power BI Desktop ile satır düzeyi güvenlik (RLS))](desktop-rls.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

