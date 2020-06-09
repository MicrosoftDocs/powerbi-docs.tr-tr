---
title: Hizmet sorumlusu oluşturma uygulaması
description: Hizmet sorumlusu oluşturma uygulaması
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 05/20/2020
ms.custom: include file
ms.openlocfilehash: 0fe3e1743cb8853d6626b59b748d70bfcc292dbd
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315837"
---
1. [Microsoft Azure](https://ms.portal.azure.com/#allservices)’da oturum açın.

2. **Uygulama kayıtlarını** arayın ve **Uygulama kayıtları** bağlantısına tıklayın.

    ![azure uygulaması kaydı](media/embedded-service-principal/azure-app-registration.png)

3. **Yeni kayıt**’a tıklayın.

    ![yeni kayıt](media/embedded-service-principal/new-registration.png)

4. Gereken bilgileri doldurun:
    * **Ad**: Uygulamanız için bir ad girin
    * **Desteklenen hesap türleri**: Desteklenen hesap türlerini seçin
    * (İsteğe bağlı) **Yeniden Yönlendirme URI’si**: Gerekirse bir URI girin

5. **Kaydet**’e tıklayın.

6. Kaydolduktan sonra, *Uygulama Kimliğini* **Genel Bakış** sekmesinde bulabilirsiniz. Daha sonra kullanmak için *Uygulama Kimliğini* kopyalayıp kaydedin.

    ![uygulama kimliği](media/embedded-service-principal/application-id.png)