---
title: "Power BI için Cortana'yı etkinleştirme"
description: "Verilerinizle ilgili sorularınıza cevap almak için Power BI ile Cortana'yı kullanın. Her bir Power BI veri kümesi için Cortana'yı etkinleştirin ve Cortana'nın, Windows cihazlarından veri kümelerinize erişebilmesini sağlayın."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
editor: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/20/2017
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 10faf7b20c91b0c709df6783152ab55d0e6c958c
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="enable-cortana-to-access-power-bi-reports-and-their-underlying-datasets"></a>Cortana'nın, Power BI raporlarına (ve bağlantılı veri kümelerine) erişebilmesini sağlama
[Cortana ve Power BI'a Giriş](service-cortana-intro.md) konulu makaleyi okudunuz. (Henüz okumadıysanız öncelikle bu makaleyi okumak isteyebilirsiniz.) Şimdi söz konusu işlemleri kendiniz gerçekleştirmek istiyorsunuz.  Cortana'da doğal dilde sorular sorup Power BI ***raporlarında*** depolanan verilerden yanıtlar elde edebilmeniz için karşılamanız gereken birkaç gereksinim mevcuttur. Aşağıdakileri yapmanız gerekir.

> [!NOTE]
> Cortana ve Power BI ***panosu*** önizlemesini kullanıyorsanız bu makalenin geri kalan kısmını okumanıza gerek yoktur. Cortana'nın, Power BI panolarınızda arama yapabilmesi için herhangi bir kurulum gereksinimi yoktur.
> 
> 

Power BI hizmetinde

* Cortana için bir veya daha fazla veri kümesi etkinleştirin (raporlar veri kümeleri temel alınarak oluşturulduğundan Cortana'nın bu veri kümelerine erişebilmesi gerekir)

Microsoft Windows'da

* Windows 10'un 1511 veya sonraki bir sürümüne sahip olduğunuzdan emin olun
* Power BI ile Windows'un "iletişim kurabildiğinden" emin olun. Bu, hesabınızla Windows arasında bağlantı kuracağınız anlamına gelir.

## <a name="use-power-bi-service-to-enable-cortana-to-access-report-pages-in-power-bi"></a>Power BI hizmetini kullanarak Cortana'nın Power BI'daki rapor sayfalarına erişebilmesini sağlama
Cortana'nın Power BI'daki raporlara erişimini sağlamak basit bir işlemdir.  Tüm yapmanız gereken "Bu veri kümesine erişebilmesi için Cortana'yı etkinleştirin" seçeneğini belirleyerek ilgili raporun bağlantılı veri kümesini etkinleştirmektir. Bu işlemin ardından, Power BI'daki veri kümesine normal Power BI paylaşımı, uygulamalar ve içerik paketi özellikleri aracılığıyla erişimi olan tüm kullanıcılar Windows 10 işletim sistemi yüklü bir cihazda Cortana'yı kullanarak raporla ilgili sorularına yanıtlar alabilir.

Power BI hizmetinde (Power BI Desktop değil) oturum açıp Cortana'nın erişebilmesini istediğiniz her veri kümesi için bu adımları yinelemeniz gerekir.

1. Hangi veri kümelerinin etkinleştirileceğini belirleyin. Rapor içerik listesinde, Cortana'nın erişmesini istediğiniz raporu ve ardından **İlişkilileri görüntüle** simgesini ![](media/service-cortana-enable/power-bi-cortana-view-related-icon.png) seçin.
   
    ![İlişkili içerikleri görüntüleme](media/service-cortana-enable/power-bi-view-related.png)
2. Bu raporla ilişkilendirilen veri kümesi **Contoso Sales**'dir.
   
    ![Contoso Sales veri kümesi](media/service-cortana-enable/power-bi-identify-dataset.png)
3. Veri kümesi adının sağında **üç nokta (...) > Ayarlar**'ı seçin.  
   
    ![Ayarlar'ı seçme](media/service-cortana-enable/power-bi-settings-cortana.png)
4. **Soru-Cevap ve Cortana** > **Cortana'nın bu veri kümesine erişmesine izin ver** > **Uygula** seçeneğini belirleyin.
   
   ![Cortana veri kümesi erişimi](media/service-cortana-enable/power-bi-cortana-enable-new.png)
   
   Bu örnekte, Contoso Sales veri kümesinde Cortana'yı etkinleştiriyoruz.
   
   > [!NOTE]
   > Yeni bir veri kümesi veya Cortana yanıt kartı Power BI'a eklenip Cortana için etkinleştirildiğinde sonuçların Cortana'da görünmeye başlaması 30 dakika sürebilir. Windows 10 oturumunu kapatıp tekrar açtığınızda veya Windows 10'daki Cortana işlemini başka bir şekilde yeniden başlattığınızda yeni içerik anında görünür hale gelir.
   > 
   > Cortana için etkinleştirdiğiniz bir veri kümesi, sahip olduğunuz bir içerik paketine veya uygulamaya aitse iş arkadaşlarınızın da Cortana ile kullanabilmesi için veri kümesini yeniden yayımlamanız gerekir.
   > 
   > 

## <a name="add-your-power-bi-credentials-to-windows"></a>Windows'a Power BI kimlik bilgilerinizi ekleme
Windows 10'un 1511 veya sonraki bir sürümünün yüklü olması gerekir.

1. Windows 10'un hangi sürümünü kullandığınızı belirleyin. **Ayarlar**'ı açın.
    ![Windows ayarlarını açın](media/service-cortana-enable/power-bi-cortana-windows.png)

    **Sistem > Hakkında**'yı seçin. Ekranın alt tarafında **Windows özellikleri > Sürüm** seçeneğini göreceksiniz

   * Windows 10'un 1511 (Windows 10 Kasım 2015 Güncelleştirmesi) ila 1607 arası bir sürümüne sahipseniz iş yeri veya okul hesabınızı ve Microsoft hesabınızı ekleyin. (Aşağıdaki 2. ve 3. adımları tamamlayın.)
   * Windows 10'un 1607 (Windows 10 Temmuz 2016 Güncelleştirmesi) veya sonraki bir sürümüne sahipseniz iş yeri veya okul hesabınızı ekleyin. (Aşağıdakiler arasından yalnızca 2. adımı tamamlayın.)
1. Cortana için iş yeri veya okul hesabınızı ekleyin.
   
   * **Ayarlar** > **Hesaplar**'ı açın.
     
       ![Ayarlar - Hesaplar](media/service-cortana-enable/power-bi-windows-accounts.png)
   * Sayfanın en altına gidin ve **İş yeri veya okul hesabı ekle** seçeneğini belirleyin. Veya **Hesaplar** sayfasından **İş yeri veya okula eriş > Bağlan**'ı seçin.
     
     ![İş yeri hesabı ekleme](media/service-cortana-enable/power-bi-add-work-account2.png)

Cortana, Cortana'daki sorularınıza olası yanıtlar bulmak için Power BI'ı kontrol etmek üzere bu iş yeri veya okul hesabınızı kullanır.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'da Cortana *yanıt kartları* oluşturma](service-cortana-answer-cards.md)

[Cortana ve Power BI tümleştirmesi ile ilgili sorunlarını giderme](service-cortana-troubleshoot.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

