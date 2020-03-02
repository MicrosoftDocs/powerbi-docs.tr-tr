---
ms.openlocfilehash: 8dc488a47ac2b5b4e7980b7404b2722b1120b6ab
ms.sourcegitcommit: cde65bb8b1bed1ee8cf512651afeb829ddc155de
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77464418"
---
## <a name="validate-the-roles-within-power-bi-desktop"></a>Power BI Desktop'ta rolleri doğrulama
Rollerinizi oluşturduktan sonra rol sonuçlarını Power BI Desktop'ta test edin.

1. **Modelleme** sekmesinde **Rol olarak görüntüle**'yi seçin. 

    ![Rol olarak görüntüle'yi seçin](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    Oluşturduğunuz rollerin yer aldığı **Rol olarak görüntüle** penceresi açılır.

    ![Rol olarak görüntüle penceresi](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. Oluşturduğunuz rollerden birini seçin ve ardından **Tamam**'ı seçerek bu rolü uygulayın. 

   Rapor seçilen rolle ilgili verileri işler.

4. **Diğer kullanıcı**’yı seçebilir ve bir kullanıcı belirtebilirsiniz. 

    ![Diğer kullanıcı'yı seçin](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

   En iyisi Kullanıcı Asıl Adını (UPN) sağlamaktır çünkü Power BI hizmeti ve Power BI Rapor Sunucusu bunu kullanır.

   Power BI Desktop'ta, **Diğer kullanıcı** ancak DAX ifadelerinize göre dinamik güvenlik kullandığınızda farklı sonuçlar gösterir. 

5. **Tamam**’ı seçin. 

   Raporlar kullanıcının görebileceği içerikle oluşturulur.



