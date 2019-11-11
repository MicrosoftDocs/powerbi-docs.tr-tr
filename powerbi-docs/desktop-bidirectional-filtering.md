---
title: Power BI Desktop'ta çift yönlü çapraz filtreleme
description: Power BI Desktop'ta DirectQuery'yi kullanarak çapraz filtrelemeyi etkinleştirin
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e0b6f3017b69540ea2a95280ceadfe7a05a9c474
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73878736"
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop"></a>Power BI Desktop'ta DirectQuery'yi kullanarak çift yönlü çapraz filtreleme

Rapor oluşturan (ve veri modelleyen) kullanıcılar, verilerin uygun görünümünü elde etmek üzere tabloları filtrelerken, filtreleme işleminin raporlara nasıl uygulanacağını belirleme konusunda bazı güçlüklerle karşılaşabilir. Bir tablonun filtre bağlamı, ilişkinin bir tarafında tutulurken diğer tarafında tutulmaz ve genellikle istenen sonuçların elde edilmesi için karmaşık DAX formülleri gerekir.

Çift yönlü çapraz filtreleme sayesinde, rapor oluşturan (ve veri modelleyen) kullanıcılar artık ilişkili tablolarla çalışırken filtrelerin nasıl uygulanacağı konusunda daha fazla denetime sahip olur. Bu özellik, söz konusu filtrelerin bir tablo ilişkisinin *her iki* tarafında da uygulanmasını sağlar. Bu işlem, filtre bağlamının, bir tablo ilişkisinin diğer tarafındaki ikinci bir ilişkili tabloya da uygulanması sağlanarak gerçekleştirilir.

## <a name="detailed-whitepaper-for-bidirectional-cross-filtering"></a>İki yönlü çapraz filtreleme için ayrıntılı teknik inceleme
Power BI Desktop'taki çift yönlü çapraz filtreleme özelliğinin açıklandığı [ayrıntılı bir teknik inceleme](https://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) vardır. (Ayrıca bu teknik incelemede, aynı davranışa sahip SQL Server Analysis Services 2016 da ele alınmıştır.)

* [Power BI Desktop için çift yönlü çapraz filtreleme](https://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) konusunun ele alındığı teknik incelemeyi indirin

## <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>DirectQuery için çift yönlü çapraz filtrelemeyi etkinleştirme

Çapraz filtrelemeyi etkinleştirmek için bir ilişkiye ait **İlişkiyi Düzenle** iletişim kutusunda aşağıdakilerin seçilmesi gerekir:

* **Çapraz filtre yönü**, **Her ikisi de** olarak ayarlanmalıdır
* Ayrıca, **Güvenlik filtrelerini her iki yönde de uygula** seçeneği de belirlenmelidir

  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

> [!NOTE]
> Power BI Desktop'ta çapraz filtreleme için DAX formülleri oluştururken *UserName* yerine *UserPrincipalName* parametresini (genellikle, <em>joe@contoso.com</em> gibi kullanıcı oturum açma bilgileri ile aynıdır) kullanın. Benzer şekilde, *UserName* (veya örneğin, EmployeeID) ile *UserPrincipalName* parametrelerini eşleyen bir ilişkili tablo oluşturmanız gerekebilir.

Daha fazla bilgi edinmek ve çift yönlü çapraz filtrelemenin nasıl çalıştığına ilişkin örnekler görmek için daha önce bu makalede bahsedilen [teknik incelemeye](https://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) göz atın.

