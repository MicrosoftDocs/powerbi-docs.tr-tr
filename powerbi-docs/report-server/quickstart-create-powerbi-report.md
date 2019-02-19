---
title: Power BI Rapor Sunucusu için Power BI raporu oluşturma
description: Power BI Rapor Sunucusu için birkaç kolay adımda Power BI raporu oluşturmayı öğrenin.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 09/19/2018
ms.author: maghan
ms.openlocfilehash: 7d97e375f7743b381f222d64e230d71133060464
ms.sourcegitcommit: 91ac6185f7026ddbaa925dc54057bb742b4fa411
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2019
ms.locfileid: "56324887"
---
# <a name="create-a-power-bi-report-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için Power BI raporu oluşturma
Power BI raporlarını, bulut üzerindeki Power BI hizmetinde (https://powerbi.com)) depoladığınız gibi şirket içi Power BI Rapor Sunucusu web portalında da depolayabilir ve yönetebilirsiniz. Raporları Power BI Desktop uygulamasında oluşturup düzenledikten sonra web portalında yayımlarsınız. Ardından kuruluşunuzdaki rapor okuyucuları bu raporları bir tarayıcıda veya mobil cihazlarındaki Power BI mobil uygulamasında görüntüleyebilir.

![Web portalında Power BI raporu](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

Hemen başlamanızı sağlayacak 4 adım:

## <a name="step-1-install-power-bi-desktop-optimized-for-power-bi-report-server"></a>1. Adım: Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yükleme

Power BI Desktop uygulamasında Power BI raporları oluşturduysanız Power BI Rapor Sunucusu için Power BI raporları oluşturmaya neredeyse hazırsınız demektir. Sunucunun ve uygulamanın her zaman eşitlenmesini sağlamak üzere, Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop sürümünü yüklemenizi öneririz. Power BI Desktop uygulamasının iki sürümünü de aynı bilgisayarda kullanabilirsiniz.

1. Rapor sunucusu web portalında, **İndir** okunu ve ardından **Power BI Desktop**'ı seçin.

    ![Web portalından Power BI Desktop'ı indirme](media/quickstart-create-powerbi-report/report-server-download-web-portal.png)

    Alternatif olarak, Microsoft İndirme Merkezi'nde doğrudan [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=57271) (Power BI Rapor Sunucusu için en iyi duruma getirilmiş - Ağustos 2018) sayfasına da gidebilirsiniz.

2. İndirme Merkezi sayfasında, **İndir** seçeneğini belirleyin.

3. Bilgisayarınıza bağlı olarak, şu seçeneklerden birini belirleyin:

    - **PBIDesktopRS.msi** (32 bit sürümü) veya

    - **PBIDesktopRS_x64.msi** (64 bit sürümü).

4. Yükleyiciyi indirdikten sonra, Power BI Desktop (Ağustos 2018) Kurulum Sihirbazını çalıştırın.

2. Yüklemenin sonunda **Start Power BI Desktop now** (Power BI Desktop'ı şimdi başlat) onay kutusunu işaretleyin.
   
    Uygulama otomatik olarak başlatılır ve kullanımınıza hazır hale gelir. Başlık çubuğundaki "Power BI Desktop (Ağustos 2018)" ifadesi, doğru sürüme sahip olduğunuzu gösterir.

    ![Power BI Desktop Ağustos 2018 sürümü](media/quickstart-create-powerbi-report/power-bi-report-server-desktop-august-2018.png)

3. Power BI Desktop uygulamasını daha önceden kullanmadıysanız karşılama ekranındaki videoları izlemek isteyebilirsiniz.
   
    ![Power BI Desktop başlangıç ekranı](media/quickstart-create-powerbi-report/report-server-powerbi-desktop-start.png)

## <a name="step-2-select-a-data-source"></a>2. Adım: Veri kaynağı seçme
Çok çeşitli veri kaynaklarına bağlanabilirsiniz. [Veri kaynaklarına bağlanma](connect-data-sources.md) hakkında daha fazla bilgi edinin.

1. Karşılama ekranında **Veri Al**'ı seçin.
   
    Alternatif olarak, **Giriş** sekmesindeki **Veri Al** seçeneğini de belirleyebilirsiniz.
2. Veri kaynağınızı seçin. Bu örnekte **Analysis Services** kullanılmıştır.
   
    ![Veri kaynağı seçme](media/quickstart-create-powerbi-report/report-server-get-data-ssas.png)
3. **Sunucu** alanını ve isterseniz **Veritabanı** alanını doldurun. **Canlı bağlan**'ın seçili olduğundan emin olun ve **Tamam**'ı seçin.
   
    ![Sunucu adı](media/quickstart-create-powerbi-report/report-server-ssas-server-name.png)
4. Raporlarınızı kaydedeceğiniz rapor sunucusunu seçin.
   
    ![Rapor sunucusu seçimi](media/quickstart-create-powerbi-report/report-server-select-server.png)

## <a name="step-3-design-your-report"></a>3. Adım: Raporunuzu tasarlama
İşte işin eğlenceli bölümüne geldik: Verilerinizi gösteren görselleştirmeler oluşturabilirsiniz.

Örneğin müşterilerinizi içeren bir huni grafik oluşturup değerleri yıllık gelire göre gruplandırabilirsiniz.

![Rapor tasarlama](media/quickstart-create-powerbi-report/report-server-create-funnel.png)

1. **Görsel Öğeler** bölümünde **Huni grafiği**'ni seçin.
2. Sayılacak alanı **Değerler** kutusuna sürükleyin. Söz konusu alan sayısal değilse Power BI Desktop bu alanı, otomatik olarak alanın *sayımına* dönüştürür.
3. Alanı **Grup** kutusundaki gruba sürükleyin.

[Power BI raporu tasarlama](../desktop-report-view.md) hakkında daha fazla bilgi edinin.

## <a name="step-4-save-your-report-to-the-report-server"></a>4. Adım: Raporunuzu rapor sunucusuna kaydetme
Hazırladığınız raporu, 2. Adımda seçtiğiniz Power BI Rapor Sunucusu'na kaydedebilirsiniz.

1. **Dosya** menüsünde, **Farklı kaydet** > **Power BI Rapor Sunucusu**'nu seçin.
   
    ![Rapor sunucusuna kaydetme](media/quickstart-create-powerbi-report/report-server-save-as-powerbi-report-server.png)
2. Artık bu raporu web portalında görüntüleyebilirsiniz.
   
    ![Raporu web portalında görüntüleme](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

## <a name="next-steps"></a>Sonraki adımlar
### <a name="power-bi-desktop"></a>Power BI Desktop
Power BI Desktop'ta rapor oluşturmak için faydalanabileceğiniz birçok harika kaynak vardır. Bu bağlantıyı iyi bir başlangıç noktasıdır.

* [Power BI Desktop ile çalışmaya başlama](../desktop-getting-started.md)
* Destekli öğrenim: [Power BI Desktop ile çalışmaya başlama](../guided-learning/gettingdata.yml?tutorial-step=2)

### <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu
* [Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yükleme](install-powerbi-desktop.md)  
* [Power BI Rapor Sunucusu nedir?](get-started.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
