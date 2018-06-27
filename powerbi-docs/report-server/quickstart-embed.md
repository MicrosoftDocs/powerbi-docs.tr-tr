---
title: iFrame kullanarak rapor gömme
description: Power BI Rapor Sunucusu raporunu SharePoint Server’da bir iFrame’e ekleme
author: markingmyname
ms.author: maghan
ms.date: 05/04/2018
ms.topic: quickstart
ms.service: powerbi
ms.component: powerbi-report-server
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 8d7653e6f390959df745fa2b19076ee89b26b1bc
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34293709"
---
# <a name="quickstart-embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>Hızlı Başlangıç: Power BI Rapor Sunucusu raporunu SharePoint Server’da bir iFrame kullanarak ekleme

Bu hızlı başlangıçta, bir SharePoint sayfasında iFrame kullanarak bir Power BI Rapor Sunucusu raporunu eklemeyi öğreneceksiniz. SharePoint Online ile çalışıyorsanız, Power BI Rapor Sunucusu genel erişime açık olmalıdır. SharePoint Online’da Power BI hizmeti ile çalışan Power BI Web Bölümü, Power BI Rapor Sunucusu ile birlikte çalışmaz. 

![iFrame örneği](media/quickstart-embed/quickstart_embed_01.png)
## <a name="prerequisites"></a>Önkoşullar
* [Power BI Rapor Sunucusu](https://powerbi.microsoft.com/en-us/report-server/) yüklü ve yapılandırılmış olmalıdır.
* [Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop](install-powerbi-desktop.md) uygulaması yüklü olmalıdır.
* Bir [SharePoint](https://docs.microsoft.com/en-us/sharepoint/install/install) ortamı yüklü ve yapılandırılmış olmalıdır.

## <a name="creating-the-power-bi-report-server-report-url"></a>Power BI Rapor Sunucusu rapor URL'si oluşturma

1. Github'dan örneği indirin - [Blog Tanıtımı](https://github.com/Microsoft/powerbi-desktop-samples).

    ![Örnek PBIX dosyasını indirme](media/quickstart-embed/quickstart_embed_14.png)

2. **Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop** uygulamasında GitHub’dan örnek PBIX dosyasını açın.

    ![PBI RS Masaüstü aracı](media/quickstart-embed/quickstart_embed_02.png)

3. Raporu **Power BI Rapor Sunucusu**’na kaydedin. 

    ![PBI RS Kaydetme](media/quickstart-embed/quickstart_embed_03.png)

4. Raporu **Web Portalında** görüntüleyin.

    ![Web Portalı](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capturing-the-url-parameter"></a>URL parametresini yakalama

URL'nizi edindikten sonra, raporun barındırılması için bir SharePoint sayfasında iFrame oluşturabilirsiniz. Herhangi bir Power BI Rapor Sunucusu rapor URL’si için raporunuzu bir iFrame’e eklemek üzere bir `?rs:embed=true` sorgu dizesi parametresi ekleyebilirsiniz. 

   Örnek:
    ``` 
    http://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embedding-a-power-bi-report-server-report-in-a-sharepoint-iframe"></a>Power BI Rapor Sunucusu raporunu SharePoint iFrame’e ekleme

1. SharePoint **Site İçeriği** sayfasına gidin.

    ![Site İçeriği Sayfası](media/quickstart-embed/quickstart_embed_05.png)

2. Raporunuzu eklemek istediğiniz sayfayı seçin.

    ![Site İçeriği Sayfası Uygulaması](media/quickstart-embed/quickstart_embed_06.png)

3. Sağ üst kısımdaki dişli simgesini ve **Sayfayı Düzenle**’yi seçin.

    ![Sayfayı Düzenle seçeneği](media/quickstart-embed/quickstart_embed_07.png)

4. **Web Bölümü Ekle**’yi seçin.

    ![Web Bölümü Ekleme](media/quickstart-embed/quickstart_embed_08.png)

5. **Kategoriler** altında **Medya ve İçerik**’i seçin, **Bölümler** altında **İçerik Düzenleyicisi**’ni ve sonra **Ekle**’yi seçin.

    ![İçerik Düzenleyicisi Web Bölümü seç](media/quickstart-embed/quickstart_embed_09.png) ![Ekle’yi seç](media/quickstart-embed/quickstart_embed_091.png)

6. **Yeni içerik eklemek için buraya tıklayın** öğesini seçin.

    ![Yeni içerik ekleme](media/quickstart-embed/quickstart_embed_10.png)

7. Şeritte **Metni Biçimlendir** sekmesini ve sonra **Kaynağı Düzenle**’yi seçin.

     ![Kaynağı Düzenle](media/quickstart-embed/quickstart_embed_11.png)

8. Kaynağı Düzenle penceresinde iFrame kodunuzu yapıştırıp Tamam’ı seçin.

    ![iFrame kodu](media/quickstart-embed/quickstart_embed_12.png)

     Örnek:
     ```
     <iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. Şeritte **Sayfa** sekmesini ve **Düzenlemeyi Durdur**’u seçin.

    ![Düzenlemeyi Durdur](media/quickstart-embed/quickstart_embed_13.png)

10. Şimdi raporu sayfada görmeniz gerekir.

    ![iFrame örneği](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>Sonraki adımlar

[Hızlı Başlangıç: Power BI Rapor Sunucusu için Power BI raporu oluşturma](quickstart-create-powerbi-report.md)  
[Hızlı Başlangıç: Power BI Rapor Sunucusu için sayfalandırılmış rapor oluşturma](quickstart-create-paginated-report.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/) 