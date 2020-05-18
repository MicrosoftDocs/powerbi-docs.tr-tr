---
title: Yeni çalışma alanlarında çalışmayı düzenleme
description: Kuruluşunuza ana ölçümler sunmayı amaçlayan yeni çalışma alanlarını, pano ve rapor koleksiyonlarını öğrenin.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/07/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: c74e9c3119c9c9a8057672d68e6499d93b46e3f8
ms.sourcegitcommit: 9dd6dc8c06091ea02dee5e9ddc45a2922877b1f2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82991388"
---
# <a name="organize-work-in-the-new-workspaces-in-power-bi"></a>Yeni çalışma alanlarında çalışmayı düzenleme

*Çalışma alanları*, çalışma arkadaşlarınızla işbirliği yaparak pano, rapor, veri kümesi ve sayfalandırılmış rapor koleksiyonları oluşturabildiğiniz yerlerdir. Yeni çalışma alanı deneyimi içeriğe erişimi daha iyi yönetmenize yardımcı olur. Bu makalede yeni çalışma alanları açıklanır ve klasik çalışma alanlarından farkları ortaya konur.  Klasik çalışma alanları gibi bunları da uygulamaları oluşturmak ve dağıtmak için kullanırsınız. Yeni bir çalışma alanı oluşturmaya hazır mısınız? Bkz. [Yeni çalışma alanı oluşturma deneyimi](service-create-the-new-workspaces.md).

