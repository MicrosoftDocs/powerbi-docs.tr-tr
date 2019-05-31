---
title: Yeni çalışma - Power BI düzenleme
description: Panoları ve raporları kuruluşunuzun ilişkin ana ölçümleri sunmak üzere tasarlanmış koleksiyonlarıdır yeni çalışma hakkında bilgi edinin.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 9f5dfaa5a23ae46fef131a52355531b5fbde3051
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100679"
---
# <a name="organize-work-in-the-new-workspaces-in-power-bi"></a>Power bı'da yeni çalışma alanlarında iş düzenleme

 *Çalışma alanları* panolar, raporlar ve sayfalandırılmış raporlar koleksiyonlarını oluşturmak için iş arkadaşlarınızla işbirliği yerlerdir. Yeni çalışma alanı deneyimi daha iyi içeriğe erişimi yönetmenize yardımcı olur. Bu makalede, yeni çalışma alanları ve klasik çalışma alanlarından farkı açıklar.  Olarak Klasik çalışma alanlarıyla, yine de bunları oluşturmak ve uygulamaları dağıtmak için kullanın. Konusunu okuyun [yeni bir çalışma deneyimi oluşturmak](service-create-the-new-workspaces.md).

Yeni çalışma alanı deneyimi, genel kullanılabilirlik (GA) ulaştı ve varsayılan çalışma alanına sunulmuştur. Oluşturma ve kullanma yine de devam edebilirsiniz [Klasik çalışma alanları](service-create-workspaces.md) Office 365 gruplarını temel alan. 

> [!NOTE]
> Bir çalışma alanındaki içeriği gözatma Power BI Pro kullanıcıları için satır düzeyi güvenlik (RLS) zorlamak için kullanmaya devam [Klasik çalışma alanları](service-create-workspaces.md). Seçin **üyeleri yalnızca Power BI içeriğini görüntüleme** seçeneği. Alternatif olarak, bu kullanıcılara Power BI uygulama yayımlama veya paylaşım içeriği dağıtmak için kullanın. Gelecek Görüntüleyicisi rolü Bu senaryoda gelecekte yeni çalışma alanı deneyimi çalışma alanlarını etkinleştirir.

Yeni çalışma alanları ile şunları yapabilirsiniz:

- Çalışma alanı rollerini kullanıcı gruplarına atayabilirsiniz: güvenlik grupları, dağıtım listeleri, Office 365 grupları ve bireyler.
- Office 365 grubu oluşturmadan Power BI'da bir çalışma alanı oluşturabilirsiniz.
- Çalışma alanında daha esnek bir izin yönetimi için daha ayrıntılı çalışma alanı rolleri kullanabilirsiniz.

Yeni çalışma alanlarından birini oluşturduğunuzda, temel, ilişkili bir Office 365 grubu oluşturmuş olmazsınız. Çalışma alanı yönetiminin tamamı Office 365'te değil Power BI'dadır. Yeni çalışma alanı deneyimi artık Office 365 grupları aracılığıyla içeriğe kullanıcı erişimi yönetmeye devam etmek için bir Office 365 Grup çalışma alanına erişim listesinde ekleyebilirsiniz.

## <a name="administering-new-workspace-experience-workspaces"></a>Yeni çalışma alanı deneyimi çalışma alanlarını yönetme
Power BI yöneticileri Power BI'da, karar artık yeni çalışma alanı deneyimi çalışma alanları için yönetim çalışma alanı kullanan bir kuruluştaki oluşturabilirsiniz olur. Bunlar ayrıca yönetebilir ve çalışma alanı kurtarın. Bunu yapmak için Power BI Yönetici portalı veya PowerShell cmdlet'lerini kullanmanız gerekir. Office 365 gruplarını temel alan Klasik çalışma alanları için yönetim, Office 365 Yönetim Portalı ve Azure Active Directory ortaya devam eder.

