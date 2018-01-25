---
title: "Power BI ile Azure Güvenlik Merkezi'ne bağlanma"
description: "Power BI için Azure Güvenlik Merkezi"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: e26a26d7cba2ae3d68586a2e0dcdf87481009bd6
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-azure-security-center-with-power-bi"></a>Power BI ile Azure Güvenlik Merkezi'ne bağlanma
Power BI ile Azure Güvenlik Verilerine bağlanarak Azure iş yükünüzün güvenliğine ilişkin öngörüler edinin. Power BI, otomatik olarak Azure Güvenlik Merkezi verilerinize ilişkin bir pano ve rapor oluşturur. Bu pano ve rapor, verileri çözümlemenize ve araştırmanıza olanak sağlar.

Power BI için [Azure Security Center içerik paketine](https://app.powerbi.com/getdata/services/azure-security-center) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-azure-security-center/getdata.png)
2. **Hizmetler** kutusundaki **Al** düğmesini seçin.
   
   ![](media/service-connect-to-azure-security-center/services.png)
3. **Azure Security Center** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-azure-security-center/asc.png)
4. Abonelik Kimliğinizi belirtin. [Bu parametreleri bulma](#FindingParams) konusundaki ayrıntılı bilgileri aşağıda bulabilirsiniz.
   
   ![](media/service-connect-to-azure-security-center/params.png)
5. **Kimlik doğrulama yöntemi** için **OAuth2** \> **Oturum aç** seçeneklerini belirleyin. İstendiğinde Azure kimlik bilgilerinizi girin.
   
    ![](media/service-connect-to-azure-security-center/creds.png)
6. Onaylamanın ardından, içeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
     ![](media/service-connect-to-azure-security-center/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
İçerik paketi; kaynak güvenlik durumu, uyarı analizi ve önleme analizi ile ilgili öngörüleri kapsar.

## <a name="system-requirements"></a>Sistem gereksinimleri
Bu içerik paketi için Azure Güvenlik Merkezi'nin etkin olduğu bir abonelik kimliğine erişim gerekir. Daha fazla ayrıntı için Azure Portal'daki [Azure Güvenlik Merkezi](https://portal.azure.com/#blade/Microsoft_Azure_Security/SecurityDashboardStartBladeV2)'ne bakın.

İçerik paketi için ayrıca, kullanıcının bir kuruluş (kişisel olmayan) hesabıyla bağlanması gerekir.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Abonelik kimliğinizi bulmanın iki kolay yolu vardır.

1. https://portal.azure.com -&gt; Gözat -&gt; Abonelikler -&gt; ABONELİK KİMLİĞİ'ne giderek
2. https://manage.windowsazure.com -&gt; Ayarlar -&gt; Abonelik Kimliği'ne giderek

Abonelik kimliğiniz yukarıda bulunan \#4 numaralı adımdaki örneğe benzer şekilde sayılardan ve karakterlerden oluşan uzun bir dizidir. 

## <a name="troubleshooting"></a>Sorun giderme
Verilerin yüklenmesi, hesabınızın boyutuna bağlı olarak biraz zaman alabilir. Oturum açma sırasında bir hata ile karşılaşırsanız lütfen parametrelerinizi ve hesapta Azure Güvenlik Merkezi'nin etkin olduğunu onaylayın.

İçerik paketi yüklendiyse ancak herhangi bir veri görüntülenmiyorsa lütfen bir kuruluş hesabıyla bağlandığınızı onaylayın. Kişisel hesaplar Azure Güvenlik Merkezi tarafından desteklense de kullanıcı, kuruluşa ait olmayan bir hesapla bağlandığında API (ve içerik paketi) beklenen değerleri döndürmez. Lütfen bir kuruluş hesabına erişim sağlayarak tekrar bağlanmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

