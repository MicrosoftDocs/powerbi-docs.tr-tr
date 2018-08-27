---
title: Power BI’da Bağlayıcı Genişletilebilirliği
description: Bağlayıcı genişletilebilirlik özellikleri, güvenlik ayarları ve sertifikalı bağlayıcılar
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/25/2018
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: bba674df9864697199a274698a1b17320b8ccd80
ms.sourcegitcommit: 9d6f37fd32b965592bd7b108dea87b8e53b11334
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2018
ms.locfileid: "40256815"
---
# <a name="connector-extensibility-in-power-bi"></a>Power BI’da bağlayıcı genişletilebilirliği

Müşteriler ve geliştiriciler Power BI'da bağlanabilecekleri veri kaynağı seçeneklerini var olan bağlayıcıları ve genel veri kaynaklarını (ODBC, OData, Oledb, Web, CSV, XML, JSON gibi) kullanma gibi birçok yöntemle genişletebilir. Geliştiriciler bu veri kaynaklarına ek olarak **Özel Bağlayıcılar** olarak adlandırılan veri uzantıları oluşturabilir ve bir bağlayıcı için sertifika oluşturarak **Sertifikalı Bağlayıcı** haline dönüştürebilir.

Şu anda **Özel Bağlayıcıları** kullanma özelliği bir özellik anahtarıyla etkinleştiriliyor. Bu özelliği beta sürümünden genel kullanıma sunmadan önce menüden sisteminizde çalıştırılmasına izin vermek istediğiniz özel kod düzeyini güvenli bir şekilde denetleme seçeneğini ekledik. Bu sayede **Veri Al** iletişim kutusunda tüm özel bağlayıcıların veya yalnızca Microsoft tarafından sertifika verilen ve dağıtılan bağlayıcıların listelenmesini sağlayabilirsiniz.

## <a name="custom-connectors"></a>Özel bağlayıcılar

**Özel Bağlayıcılar** işletmeniz için kritik öneme sahip küçük API'lerden Microsoft'un bağlayıcı yayımlamadığı sektöre özgü büyük hizmetlere kadar çok farklı özelliklere sahip olabilir. Bu bağlayıcıların çoğu satıcı tarafından dağıtılır ve belirli bir veri bağlayıcısına ihtiyacınız varsa satıcıyla iletişime geçmeniz gerekir.

Kullanmak istediğiniz **Özel Bağlayıcıları** *\[Belgeler]\\Power BI Desktop\\Custom Connectors* klasörüne eklemeniz ve güvenlik ayarlarını aşağıdaki bölümde anlatılan şekilde yapmanız gerekir.

**Sertifikalı Bağlayıcıları** kullanmak için güvenlik ayarlarını değiştirmeniz gerekmez.

## <a name="data-extension-security"></a>Veri uzantısı güvenliği

Veri uzantısı güvenlik ayarlarını değiştirmek için **Power BI Desktop** uygulamasında **Dosya > Seçenekler ve Ayarlar > Seçenekler > Güvenlik** yolunu izleyin.

![Veri Uzantısı Güvenliği seçeneklerini kullanarak özel bağlayıcı yükleyip yükleyemeyeceğinizi denetleyebilirsiniz](media/desktop-connector-extensibility/data-extension-security-1.png)

**Veri Uzantıları** bölümünde iki farklı güvenlik düzeyinden birini seçebilirsiniz:

* (Önerilir) Yalnızca sertifikalı uzantıların yüklenmesine izin ver
* (Önerilmez) Uzantıların uyarı olmadan yüklenmesine izin ver

**Özel Bağlayıcıları** veya üçüncü taraf geliştiricilerin geliştirip dağıttığı bağlayıcıları kullanmayı planlıyorsanız **"(Önerilmez) Uzantıların uyarı olmadan yüklenmesine izin ver"** seçeneğini belirlemeniz gerekir. **Özel Bağlayıcılar** çalıştırmayı planlamıyorsanız bu güvenlik ayarını kullanmanız önerilmez.

**"(Önerilir)"** güvenlik ayarında sisteminizde özel bağlayıcıların bulunması durumunda bu bağlayıcıların güvenlik nedeniyle yüklenemediğini belirten bir hata görüntülenir.

![Güvenlik ayarları nedeniyle yüklenemeyen Özel Bağlayıcılar iletişim kutusunda görüntülenir, bu örnekte TripPin](media/desktop-connector-extensibility/data-extension-security-2.png)

Hatayı çözmek ve bu bağlayıcıları kullanmak için yukarıdaki adımları kullanarak **"(Önerilmez)"** güvenlik ayarını seçmeniz ve **Power BI Desktop** uygulamasını yeniden başlatmanız gerekir.

## <a name="certified-connectors"></a>Sertifikalı bağlayıcılar

Sınırlı sayıda veri uzantısı **Sertifikalı** olarak belirlenmiştir ve bu sertifikalı bağlayıcılara **Veri Al** iletişim kutusundan ulaşabilirsiniz ancak bakım ve destek sorumluluğu bağlayıcıyı oluşturan üçüncü taraf geliştiriciye aittir. Microsoft bu bağlayıcıları dağıtmasına rağmen performansından veya işlevlerinin devamlılığından sorumlu değildir.

Özel bağlayıcınızın sertifikalı hale gelmesini istiyorsanız satıcınızdan dataconnectors@microsoft.com ile iletişime geçmesini isteyin.
