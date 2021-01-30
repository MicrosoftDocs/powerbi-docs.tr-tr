---
title: Power BI kullanıcıları lisanslarını görüntüleme ve yönetme
description: Yöneticilerin kuruluşlarındaki Power BI kullanıcı lisanslarını görüntülemesi ve yönetmesi için nasıl yapılır bilgileri.
author: mihart
ms.author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 04/08/2020
ms.custom: licensing support
LocalizationGroup: Administration
ms.openlocfilehash: 929540e0f04fb6f8fa7b3f71da2a2f34f5fd273b
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99085579"
---
# <a name="view-and-manage-power-bi-user-licenses"></a>Power BI kullanıcıları lisanslarını görüntüleme ve yönetme

Bu makalede, yöneticilerin Power BI hizmetine ilişkin kullanıcı lisanslarını görüntülemek ve yönetmek için Microsoft 365 yönetim merkezini veya Azure portalını nasıl kullanabileceği açıklanmaktadır.

> [!NOTE]
>
>Bir kullanıcı için hem Power BI (ücretsiz) hem de Power BI Pro lisansı atanmış olması mümkündür. Bu durum, bir kullanıcı ücretsiz lisansa kaydolursa ve daha sonra kendisine bir Power BI Pro lisansı atanırsa meydana gelebilir. Bu durumda en yüksek lisanslama düzeyi etkili olur.
>

## <a name="view-your-subscriptions"></a>Aboneliklerinizi görüntüleme

Kuruluşunuzun hangi Power BI aboneliklerini olduğunu görmek için aşağıdaki adımları izleyin.

1. [Microsoft 365 yönetim merkezinde](https://admin.microsoft.com) oturum açın.
2. Gezinti menüsünde **Faturalama** > **Ürünler ve hizmetler** öğesini seçin.

Etkin Power BI abonelikleriniz, sahip olduğunuz diğer aboneliklerle birlikte listelenir. Burada gösterildiği gibi Power BI (ücretsiz) için beklenmeyen bir abonelik görebilirsiniz.

  ![Ücretsiz bir aboneliği gösteren Power BI aboneliğinin ekran görüntüsü.](media/service-admin-manage-licenses/power-bi-free-user-activated.png)

Kullanıcılar self servis kaydolma özelliğinden yararlanıyorsa, bu tür bir abonelik sizin için oluşturulur. Daha fazla bilgi edinmek için bkz. [Kuruluşunuzda Power BI](/microsoft-365/admin/misc/power-bi-in-your-organization).

## <a name="manage-user-licenses-in-microsoft-365"></a>Microsoft 365’te kullanıcı lisanslarını yönetme

Kullanıcı lisanslarını yönetmek üzere Microsoft 365 yönetim merkezini kullanmak için bkz. [İş abonelikleri ve faturalama belgeleri](/microsoft-365/commerce/).

## <a name="manage-user-licenses-in-azure-portal"></a>Azure portalında kullanıcı lisanslarını yönetme

Azure portalını kullanarak Power BI lisanslarını görüntülemek ve atamak için bu adımları izleyin.

1. [Azure portalında](https://portal.azure.com) oturum açın.

2. **Azure Active Directory**'yi bulun ve seçin.

3. Azure Active Directory kaynağı menüsündeki **Yönet**’in altında **Lisanslar**’ı seçin.

4. Kaynak menüsünden **Tüm ürünler**’i ve ardından bir Power BI lisans türü seçerek lisanslı kullanıcıların listesini görüntüleyin.

5. Lisans atamak için komut çubuğundan **+ Ata**’yı seçin. **Lisans ata** sayfasında bir kullanıcı seçtikten sonra **Atama seçenekleri**’ni belirleyerek seçili kullanıcı hesabı için Power BI lisansını etkinleştirin.

6. Lisans kaldırmak için, kullanıcı adının yanındaki onay kutusunu işaretleyin ve ardından **Lisansı kaldır**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Pro satın alma](service-admin-purchasing-power-bi-pro.md)
- [Kuruluşunuz için lisanslama](service-admin-licensing-organization.md)