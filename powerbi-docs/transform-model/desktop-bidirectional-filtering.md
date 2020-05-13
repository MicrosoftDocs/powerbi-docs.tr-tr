---
title: Power BI Desktop'ta çift yönlü çapraz filtreleme
description: Power BI Desktop'ta DirectQuery'yi kullanarak çapraz filtrelemeyi etkinleştirin
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 141dabdce7816d21c49d8c7f98d1438c2fc20e8d
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83339111"
---
# <a name="enable-bidirectional-cross-filtering-for-directquery-in-power-bi-desktop"></a>Power BI Desktop'ta DirectQuery için çift yönlü çapraz filtrelemeyi etkinleştirme

Rapor oluşturucuları ve veri modelleyicileri verilerin uygun görünümünü oluşturmak için tabloları filtrelerken, rapora filtrelerin nasıl uygulanacağını saptama konusunda zorlanır. Daha önce tablonun filtre bağlamı ilişkinin bir tarafında korunuyor ama diğer tarafında korunmuyordu. Bu düzenleme çoğunlukla istenen sonuçları elde etmek için karmaşık DAX formülü kullanmayı gerektiriyordu.

Çift yönlü çapraz filtrelemeyle, rapor oluşturucuları ve veri modelleyicileri artık ilişkili tablolarla çalışırken filtreleri nasıl uygulayabilecekleri konusunda daha fazla denetime sahip olur. Çift yönlü çapraz filtreleme sayesinde filtreleri tablo ilişkisinin *her iki* tarafına da uygulayabilirler. Filtre bağlamını tablo ilişkisinin diğer tarafındaki ikinci ilişkili tabloya yayarak filtreleri uygulayabilirsiniz.

## <a name="enable-bidirectional-cross-filtering-for-directquery"></a>DirectQuery için çift yönlü çapraz filtrelemeyi etkinleştirme

Çapraz filtrelemeyi **İlişkiyi düzenle** iletişim kutusunda etkinleştirebilirsiniz. İlişkide çapraz filtrelemeyi etkinleştirmek için aşağıdaki seçenekleri yapılandırmanız gerekir:

* **Çapraz filtre yönü**'nü **Her İkisi** olarak ayarlayın.
* **Güvenlik filtrelerini her iki yönde de uygula**'yı seçin.

  ![Power BI Desktop'ta çift yönlü filtrelemeyi yapılandırın.](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

> [!NOTE]
> Power BI Desktop'ta filtreleme DAX formülleri oluştururken *UserPrincipalName* kullanın. Bu alan genellikle *UserName* yerine kullanıcının oturum açma kimliğiyle aynıdır (örneğin<em>joe@contoso.com</em>). Benzer şekilde, *UserName* veya *EmployeeID* ile *UserPrincipalName* parametrelerini eşleyen bir ilişkili tablo oluşturmanız gerekebilir.

Daha fazla bilgi edinmek ve çift yönlü çapraz filtrelemenin nasıl çalıştığına ilişkin örnekleri görmek için [Power BI Desktop için çift yönlü çapraz filtreleme teknik incelemesini](https://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) gözden geçirin.

