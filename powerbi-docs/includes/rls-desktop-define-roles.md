---
ms.openlocfilehash: 6e48713315b23cf322b635f1650374251b639e4f
ms.sourcegitcommit: bbd9b38f30a4ca5cb8072496c9cacb635b03aa88
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71409390"
---
## <a name="define-roles-and-rules-in-power-bi-desktop"></a>Power BI Desktop'ta rol ve kural tanımlama
Power BI Desktop'ta rol ve kural tanımlayabilirsiniz. İçeriğinizi Power BI'da yayımladığınızda rol tanımları da yayımlanır.

Güvenlik rollerini tanımlamak için şu adımları izleyin.

1. Verilerinizi Power BI Desktop raporunuza aktarın veya bir DirectQuery bağlantısı yapılandırın.
   
   > [!NOTE]
   > Analysis Services için Power BI Desktop canlı bağlantılarında rol tanımlayamazsınız. Bu işlemi Analysis Services modelinin içinde yapmanız gerekir.
   > 
   > 
1. **Modelleme** sekmesini seçin.
2. **Rolleri Yönet**'i seçin.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)
4. **Oluştur**'u seçin.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)
5. Rol için bir ad girin. 
6. DAX kuralı uygulamak istediğiniz tabloyu seçin.
7. DAX ifadelerini girin. İfadenin true veya false değeri döndürmesi gerekir. Örneğin: [Entity ID] = "Değer".
   
   > [!NOTE]
   > Bu ifadede *username()* parametresini kullanabilirsiniz. *username()* parametresinin Power BI Desktop'ta *ETKİALANI\kullanıcıadı* biçiminde olduğunu unutmayın. Power BI hizmetinde ve Power BI Rapor Sunucusu'nda, kullanıcının Kullanıcı Asıl Adı (UPN) biçimindedir. Alternatif olarak kullanıcıyı her zaman kullanıcı asıl adı biçiminde (*kullanıcıadı\@contoso.com*) döndüren *userprincipalname()* işlevini kullanabilirsiniz.
   > 
   > 
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)
8. DAX ifadesini oluşturduktan sonra ifadeyi doğrulamak için ifade kutusunun üstündeki onay işaretini seçebilirsiniz.
      
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)
   
   > [!NOTE]
   > Bu ifade kutusunda, normalde noktalı virgül ayırıcıları kullanan bir yerel ayar (ör. Fransızca veya Almanca) kullanıyor olsanız bile DAX işlevi bağımsız değişkenlerini ayırmak için virgül kullanırsınız. 
   >
   >
   
9. **Kaydet**'i seçin.

Power BI Desktop'ta kullanıcıları bir role atayamazsınız. Onları Power BI hizmetinde atarsınız. *username()* veya *userprincipalname()* DAX işlevlerini kullanarak ve ilişkileri doğru şekilde yapılandırarak Power BI Desktop'ta dinamik güvenliği etkinleştirebilirsiniz. 

