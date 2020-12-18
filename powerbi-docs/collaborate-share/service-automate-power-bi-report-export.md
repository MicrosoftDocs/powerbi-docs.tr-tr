---
title: Power Automate ile bir raporu dışarı aktarma ve e-posta ile gönderme
description: Bu makalede Power BI raporlarının desteklenen biçimlerde ve senaryolarda dışarı aktarılmasını ve dağıtılmasını otomatikleştirmek için Power Automate kullanırsınız.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: how-to
ms.date: 12/10/2020
LocalizationGroup: Get started
ms.openlocfilehash: 45bccbefc6e499375d33aa049ead8a6c6e47bc8c
ms.sourcegitcommit: bbf7e9341a4e1cc96c969e24318c8605440282a5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97098838"
---
# <a name="export-and-email-a-power-bi-report-with-power-automate"></a>Power Automate ile bir Power BI raporunu dışarı aktarma ve e-posta ile gönderme

[Power Automate](/power-automate/getting-started) ile Power BI raporlarını çeşitli biçim ve senaryolarda dışarı aktarma ve dağıtma işlemlerini otomatikleştirebilirsiniz. Bu makalede kendi akışınızı sıfırdan oluşturacaksınız. Power BI raporunu e-posta yoluyla otomatik olarak dağıtmak için Power BI Raporları’nın Dosyaya Aktar eylemini kullanırsınız.

:::image type="content" source="media/service-automate-power-bi-report-export/automate-power-bi-report-overview.png" alt-text="Raporu dışarı aktarmak ve e-postayla göndermek için Power Automate adımları.":::

## <a name="prerequisites"></a>Önkoşullar  

Buradaki adımları takip etmek için aşağıdakilere sahip olduğunuzdan emin olun:

- Power BI kiracınızda ayrılmış kapasiteye sahip olan en az bir çalışma alanı. Bu kapasite A1/EM1 - A6/P3 SKU'larından herhangi biri olabilir. [Power BI Premium'daki ayrılmış kapasiteler](../admin/service-premium-what-is.md) hakkında daha fazla bilgi edinin.
- Power Automate'teki standart bağlayıcılara erişim (tüm Office 365 abonelikleriyle sunulur).

## <a name="create-a-flow-from-scratch"></a>Sıfırdan akış oluşturma 

Bu görevde sıfırdan basit bir akış oluşturacaksınız. Akış, Power BI raporunu PDF olarak dışarı aktarır ve haftada bir gönderilmek üzere e-postaya ekler.  

1. Power Automate’te oturum açın (flow.microsoft.com).
2. **Oluştur** > **Zamanlanan akış**’ı seçin. 

    :::image type="content" source="media/service-automate-power-bi-report-export/automate-report-scheduled-flow-2.png" alt-text="Power Automate’de zamanlanan akış oluşturun.":::

3. **Zamanlanan akış oluştur** alanında akışınıza bir ad verin. 
4. **Bu akışı çalıştır** alanında akışınızın başlangıç tarihi ve saatiyle yinelenme sıklığını seçin.
5. **Şu günlerde** alanında akışınızın çalışmasını istediğiniz günleri belirtin ve **Oluştur**’u seçin.

    :::image type="content" source="media/service-automate-power-bi-report-export/automate-report-build-flow-5.png" alt-text="Power Automate, akış için zamanlama.":::

6. **Yinelenme** bölümünde **Gelişmiş seçenekleri göster**’i seçin ve akışınızın çalışacağı belirli saatleri ayarlamak için **Şu saatlerde** ve **Şu dakikalarda** alanlarına değer girin.
 
    :::image type="content" source="media/service-automate-power-bi-report-export/automate-report-recurrence-6.png" alt-text="Power Automate’de yinelemeyi ayarlayın.":::

7. **Yeni adım** seçeneğini belirleyin.
8. **Bir eylem seçin** bölümünde **Power BI**’ı arayın ve **Power BI raporları için Dosyaya Aktar** seçeneğini belirleyin.
 
    :::image type="content" source="media/service-automate-power-bi-report-export/automate-report-choose-action-8.png" alt-text="Power Automate’de bir eylem seçin.":::

9. **Power BI raporları için Dosyaya Aktar** bölümünde açılan listeden bir **Çalışma alanı** ve **Rapor** seçin.
10. Power BI raporunuz için istediğiniz **Dışarı Aktarma Biçimi**'ni seçin.
 
    :::image type="content" source="media/service-automate-power-bi-report-export/automate-report-export-file-10.png" alt-text="Power Automate’de dışarı aktarma biçimini seçin.":::

11. İsteğe bağlı olarak, **Sayfalar pageName -1** alanında dışarı aktarılacak belirli sayfaları gösterin. Sayfa adı parametresinin görüntülenen sayfa adından farklı olduğunu unutmayın. Sayfa adını, Power BI hizmetinde sayfaya gidip URL’nin son bölümünü kopyalayarak alın.
 
     :::image type="content" source="media/service-automate-power-bi-report-export/automate-report-copy-url-11.png" alt-text="U R L'de bölme adını seçin.":::

12. İsteğe bağlı olarak, **Sayfaların Yer İşareti Adı** alanında görüntülenecek belirli bir yer işareti belirtin. Sayfa adı parametresinde de olduğu gibi yer işareti parametresini rapor URL’sinde bulabilirsiniz. Power BI raporu için ek parametreler belirtebilirsiniz. Bu parametrelerle ilgili ayrıntılı açıklamalar için bkz. [Power BI REST API için bağlayıcı başvurusu](/connectors/powerbi/#export-to-file-for-power-bi-reports).

    :::image type="content" source="media/service-automate-power-bi-report-export/automate-report-bookmark-url-12.png" alt-text="U R L'de yer işareti adını seçin.":::

13. **Yeni adım** seçeneğini belirleyin.
14. **Bir eylem seçin** bölümünde **Outlook**’u arayın ve **E-posta gönder (V2)** seçeneğini belirtin.
15. **E-posta gönder (V2)** bölümünde e-postanızın **Alıcı**, **Konu** ve **Gövde** alanlarını doldurun.
16. **Gelişmiş seçenekleri göster**’i seçin. **Ek Adı – 1** alanında ekiniz için bir ad girin. Dosya adına, istediğiniz **Dışarı Aktarma Biçimi** ile eşleşen bir dosya uzantısı ekleyin (örneğin .PDF).
17. **Ek İçeriği**’nde **Dosya İçeriği**'ni seçerek dışarı aktardığınız Power BI raporunu ekleyin.  
 
    :::image type="content" source="media/service-automate-power-bi-report-export/automate-report-send-email-17.png" alt-text="E-postayla göndermek üzere dışarı aktarılan raporunuzu seçin.":::

18. İşlemleri tamamladığınızda **Sonraki adım**'ı veya **Kaydet**'i seçin. Power Automate akışı oluşturup değerlendirir ve varsa hataları bildirir.
1. Hatalar varsa **Akışı düzenle** ile düzeltin. Yoksa **Geri** okunu seçerek akış ayrıntılarını görüntüleyin ve yeni akışı çalıştırın.
    Akışı çalıştırdığınızda Power Automate, Power BI raporunu belirtilen biçimde dışarı aktarır ve onu zamanlanan saatte bir e-posta eki olarak gönderir.  

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI veri uyarılarını Power Automate ile tümleştirme](service-flow-integration.md)
- [Power Automate kullanmaya başlama](/power-automate/getting-started/)
- Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
