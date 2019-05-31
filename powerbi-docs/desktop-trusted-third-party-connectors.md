---
title: Power BI üçüncü taraf bağlayıcı güvenilir
description: Power bı'da imzalı üçüncü taraf bağlayıcı güven nasıl
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 30b7457c6149320c43f24b967a842382821b01b1
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607783"
---
# <a name="trusting-third-party-connectors"></a>Güvenen üçüncü taraf bağlayıcılar

## <a name="why-do-you-need-trusted-third-party-connectors"></a>Güvenilir bir üçüncü taraf bağlayıcılar neden gerekiyor?

Power BI'da genellikle 'veri uzantısını güvenlik', Microsoft tarafından onaylanmamıştır kod yüklenmesini engeller daha yüksek düzeydeki düzeyi tutulması önerilir. Ancak, özel bağlayıcılar--olanları, yazdığınız veya size bir danışman veya Microsoft Sertifika yolu dışında bir satıcı tarafından sağlanan olanları yüklemek istediğiniz birçok durumlar olabilir.

Belirli bir bağlayıcı geliştiricisi, bir sertifika ile oturum ve güvenlik ayarlarınızı azaltmayı olmadan güvenli bir şekilde yüklemek gereken bilgileri sağlarız.

Güvenlik ayarları hakkında daha fazla bilgi edinmek istiyorsanız, bunları hakkında bilgi edinebilirsiniz [burada](https://docs.microsoft.com/power-bi/desktop-connector-extensibility).

## <a name="using-the-registry-to-trust-third-party-connectors"></a>Üçüncü taraf bağlayıcılar güvenecek şekilde kayıt defterini kullanma

Power BI üçüncü taraf bağlayıcı güvenen belirtilen kayıt defteri değerindeki güven istediğiniz sertifikanın parmak izini listeleyerek gerçekleştirilir. Bu parmak izine Bağlayıcısı'nı yüklemek istediğiniz sertifika parmak izi eşleşirse, Power BI 'Önerilen' güvenlik düzeyini yüklemek mümkün olacaktır. 

Kayıt defteri yolunu HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI Masaüstü ' dir. Yolun var olduğundan emin olun veya oluşturun. Bu konum, BT ilkesi hem de tarafından gerektiren yerel makine yönetim erişimini düzenlemek için öncelikle denetlenen seçtik. 

![Power BI Desktop kayıt defteri güvenilir bir üçüncü taraf anahtar olmadan ayarlayın](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

Yukarıda belirtilen yolun altındaki yeni bir değer ekleyin. Tür "Çok dizeli değer" (REG_MULTI_SZ) olmalıdır ve "TrustedCertificateThumbprints" çağrılmalıdır 

![Power BI Desktop kayıt defteri ile güvenilir üçüncü taraf bağlayıcılar ancak hiçbir anahtar için bir giriş](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

Güven istediğiniz sertifikaların parmak izleriyle ekleyin. Ayırıcı olarak ya da -> tıklatın doğru Kayıt Defteri Düzenleyicisi'nde "\0" kullanarak birden çok sertifika değiştirin ve her parmak izi yeni bir satıra ekleyebilirsiniz. Otomatik olarak imzalanan bir sertifika parmak izi alınır. 

 ![Power BI Desktop güvenilir bir üçüncü taraf anahtar kümesi ile kayıt defteri](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

Yönergeleri takip düzgün bir şekilde ve uygun parmak izi, geliştirici tarafından verilmiş, güvenli bir şekilde ilişkili sertifika ile imzalanmış güven bağlayıcılara mümkün olması gerekir.

## <a name="how-to-sign-connectors"></a>Bağlayıcılar oturum açma

Bağlayıcı, ya da oturum açmanız gerekir Geliştirici varsa, bu konuda Power Query belgelere okuyabilirsiniz [burada](https://docs.microsoft.com/power-query/handlingconnectorsigning).
