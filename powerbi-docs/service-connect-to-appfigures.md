---
title: Power BI ile appFigures'a bağlanma
description: Power BI için appFigures
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 7990cdbc0741e80bf2cbb60431228ff6a1d41485
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34243834"
---
# <a name="connect-to-appfigures-with-power-bi"></a>Power BI ile appFigures'a bağlanma
Power BI ve appFigures içerik paketi ile uygulamalarınıza ilişkin önemli istatistikleri izlemek son derece kolaydır. Power BI; uygulama satışları, indirmeler ve reklam istatistikleri gibi verilerinizi alarak varsayılan bir pano ve bu verilere dayalı raporlar oluşturur.

[appFigures içerik paketine](https://app.powerbi.com/getdata/services/appfigures) bağlanın veya Power BI ile [appFigures tümleştirmesi](https://powerbi.microsoft.com/integrations/appfigures) hakkında daha fazla bilgi edinin.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-appfigures/pbi_getdata.png)
2. **Hizmetler** kutusundaki **Al** düğmesini seçin.
   
   ![](media/service-connect-to-appfigures/pbi_getservices.png)
3. **appFigures** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-appfigures/appfigures.png)
4. **Kimlik doğrulama yöntemi** için **OAuth2** \> **Oturum aç** seçeneklerini belirleyin. İstendiğinde appFigures kimlik bilgilerinizi girin ve appFigures kimlik doğrulama işlemindeki diğer adımlarla devam edin.
   
   İlk bağlandığınızda Power BI, hesabınıza yalnızca okuma erişim izni vermenizi ister. İçeri aktarma işlemini başlatmak için **Allow** (İzin ver) seçeneğini belirleyin. Bu işlem, hesabınızdaki verilerin hacmine bağlı olarak birkaç dakika sürebilir.
   
   ![](media/service-connect-to-appfigures/appfiguresdoc_06.png)
5. Veriler Power BI tarafından içeri aktarıldıktan sonra sol gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz. Yeni öğeler sarı yıldız işareti \* ile gösterilir:
   
    ![](media/service-connect-to-appfigures/pbi_appfigures3.png)
6. appFigures panosunu seçin. Bu, Power BI'ın verilerinizi görüntülemek için oluşturduğu varsayılan panodur. Bu panoyu, verilerinizi istediğiniz herhangi bir biçimde görüntüleyecek şekilde değiştirebilirsiniz.
   
    ![](media/service-connect-to-appfigures/appfiguresdoc_01.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
Power BI'da appFigures ile kullanabileceğiniz veriler aşağıdadır.

| **Tablo Adı** | **Açıklama** |
| --- | --- |
| Countries |Bu tablo, ülke adı bilgisini sağlar. |
| Dates |Bu tablo, içinde bulunduğunuz günden başlayarak, appFigures hesabınızda Active (Etkin) ve Visible (Görünür) durumda olan uygulamaların en erken Yayımlanma Tarihine kadar olan tarihleri içerir. |
| Events |Bu tabloda ülkelere göre günlük olarak her bir uygulamaya ilişkin indirme, satış ve reklam bilgileri bulunur. Hem uygulama hem de uygulama içi satın alma bilgilerinin tümünün bu tek tabloda verileceğini ve bunları ayırt etmek için <strong>Type</strong> sütununu kullanabileceğinizi unutmayın. |
| Inapps |Bu tablo, appFigures hesabınızdaki Active (Etkin) ve Visible (Görünür) durumdaki uygulamalarla ilişkili farklı Uygulama İçi Satın Alma türleri ile ilgili verileri içerir. |
| Ürünler |Bu tablo, appFigures hesabınızda Active (Etkin) ve Visible (Görünür) olan farklı uygulamalar ile ilgili verileri içerir. |

## <a name="troubleshooting"></a>Sorun giderme
Bazı uygulamalarınızdan alınan veriler Power BI'da gösterilmiyorsa bu uygulamaların appFigures sitesindeki **apps** (uygulamalar) sekmesinde Visible (Görünür) ve Active (Etkin) durumda olup olmadıklarını denetleyin.

![](media/service-connect-to-appfigures/appfiguresdoc_11.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI ile çalışmaya başlama](service-get-started.md)
* [Power BI'da veri alma](service-get-data.md)

