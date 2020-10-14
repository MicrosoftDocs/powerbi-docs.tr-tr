---
title: Hizmet sorumlusuna genel bakış
description: Hizmet sorumlusuna genel bakış
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 04/05/2020
ms.custom: include file
ms.openlocfilehash: 6086185fb671b9f418ef2ec070b762020fbe8f75
ms.sourcegitcommit: 02484b2d7a352e96213353702d60c21e8c07c6c0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "91989516"
---
Hizmet sorumlusu, bir Azure AD uygulamasının Power BI hizmet içeriğine ve API’lerine erişmesine izin vermek için kullanılan bir kimlik doğrulaması yöntemidir.

Bir Azure Active Directory (Azure AD) uygulaması oluşturduğunuzda, bir [hizmet sorumlusu nesnesi](/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object) oluşturulur. Yalnızca *hizmet sorumlusu* olarak da bilinen hizmet sorumlusu nesnesi, Azure AD’nin uygulamanızın kimliğini doğrulamasına olanak sağlar. Kimlik doğrulandıktan sonra uygulama, Azure AD kiracı kaynaklarına erişebilir.

Hizmet sorumlusu, kimlik doğrulaması yapmak için Azure AD uygulamasının *Uygulama Kimliğini* ve şunlardan birini kullanır:

* Uygulama gizli dizisi
* Sertifika