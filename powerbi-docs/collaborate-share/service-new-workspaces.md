---
title: Yeni çalışma alanlarında çalışmayı düzenleme
description: Kuruluşunuza ana ölçümler sunmayı amaçlayan yeni çalışma alanlarını, pano ve rapor koleksiyonlarını öğrenin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: conceptual
ms.date: 10/21/2020
ms.custom: contperf-fy20q4
LocalizationGroup: Share your work
ms.openlocfilehash: 5aabc825ecd22ed49d05428148133be17156645d
ms.sourcegitcommit: 7bf09116163afaae312eb2b232eb7967baee2c92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97621499"
---
# <a name="organize-work-in-the-new-workspaces-in-power-bi"></a>Yeni çalışma alanlarında çalışmayı düzenleme

*Çalışma alanları*, çalışma arkadaşlarınızla işbirliği yaparak pano, rapor, veri kümesi ve sayfalandırılmış rapor koleksiyonları oluşturabildiğiniz yerlerdir. Yeni çalışma alanı deneyimi içeriğe erişimi daha iyi yönetmenize yardımcı olur. Bu makalede yeni çalışma alanları açıklanır ve klasik çalışma alanlarından farkları ortaya konur.  Klasik çalışma alanları gibi bunları da uygulamaları oluşturmak ve dağıtmak için kullanırsınız. 

Yeni bir çalışma alanı oluşturmaya hazır mısınız? Bkz. [Yeni çalışma alanı oluşturma deneyimi](service-create-the-new-workspaces.md).

:::image type="content" source="media/service-new-workspaces/power-bi-workspace-opportunity.png" alt-text="Power BI yeni çalışma alanı deneyimi":::

