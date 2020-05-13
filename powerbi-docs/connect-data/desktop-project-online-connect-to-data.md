---
title: 'Project Online: Power BI Desktop aracılığıyla verilere bağlanma'
description: 'Project Online: Power BI Desktop aracılığıyla verilere bağlanma'
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/01/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 0f01a6da3bb0d829d396861814f71d33ba69f22f
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83291938"
---
# <a name="connect-to-project-online-data-through-power-bi-desktop"></a>Power BI Desktop aracılığıyla Project Online verilerine bağlanma
Power BI Desktop aracılığıyla Project Online verilerinize bağlanabilirsiniz.

## <a name="step-1-download-power-bi-desktop"></a>1\. Adım: Power BI Desktop'ı indirme
1. [Power BI Desktop'ı indirip](https://go.microsoft.com/fwlink/?LinkID=521662) yükleyiciyi çalıştırarak **Power BI Desktop** uygulamasını bilgisayarınıza yükleyin.

## <a name="step-2-connect-to-project-online-with-odata"></a>2\. Adım: OData ile Project Online'a bağlanma
1. **Power BI Desktop**’ı açın.
2. *Hoş Geldiniz* ekranında **Veri Al**'ı seçin.
3. **OData akışı**'nı ve ardından **Bağlan**'ı seçin.
4. URL kutusuna OData akışınızın adresini girip Tamam'a tıklayın.
   
   Project Web sitenizin adresi *https://\<kiracıadı\>.sharepoint.com/sites/pwa* gibiyse OData Akışı için girmeniz gereken adres *https://\<kiracıadı\>.sharepoint.com/sites/pwa/\_api/Projectdata* şeklinde olacaktır.
   
   Biz bu örnekte şu seçeneği kullanıyoruz:

    `https://contoso.sharepoint.com/sites/pwa/default.aspx`

5. Power BI Desktop, Office 365 hesabınızla kimlik doğrulamasından geçmenizi isteyecektir. Kuruluş hesabınızı seçip kimlik bilgilerinizi girin.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

OData akışına bağlanmak için kullandığınız hesabın, Project Web App sitesine en az Portföy Görüntüleyicisi düzeyinde erişim izni olması gerekir. 

Buradan bağlanmak istediğiniz tabloları seçebilir ve sorgu oluşturabilirsiniz.  Nereden başlayacağınızı bilemiyor musunuz?  Aşağıdaki blog gönderisi, Project Online verilerinizden ilerleme grafiği oluşturmayı göstermektedir.  Blog gönderisinde, Project Online'a bağlanmak için Power Query kullanılmaktadır ancak aynı adımlar Power BI Desktop için de geçerlidir.

[Power Pivot ve Power Query kullanarak Proje için ilerleme grafiği oluşturma](https://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

