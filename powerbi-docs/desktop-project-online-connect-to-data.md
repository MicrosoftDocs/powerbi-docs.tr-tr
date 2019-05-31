---
title: 'Project Online: Power BI Desktop aracılığıyla verilere bağlanma'
description: 'Project Online: Power BI Desktop aracılığıyla verilere bağlanma'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b0dc84d7b2d8da0df8a9e61a43f35898d197c188
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513724"
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online: Power BI Desktop aracılığıyla verilere bağlanma
Power BI Desktop aracılığıyla Project Online verilerinize bağlanabilirsiniz.

## <a name="step-1-download-power-bi-desktop"></a>1. Adım: Power BI Desktop'ı indirme
1. [Power BI Desktop'ı indirip](http://go.microsoft.com/fwlink/?LinkID=521662) yükleyiciyi çalıştırarak **Power BI Desktop** uygulamasını bilgisayarınıza yükleyin.

## <a name="step-2-connect-to-project-online-with-odata"></a>2. Adım: OData ile Project Online’a bağlanma
1. **Power BI Desktop**'ı açın.
2. *Hoş Geldiniz* ekranında **Veri Al**'ı seçin.
3. **OData akışı**'nı ve ardından **Bağlan**'ı seçin.
4. URL kutusuna OData akışınızın adresini girip Tamam'a tıklayın.
   
   Project Web App sitenizin adresi benzer varsa *https://\<kiracıadı\>.sharepoint.com/sites/pwa*, gibiyse OData akışı için girmeniz adresi ise *https://\<kiracıadı\>.sharepoint.com/sites/pwa/\_API/projectdata şeklinde olacaktır*.
   
   Biz bu örnekte https://contoso.sharepoint.com/sites/pwa/default.aspx seçeneğini kullanıyoruz.
5. Power BI Desktop, Office 365 hesabınızla kimlik doğrulamasından geçmenizi isteyecektir. Kuruluş hesabınızı seçip kimlik bilgilerinizi girin.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

OData akışı en az olmalıdır bağlanmak için kullandığınız hesabın Project Web App sitesine Portföy Görüntüleyicisi düzeyinde erişim. 

Buradan bağlanmak istediğiniz tabloları seçebilir ve sorgu oluşturabilirsiniz.  Nereden başlayacağınızı bilemiyor musunuz?  Aşağıdaki Web günlüğü gönderisinde bir yazma şeması Project Online verilerinizden aşağı oluşturulması gösterilir.  Blog gönderisinde, Project Online'a bağlanmak için Power Query kullanılmaktadır ancak aynı adımlar Power BI Desktop için de geçerlidir.

[Power Pivot ve Power Query kullanarak Project için yazma aşağı grafikler oluşturma](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

