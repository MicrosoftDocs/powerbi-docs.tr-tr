---
title: Power BI’da veri koruma
description: Veri korumanın Power BI’da nasıl çalıştığını öğrenin
author: paulinbar
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/21/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: fa969f8f738cf09e9e01e284de8f60e2fd8ce9ab
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315684"
---
# <a name="data-protection-in-power-bi"></a>Power BI’da veri koruma

Modern kuruluşlar, hassas verileri işleme ve koruma hakkında katı iş düzenlemeleri ve gereksinimleri uygular. Power BI, Power BI’daki bu veriler üzerinde daha fazla denetim ve görünürlük sağlamak için Microsoft Information Protection ve Microsoft Cloud App Security ile tümleşiktir. Şunları yapmanızı sağlar:
* Office 365’te dosyaları sınıflandırıp korumak için kullanılan taksonomiden yararlanarak, Power BI hizmetindeki içeriği (panolar, raporlar, veri kümeleri ve veri akışları) sınıflandırıp etiketlemek için Microsoft Information Protection’ın [duyarlılık etiketlerini](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels?view=o365-worldwide) kullanın.
* Excel, PowerPoint veya PDF dosyalarına dışarı aktarıldıklarında verilere Microsoft Information Protection duyarlılık etiketlerini ve korumasını uygulayın.
* Power BI’daki etkinlikleri izlemek, güvenlik sorunlarını araştırmak ve Microsoft Cloud App Security Koşullu Erişim Uygulama Denetimi ile Power BI’daki içeriği korumak için Microsoft Cloud App Security kullanın.

