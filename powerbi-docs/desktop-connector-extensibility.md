---
title: Power BI’da Bağlayıcı Genişletilebilirliği
description: Bağlayıcı genişletilebilirlik özellikleri, güvenlik ayarları ve sertifikalı bağlayıcılar
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/02/2020
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: b604ade56335e65b25501eb9fe3d3c2fd185a6f0
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75761421"
---
# <a name="connector-extensibility-in-power-bi"></a>Power BI’da bağlayıcı genişletilebilirliği

Power BI; var olan bağlayıcıları ve ODBC, OData, OLE DB, Web, CSV, XML ve JSON gibi genel veri kaynaklarını kullanarak verilere bağlanabilir. Alternatif olarak geliştiriciler, *özel bağlayıcılar* olarak adlandırılan özel veri uzantılarını kullanarak yeni veri kaynaklarını etkinleştirebilir. Bazı özel bağlayıcılar sertifikalıdır ve Microsoft tarafından *sertifikalı bağlayıcılar* adı altında dağıtılır.

Kendi geliştirdiğiniz veya üçüncü tarafların geliştirdiği sertifikalı olmayan özel bağlayıcıları kullanmak için Power BI Desktop güvenlik ayarlarını, uzantıların doğrulama veya uyarı olmadan yüklenmesine izin verecek şekilde düzenlemeniz gerekir. Bu kod kimlik bilgilerini işleyebileceğinden (bu bilgileri HTTP üzerinden göndermek de dahil) ve gizlilik düzeylerini yoksayabileceğinden bu güvenlik ayarını yalnızca özel bağlayıcılarınıza güveniyorsanız kullanmanız gerekir.

Diğer bir seçenek de geliştiricinin bağlayıcıyı bir sertifika ile imzalaması ve güvenlik ayarlarınızı değiştirmeden kullanabilmeniz için gerekli bilgileri sağlamasıdır. Daha fazla bilgi için bkz. [Güvenilen üçüncü taraf bağlayıcılar hakkında](desktop-trusted-third-party-connectors.md).

## <a name="custom-connectors"></a>Özel bağlayıcılar

Sertifikalı olmayan özel bağlayıcılar, küçük işletmeler için kritik öneme sahip API'lerden Microsoft'un bağlayıcı yayımlamadığı sektöre özgü büyük hizmetlere kadar çok farklı özelliklere sahip olabilir. Birçok bağlayıcı satıcılar tarafından dağıtılır. Belirli bir veri bağlayıcısına ihtiyacınız varsa satıcıyla iletişime geçin. 

Sertifikalı olmayan bir özel bağlayıcıyı kullanmak için *.pq*, *.pqx*, *.m*, veya *.mez* dosyasını *\[Belgeler]\\Power BI Desktop\\Özel Bağlayıcılar* klasörüne yerleştirin. Bu klasör mevcut değilse oluşturun.

Veri uzantısı güvenlik ayarlarını şu şekilde düzenleyin:

Power BI Desktop'ta **Dosya** > **Seçenekler ve ayarlar** > **Seçenekler** > **Güvenlik** yolunu izleyin.

**Veri Uzantıları**'nın altında **(Önerilmez) Uzantıların doğrulama veya uyarı olmadan yüklenmesine izin ver**'i seçin. **Tamam**'ı seçin ve Power BI Desktop'ı yeniden başlatın. 

![Sertifikalı olmayan özel bağlayıcılara Veri Uzantısı Güvenlik seçeneklerinde izin verme](media/desktop-connector-extensibility/data-extension-security-1.png)

Varsayılan Power BI Desktop veri uzantısı güvenlik ayarı **(Önerilir) Yalnızca Microsoft sertifikalı ve diğer güvenilen üçüncü taraf uzantılarının yüklenmesine izin ver** şeklindedir. Bu ayar seçili olduğunda, sisteminizde sertifikalı olmayan özel bağlayıcılar varsa Power BI Desktop açıldığında güvenli bir şekilde yüklenemeyen bağlayıcıların listelendiği **Sertifikasız Bağlayıcılar** iletişim kutusu açılır.

![Sertifikasız Bağlayıcılar iletişim kutusu](media/desktop-connector-extensibility/data-extension-security-2.png)

Bu hatayı gidermek için **Veri Uzantıları** güvenlik ayarını değiştirebilir veya *Özel Bağlayıcılar* klasöründeki sertifikasız bağlayıcıları kaldırabilirsiniz.

## <a name="certified-connectors"></a>Sertifikalı bağlayıcılar

Veri uzantılarının sınırlı bir alt kümesi *sertifikalı* olarak kabul edilir. Microsoft bağlayıcıları dağıtmasına rağmen performansından veya işlevlerinin devamlılığından sorumlu değildir. Bağlayıcının bakımı ve desteği bağlayıcıyı oluşturan üçüncü taraf geliştiricinin sorumluluğundadır. 

Power BI Desktop'ta sertifikalı üçüncü taraf bağlayıcıları, genel ve yaygın kullanılan bağlayıcılarla birlikte **Veri Al** iletişim kutusundaki listede görünür. Sertifikalı bağlayıcıları kullanmak için güvenlik ayarlarını değiştirmeniz gerekmez.

Özel bağlayıcınızın sertifikalı hale gelmesini istiyorsanız satıcınızdan dataconnectors@microsoft.com ile iletişime geçmesini isteyin.
