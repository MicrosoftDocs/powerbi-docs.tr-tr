---
title: Power BI ile Office365Mon'a bağlanma
description: Power BI için Office365Mon
author: paulinbar
ms.author: painbar
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 11/26/2019
LocalizationGroup: Connect to services
ms.openlocfilehash: c7433bcc75da316e2e705a63dbcc2f17745ad573
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96403065"
---
# <a name="connect-to-office365mon-with-power-bi"></a>Power BI ile Office365Mon'a bağlanma
Office 365 ile ilgili hizmet kesintilerinizi ve sistem durumuna ilişkin performans verilerinizi Power BI ve Office365Mon şablon uygulamasıyla kolayca analiz edebilirsiniz. Power BI, hizmet kesintileri ve sistem durumu araştırmalarının yer aldığı verilerinizi alır ve ardından kullanıma hazır bir pano ve bu verilere dayalı raporlar oluşturur.

Power BI için [Office365Mon şablon uygulamasına](https://msit.powerbi.com/groups/me/getapps/services/office365mon.office365mon_powerbi_v3) bağlanın.

>[!NOTE]
>Power BI şablon uygulamasına bağlanmak ve paketi yüklemek için bir Office365Mon yönetici hesabı gereklidir.

## <a name="how-to-connect"></a>Bağlanma
1. Gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![Gezinti bölmesinde görüntülenen Veri Al düğmesinin ekran görüntüsü.](media/service-connect-to-office365mon/pbi_getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![Al düğmesini gösteren Hizmetler iletişim kutusunun ekran görüntüsü.](media/service-connect-to-office365mon/pbi_getservices.png) 
3. **Office365Mon** \> **Al**’ı seçin.
   
   ![Al bağlantısını gösteren Office365Mon iletişim kutusunun ekran görüntüsü.](media/service-connect-to-office365mon/o365mon.png)
4. Kimlik Doğrulama Yöntemi için **oAuth2** \> **Oturum Aç**'ı seçin.
   
   İstendiğinde Office365Mon yönetici kimlik bilgilerinizi girin ve kimlik doğrulama işlemini gerçekleştirin.
   
   ![Kimlik Doğrulama Yöntemi alanında OAuth2’yi gösteren Office365Mon’a Bağlan iletişim kutusunun ekran görüntüsü.](media/service-connect-to-office365mon/creds.png)
   
   ![Kimlik bilgilerini isteyen Office365Mon oturum açma ekranının görüntüsü.](media/service-connect-to-office365mon/creds2.png)
5. Veriler Power BI tarafından içeri aktarıldıktan sonra gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz. Yeni öğeler sarı bir yıldız işaretiyle \* gösterilir, Office365Mon girişini seçin.
   
   ![Pano, rapor ve veri kümelerini gösteren, Power BI’daki gezinti bölmesinin ekran görüntüsü.](media/service-connect-to-office365mon/dashboard4.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](../consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](../create-reports/service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](../consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="troubleshooting"></a>Sorun giderme
Oturum açmak için Office365Mon abonelik kimlik bilgilerinizi kullandıktan sonra bir **"oturum açma başarısız oldu"** hatası alırsanız kullandığınız hesabın Office365Mon verilerini hesabınızdan alma izinleri yok demektir. Bir yönetici hesabı kullandığınızı doğrulayın ve yeniden deneyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI nedir?](../fundamentals/power-bi-overview.md)

[Power BI için veri alma](service-get-data.md)
