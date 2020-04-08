---
ms.openlocfilehash: 26f4b82301915524b65d9d2d6b39d61b54ed0321
ms.sourcegitcommit: 8eeb784fd46321680367ac913ef976aeedaa7766
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2020
ms.locfileid: "80621594"
---
Hizmet sorumlusu, bir Azure AD uygulamasının Power BI hizmet içeriğine ve API’lerine erişmesine izin vermek için kullanılan bir kimlik doğrulaması yöntemidir.

Bir Azure Active Directory (Azure AD) uygulaması oluşturduğunuzda, bir [hizmet sorumlusu nesnesi](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object) oluşturulur. Yalnızca *hizmet sorumlusu* olarak da bilinen hizmet sorumlusu nesnesi, Azure AD’nin uygulamanızın kimliğini doğrulamasına olanak sağlar. Kimlik doğrulandıktan sonra uygulama, Azure AD kiracı kaynaklarına erişebilir.

Hizmet sorumlusu, kimlik doğrulaması yapmak için Azure AD uygulamasının *Uygulama Kimliğini* ve şunlardan birini kullanır:
* Uygulama gizli dizisi
* Sertifika