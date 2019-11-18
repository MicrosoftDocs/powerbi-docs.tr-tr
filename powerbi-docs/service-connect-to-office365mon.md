---
title: Power BI ile Office365Mon'a bağlanma
description: Power BI için Office365Mon
author: teddybercovitz
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 8/29/2019
ms.author: tebercov
LocalizationGroup: Connect to services
ms.openlocfilehash: 64e8365a6d4e0c01911de9e69998af4d58d59202
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73854711"
---
# <a name="connect-to-office365mon-with-power-bi"></a>Power BI ile Office365Mon'a bağlanma
Office 365 ile ilgili hizmet kesintilerinizi ve sistem durumuna ilişkin performans verilerinizi Power BI ve Office365Mon şablon uygulamasıyla kolayca analiz edebilirsiniz. Power BI, hizmet kesintileri ve sistem durumu araştırmalarının yer aldığı verilerinizi alır ve ardından kullanıma hazır bir pano ve bu verilere dayalı raporlar oluşturur.

Power BI için [Office365Mon şablon uygulamasına](https://app.powerbi.com/groups/me/getdata/services/office365mon) bağlanın.

>[!NOTE]
>Power BI şablon uygulamasına bağlanmak ve paketi yüklemek için bir Office365Mon yönetici hesabı gereklidir.

## <a name="how-to-connect"></a>Bağlanma
1. Gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-office365mon/pbi_getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-office365mon/pbi_getservices.png) 
3. **Office365Mon** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-office365mon/o365mon.png)
4. Kimlik Doğrulama Yöntemi için **OAuth2** \> **Oturum aç** seçeneğini belirleyin.
   
   İstendiğinde Office365Mon yönetici kimlik bilgilerinizi girin ve kimlik doğrulama işlemini gerçekleştirin.
   
   ![](media/service-connect-to-office365mon/creds.png)
   
   ![](media/service-connect-to-office365mon/creds2.png)
5. Veriler Power BI tarafından içeri aktarıldıktan sonra gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz. Yeni öğeler sarı bir yıldız işaretiyle \* gösterilir, Office365Mon girişini seçin.
   
   ![](media/service-connect-to-office365mon/dashboard4.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="troubleshooting"></a>Sorun giderme
Oturum açmak için Office365Mon abonelik kimlik bilgilerinizi kullandıktan sonra bir **"oturum açma başarısız oldu"** hatası alırsanız kullandığınız hesabın Office365Mon verilerini hesabınızdan alma izinleri yok demektir. Bir yönetici hesabı olduğunu doğrulayın ve yeniden deneyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI nedir?](fundamentals/power-bi-overview.md)

[Power BI için veri alma](service-get-data.md)

