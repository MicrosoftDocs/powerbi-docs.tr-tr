---
title: Power Automate ile sayfalandırılmış raporu yerel bir klasöre kaydetme
description: Bu makalede sayfalandırılmış raporun istenen biçimde dosya sisteminize yinelenen aktarmalarını ayarlamak için bir şablon kullanacaksınız.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: how-to
ms.date: 12/08/2020
LocalizationGroup: Get started
ms.openlocfilehash: a30f0df972c375af4fb284ce3bba5372870d6efb
ms.sourcegitcommit: bbf7e9341a4e1cc96c969e24318c8605440282a5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97098817"
---
# <a name="save-a-power-bi-paginated-report-to-a-local-folder--with-power-automate"></a>Power Automate ile Power BI sayfalandırılmış raporunu yerel bir klasöre kaydetme

[Power Automate](/power-automate/getting-started) ile Power BI sayfalandırılmış raporlarını birçok farklı biçim ve senaryo kapsamında dışarı aktarma ve dağıtma işlemlerini otomatikleştirebilirsiniz. Bu makalede sayfalandırılmış raporun istenen biçimde dosya sisteminize yinelenen aktarmalarını ayarlamak için bir şablon kullanacaksınız. Power Automate akışında Sayfalandırılmış Raporlar için Dosyaya Aktarma eylemini ilk kez kullanıyorsanız Önkoşullar bölümüne bakın.

:::image type="content" source="media/service-automate-paginated-local-file/paginated-local-file-overview.png" alt-text="Sayfalandırılmış raporun yinelenen dışarı aktarmalarını ayarlayın.":::

Power BI sayfalandırılmış raporlarına yönelik farklı Power Automate şablonları mı arıyorsunuz? Bkz. [Power Automate ile Power BI sayfalandırılmış raporlarını dışarı aktarma](service-automate-paginated-integration.md).

## <a name="prerequisites"></a>Önkoşullar  

Buradaki adımları takip etmek için aşağıdakilere sahip olduğunuzdan emin olun:

- Power BI kiracınızda ayrılmış kapasiteye sahip olan en az bir çalışma alanı. Bu kapasite A4/P1 - A6/P3 arası SKU'lardan herhangi biri olabilir. [Power BI Premium'da sayfalandırılmış raporlar için ayrılmış kapasiteler](../admin/service-premium-what-is.md#paginated-reports) hakkında daha fazla bilgi edinin.
- Power Automate'teki standart bağlayıcılara erişim (tüm Office 365 abonelikleriyle sunulur).

## <a name="save-a-power-bi-paginated-report-to-a-local-folder"></a>Power BI sayfalandırılmış raporunu yerel klasöre kaydetme

1. **Power BI sayfalandırılmış raporunu yerel dosya sistemine kaydetme** şablonunu seçin. Power BI'da oturum açtığınızdan ve yerel dosya sisteminize bağlandığınızdan emin olun. **Devam**’ı seçin. 

    :::image type="content" source="media/service-automate-paginated-local-file/paginated-local-file-save-report-local-file-1.png" alt-text="Power BI sayfalandırılmış raporunu yerel dosya sistemine kaydedin.":::

2. Dosya sisteminize bağlanmak için **Yeni bağlantı ekle**'yi seçmeniz gerekebilir. 
1. **Bağlantı Adı**'nı, istediğiniz **Kök klasör** yolunu girin ve **Kullanıcı adı** ile **Parola** bilgilerinizi girerek kimliğinizi doğrulayın. Şirket içi veri ağ geçidi kullanıyorsanız açılan listeden bir **ağ geçidi** seçin.

    :::image type="content" source="media/service-automate-paginated-local-file/paginated-local-file-set-file-system-2.png" alt-text="Bağlantı adı ve Kök klasör girin.":::
 
3. Akışınızın **Yinelenme** sıklığı değerini ayarlamak için **Sıklık** açılan listesinden bir seçenek belirtip istediğiniz **Aralık** değerini girin.  

    :::image type="content" source="media/service-automate-paginated-local-file/paginated-local-file-recurrence-frequency-3.png" alt-text="Akışınızın Yinelenme sıklığını ayarlayın.":::

4. İsteğe bağlı olarak **Gelişmiş seçenekleri göster**'i seçin. **Saat dilimi**, **Başlangıç saati**, **Şu günlerde**, **Şu saatlerde** ve **Şu dakikalarda** gibi ek **Yinelenme** parametrelerini ayarlayın. 
 
    :::image type="content" source="media/service-automate-paginated-local-file/paginated-local-file-recurrence-advanced-4.png" alt-text="Yinelenme için gelişmiş seçenekleri ayarlayın.":::

5. **Çalışma alanı** kutusunda raporun yer aldığı ayrılmış kapasitede bulunan bir çalışma alanını seçin. **Rapor** kutusunda çalışma alanında dışarı aktarmak istediğiniz sayfalandırılmış raporu seçin. **Dışarı Aktarma Biçimi** kutusunda istediğiniz dışarı aktarma biçimini seçin. İsteğe bağlı olarak sayfalandırılmış rapora yönelik parametreler belirtebilirsiniz. Parametrelerle ilgili ayrıntılı açıklamalar için bkz. [Power BI REST API için bağlayıcı başvurusu](/connectors/powerbi/#export-to-file-for-paginated-reports).  
 
    :::image type="content" source="media/service-automate-paginated-local-file/paginated-local-file-select-workspace-report-5.png" alt-text="Çalışma alanını ve raporu seçin.":::

6. **Dosya oluştur** iletişim kutusunun **Klasör Yolu** bölümünde sayfalandırılmış raporunuzu dışarı aktarmak istediğiniz klasörü seçin.
 
    :::image type="content" source="media/service-automate-paginated-local-file/paginated-local-file-create-file-6.png" alt-text="Sayfalandırılmış raporunuzu dışarı aktarmak istediğiniz klasörü seçin":::

7. Power Automate, **Dosya adı** ve **Dosya içeriği** alanlarını sizin için otomatik olarak oluşturur. **Dosya adı** alanındaki değeri değiştirebilirsiniz ancak dinamik olarak oluşturulan **Dosya içeriği** değerini bırakın.
8. İşlemleri tamamladığınızda **Sonraki adım**'ı veya **Kaydet**'i seçin. Power Automate akışı oluşturur ve değerlendirir.
9. Power Automate hatalar bulursa, bunları düzeltmek için **Akışı düzenle**'yi seçin. Yoksa Geri okunu seçerek akış ayrıntılarını görüntüleyin ve yeni akışı çalıştırın.
10. Akışı çalıştırdığınızda Power Automate sayfalandırılmış raporu belirtilen biçimde dosya sisteminizden seçilen klasöre aktarır.

    :::image type="content" source="media/service-automate-paginated-local-file/paginated-local-file-exported-10.png" alt-text="Power Automate sayfalandırılmış raporu belirtilen biçimde dışarı aktarır.":::

## <a name="next-steps"></a>Sonraki adımlar

- [Power Automate ile Power BI sayfalandırılmış raporlarını dışarı aktarma](service-automate-paginated-integration.md)
- [Power Automate kullanmaya başlama](/power-automate/getting-started/)
- Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

