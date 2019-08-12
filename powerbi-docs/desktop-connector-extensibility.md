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
ms.openlocfilehash: 7d5d743dda31d05df0beb528648c5a43ffc6b335
ms.sourcegitcommit: 32a44dd17a44ccfd4a2d86a0d235251c2fda1c5c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2019
ms.locfileid: "68702100"
---
# <a name="connector-extensibility-in-power-bi"></a>Power BI’da bağlayıcı genişletilebilirliği

Power BI'da müşteriler ve geliştiriciler bağlandıkları veri kaynaklarını birçok yolla genişletebilir. Mevcut bağlayıcıları ve genel veri kaynaklarını (ODBC, OData, Oledb, Web, CSV, XML, JSON gibi) kullanırlar. Öte yandan geliştiriciler **Özel Bağlayıcılar** olarak adlandırılan veri uzantıları oluşturabilir ve bunları **Sertifikalı Bağlayıcılar**'a dönüştürebilir.

Şu anda sisteminizde çalıştırılmasına izin vermek istediğiniz özel kod düzeyini güvenle denetlemenizi sağlayan bir menüyü kullanarak **Özel Bağlayıcıları** etkinleştirirsiniz. **Veri Al** iletişim kutusunda tüm özel bağlayıcıları seçebileceğiniz gibi yalnızca Microsoft tarafından onaylanan ve dağıtılan bağlayıcıları da seçebilirsiniz.

## <a name="custom-connectors"></a>Özel bağlayıcılar

**Özel Bağlayıcılar** işletmeniz için kritik öneme sahip küçük API'lerden Microsoft'un bağlayıcı yayımlamadığı sektöre özgü büyük hizmetlere kadar çok farklı özelliklere sahip olabilir. Birçok bağlayıcı satıcı tarafından dağıtılır. Belirli bir veri bağlayıcısına ihtiyacınız varsa satıcıya başvurmalısınız.

Kullanmak istediğiniz **Özel Bağlayıcıları** *\[Belgeler]\\Power BI Desktop\\Custom Connectors* klasörüne eklemeniz ve güvenlik ayarlarını aşağıdaki bölümde anlatılan şekilde yapmanız gerekir.

**Sertifikalı Bağlayıcıları** kullanmak için güvenlik ayarlarını değiştirmeniz gerekmez.

## <a name="data-extension-security"></a>Veri uzantısı güvenliği

Veri uzantısı güvenlik ayarlarını değiştirmek için **Power BI Desktop** uygulamasında **Dosya > Seçenekler ve ayarlar > Seçenekler > Güvenlik** yolunu izleyin.

![Veri Uzantısı Güvenliği seçeneklerini kullanarak özel bağlayıcı yüklemek isteyip istemediğinizi denetleme](media/desktop-connector-extensibility/data-extension-security-1.png)

**Veri Uzantıları** bölümünde iki farklı güvenlik düzeyinden birini seçebilirsiniz:

* (Önerilir) Yalnızca sertifikalı uzantıların yüklenmesine izin ver
* (Önerilmez) Uzantıların uyarı olmadan yüklenmesine izin ver

**Özel Bağlayıcıları** veya üçüncü taraf geliştiricilerin geliştirdiği bağlayıcıları kullanmayı planlıyorsanız **"(Önerilmez) Uzantıların uyarı olmadan yüklenmesine izin ver"** seçeneğini belirlemeniz gerekir. Özel Bağlayıcılarınıza tam olarak güvenmediğiniz sürece bu güvenlik ayarını kullanmanızı önermeyiz. Çünkü buradaki kod kimlik bilgilerini işleyebilir, örneğin bunları HTTP üzerinden gönderebilir ve gizlilik düzeylerini yoksayar.

**"(Önerilen)"** güvenlik ayarında, sisteminizde özel bağlayıcılar varsa "Aşağıdaki bağlayıcı sertifikalı değil ve kullanımının güvenli olup olmadığını doğrulayamıyoruz" hatasını alırsınız ve bu hatayı güvenle yüklenemeyen bağlayıcıların listesi izler.

![Güvenlik ayarları nedeniyle yüklenemeyen Özel Bağlayıcıların (bu örnekte TripPin) açıklandığı iletişim kutusu](media/desktop-connector-extensibility/data-extension-security-2.png)

Güvenliği değiştirmeden hataya düzeltmek için imzalanmamış bağlayıcıları 'Custom Connectors' klasörünüzden kaldırın.

Hatayı düzeltmek ve bu bağlayıcıları kullanmak için güvenlik ayarlarınızı daha önce açıklandığı gibi **"(Önerilmez)" Uzantıların doğrulama veya uyarı olmadan yüklenmesine izin ver"** olarak değiştirin. Ardından **Power BI Desktop**'ı yeniden başlatın.

## <a name="certified-connectors"></a>Sertifikalı bağlayıcılar

Veri uzantılarının sınırlı bir alt kümesi **Sertifikalı** olarak kabul edilir. Sertifikalı bağlayıcılara **Veri Al** iletişim kutusunda erişebilirsiniz. Ama bağlayıcının bakımı ve desteği bağlayıcıyı oluşturan üçüncü taraf geliştiricinin sorumluluğundadır. Microsoft bağlayıcıları dağıtmasına rağmen performansından veya işlevlerinin devamlılığından sorumlu değildir.

Özel bağlayıcınızın sertifikalı hale gelmesini istiyorsanız satıcınızdan dataconnectors@microsoft.com ile iletişime geçmesini isteyin.
