---
ms.openlocfilehash: eb7cba03daee47f6772fc46be50419731b41765e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61194131"
---
## <a name="validate-the-roles-within-power-bi-desktop"></a>Power BI Desktop'ta rolleri doğrulama
Rollerinizi oluşturduktan sonra rol sonuçlarını Power BI Desktop'ta test edin.

1. **Rol Olarak Görüntüle**’yi seçin. 

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    **Rol olarak görüntüle**'nin altında, oluşturduğunuz rolleri görürsünüz.

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. Oluşturduğunuz rollerden birini seçin > **Tamam**'ı seçerek bu rolü uygulayın. Rapor seçilen rolle ilgili verileri işler. 

4. **Diğer kullanıcı**’yı seçebilir ve bir kullanıcı belirtebilirsiniz. En iyisi Kullanıcı Asıl Adını (UPN) sağlamaktır çünkü Power BI hizmeti ve Power BI Rapor Sunucusu bunu kullanır.

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

1. **Tamam**'ı seçtiğinizde raporlar kullanıcının görebileceği içerikle oluşturulur. 

Power BI Desktop'ta, **Diğer kullanıcı** ancak DAX ifadelerinize göre dinamik güvenlik kullandığınızda farklı sonuçlar gösterir. 

