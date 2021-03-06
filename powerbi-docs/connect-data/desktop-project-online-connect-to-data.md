---
title: 'Project Online: Power BI Desktop aracılığıyla verilere bağlanma'
description: 'Project Online: Power BI Desktop aracılığıyla verilere bağlanma'
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 04/01/2020
LocalizationGroup: Connect to data
ms.openlocfilehash: b6078a2122a77682af328f9935b23da0d0d0d945
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96404951"
---
# <a name="connect-to-project-online-data-through-power-bi-desktop"></a>Power BI Desktop aracılığıyla Project Online verilerine bağlanma
Power BI Desktop aracılığıyla Project Online verilerinize bağlanabilirsiniz.

## <a name="step-1-download-power-bi-desktop"></a>1\. Adım: Power BI Desktop'ı indirme
1. [Power BI Desktop'ı indirip](https://go.microsoft.com/fwlink/?LinkID=521662) yükleyiciyi çalıştırarak **Power BI Desktop** uygulamasını bilgisayarınıza yükleyin.

## <a name="step-2-connect-to-project-online-with-odata"></a>2\. Adım: OData ile Project Online’a bağlanma
1. **Power BI Desktop**'ı açın.
2. *Hoş Geldiniz* ekranında **Veri Al**'ı seçin.
3. **OData akışı**'nı ve ardından **Bağlan**'ı seçin.
4. URL kutusuna OData akışınızın adresini girip Tamam'a tıklayın.
   
   Project Web sitenizin adresi *https://\<tenantname\>.sharepoint.com/sites/pwa* gibiyse OData Akışı için girmeniz gereken adres *https://\<tenantname\>.sharepoint.com/sites/pwa/\_api/Projectdata* şeklinde olacaktır.
   
   Biz bu örnekte şu seçeneği kullanıyoruz:

    `https://contoso.sharepoint.com/sites/pwa/default.aspx`

5. Power BI Desktop iş veya okul hesabınızla kimliğinizi doğrulamanızı ister. Kuruluş hesabınızı seçip kimlik bilgilerinizi girin.
   
   ![Bağlanmak için kimlik bilgileri istemini gösteren Power BI Desktop’ın ekran görüntüsü.](media/desktop-project-online-connect-to-data/image.png)

OData akışına bağlanmak için kullandığınız hesabın, Project Web App sitesine en az Portföy Görüntüleyicisi düzeyinde erişim izni olması gerekir. 

Buradan bağlanmak istediğiniz tabloları seçebilir ve sorgu oluşturabilirsiniz.  Nereden başlayacağınızı bilemiyor musunuz?  Aşağıdaki blog gönderisi, Project Online verilerinizden ilerleme grafiği oluşturmayı göstermektedir.  Blog gönderisinde, Project Online'a bağlanmak için Power Query kullanılmaktadır ancak aynı adımlar Power BI Desktop için de geçerlidir.

[Power Pivot ve Power Query kullanarak Proje için ilerleme grafiği oluşturma](https://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

