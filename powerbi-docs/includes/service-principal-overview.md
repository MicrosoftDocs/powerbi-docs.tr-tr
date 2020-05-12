---
title: Hizmet sorumlusuna genel bakış
description: Hizmet sorumlusuna genel bakış
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 04/05/2020
ms.custom: include file
ms.openlocfilehash: 7fc4412a66602fe3a6548c3e1afb06de788da90d
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82616095"
---
Hizmet sorumlusu, bir Azure AD uygulamasının Power BI hizmet içeriğine ve API’lerine erişmesine izin vermek için kullanılan bir kimlik doğrulaması yöntemidir.

Bir Azure Active Directory (Azure AD) uygulaması oluşturduğunuzda, bir [hizmet sorumlusu nesnesi](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object) oluşturulur. Yalnızca *hizmet sorumlusu* olarak da bilinen hizmet sorumlusu nesnesi, Azure AD’nin uygulamanızın kimliğini doğrulamasına olanak sağlar. Kimlik doğrulandıktan sonra uygulama, Azure AD kiracı kaynaklarına erişebilir.

Hizmet sorumlusu, kimlik doğrulaması yapmak için Azure AD uygulamasının *Uygulama Kimliğini* ve şunlardan birini kullanır:
* Uygulama gizli dizisi
* Sertifika