Yeni, yükseltilmiş çalışma alanları ve mevcut klasik çalışma alanları birlikte kullanılabilir. Yeni çalışma alanı deneyimi varsayılan çalışma alanı türüdür. Yine de ihtiyaç duyarsanız Microsoft 365 gruplarını temel alarak [klasik çalışma alanlarını](service-create-workspaces.md) oluşturabilir ve kullanabilirsiniz. Klasik çalışma alanınızı geçirmeye hazır mısınız? Ayrıntılar için bkz. [Power BI'da klasik çalışma alanlarını yeni çalışma alanlarına yükseltme](service-upgrade-workspaces.md).

## <a name="new-and-classic-workspace-differences"></a>Yeni ve klasik çalışma alanları arasındaki farklar

Yeni çalışma alanlarıyla bazı özellikleri yeniden tasarladık. Temel farklar aşağıda belirtilmiştir.

- **Yeni çalışma alanlarının oluşturulması, klasik çalışma alanlarında olduğu gibi Microsoft 365 gruplarının oluşturulmasına neden olmaz**. Yeni çalışma alanı yönetiminin tamamı Office 365’te değil Power BI’dadır. İçeriklere kullanıcı erişimini Microsoft 365 gruplarıyla yönetmeye devam edebilirsiniz. Bunun için tek yapmanız gereken çalışma alanı erişim listesine bir Microsoft 365 grubu eklemektir.
- Yeni çalışma alanlarında daha esnek bir izin yönetimi için **daha ayrıntılı çalışma alanı rolleri kullanabilirsiniz**.  Klasik çalışma alanlarında, üyeler ve yöneticiler listesine sadece kişileri ekleyebilirsiniz. 
- **Çalışma alanı rollerine kullanıcı grupları atama**: Yeni çalışma alanlarında, kullanıcı yönetimini kolaylaştırmak için bu rollere birden çok Active Directory güvenlik grubu, dağıtım listesi veya Microsoft 365 grubu ekleyebilirsiniz. 
- **Kişi listesi**: Yeni çalışma alanlarında, çalışma alanı etkinliği hakkında bildirim alacak kişileri belirleyebilirsiniz.
- **Şablon uygulamaları oluşturma**: Yeni çalışma alanlarında yalnızca *şablon uygulamaları* oluşturulabilir. Şablon uygulamaları, kuruluşunuzun dışındaki müşterilere dağıtabileceğiniz uygulamalardır. Daha sonra bu müşteriler kendi verilerini şablon uygulamanıza bağlayabilir. [Şablon uygulamaları](../connect-data/service-template-apps-overview.md) hakkında daha fazla bilgi edinin.
- **Veri kümelerini paylaşma**: Belirli bir çalışma alanının dışında veri kümesi paylaşmak için, veri kümesini içeren raporu yeni çalışma alanlarından birine kaydetmeniz gerekir. Klasik çalışma alanlarından veri kümeleri paylaşılamaz. [Paylaşılan veri kümeleri](../connect-data/service-datasets-across-workspaces.md) hakkında daha fazla bilgi edinin.
- **Kurumsal içerik paketleri**: Klasik çalışma alanlarında kurumsal içerik paketleri oluşturup kullanırsınız. Yeni çalışma alanlarında bunları oluşturamaz veya kullanamazsınız. Uygulamalar ve şablon uygulamaları, yeni çalışma alanlarındaki kurumsal içerik paketlerinin yerine geçer.

Bu makalede, bu özellikler daha ayrıntılı olarak açıklanmaktadır.

> [!NOTE]
> Power BI, üyesi olduğunuz tüm Microsoft 365 gruplarını listelemeye devam eder. Bu da mevcut iş akışlarının sürdürülebilmesini sağlar.

### <a name="features-that-work-differently"></a>Farklı çalışan özellikler

Yeni çalışma alanlarında bazı özellikler farklı çalışır. Bu farklar, müşterilerden gelen geri bildirimlere göre özellikle korunmuştur. Bunlar, çalışma alanlarında işbirliği yapmak için daha esnek bir yaklaşım sağlar.

- **Lisanslama zorunluluğu**: Raporları bir yeni çalışma alanı deneyiminde yayımlama işlemi mevcut lisans kurallarını zorunlu kılar. Yeni çalışma alanlarında işbirliği yapan veya Power BI hizmetindeki diğer kullanıcılarla içerik paylaşan kullanıcıların Power BI Pro lisansına sahip olması gerekir. Pro lisansı olmayan kullanıcılar "Yalnızca Power BI Pro lisansı olan kullanıcılar bu çalışma alanında yayımlayabilir" hatasını görür.
- **”Üyeler yeniden paylaşabilir” ayarı**: Yeni çalışma alanlarındaki Katkıda Bulunan rolü, klasik çalışma alanlarındaki “Üyeler yeniden paylaşabilir” ayarının yerine geçer.
- **Salt okunur çalışma alanları**: Yeni çalışma alanlarındaki Görüntüleyici rolü, klasik bir çalışma alanında kullanıcılara salt okuma erişimi verme işleminin yerine geçer. Görüntüleyici rolü, yeni çalışma alanlarında benzer salt okuma erişimini sağlar.
- **Pro lisansı olmayan kullanıcılar**, ancak Görüntüleyici rolüne sahip olmaları durumunda Power BI Premium kapasitesinde bulunan yeni bir çalışma alanına erişebilir.
- **Kullanıcıların verileri dışarı aktarmasına izin verme**: Yeni çalışma alanında Görüntüleyici rolüne sahip olan kullanıcılar bile çalışma alanındaki veri kümelerinde Oluşturma iznine sahip olmaları durumunda verileri dışarı aktarabilir. [Veri kümeleri için oluşturma izni](../connect-data/service-datasets-build-permissions.md) hakkında daha fazla bilgi edinin.
- Yeni çalışma alanlarında **Çalışma alanından ayrıl** düğmesi yoktur.

### <a name="workspace-contact-list"></a>Çalışma alanı kişi listesi

Yeni **Kişi listesi** özelliği, yeni çalışma alanında oluşan sorunlar hakkında bildirim alacak kullanıcıları belirtmenize olanak verir. Varsayılan olarak, yeni çalışma alanında çalışma alanı yöneticisi olarak belirtilen tüm kullanıcı veya gruplar bildirim alır. Bu listeye ekleme yapabilirsiniz. Kişi listesindeki kullanıcı veya gruplar da yeni çalışma alanlarındaki kullanıcı arabiriminde (UI) listelenir, böylece çalışma alanındaki son kullanıcılar iletişim kuracakları kişileri bilirler. 

[Çalışma alanı kişi listesini oluşturma](service-create-the-new-workspaces.md#create-a-contact-list) hakkında bilgi edinin.

### <a name="workspace-onedrive"></a>OneDrive Çalışma Alanı

Önceden belirttiğimiz gibi, siz yeni çalışma alanlarından birini oluşturduğunuzda, Power BI arka planda bir Microsoft 365 grubu oluşturmaz. Yine de, yeni çalışma alanıyla ilişkili bir OneDrive’a sahip olmanız yararlı olabilir. Yeni çalışma alanlarındaki OneDrive Çalışma Alanı özelliği sayesinde, SharePoint Belge Kitaplığı dosya depolama alanının çalışma alanı kullanıcıları tarafından kullanılabildiği bir Microsoft 365 grubu yapılandırabilirsiniz. Grubu Power BI dışında oluşturmanız gerekir.
 
Power BI, Microsoft 365 grup üyeliği ve yeni çalışma alanına erişimi olan kullanıcıların veya grupların izinleri arasında eşitleme işlemi yapmaz. Bunları eşitlemek için: Çalışma alanı erişimini yönetmek amacıyla bu ayarda dosya depolama alanını yapılandırdığınız aynı Microsoft 365 grubunu kullanabilirsiniz. 

[OneDrive çalışma alanını ayarlama](service-create-the-new-workspaces.md#set-a-workspace-onedrive) hakkında bilgi edinin.  

## <a name="roles-in-the-new-workspaces"></a>Yeni çalışma alanlarındaki roller

Roller yeni çalışma alanlarında kimlerin neler yapabileceğini yönetmenizi sağlar ve bu sayede ekipler işbirliği yapabilir. Yeni çalışma alanları kişilere ve kullanıcı gruplarına (güvenlik grupları, Microsoft 365 grupları ve dağıtım listeleri) roller atamanıza olanak tanır. 

Yeni çalışma alanına erişim vermek için, bu kullanıcı gruplarını veya kişileri çalışma alanı rollerinden birine atayın: Yönetici, Üye, Katkıda Bulunan veya Görüntüleyici. Kullanıcı grubundaki herkes atadığınız rolü alır. Bir kişi birkaç kullanıcı grubunda yer alıyorsa atandıkları rol tarafından sağlanan en yüksek izin düzeyine sahip olur. İç içe kullanıcı gruplarınız varsa, kapsam içinde yer alan tüm kullanıcıların izni olur. Görüntüleme ve etkileşim dışında bu özelliklerin tamamı için bir Power BI Pro lisansı gerekir. Bu makalede [lisanslama](#licenses) hakkında daha fazla bilgi edinebilirsiniz.

[!INCLUDE [power-bi-workspace-roles-table](../includes/power-bi-workspace-roles-table.md)]

> [!NOTE]
> - Rolleri kullanamasalar da kullanıcıları tek başına veya grup içinde rollere atayabilirsiniz. Başka bir deyişle, Power BI Pro lisansı olmayan kullanıcıları lisans gerektiren bir role atayabilirsiniz. Ayrıntılar için bu makalenin [Lisanslar](#licenses) bölümüne bakın.
> - Çalışma alanındaki içeriğe göz atan kullanıcılar için [satır düzeyi güvenliği (RLS)](../admin/service-admin-rls.md) zorunlu tutmak üzere Görüntüleyici rolünü kullanın. Yeni çalışma alanına erişim vermeden de RLS’yi zorunlu tutabilirsiniz. [Bir uygulama yayımlayıp](service-create-distribute-apps.md) bunu söz konusu kullanıcılara dağıtabilir veya bu kişilere [içerik dağıtmak için paylaşım özelliğini](service-share-dashboards.md) kullanabilirsiniz.

## <a name="licensing-and-administering"></a>Lisanslama ve yönetme

### <a name="licenses"></a>Lisanslar
Yeni çalışma alanlarından birisi paylaşılan bir kapasitede yer alıyorsa bu çalışma alanına eklediğiniz herkesin bir Power BI Pro lisansına sahip olması gerekir. Bu kullanıcıların tümü yeni çalışma alanındaki panolarda ve raporlarda işbirliği yapabilir. Kuruluşunuzun içindeki diğer kişilere içerik dağıtmak istiyorsanız söz konusu kullanıcılara Power BI Pro lisansları atayın veya çalışma alanını Power BI Premium kapasitesine taşıyın.

Yeni çalışma alanı Power BI Premium kapasitesinde olduğunda, Görüntüleyici rolüne sahip kullanıcılar Power BI Pro lisansları olmasa bile çalışma alanına erişebilir. Öte yandan bu kullanıcıları Yönetici, Üye veya Katkıda Bulunan gibi daha yüksek bir role atarsanız, kullanıcılar çalışma alanına erişmeye çalıştığında bir Pro denemesi başlatmaları istenir. Pro lisansı olmayan kullanıcıların Görüntüleyici rolünü kullanmalarını istiyorsanız bireysel veya bir kullanıcı grubunun parçası olarak başka çalışma alanı rollerine sahip olmadıklarından emin olun.

Raporları yeni çalışma alanı deneyiminde yayımlama işlemi mevcut lisans kurallarının daha sıkı uygulanmasını gerektirir. Pro lisansı olmadan Power BI Desktop'tan veya başka istemci araçlarından yayımlamayı denerseniz "Yalnızca Power BI Pro lisansı olan kullanıcılar bu çalışma alanında yayımlayabilir" hatasını görürsünüz.

> [!NOTE]
> Power BI US Government, Ücretsiz lisans olarak sağlanmaz. Lisanslama ayrıntıları için bkz. [ABD kamu müşterileri için Power BI](../admin/service-govus-overview.md).

### <a name="guest-users"></a>Konuk kullanıcılar

Varsayılan olarak [Azure AD B2B Konuk kullanıcıları](../admin/service-admin-azure-ad-b2b.md) çalışma alanlarına erişemez. Power BI yöneticileri [dış konuk kullanıcıların kuruluşta içeriği düzenlemesine ve yönetmesine izin verebilir](../admin/service-admin-azure-ad-b2b.md#guest-users-who-can-edit-and-manage-content). Etkinleştirilen Konuk kullanıcılar izinleri olan çalışma alanlarına erişebilir.

### <a name="administering-new-workspace-experience-workspaces"></a>Yeni çalışma alanı deneyimi çalışma alanlarını yönetme

Yeni çalışma alanı deneyimiyle oluşturulan çalışma alanlarının yönetimi Power BI yönetim portalından yapılır. Bir kuruluşta kimlerin çalışma alanı oluşturup uygulama dağıtacağına Power BI yöneticileri karar verir. "Yönetici portalı" makalesinde [kullanıcıların çalışma alanı oluşturma yeteneğini yönetme](../admin/service-admin-portal.md#create-the-new-workspaces) hakkında bilgi edinin. 

Yöneticiler, kuruluşlarındaki tüm çalışma alanlarının durumunu da görebilirler. Çalışma alanlarını yönetebilir, kurtarabilir ve hatta silebilirler. "Yönetici portalı" makalesinde [çalışma alanlarını yönetme](../admin/service-admin-portal.md#workspaces) hakkında bilgi edinin.

### <a name="auditing"></a>Denetim

Yeni çalışma alanı deneyiminde sunulan çalışma alanları için aşağıdaki etkinlikler Power BI tarafından denetlenir.

| Kolay ad | İşlem adı |
|---|---|
| Power BI klasörü oluşturuldu | CreateFolder |
| Power BI klasörü silindi | DeleteFolder |
| Power BI klasörü güncelleştirildi | UpdateFolder |
| Power BI klasörüne erişim güncelleştirildi| UpdateFolderAccess |

[Power BI denetimi](../admin/service-admin-auditing.md) ile ilgili daha fazla bilgi edinin.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

Dikkat edilmesi gereken sınırlamalar:

- Çalışma alanları en çok 1.000 veri kümesi veya veri kümesi başına 1.000 rapor içerebilir. 
- Power BI Pro lisansı olan biri, en çok 1.000 çalışma alanına üye olabilir.
- Excel için Power BI Publisher desteklenmez.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

**Yeni çalışma alanı deneyimi, mevcut içerik bağlantılarını etkiler mi?**

Hayır. Klasik çalışma alanlarındaki mevcut öğelerin bağlantıları yeni çalışma alanı deneyiminden etkilenmez. Yeni çalışma alanı deneyiminin genel kullanılabilirliği, oluşturduğunuz varsayılan çalışma alanını değiştirir ama mevcut çalışma alanlarını değiştirmez. 

**Mevcut çalışma alanları genel kullanılabilirlikle yeni çalışma alanı deneyimine yükseltilir mi?**

Hayır. Yeni çalışma alanı deneyimi genel kullanılabilirliği yalnızca varsayılan çalışma alanı türünü yeni çalışma alanı deneyimi olarak değiştirir. Microsoft 365 gruplarını temel alan mevcut klasik çalışma alanları olduğu gibi kalır.

**Microsoft 365 grupları için çalışma alanları otomatik olarak oluşturulmaya devam ediyor mu?**

Evet. Her iki türde çalışma alanlarını da yan yana desteklediğimiz için, çalışma alanları listesinde erişiminiz olan tüm Microsoft 365 gruplarını listelemeye devam ediyoruz.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI'da yeni çalışma alanları oluşturma](service-create-the-new-workspaces.md)
* [Klasik çalışma alanları oluşturma](service-create-workspaces.md)
* [Power BI'da uygulamaları yükleme ve kullanma](service-create-distribute-apps.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

