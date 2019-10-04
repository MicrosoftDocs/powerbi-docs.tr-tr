---
ms.openlocfilehash: cd0696b44e285119193059304c89cfa04c755771
ms.sourcegitcommit: bbd9b38f30a4ca5cb8072496c9cacb635b03aa88
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71409391"
---
## <a name="faq"></a>SSS
**Soru:** Power BI hizmetindeki bir veri kümesi için önceden roller ve kurallar oluşturduysam ne yapmam gerekir? Herhangi bir işlem yapmasam da bunlar çalışmaya devam eder mi?  
**Cevap:** Hayır. Görseller düzgün şekilde oluşturulmaz. Rolleri ve kuralları Power BI Desktop uygulamasında tekrar oluşturmanız ve Power BI hizmetinde yayımlamanız gerekir.

**Soru:** Bu rolleri Analysis Services veri kaynakları için oluşturabilir miyim?  
**Cevap:** Verileri Power BI Desktop'a aktardıysanız oluşturabilirsiniz. Canlı bağlantı kullanıyorsanız Power BI hizmetinden RLS yapılandırması gerçekleştiremezsiniz. Bu yapılandırma şirket içi Analysis Services modelinde tanımlanır.

**Soru:** Kullanıcılarımın erişebileceği sütunları veya ölçüleri sınırlamak için RLS kullanabilir miyim?  
**Cevap:** Hayır. Belirli bir veri satırına erişimi olan kullanıcılar, ilgili satırdaki tüm veri sütunlarını görebilir.

**Soru:** RLS, ayrıntılı verileri gizlerken görsellerde özetlenmiş verilere erişim vermemi sağlar mı?  
**Cevap:** Hayır. Belirli veri satırlarının güvenliğini sağlayabilirsiniz, ama kullanıcılar ayrıntıları veya özetlenmiş verileri her zaman görebilir.

**Soru:** Veri kaynağımda tanımlanmış güvenlik rolleri zaten var (örneğin, SQL Server rolleri veya SAP BW rolleri). Bunlar ile RLS arasındaki ilişki nedir?  
**Cevap:** Yanıt, verileri içeri aktarıp aktarmadığınıza veya DirectQuery kullanıp kullanmadığınıza bağlı olarak değişir. Power BI veri kümenize veri aktarıyorsanız, veri kaynağınızdaki güvenlik rolleri kullanılmaz. Bu durumda, Power BI’da bağlanan kullanıcılar için güvenlik kurallarını uygulamak için RLS tanımlamanız gerekir. DirectQuery kullanıyorsanız, veri kaynağınızdaki güvenlik rolleri kullanılır. Kullanıcı bir rapor açtığında Power BI temel alınan veri kaynağına bir sorgu gönderir ve bu sorgu, kullanıcının kimlik bilgilerine göre bu verilere güvenlik kuralları uygular.
