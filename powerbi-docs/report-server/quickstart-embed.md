---
title: Power BI Rapor Sunucusu raporunu SharePoint Server’da bir iFrame kullanarak ekleme
description: Bu makalede Power BI Rapor Sunucusu raporunu SharePoint Server’da bir iFrame kullanarak ekleme işlemi gösterilmektedir
author: maggiesMSFT
ms.author: maggies
ms.date: 07/28/2020
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
ms.openlocfilehash: 698f12f4bf5266373be8393d2add45d70979ab41
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96418452"
---
# <a name="embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>Power BI Rapor Sunucusu raporunu SharePoint Server’da bir iFrame kullanarak ekleme

Bu makalede, bir SharePoint sayfasında iFrame kullanarak bir Power BI Rapor Sunucusu raporunu eklemeyi öğreneceksiniz. SharePoint Online ile çalışıyorsanız, Power BI Rapor Sunucusu genel erişime açık olmalıdır. SharePoint Online’da Power BI hizmeti ile çalışan Power BI Web bölümü, Power BI Rapor Sunucusu ile birlikte çalışmaz.  

![iFrame örneği](media/quickstart-embed/quickstart_embed_01.png)

## <a name="prerequisites"></a>Önkoşullar
* [Power BI Rapor Sunucusu](https://powerbi.microsoft.com/report-server/) yüklü ve yapılandırılmış.
* [Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulaması](install-powerbi-desktop.md) yüklü.
* [SharePoint 2013, 2016 veya 2019 ortamı](/sharepoint/install/install) yüklü ve yapılandırılmış.
* Internet Explorer 11, belge modu IE11 (Microsoft Edge) olarak ayarlandığında veya SharePoint Online kullanılırken desteklenir. SharePoint şirket içi ve SharePoint Online ile desteklenen diğer tarayıcıları kullanabilirsiniz.

## <a name="create-the-power-bi-report-url"></a>Power BI rapor URL’si oluşturma

1. Github'dan örneği indirin: [Blog Tanıtımı](https://github.com/Microsoft/powerbi-desktop-samples). **Kopyala veya indir**’i, ardından **ZIP indir**’i seçin.

    ![Örnek PBIX dosyasını indirme](media/quickstart-embed/quickstart_embed_14.png)

2. Zip dosyasını açın ve Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasında örnek .pbix dosyasını açın.

    ![PBI RS Masaüstü aracı](media/quickstart-embed/quickstart_embed_02.png)

3. Raporu **Power BI Rapor Sunucusu**’na kaydedin. 

    ![PBI RS Kaydetme](media/quickstart-embed/quickstart_embed_03.png)

4. Power BI Rapor Sunucusu web portalında içeriği görüntüleyin.

    ![Web portalı](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capture-the-url-parameter"></a>URL parametresini yakalama

URL'nizi edindikten sonra, raporun barındırılması için bir SharePoint sayfasında iFrame oluşturabilirsiniz. Herhangi bir Power BI Rapor Sunucusu rapor URL’si için, raporunuzu bir SharePoint iFrame'e eklemek üzere şu sorgu dizesi parametresini ekleyin: `?rs:embed=true`.

   Örnek:
    ``` 
    https://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embed-the-report-in-a-sharepoint-iframe"></a>Raporu bir SharePoint iFrame'e ekleme

1. SharePoint **Site İçeriği** sayfasına gidin.

    ![Site İçeriği sayfası](media/quickstart-embed/quickstart_embed_05.png)

2. Raporunuzu eklemek istediğiniz sayfayı seçin.

    ![Site İçeriği sayfası uygulaması](media/quickstart-embed/quickstart_embed_06.png)

3. Sağ üst kısımdaki dişli simgesini ve sonra **Sayfayı düzenle**’yi seçin.

    ![Sayfayı düzenle seçeneği](media/quickstart-embed/quickstart_embed_07.png)

4. **Web Bölümü Ekle**’yi seçin.

5. **Kategoriler** altında **Medya ve İçerik**’i seçin. **Bölümler** altında **İçerik Düzenleyicisi**’ni ve **Ekle**’yi seçin.

    ![İçerik Düzenleyicisi Web Bölümü seçme](media/quickstart-embed/quickstart_embed_09.png)

6. **Yeni içerik eklemek için buraya tıklayın** öğesini seçin.

7. Üstteki menüden **Metin Biçimlendir**’i ve ardından **Kaynağı Düzenle**’yi seçin.

     ![Kaynağı Düzenle](media/quickstart-embed/quickstart_embed_11.png)

8. **Kaynağı Düzenle** penceresinde iFrame kodunuzu **HTML Kaynağı** içine yapıştırıp **Tamam**’ı seçin.

    ![iFrame kodu](media/quickstart-embed/quickstart_embed_12.png)

     Örnek:
     ```html
     <iframe width="800" height="600" src="https://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. Üstteki menüde **Sayfa**’yı ve sonra **Düzenlemeyi Durdur**’u seçin.

    ![Düzenlemeyi Durdur](media/quickstart-embed/quickstart_embed_13.png)

    Rapor, sayfada görüntülenir.

    ![iFrame örneği](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Rapor Sunucusu için Power BI raporu oluşturma](quickstart-create-powerbi-report.md).  
- [Power BI Rapor Sunucusu için sayfalandırılmış rapor oluşturma](quickstart-create-paginated-report.md).  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/).