Yeni, yükseltilmiş çalışma alanları ve mevcut klasik çalışma alanları birlikte kullanılabilir. Yeni çalışma alanı deneyimi varsayılan çalışma alanı türüdür. Yine de ihtiyaç duyarsanız Office 365 Gruplarını temel alarak [klasik çalışma alanlarını](service-create-workspaces.md) oluşturabilir ve kullanabilirsiniz. Klasik çalışma alanınızı geçirmeye hazır mısınız? Ayrıntılar için bkz. [Power BI'da klasik çalışma alanlarını yeni çalışma alanlarına yükseltme](designer/service-upgrade-workspaces.md).

Yeni çalışma alanlarıyla şunları yapabilirsiniz:

- Çalışma alanı rollerini kullanıcı gruplarına atayabilirsiniz: güvenlik grupları, dağıtım listeleri, Office 365 grupları ve bireyler.
- Temel alınan, ilişkili bir Office 365 grubu oluşturmadan Power BI'da bir çalışma alanı oluşturun. Çalışma alanı yönetiminin tamamı Office 365'te değil Power BI'dadır.
- İsterseniz içeriklere kullanıcı erişimini Office 365 gruplarıyla yönetmeye devam edebilirsiniz. Bunun için tek yapmanız gereken çalışma alanı erişim listesine bir Office 365 grubu eklemektir.
- Çalışma alanında daha esnek bir izin yönetimi için daha ayrıntılı çalışma alanı rolleri kullanabilirsiniz.

Power BI, üyesi olduğunuz tüm Office 365 Gruplarını listelemeye devam eder. Bu da mevcut iş akışlarının sürdürülebilmesini sağlar.

## <a name="new-and-classic-workspace-differences"></a>Yeni ve klasik çalışma alanları arasındaki farklar

Yeni çalışma alanlarıyla bazı özellikleri yeniden tasarladık. Temel farklar aşağıda belirtilmiştir.

* Bu çalışma alanlarının oluşturulması klasik çalışma alanlarında olduğu gibi Office 365 gruplarının oluşturulmasına neden olmaz. Öte yandan şimdi kullanıcılara bir rol atayarak çalışma alanınıza erişme vermek için Office 365 grubunu kullanabilirsiniz. 
* Klasik çalışma alanlarında, üyeler ve yöneticiler listesine sadece kişileri ekleyebilirsiniz. Yeni çalışma alanlarında, kullanıcı yönetimini kolaylaştırmak için bu listelere birden çok Active Directory güvenlik grubu, dağıtım listesi veya Office 365 grubu ekleyebilirsiniz. 
- Klasik çalışma alandan bir kurumsal içerik paketi oluşturabilirsiniz. Yeni çalışma alanlarından oluşturamazsınız.
- Klasik çalışma alandan bir kurumsal içerik paketini kullanabilirsiniz. Yeni çalışma alanlarından kullanamazsınız.

### <a name="workspace-features-that-work-differently"></a>Farklı çalışan çalışma alanı özellikleri

Yeni çalışma alanlarındaki bazı özellikler geçerli çalışma alanlarından farklı çalışır. Bu farklar, müşterilerden gelen geri bildirimlere göre özellikle korunmuştur. Çalışma alanlarıyla işbirliği yapmak için daha esnek bir yaklaşım sağlar.

- **Lisanslama zorunluluğu**: Raporları yeni çalışma alanı deneyiminde yayımlama işlemi mevcut lisans kurallarını zorunlu kılar. Çalışma alanlarında işbirliği yapan veya içeriği Power BI hizmetindeki diğer kullanıcılarla paylaşan kullanıcıların Power BI Pro lisansına sahip olması gerekir. Pro lisansı olmayan kullanıcılar "Yalnızca Power BI Pro lisansı olan kullanıcılar bu çalışma alanında yayımlayabilir" hatasını görür.
- **Yeniden paylaşım yapabilen ve yapamayan üyeler**: Bu ayarın yerini Katkıda bulunan rolü almıştır.
- **Salt okunur çalışma alanları**: Kullanıcılara bir çalışma alanında salt okuma yetkisi vermek yerine onları Görüntüleyici rolüne atayabilirsiniz. Bu da çalışma alanında benzer salt okuma erişimi sağlar.
- **Pro lisansı olmayan kullanıcılar**, yalnızca Görüntüleyici rolüne sahip olsalar dahi Power BI Premium kapasitesinde bulunan çalışma alanına erişebilir.
- **Kullanıcıların verileri dışarı aktarmasına izin verme**: Görüntüleyici rolüne sahip olan kullanıcılar, çalışma alanındaki veri kümelerinde Oluşturma iznine sahip olmaları durumunda verileri dışarı aktarabilir. [Veri kümeleri için oluşturma izni](service-datasets-build-permissions.md) hakkında daha fazla bilgi edinin.
- **Çalışma alanından ayrıl** düğmesi yok.

### <a name="workspace-contact-list"></a>Çalışma alanı kişi listesi

Yeni **Kişi listesi** özelliği çalışma alanında oluşan sorunlar hakkında hangi kullanıcıların bildirim alacağını belirtmenize olanak tanır. Varsayılan olarak çalışma alanı yöneticisi olarak belirtilen tüm kullanıcı veya gruplar bildirim alır ama listeyi özelleştirebilirsiniz. Kullanıcıların çalışma alanıyla ilgili yardım alabilmesi için kişi listesinde yer alan kullanıcılar ve gruplar kullanıcı arabiriminde gösterilir. 

[Çalışma alanı kişi listesini ayarlama](service-create-the-new-workspaces.md#workspace-contact-list) hakkında daha fazla bilgi edinin.

### <a name="workspace-onedrive"></a>OneDrive Çalışma Alanı

OneDrive Çalışma Alanı özelliği, SharePoint Belge Kitaplığı dosya depolama alanının çalışma alanı kullanıcıları tarafından kullanılabildiği bir Office 365 Grubu yapılandırmanızı sağlar. Grubu Power BI dışında oluşturmanız gerekir.

Power BI, Office 365 Grubu üyeliğiyle çalışma alanı erişimi olacak şekilde yapılandırılmış kullanıcı veya grupların izinlerini eşitlemez. En iyi yöntem çalışma alanı erişimini yönetmek için bu ayarda dosya depolama alanını yapılandırdığınız aynı Office 365 Grubunu kullanmaktır. 

[OneDrive Çalışma Alanı'nı ayarlama ve bu çalışma alanına erişme](service-create-the-new-workspaces.md#workspace-onedrive) hakkında bilgi edinin.  

## <a name="roles-in-the-new-workspaces"></a>Yeni çalışma alanlarındaki roller

Yeni çalışma alanına erişim vermek için, kullanıcı gruplarını veya kişileri çalışma alanı rollerinden birine atayın: yöneticiler, üyeler, katkıda bulunanlar veya görüntüleyiciler. Kullanıcı grubundaki herkes tanımladığınız rolü alır. Bir kişi birkaç kullanıcı grubunda yer alıyorsa, atandıkları rol tarafından sağlanan en yüksek izin düzeyine sahip olur.

Roller çalışma alanında kimlerin neler yapabileceğini yönetmenizi sağlar ve bu sayede ekipler işbirliği yapabilir. Yeni çalışma alanları kişilere ve kullanıcı gruplarına (güvenlik grupları, Office 365 grupları ve dağıtım listeleri) roller atamanıza olanak tanır. 

Bir kullanıcı grubuna roller atadığınızda, gruptaki kişiler içeriğe erişim sahibi olur. İç içe kullanıcı gruplarınız varsa, kapsam içinde yer alan tüm kullanıcıların izni olur.

[!INCLUDE [power-bi-workspace-roles-table](includes/power-bi-workspace-roles-table.md)]

> [!NOTE]
> Çalışma alanındaki içeriğe göz atan kullanıcılarda satır düzeyi güvenliği (RLS) zorunlu tutmak için Görüntüleyici rolünü kullanın. Çalışma alanına erişim vermeden RLS'yi zorunlu tutmak için söz konusu kullanıcılara bir Power BI uygulaması yayımlayın veya içeriği dağıtmak için paylaşım kullanın.

## <a name="licensing"></a>Lisanslama
Paylaşılan bir kapasitedeki çalışma alanına eklediğiniz herkesin Power BI Pro lisansına ihtiyacı vardır. Bu kullanıcılar çalışma alanında hep birlikte, daha geniş bir kitleye, hatta tüm kuruluşunuza dağıtmayı planladığınız panolar ve raporlar üzerinde işbirliği yapabilir. 

Kuruluşunuzun içindeki diğer kişilere içerik dağıtmak istiyorsanız, söz konusu kullanıcılara Power BI Pro lisansları atayabilir veya çalışma alanını Power BI Premium kapasitesine getirebilirsiniz.

Çalışma alanı Power BI Premium kapasitesinde olduğunda, Görüntüleyici rolüne sahip kullanıcılar Power BI Pro lisansları olmasa bile çalışma alanına erişebilir. Öte yandan bu kullanıcıları Yönetici, Üye veya Katkıda Bulunan gibi daha yüksek bir role atarsanız, kullanıcılar çalışma alanına erişmeye çalıştığında bir Pro Denemesi başlatmaları istenir. Pro lisans sahip olmayan kullanıcıların Görüntüleyici rolünü kullanabilmeleri için bireysel veya grup aracılığıyla başka çalışma alanı rollerine sahip olmadıklarından emin olun.

> [!NOTE]
> Raporları yeni çalışma alanı deneyiminde yayımlama işlemi mevcut lisans kurallarının daha sıkı uygulanmasını gerektirir. Pro lisansı olmadan Power BI Desktop'tan veya başka istemci araçlarından yayımlamayı denerseniz "Yalnızca Power BI Pro lisansı olan kullanıcılar bu çalışma alanında yayımlayabilir" hatasını görürsünüz.

## <a name="administering-new-workspace-experience-workspaces"></a>Yeni çalışma alanı deneyimi çalışma alanlarını yönetme

Yeni çalışma alanı deneyimiyle oluşturulan çalışma alanlarının yönetimi artık Power BI yönetim portalından yapılır. Bir kuruluşta kimlerin çalışma alanı oluşturup uygulama dağıtacağına Power BI yöneticileri karar verir. Yöneticiler, kuruluşlarındaki tüm çalışma alanlarının durumunu görebilir. Ayrıca çalışma alanlarını yönetebilir ve kurtarabilirler. [Yeni çalışma alanı oluşturma](service-admin-portal.md#create-the-new-workspaces) hakkında daha fazla bilgi için Yönetim portalı makalesini inceleyin.

## <a name="guest-users"></a>Konuk kullanıcılar

Varsayılan olarak [Azure AD B2B Konuk kullanıcıları](service-admin-azure-ad-b2b.md) çalışma alanlarına erişemez. Power BI yöneticileri [dış konuk kullanıcıların kuruluşta içeriği düzenlemesine ve yönetmesine izin verebilir](service-admin-azure-ad-b2b.md#guest-users-who-can-edit-and-manage-content). Etkinleştirilen Konuk kullanıcılar izinleri olan çalışma alanlarına erişebilir.

## <a name="auditing"></a>Denetim

Yeni çalışma alanı deneyimi çalışma alanları için aşağıdaki etkinlikler Power BI tarafından denetlenir.

| Kolay ad | İşlem adı |
|---|---|
| Power BI klasörü oluşturuldu | CreateFolder |
| Power BI klasörü silindi | DeleteFolder |
| Power BI klasörü güncelleştirildi | UpdateFolder |
| Power BI klasörüne erişim güncelleştirildi| UpdateFolderAccess |

[Power BI denetimi](service-admin-auditing.md) ile ilgili daha fazla bilgi edinin.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

Dikkat edilmesi gereken sınırlamalar:

- Çalışma alanları en çok 1.000 veri kümesi veya veri kümesi başına 1.000 rapor içerebilir. 
- Power BI Pro lisansı olan biri, en çok 1.000 çalışma alanına üye olabilir.
- Excel için Power BI Publisher desteklenmez.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

**Yeni çalışma alanı deneyimi mevcut içerik bağlantılarını etkiler mi?**

Hayır. Klasik çalışma alanlarındaki mevcut öğelerin bağlantıları yeni çalışma alanı deneyiminden etkilenmez. Yeni çalışma alanı deneyiminin genel kullanılabilirliği, oluşturduğunuz varsayılan çalışma alanını değiştirir ama mevcut çalışma alanlarını değiştirmez. 

**Genel kullanılabilirlikle birlikte mevcut çalışma alanları yükseltilir mi?**

Hayır. Yeni çalışma alanı deneyimi genel kullanılabilirliği yalnızca varsayılan çalışma alanı türünü yeni çalışma alanı deneyimi olarak değiştirir. Office 365 Gruplarını temel alan mevcut klasik çalışma alanları olduğu gibi kalır.

**Office 365 Grupları için yine otomatik olarak çalışma alanları oluşturuluyor mu?**

Evet. Her iki türde çalışma alanlarını da yan yana desteklediğimiz için, çalışma alanları listesinde erişiminiz olan tüm Office 365 Gruplarını listelemeye devam ediyoruz.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI'da yeni çalışma alanları oluşturma](service-create-the-new-workspaces.md)
* [Klasik çalışma alanları oluşturma](service-create-workspaces.md)
* [Power BI'da uygulamaları yükleme ve kullanma](service-create-distribute-apps.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