İçinde **çalışma alanı ayarlarını** Yönetim Portalı'nda, yeni çalışma alanı deneyimi çalışma alanları oluşturmak için kuruluştaki herkesin veya hiç kimse izin ayarı oluşturma çalışma alanları (yeni çalışma alanı deneyimi) yöneticiler kullanabilir. Ayrıca çalışma alanı oluşturmayı belirli güvenlik gruplarının üyeleriyle de sınırlayabilir.

> [!NOTE]
> Power BI'da yeni çalışma alanı oluşturmak için Office 365 grupları oluşturan kullanıcılar yalnızca izin vermek için varsayılanları ayarlama oluşturma çalışma alanları (yeni çalışma alanı deneyimi). Uygun kullanıcılar yeni çalışma alanı deneyimi çalışma alanları oluşturabilir emin olmak için Power BI Yönetici portalında bir değer ayarlamayı unutmayın.

![Yönetici portalındaki Çalışma alanı ayarları](media/service-new-workspaces/power-bi-workspace-admin-settings.png)

[Çalışma alanlarının listesi kullanılabilir](service-admin-portal.md#workspaces) Power BI Yönetici portalı'nda. 

![Çalışma alanları listesi](media/service-admin-portal/workspaces-list.png)

## <a name="new-workspaces-side-by-side-with-classic-workspaces"></a>Klasik çalışma alanları yeni çalışma alanları yan yana

Yeni ve yükseltilmiş çalışma alanları ve klasik mevcut çalışma alanlarınızın yan yana bir arada ve ya da oluşturabilirsiniz. Yeni çalışma alanı deneyimi varsayılan çalışma alanı türüdür. Power BI, kullanıcının mevcut iş akışları değiştirmekten kaçınmak için Power bı'da bir üye olduğu tüm Office 365 grupları listesinde devam eder. Yeni bir çalışma alanı oluşturmayı öğrenmek için okumaya devam [yeni çalışma alanları oluşturma](service-create-the-new-workspaces.md). Klasik bir çalışma alanı oluşturmayı öğrenmek için okumaya devam [Klasik çalışma alanları oluşturma](service-create-workspaces.md).

## <a name="roles-in-the-new-workspaces"></a>Yeni çalışma alanlarındaki roller

Yeni bir çalışma alanı erişimi vermek için kullanıcı grupları veya kişiler çalışma rollerden birine ekleyin: üye, katkıda bulunan veya yönetici. Kullanıcı grubundaki herkes tanımladığınız rolü alır. Bireysel çeşitli kullanıcı gruplarının ise, bunlar iznine atanmış olan rolleri tarafından sağlanan en yüksek düzeyde alın.

Roller çalışma alanında kimlerin neler yapabileceğini yönetmenizi sağlar ve bu sayede ekipler işbirliği yapabilir. Yeni çalışma alanları kişilere ve kullanıcı gruplarına (güvenlik grupları, Office 365 grupları ve dağıtım listeleri) roller atamanıza olanak tanır. 

Bir kullanıcı grubuna roller atadığınızda, gruptaki kişiler içeriğe erişim sahibi olur. İç içe kullanıcı gruplarınız varsa, kapsam içinde yer alan tüm kullanıcıların izni olur. Farklı rollere sahip birden çok kullanıcı grubunda yer alan bir kullanıcı, kendisine verilen en yüksek izin düzeyine sahip olur. 

Yeni çalışma alanları üç rol sunar: yöneticiler, üyeler ve katkıda bulunanlar.

|Özellik   | Yönetici  | Üye  | Katılımcı  | 
|---|---|---|---|
| Çalışma alanını güncelleştirebilir ve silebilir.  | X  |   |   |
| Diğer yöneticiler de dahil olmak üzere kişileri ekleyebilir/kaldırabilir.  | X  |   |   |
| Üyeleri ve düşük izinlere sahip diğer kişileri ekleyebilir.  |  X | X  |   |
| Uygulama yayımlayabilir ve güncelleştirebilir. |  X | X  |   |
| Öğe veya uygulama paylaşabilir. |  X | X  |   |
| Diğer kişilerin öğeleri yeniden paylaşmasına izin verebilir. |  X | X  |   |
| Çalışma alanında içerik oluşturabilir, düzenleyebilir ve silebilir.  |  X | X  | X  |
| Çalışma alanında rapor yayımlayabilir, içeriği silebilir. |  X | X  | X  |
 
 
## <a name="licensing"></a>Lisanslama
Bir çalışma alanına eklediğiniz herkesin Power BI Pro lisansına ihtiyacı vardır. Bu kullanıcılar çalışma alanında hep birlikte, daha geniş bir kitleye, hatta tüm kuruluşunuza dağıtmayı planladığınız panolar ve raporlar üzerinde işbirliği yapabilir. Kuruluşunuzun içindeki diğer kişilere içerik dağıtmak istiyorsanız, söz konusu kullanıcılara Power BI Pro lisansları atayabilir veya çalışma alanını Power BI Premium kapasitesine getirebilirsiniz.

> [!NOTE]
> Yeni çalışma deneyimi için raporlar yayımlayan katı zorlama varolan kuralları lisanslama sahiptir. Kullanıcılar, Power BI Desktop veya diğer istemcilerin Araçlar Pro sürüm lisansı olmadan yayımlamayı deneyin "yalnızca Power BI Pro lisanslarına sahip kullanıcılar bu çalışma alanında yayımlayabilirsiniz." hatası bakın.

## <a name="how-are-the-new-workspaces-different-from-current-workspaces"></a>Yeni çalışma alanlarıyla geçerli çalışma alanları arasında ne fark vardır?

Yeni çalışma alanlarıyla, bazı özellikleri yeniden tasarlıyoruz. Kalıcı olmasını beklediğiniz değişiklikleri aşağıda verilmiştir. 

* Bu çalışma alanları oluşturma Klasik çalışma alanlarının yaptığı gibi Office 365 grupları oluşturmaz. Ancak, kullanıcılar, bir rol atayarak çalışma alanınıza erişimi vermek için artık bir Office 365 grubu kullanabilirsiniz. 
* Klasik çalışma alanlarında, üyeleri ve yöneticiler listesine sadece bireyleri ekleyebilirsiniz. Yeni çalışma alanlarında, kullanıcı yönetimini kolaylaştırmak için bu listelere birden çok AD güvenlik grubu, dağıtım listesi veya Office 365 grubu ekleyebilirsiniz. 
- Klasik bir çalışma alanından bir kurumsal içerik paketi oluşturabilirsiniz. Yeni çalışma alanlarından oluşturamazsınız.
- Klasik bir çalışma alanından bir kurumsal içerik paketi kullanabilir. Yeni çalışma alanlarından kullanamazsınız.

## <a name="workspace-contact-list"></a>Çalışma alanı kişi listesi
Yeni **kişi listesi** özellik hangi kullanıcıların çalışma alanında oluşan sorunlarla ilgili bildirim almak belirtmenize olanak tanır. Varsayılan olarak, herhangi bir kullanıcı veya Grup yönetici bildirim, ancak liste özelleştirebileceğiniz bir çalışma alanı olarak belirtilmiş. Kişi listesi listelenen kullanıcılar veya gruplar, kullanıcılar çalışma alanına ilgili yardım alın yardımcı olmak için kullanıcı arabiriminde (UI) gösterilir. 

Daha fazla bilgi edinin [çalışma kişi listesi ayarını](service-create-the-new-workspaces.md#workspace-contact-list).

## <a name="workspace-onedrive"></a>Çalışma alanı OneDrive
Çalışma alanı OneDrive bu özellik, SharePoint belge kitaplığına dosya depolama çalışma alanı kullanıcılara bir Office 365 grubu yapılandırmanızı sağlar. Grubun Power BI dışında oluşturulması gerekir. 

Power BI, kullanıcılar veya gruplar Office 365 grup üyeliği ile çalışma alanı erişimi olacak şekilde yapılandırılmış izinlerini eşitleme değil. Çalışma alanı erişimi aynı Office 365 dosya depolama, bu ayarı yapılandırmanız grubu aracılığıyla yönetmek için en iyi yöntem olacaktır. 

Konusunu okuyun [ayarlayın ve çalışma alanı OneDrive erişim](service-create-the-new-workspaces.md#workspace-onedrive).  
   
## <a name="auditing"></a>Denetleme
Aşağıdaki aktiviteleri yeni çalışma alanı deneyimi çalışma alanları için Power BI tarafından denetlenir.

| Kolay ad |   İşlem adı |
|---|---|
| Power BI klasörü oluşturuldu | CreateFolder |
| Power BI klasörü silindi | DeleteFolder |
| Power BI klasörü güncelleştirildi | UpdateFolder |
| Power BI klasörüne erişim güncelleştirildi| UpdateFolderAccess |

Daha fazla bilgi edinin [Power BI denetim](service-admin-auditing.md#activities-audited-by-power-bi).

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

Dikkat edilmesi gereken sınırlamalar:

- Çalışma alanları en çok 1.000 veri kümesi veya veri kümesi başına 1.000 rapor içerebilir. 
- Power BI Pro lisansı olan bir kişi, en fazla 1.000 bir çalışma alanı üyesi olabilir.
- Excel için Power BI publisher desteklenmez.

## <a name="workspace-features-that-work-differently"></a>Farklı çalışan çalışma alanı özellikleri

Yeni çalışma alanlarındaki bazı özellikler geçerli çalışma alanlarından farklı çalışır. Biz müşterilerden aldınız ve daha esnek bir yaklaşım çalışma alanlarıyla işbirliği için geri bildirim göre bilerek, bu farklar şunlardır:

- Lisans zorlama: Yeni çalışma deneyimi için raporlar yayımlayan, çalışma alanlarında işbirliği veya Power BI hizmetindeki içeriği diğer kullanıcılarla paylaşma kullanıcılar için Power BI Pro lisansı var olan lisans kuralları zorlar. Pro lisansı olmayan kullanıcılar "yalnızca Powre BI Pro lisanslarına sahip kullanıcılar bu çalışma alanında yayımlayabilirsiniz." hatası bakın.
- Üyeler yeniden paylaşabilir veya paylaşamaz: bunun yerini Katkıda Bulunan rolü almıştır
- Salt okunur çalışma alanları: Kullanıcılara bir çalışma alanı için salt okuma erişim vermek yerine çalışma alanındaki içeriğe benzer salt okuma erişim sunan ve hazırlanmakta olan Görüntüleyici rolünü atarsınız.
- **Çalışma alanından ayrıl** düğmesi yok.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

**Mevcut içeriklere yeni çalışma alanı tarafından etkilenen GA deneyimi olan**

Hayır. Klasik çalışma alanlarındaki mevcut öğelerine bağlantılar yeni çalışma alanı deneyimi tarafından etkilenmez. Yeni çalışma alanı deneyiminin genel kullanılabilirlik (GA) oluşturmak, ancak mevcut çalışma alanlarınızın değişmez varsayılan çalışma alanını değiştirir. 

**Çalışma alanları GA yeni çalışma deneyimiyle yükseltme var**

Hayır. Yeni çalışma alanı deneyimi GA, yalnızca varsayılan çalışma alanı türünü yeni çalışma alanı deneyimine değiştirir. Office 365 gruplarını temel alan varolan Klasik çalışma değişmeden kalır.

**Çalışma alanları, Office 365 grupları için yine de otomatik olarak oluşturulur**

Evet. Her iki türde çalışma alanları yan yana destekliyoruz olduğundan, kullanıcı çalışma alanları listesinde erişimi olan tüm Office 365 gruplarını listelemek devam ediyoruz.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da yeni çalışma alanları oluşturma](service-create-the-new-workspaces.md)
* [Klasik çalışma alanları oluşturma](service-create-workspaces.md)
* [Power BI'da uygulamaları yükleme ve kullanma](service-create-distribute-apps.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
