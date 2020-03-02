---
ms.openlocfilehash: 27d6db6cf8ad8ebd7b2c957954ceec34b83681d0
ms.sourcegitcommit: cde65bb8b1bed1ee8cf512651afeb829ddc155de
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77464443"
---
## <a name="define-roles-and-rules-in-power-bi-desktop"></a>Power BI Desktop'ta rol ve kural tanımlama
Power BI Desktop'ta rol ve kural tanımlayabilirsiniz. İçeriğinizi Power BI'da yayımladığınızda rol tanımları da yayımlanır.

Güvenlik rollerini tanımlamak için şu adımları izleyin.

1. Verilerinizi Power BI Desktop raporunuza aktarın veya bir DirectQuery bağlantısı yapılandırın.
   
   > [!NOTE]
   > Analysis Services için Power BI Desktop canlı bağlantılarında rol tanımlayamazsınız. Bu işlemi Analysis Services modelinin içinde yapmanız gerekir.
   > 
   > 
2. **Modelleme** sekmesinde **Rolleri Yönet**'i seçin.
   
   ![Rolleri Yönet’i seçin](./media/rls-desktop-define-roles/powerbi-desktop-security.png)
3. **Rolleri Yönet** penceresinde **Oluştur**'u seçin.
   
   ![Oluştur’u seçin](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)
4. **Roller** bölümünde rol için bir ad girin. 
5. **Tablolar** bölümünde DAX kuralı uygulamak istediğiniz tabloyu seçin.
6. **Tablo filtresi DAX ifadesi** kutusuna DAX ifadelerini girin. Bu ifade true veya false değerini döndürür. Örneğin: ```[Entity ID] = “Value”```.
      
   ![Rolleri yönet penceresi](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)

   > [!NOTE]
   > Bu ifadede *username()* parametresini kullanabilirsiniz. *username()* parametresinin Power BI Desktop'ta *ETKİALANI\kullanıcıadı* biçiminde olduğunu unutmayın. Power BI hizmetinde ve Power BI Rapor Sunucusu'nda, kullanıcının Kullanıcı Asıl Adı (UPN) biçimindedir. Alternatif olarak kullanıcıyı her zaman kullanıcı asıl adı biçiminde (*kullanıcıadı\@contoso.com*) döndüren *userprincipalname()* işlevini kullanabilirsiniz.
   > 
   > 

7. DAX ifadesini oluşturduktan sonra ifadeyi doğrulamak için ifade kutusunun üstündeki onay işaretini seçin.
      
   ![DAX ifadesini doğrulama](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)
   
   > [!NOTE]
   > Bu ifade kutusunda, normalde noktalı virgül ayırıcıları kullanan bir yerel ayar (ör. Fransızca veya Almanca) kullanıyor olsanız bile DAX işlevi bağımsız değişkenlerini ayırmak için virgül kullanırsınız. 
   >
   >
   
8. **Kaydet**'i seçin.

Power BI Desktop'ta kullanıcıları bir role atayamazsınız. Onları Power BI hizmetinde atarsınız. *username()* veya *userprincipalname()* DAX işlevlerini kullanarak ve ilişkileri doğru şekilde yapılandırarak Power BI Desktop'ta dinamik güvenliği etkinleştirebilirsiniz. 

