---
ms.openlocfilehash: 0592cb7ef076f8094aca565d955cc238b2181068
ms.sourcegitcommit: f6ac9e25760561f49d4257a6335ca0f54ad2d22e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69560970"
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

