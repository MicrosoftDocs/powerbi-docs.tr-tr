---
title: Power BI’da Bağlayıcı Genişletilebilirliği
description: Bağlayıcı genişletilebilirlik özellikleri, güvenlik ayarları ve sertifikalı bağlayıcılar
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 16b96d91a9dd37fa8a502bbcca772438c703cb63
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412974"
---
# <a name="connector-extensibility-in-power-bi"></a>Power BI’da bağlayıcı genişletilebilirliği

Power BI'da, müşteriler ve geliştiricilerin birçok şekilde bağlandıklarında veri kaynakları genişletebilirsiniz. Bunlar, mevcut bağlayıcılar ve genel veri kaynakları (örneğin, ODBC, OData, Oledb, Web, CSV, XML, JSON) kullanır. Veya veri uzantıları olarak adlandırılır, geliştiriciler oluşturma **özel Bağlayıcılar**ve onları **sertifikalı Bağlayıcılar**.

Şu anda, etkinleştirdiğiniz **özel Bağlayıcılar** güvenli bir şekilde olanak sağlayan bir menüyü kullanarak, istediğiniz sisteminizde çalıştırmak için özel kod düzeyini denetleme. Tüm özel bağlayıcıları veya sertifikalıdır ve Microsoft tarafından dağıtılan bağlayıcıları seçebileceğiniz **Veri Al** iletişim kutusu.

## <a name="custom-connectors"></a>Özel bağlayıcılar

**Özel Bağlayıcılar** çok çeşitli olanaklar içerebilir, Microsoft'un küçük API'lerinden kritik büyük sektöre özgü hizmetlerine işiniz arasında değişen bir bağlayıcı için yayımlanan edilmemiş. Çok sayıda bağlayıcı, satıcı tarafından dağıtılır. Belirli veri bağlayıcı için bir gereksinimi varsa, bir satıcı başvurmanız gerekir.

Kullanılacak bir **özel bağlayıcı**, böyle  *\[belgeler]\\Power BI Desktop\\özel Bağlayıcılar* klasöründe ve açıklandığı gibi güvenlik ayarlarını Aşağıdaki bölümde.

**Sertifikalı Bağlayıcıları** kullanmak için güvenlik ayarlarını değiştirmeniz gerekmez.

## <a name="data-extension-security"></a>Veri uzantısı güvenliği

Veri uzantısı güvenlik ayarlarını değiştirmek için **Power BI Desktop** seçin **Dosya > Seçenekler ve Ayarlar > Seçenekler > Güvenlik**.

![Veri uzantısı güvenlik seçenekleri ile özel bağlayıcılar yüklemek isteyip istemediğinizi kontrol](media/desktop-connector-extensibility/data-extension-security-1.png)

**Veri Uzantıları** bölümünde iki farklı güvenlik düzeyinden birini seçebilirsiniz:

* (Önerilir) Yalnızca sertifikalı uzantıların yüklenmesine izin ver
* (Önerilmez) Uzantıların uyarı olmadan yüklenmesine izin ver

Kullanmayı planlıyorsanız **özel Bağlayıcılar** veya, veya bir üçüncü taraf geliştirilen bağlayıcılar, seçmelisiniz **"(Not Recommended) uyarı vermeden yüklemek herhangi bir uzantısına izin ver"** . Özel Bağlayıcılarınızı kesinlikle güvenmedikçe bu güvenlik ayarı önerilmemektedir. Burada kodda işlemek HTTP üzerinden göndererek gibi kimlik bilgilerini ve gizlilik düzeylerini yoksayın.

Konumunda **"(önerilen)"** güvenlik ayarı, sisteminizde özel bağlayıcılar kullanıyorsanız, bir hata güvenlik nedeniyle yüklenemiyor bağlayıcıları açıklayan görüntülenir.

![Bir iletişim kutusu özel bağlayıcılar, güvenlik ayarları, bu büyük/küçük harf TripPin nedeniyle yüklenemiyor açıklar.](media/desktop-connector-extensibility/data-extension-security-2.png)

Hatayı çözün ve söz konusu bağlayıcıları kullanmak için güvenlik ayarlarınızı değiştirme **"(Not Recommended) uyarı vermeden yüklemek herhangi bir uzantısına izin ver"** daha önce açıklandığı gibi ayarlar. Daha sonra yeniden **Power BI Desktop**.

## <a name="certified-connectors"></a>Sertifikalı bağlayıcılar

Sınırlı bir alt kümesinde veri uzantıları kabul **sertifikalı**. Sertifikalı bağlayıcılar, erişim **Veri Al** iletişim kutusu. Ancak, Bakım ve destek için bağlayıcıyı oluşturan üçüncü taraf geliştirici sorumludur. Microsoft bağlayıcıları dağıtır olsa da, performans veya devam eden bir işlev için sorumlu değildir.

Özel bağlayıcınızın sertifikalı hale gelmesini istiyorsanız satıcınızdan dataconnectors@microsoft.com ile iletişime geçmesini isteyin.
