---
title: "Project Online: Power BI Desktop aracılığıyla verilere bağlanma"
description: "Project Online: Power BI Desktop aracılığıyla verilere bağlanma"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1f5fa21845167d2d9d419f163429fd1f025c1749
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online: Power BI Desktop aracılığıyla verilere bağlanma
Power BI Desktop aracılığıyla Project Online verilerinize bağlanabilirsiniz.

### <a name="step-1-download-power-bi-desktop"></a>1. Adım: Power BI Desktop'ı indirme
1. [Power BI Desktop'ı indirip](http://go.microsoft.com/fwlink/?LinkID=521662) yükleyiciyi çalıştırarak **Power BI Desktop** uygulamasını bilgisayarınıza yükleyin.

### <a name="step-2-connect-to-project-online-with-odata"></a>2. Adım: OData ile Project Online'a bağlanma
1. **Power BI Desktop**'ı açın.
2. *Hoş Geldiniz* ekranında **Veri Al**'ı seçin.
3. **OData akışı**'nı ve ardından **Bağlan**'ı seçin.
4. URL kutusuna OData akışınızın adresini girip Tamam'a tıklayın.
   
   Project Web sitenizin adresi https://\<kiracıadı\>.sharepoint.com/sites/pwa gibiyse OData Akışı için girmeniz gereken adres https://\<kiracıadı\>.sharepoint.com/sites/pwa/\_api/Projectdata şeklinde olacaktır.
   
   Bu örnekte kullandığımız adres: https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Power BI Desktop, Office 365 hesabınızla kimlik doğrulamasından geçmenizi isteyecektir. Kuruluş hesabınızı seçip kimlik bilgilerinizi girin.
   
   ![](media/desktop-project-online-connect-to-data/image.png)

Buradan bağlanmak istediğiniz tabloları seçebilir ve sorgu oluşturabilirsiniz.  Nereden başlayacağınızı bilemiyor musunuz?  Aşağıdaki blog gönderisi, Project Online verilerinizden ilerleme grafiği oluşturmayı göstermektedir.  Blog gönderisinde, Project Online'a bağlanmak için Power Query kullanılmaktadır ancak aynı adımlar Power BI Desktop için de geçerlidir.

[Creating burndown charts for Project using Power Pivot and Power Query (Power Pivot ve Power Query kullanarak Project Online için ilerleme grafiği oluşturma)](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)