**Önemli notlar**
* Duyarlılık etiketlemesi Power BI’daki içeriğe erişimi **etkilemez**. Power BI’daki içeriğe erişim yalnızca Power BI izinleri tarafından yönetilir. Etiketler görünür olduğundan, ilişkili şifreleme ayarlarının ([Microsoft 365 güvenlik merkezinde](https://security.microsoft.com/) veya [Microsoft 365 uyumluluk merkezinde](https://compliance.microsoft.com/) yapılandırılan) hiçbiri uygulanmaz. Yalnızca Excel, PowerPoint ve PDF dosyalarına dışarı aktarılan verilere uygulanırlar.
* Duyarlılık etiketleri ve dosya şifreleme Excel, PowerPoint ve PDF’ye dışarı aktarmalar dışındaki hiçbir dışarı aktarma yoluna **uygulanmaz**. Power BI kiracı yöneticisi, duyarlılık etiketlerinin ve bu etiketlerle ilişkili dosya şifreleme ayarlarının uygulanmasını desteklemeyen dışarı aktarma yollarının bir kısmını veya tamamını devre dışı bırakabilir.

## <a name="sensitivity-labels-in-power-bi"></a>Power BI'da duyarlılık etiketleri

Duyarlılık etiketleri [Microsoft 365 güvenlik merkezi](https://security.microsoft.com/) ya da [Microsoft 365 uyumluluk merkezi](https://compliance.microsoft.com/) içinde oluşturulur ve yönetilir.

Bu merkezlerin birinde duyarlılık etiketlerine erişmek için **Sınıflandırma > Duyarlılık etiketleri**’ne gidin. Bu duyarlılık etiketleri Azure Information Protection, Office uygulamaları ve Office 365 hizmetleri gibi birden çok Microsoft hizmeti tarafından kullanılabilir.

> [!Important]
> Kuruluşunuzda Azure Information Protection duyarlılık etiketleri kullanılıyorsa bunları Power BI’da kullanılabilmeleri için önceden listelenen hizmetlerden birine [geçirmeniz](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) gerekir.

> [!NOTE]
> Duyarlılık etiketleri yalnızca genel bulutlardaki kiracılarda desteklenir, bağımsız bulutlar gibi bulutlar içindeki kiracılar için desteklenmez.

## <a name="how-sensitivity-labels-work-in-power-bi"></a>Duyarlılık etiketlerinin Power BI’daki işleyişi

Bir Power BI panosuna, raporuna, veri kümesine veya veri akışına duyarlılık etiketi uyguladığınızda, kaynağa aşağıdaki avantajlara sahip olan bir etiket uygulamaya benzer:
* **Özelleştirilebilir** - Kuruluşunuzda Kişisel, Ortak, Genel, Gizli ve Çok Gizli gibi farklı düzeylerde hassas içerikler için kategoriler oluşturabilirsiniz.
* **Düz metin** - Etiket düz metin biçiminde olduğundan, kullanıcıların duyarlılık etiketi yönergelerine uygun olarak içeriğin nasıl işleneceğini anlaması kolaydır.
* **Kalıcı**: İçeriğe bir duyarlılık etiketi uygulandıktan sonra Excel, PowerPoint ve PDF dosyalarına dışarı aktarılan içeriğe eşlik eder ve ilkelerin uygulanıp zorunlu tutulmasına yönelik bir temel oluşturur.

Bu, duyarlılık etiketinin içeriği Excel, PowerPoint ve PDF dosyalarına dışarı aktarıldığında izlemesi ve ilkelerin uygulanıp zorunlu tutulması için bir temel oluşturması anlamına gelir.

Power BI kiracı yöneticileri [Excel’e dışarı aktarma](service-admin-portal.md#export-to-excel) ile [PowerPoint ve PDF’ye dışarı aktarmayı](service-admin-portal.md#export-reports-as-powerpoint-presentations-or-pdf-documents) [Power BI yönetici portalında](service-admin-portal.md) denetleyebilir.

## <a name="sensitivity-label-example"></a>Duyarlılık etiketi örneği

Power BI’da duyarlılık etiketinin işleyişi hakkında kısa bir örnek aşağıda verilmiştir.
1. Power BI hizmetinde bir rapora **Çok Gizli** duyarlılık etiketi uygulanır.

   ![Liste görünümünde duyarlılık etiketleri](media/service-security-data-protection-overview/sensitivity-labels-overview-01.png)
   
1. Veriler bu rapordan bir Excel dosyasına aktarıldığında, duyarlılık etiketi ve koruması dışarıya aktarılmış Excel dosyasına uygulanır.

   ![Duyarlılık etiketi içeriği takip eder](media/service-security-data-protection-overview/sensitivity-labels-overview-02.png)

Microsoft Office uygulamalarında duyarlılık etiketi, yukarıdaki görüntüdekine benzer şekilde e-posta veya belge üzerinde etiket olarak görünür. Ayrıca, Power BI genelinde kullanılan ve paylaşılan içerikle kalıcı hale gelip dolaşan içeriğe bir sınıflandırma (etiket gibi) atayabilirsiniz. Bu sınıflandırmayı kullanarak kullanım raporları oluşturabilir ve hassas içeriğiniz için etkinlik verilerini görebilirsiniz. Bu bilgilere göre, koruma ayarlarını uygulamayı daha sonra dilediğiniz zaman seçebilirsiniz.

## <a name="requirements-for-using-sensitivity-labels-in-power-bi"></a>Power BI’da duyarlılık etiketlerini kullanma gereksinimleri

Power BI’da duyarlılık etiketlerinizin etkinleştirilip kullanılabilmesi için önce aşağıdaki önkoşulları karşılamanız gerekir:
* Duyarlılık etiketlerinin [Microsoft 365 güvenlik merkezi](https://security.microsoft.com/) ya da [Microsoft 365 uyumluluk merkezi](https://compliance.microsoft.com/) içinde oluşturulup yönetildiğinden emin olun.
* Power BI’da [duyarlılık etiketlerini etkinleştirme](service-security-enable-data-sensitivity-labels.md).
* Kullanıcıların [uygun lisanslara](#licensing) sahip olduğundan emin olma.
* Power BI ile Microsoft Cloud App Security kullanıyorsanız [uygun lisansa](service-security-using-microsoft-cloud-app-security-controls.md#cloud-app-security-licensing) sahip olduğunuzdan emin olma.

## <a name="protect-content-using-microsoft-cloud-app-security"></a>Microsoft Cloud App Security kullanarak içeriği koruma

Microsoft Cloud App Security kullanarak Power BI’daki içeriği istenmeyen sızıntılara veya ihlallere karşı koruyabilirsiniz. Microsoft Cloud App Security ayarlanıp yapılandırıldıktan sonra güvenlik yöneticileri kullanıcı erişimini ve etkinliğini izleyebilir, gerçek zamanlı risk analizi gerçekleştirebilir ve etikete özel denetimler belirleyebilir.

Örneğin, kuruluşlar kullanıcıların Power BI’daki hassas içerikleri yönetilmeyen cihazlara indirmesini önleyen bir ilke yapılandırmak üzere Microsoft Cloud App Security’yi kullanabilir. Bu tür bir yapılandırma, kullanıcıların üretkenliğini sürdürmesine ve Power BI’a her yerden bağlanmasına, diğer yandan kullanıcı eylemlerinin güvenliğinin aşılmasını önlemek için Microsoft Cloud App Security kullanmasına ve tüm bunları gerçek zamanlı olarak yapmasına olanak tanır.

**Gereksinimler**

Duyarlılık etiketlerinizin Microsoft Cloud App Security kullanabilmesi için aşağıdaki önkoşulların karşılanması gerekir:
* Cloud App Security ve Azure Information Protection, [kiracınız için etkinleştirilmelidir](https://docs.microsoft.com/cloud-app-security/azip-integration).
* Uygulama [Microsoft Cloud App Security’ye bağlanmalıdır](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

## <a name="licensing"></a>Lisanslama

* Power BI’da Microsoft Azure Information Protection duyarlılık etiketlerini uygulamak ve görüntülemek için bir Azure Information Protection Premium P1 veya Premium P2 lisansı gerekir. Microsoft Azure Information Protection tek başına ya da Microsoft lisanslama paketlerinden biri aracılığıyla satın alınabilir. Ayrıntılı bilgi için [Azure Information Protection fiyatlandırmasına](https://azure.microsoft.com/pricing/details/information-protection/) bakın.
* Office uygulamalarında etiketleri görüntülemek ve uygulamak için [lisanslama gereksinimleri](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels#subscription-and-licensing-requirements-for-sensitivity-labels) mevcuttur.
* Power BI içeriğine etiketler uygulamak için, kullanıcının yukarıda bahsedilen Azure Information Protection lisanslarından birine ek olarak Power BI Pro lisansına sahip olması gerekir.
* İstenmeyen sızıntı ve ihlallere karşı Power BI içeriğini korumak amacıyla kullanmak için [gerekli Microsoft Cloud App Security lisanslarına](https://docs.microsoft.com/power-bi/admin/service-security-using-microsoft-cloud-app-security-controls#microsoft-cloud-app-security-licensing) sahip olmanız gerekir.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Aşağıdaki listede, Power BI’daki duyarlılık etiketlerinin bazı sınırlamaları verilmiştir:

**Genel**
* Duyarlılık etiketleri yalnızca panolara, raporlara, veri kümelerine ve veri akışlarına uygulanabilir. Bunlar, şu anda [sayfalandırılmış raporlar](../paginated-reports/report-builder-power-bi.md) ve çalışma kitapları için kullanılamaz.
* Power BI varlıklarındaki duyarlılık etiketleri çalışma alanı listesi, veri kökeni, sık kullanılanlar, son kullanılanlar ve uygulama görünümlerinde görünür durumdadır. Etiketler şu anda “benimle paylaşılan” görünümünde görünür değildir. Ancak, görünür olmasa bile, Power BI varlığına uygulanmış bir etiketin Excel, PowerPoint ve PDF dosyalarına aktarılmış veriler üzerinde her zaman kalıcı olacağını unutmayın.
* Duyarlılık etiketleri yalnızca genel (ortak) buluttaki kiracılar için desteklenir. Duyarlılık etiketleri diğer bulutlardaki kiracılar için desteklenmez.
* Veri duyarlılık etiketleri şablon uygulamaları için desteklenmez. Şablon uygulama oluşturucu tarafından ayarlanan duyarlılık etiketleri, uygulama ayıklandığında ve yüklendiğinde kaldırılır ve yüklü bir şablon uygulamada uygulama tüketicisi tarafından yapıtlara eklenen duyarlılık etiketleri, uygulama güncelleştirildiğinde kaybolur (sıfırlanır).
* Power BI [İletme](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions), [kullanıcı tanımlı](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions) ve [HYOK](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) koruma türlerinin duyarlılık etiketlerini desteklemez. İletme ve kullanıcı tanımlı koruma türleri [Microsoft 365 güvenlik merkezinde](https://security.microsoft.com/) ve [Microsoft 365 uyumluluk merkezinde](https://compliance.microsoft.com/) tanımlanan etiketleri ifade eder.
* Kullanıcıların Power BI’da üst etiketler uygulamaları önerilmez. İçeriğe bir üst etiket uygulandıysa bu içerikten bir dosyaya (Excel, PowerPoint ve PDF) veri aktarma işlemi başarısız olur. Bkz. [Alt etiketler (gruplandırma etiketleri)](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels?view=o365-worldwide#sublabels-grouping-labels).

**Dışarı Aktarma**
* Etiket ve koruma denetimleri yalnızca veriler Excel, PowerPoint ve PDF dosyalarına aktarıldığında zorlanır. Veriler .csv veya .pbix dosyalarına, Excel’de Analiz Et’e veya başka bir dışarı aktarma yoluna aktarıldığında etiket ve koruma zorlanmaz.
* Dışarı aktarılan bir dosyaya duyarlılık etiketi ve koruma uygulandığında, dosyaya içerik işaretlemesi eklenmez. Ancak, etiket içerik işaretlemelerini uygulayacak şekilde yapılandırıldıysa dosya Office masaüstü uygulamalarında açıldığında içerik işaretlemeleri Azure Information Protection birleşik etiketleme istemcisi tarafından otomatik olarak uygulanır. Masaüstü uygulamaları, mobil uygulamalar ve web uygulamaları için yerleşik etiketleme kullandığınızda içerik işaretlemeleri otomatik olarak uygulanmaz. Diğer ayrıntılar için bkz. [Office uygulamaları içerik işaretlemesini ve şifrelemeyi ne zaman uygular?](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-office-apps?view=o365-worldwide#when-office-apps-apply-content-marking-and-encryption).
* Power BI’dan dosya aktaran kullanıcının, duyarlık etiketi ayarlarına uygun olarak bu dosyaya erişme ve dosyayı düzenleme izinleri vardır. Verileri dışarı aktaran kullanıcı, dosya üzerinde sahip izinleri almaz.
* Veriler bir dosyaya dışarı aktarıldığında etiket uygulanamıyorsa dışarı aktarma işlemi başarısız olur. Dışarı aktarma işleminin etiket uygulanamadığından başarısız olup olmadığını denetlemek için başlık çubuğunun ortasındaki rapor veya pano adına tıklayın ve açılan bilgi menüsünde “Duyarlılık etiketi yüklenemiyor” yazıp yazmadığına bakın. Bu, uygulanan etiket güvenlik yöneticisi tarafından yayımdan kaldırıldıysa veya silindiyse ya da geçici bir sistem sorununun sonucu olarak oluşur.


## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, Power BI'da veri korumasına genel bakış sunulmuştur. Aşağıdaki makalelerde Power BI’da veri koruma hakkında daha fazla bilgi verilmektedir. 

* [Power BI'da veri duyarlılığı etiketlerini etkinleştirme](service-security-enable-data-sensitivity-labels.md)
* [Power BI'da veri duyarlılığı etiketleri uygulama](../collaborate-share/service-security-apply-data-sensitivity-labels.md)
* [Power BI’da Microsoft Cloud App Security denetimlerini kullanma](service-security-using-microsoft-cloud-app-security-controls.md)
* [Veri koruma ölçümleri raporu](service-security-data-protection-metrics-report.md)