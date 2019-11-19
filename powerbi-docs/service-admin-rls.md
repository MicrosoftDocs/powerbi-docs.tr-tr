---
title: Power BI ile satır düzeyi güvenlik (RLS)
description: Power BI hizmetinde, içeri aktarılan veri kümeleri ve DirectQuery için satır düzeyi güvenliği yapılandırma.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.author: mblythe
ms.date: 09/09/2019
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 7d2bfbfb53914fea43014c78d88ac0c66559466c
ms.sourcegitcommit: 8cc2b7510aae76c0334df6f495752e143a5851c4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73431355"
---
# <a name="row-level-security-rls-with-power-bi"></a>Power BI ile satır düzeyi güvenlik (RLS)

Power BI ile satır düzeyi güvenlik (RLS), belirli kullanıcıların veri erişimini kısıtlamak için kullanılabilir. Filtreler, veri erişimini satır düzeyinde sınırlar ve rollerin içinde filtre tanımlayabilirsiniz. Power BI hizmetinde bir çalışma alanının üyelerinin o çalışma alanındaki veri kümelerine erişebildiğini unutmayın. RLS bu veri erişimini kısıtlamaz.

Power BI Desktop ile Power BI'a aktarılan veri modelleri için RLS'yi yapılandırabilirsiniz. Ayrıca DirectQuery'yi kullanan SQL Server gibi veri kümelerinde de RLS'yi yapılandırabilirsiniz. Önceden RLS'yi yalnızca Power BI dışındaki şirket içi Analysis Services modellerinde uygulayabiliyordunuz. Analysis Services canlı bağlantıları için Satır düzeyi güvenliği şirket içi model üzerinde yapılandırırsınız. Güvenlik seçeneği, canlı bağlantı veri kümeleri için gösterilmez.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

Varsayılan olarak, ilişkilerin tek yönlü veya çift yönlü olarak ayarlanmış olması fark etmeksizin satır düzeyi güvenlik filtrelemesi için tek yönlü filtreler kullanılır. İlişkiyi seçip **Güvenlik filtrelerini her iki yönde de uygula** onay kutusunu işaretleyerek, satır düzeyi güvenlik için çift yönlü çapraz filtrelemeyi elle etkinleştirebilirsiniz. Sunucu düzeyinde dinamik satır düzeyi güvenlik de uyguladıysanız (satır düzeyi güvenlik kullanıcı adına ve oturum açma kimliğine göre yapıldığında) bu kutuyu da işaretlemeniz gerekir.

Daha fazla bilgi için [Power BI Desktop'ta DirectQuery'yi kullanarak çift yönlü çapraz filtreleme](desktop-bidirectional-filtering.md) makalesine ve [Securing the Tabular BI Semantic Model (Tablolu BI Anlam Modelinin Güvenliğini Sağlama)](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Securing%20the%20Tabular%20BI%20Semantic%20Model.docx) başlıklı teknik makaleye bakın.

![Güvenlik Filtresi uygulama](media/service-admin-rls/rls-apply-security-filter.png)


[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

## <a name="manage-security-on-your-model"></a>Modelinizde güvenliği yönetme

Veri modelinizde güvenliği yönetmek için aşağıdakileri gerçekleştirmeniz gerekir.

1. Bir veri kümesine ilişkin **üç nokta (…)** simgesini seçin.
2. **Güvenlik** seçeneğini belirleyin.
   
   ![Güvenlik filtrelerini her iki yönde de uygula](media/service-admin-rls/rls-security.png)

Bu, Power BI Desktop'ta oluşturduğunuz bir role üye eklemeniz için sizi RLS sayfasına yönlendirir. Yalnızca veri kümesinin sahipleri Güvenlik seçeneğini görür. Veri kümesi bir Grupta yer alıyorsa yalnızca grup Yöneticileri güvenlik seçeneğini görür. 

Power BI Desktop'ta yalnızca rol oluşturabilir veya rolleri değiştirebilirsiniz.

## <a name="working-with-members"></a>Üyelerle çalışma

### <a name="add-members"></a>Üye ekleme

Eklemek istediğiniz kullanıcının, güvenlik grubunun veya dağıtım listesinin e-posta adresini ya da adını yazarak role üye ekleyebilirsiniz. Power BI'da oluşturulan Grupları ekleyemezsiniz. [Kuruluşunuzun dışından](whitepaper-azure-b2b-power-bi.md#data-security-for-external-partners) üyeler ekleyebilirsiniz.

![Üye ekleme](media/service-admin-rls/rls-add-member.png)

Rol adının veya Üyeler'in yanında parantez içinde gösterilen sayıya bakarak role kaç üyenin dahil olduğunu da görebilirsiniz.

![Roldeki üyeler](media/service-admin-rls/rls-member-count.png)

### <a name="remove-members"></a>Üyeleri kaldırma

Üye adlarının yanındaki X işaretlerini seçerek üyeleri kaldırabilirsiniz. 

![Üyeyi kaldırma](media/service-admin-rls/rls-remove-member.png)

## <a name="validating-the-role-within-the-power-bi-service"></a>Power BI hizmetinde rolü doğrulama

Tanımladığınız rolü test ederek rolün doğru şekilde çalışıp çalışmadığını doğrulayabilirsiniz. 

1. Rolün yanındaki **Diğer seçenekler** (...) düğmesini seçin.
2. **Verileri role göre test et** seçeneğini belirleyin

![Role göre test et](media/service-admin-rls/rls-test-role.png)

Ardından, bu rol için kullanılabilen raporları görürsünüz. Panolar bu görünümde sunulmaz. Yukarıdaki mavi çubuk, hangi rolün filtrelendiğini gösterir.

![Artık <rol> olarak görüntüleniyor](media/service-admin-rls/rls-test-role2.png)

**Şu anda şu kişi olarak görüntülüyorsunuz** seçeneğini belirleyerek diğer rolleri veya rol birleşimlerini test edebilirsiniz.

![Diğer rolleri test etme](media/service-admin-rls/rls-test-role3.png)

Verileri belirli bir kullanıcı olarak görüntülemeyi tercih edebilir veya kullanılabilir rollerin bir birleşimini seçerek çalışıp çalışmadıklarını doğrulayabilirsiniz. 

Normal görüntülemeye geri dönmek için **Satır Düzeyi Güvenliğe Geri Dön** seçeneğini belirleyin.

[!INCLUDE [include-short-name](./includes/rls-usernames.md)]

## <a name="using-rls-with-workspaces-in-power-bi"></a>Power BI'da çalışma alanlarıyla RLS'yi kullanma

Power BI Desktop raporunuzu Power BI hizmetindeki bir çalışma alanında yayımlarsanız roller salt okunur üyeler için geçerli olur. Çalışma alanı ayarlarında üyelerin Power BI içeriğini yalnızca görüntüleyebileceklerini belirtmeniz gerekir.

> [!WARNING]
> Çalışma alanını yapılandırırken üyelerin, düzenleme izinlerine sahip olacağını belirtirseniz RLS rolleri söz konusu üyeler için geçerli olmaz. Bu durumda, kullanıcılar tüm verileri görebilir.

![Grup ayarları](media/service-admin-rls/rls-group-settings.png)

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Sonraki adımlar
[Row-level security (RLS) with Power BI Desktop (Power BI Desktop ile satır düzeyi güvenlik (RLS))](desktop-rls.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
