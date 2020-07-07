---
title: Power BI hizmetinde görselleştirmeleri kopyalayıp yapıştırma
description: Power BI hizmetinde görselleştirmeleri kopyalayıp yapıştırma
author: mihart
ms.reviewer: maggie tsang
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 06/25/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 4ff249002248b438b189b59defffd3c61d981b70
ms.sourcegitcommit: 46a340937d9f01c6daba86a4ab178743858722ec
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85398316"
---
# <a name="copy-a-visual-as-an-image-to-your-clipboard"></a>Bir görseli görüntü olarak panonuza kopyalama

[!INCLUDE[consumer-appliesto-yyyn](../includes/consumer-appliesto-yyyn.md)]

Power BI raporundan veya panosundan bir görüntü paylaşmak istediğiniz oldu mu? Artık görseli kopyalayabilir ve yapıştırmayı destekleyen başka bir uygulamaya yapıştırabilirsiniz. 

Görselin statik bir görüntüsünü kopyaladığınızda, meta verilerle birlikte görselin bir kopyasını alırsınız. Buna aşağıdakiler dahildir:
* Power BI raporuna veya panosuna geri dönen bağlantı
* raporun veya panonun başlığı
* görüntünün gizli bilgiler içerip içermediğiyle ilgili uyarı
* Son güncellenme zaman damgası
* görsele uygulanan filtreler

### <a name="copy-from-a-dashboard-tile"></a>Pano kutucuğundaki kopya

1. Kopyalamak istediğiniz panoya gidin.

2. Görselin sağ üst köşesinden **Diğer eylemler (...)** ve ardından **Görseli görüntü olarak kopyala**’yı seçin. 

    ![Görseli görüntü olarak kopyala simgesi görüntülendi](media/end-user-copy-paste/power-bi-copy-dashboard.png)

3. **Görselinizi kopyalamaya hazır** iletişim kutusu göründüğünde **Panoya kopyala**'yı seçin.

    ![Panoya kopyala seçeneğine sahip iletişim kutusu](media//end-user-copy-paste/power-bi-copied.png)

4. Görseliniz kopyalandığında, **Ctrl + V** kullanarak veya sağ tıklayıp > Yapıştır’ı seçerek başka bir uygulamaya yapıştırın. Aşağıdaki ekran görüntüsünde görseli Microsoft Word'e yapıştırdık. 

    ![Outlook'a yapıştırılan görsel](media//end-user-copy-paste/power-bi-paste-word.png)

### <a name="copy-from-a-report-visual"></a>Rapor görselindeki kopya 

1. Kopyalamak istediğiniz rapora gidin.

2. Görselin sağ üst köşesinden **Görseli görüntü olarak kopyala** simgesini seçin. 

    ![Görseli görüntü olarak kopyala simgesi görüntülendi](media/end-user-copy-paste/power-bi-copy-icon.png)

3. **Görselinizi kopyalamaya hazır** iletişim kutusu göründüğünde **Panoya kopyala**'yı seçin.

    ![Panoya kopyala seçeneğine sahip iletişim kutusu](media//end-user-copy-paste/power-bi-copied.png)


4. Görseliniz kopyalandığında, **Ctrl + V** kullanarak veya sağ tıklayıp > Yapıştır’ı seçerek başka bir uygulamaya yapıştırın. Aşağıdaki ekran görüntüsünde görseli bir e-postaya yapıştırdık.

    ![Outlook'a yapıştırılan görsel](media//end-user-copy-paste/power-bi-copy-email.png)

5. Rapora uygulanmış bir veri duyarlılığı etiketi varsa, kopyala simgesini seçtiğinizde bir uyarı alırsınız.  

    ![duyarlı veri uyarısı](media//end-user-copy-paste/power-bi-sensitive.png)

    Yapıştırılan görselin altındaki meta verilere bir duyarlılık etiketi eklenir. 

    ![gizli bilgi etiketine sahip görsel](media//end-user-copy-paste/power-bi-confidential.png)



## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

   ![kopya kullanılamıyor](media//end-user-copy-paste/power-bi-copy-grey.png)


S: Kopyala simgesi neden bir görselde devre dışıdır?    
Y: Şu anda yerel Power BI görsellerini ve onaylı özel görselleri destekliyoruz. Aşağıdakiler dahil belirli görseller için sınırlı destek vardır: 
- ESRI ve diğer Harita görselleri 
- Python görselleri 
- R görselleri 
- PowerApps    

Y: Bir görseli kopyalama özelliği, BT departmanınız veya Power BI yöneticiniz tarafından kapatılabilir.


S: Görselim neden doğru şekilde yapıştırmıyor?    
Y: Özel görseller ve animasyonlu görseller için sınırlamalar vardır. 



## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki görselleştirmeler](end-user-visual-type.md) hakkında daha fazla bilgi

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

