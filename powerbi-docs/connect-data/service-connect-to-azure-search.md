---
title: Power BI ile Azure Search'e bağlanma
description: Power BI için Azure Search
author: SarinaJoan
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 11389b5986d0dd627b0077808a74db5ab2769a65
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86216301"
---
# <a name="connect-to-azure-search-with-power-bi"></a>Power BI ile Azure Search'e bağlanma
Azure Search Trafik Analizi, Azure Search hizmetinize ilişkin trafiği izleyip anlamanıza olanak sağlar. Power BI için Azure Search içerik paketi, son 30 güne ait Arama ve Dizin Oluşturma verilerinin yanı sıra Hizmet İstatistikleri ve Gecikme Süreleri de dahil olmak üzere Search verilerinize ilişkin ayrıntılı öngörüler sağlar. Daha ayrıntılı bilgiye [Azure blog gönderisinden](https://azure.microsoft.com/blog/analyzing-your-azure-search-traffic/) ulaşabilirsiniz.

[!INCLUDE [include-short-name](../includes/service-deprecate-content-packs.md)]

Power BI için [Azure Search içerik paketine](https://app.powerbi.com/getdata/services/azure-search) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![Gezgin bölmesindeki düğmeyi gösteren Power BI Desktop’taki Veri Al’ın ekran görüntüsü.](media/service-connect-to-azure-search/pbi_getdata.png) 
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![Al düğmesini gösteren Hizmetler iletişim kutusunun ekran görüntüsü.](media/service-connect-to-azure-search/pbi_getservices.png) 
3. **Azure Search** \> **Al**’ı seçin.
   
   ![Al bağlantısını gösteren, Azure Services iletişim kutusunun ekran görüntüsü.](media/service-connect-to-azure-search/azuresearch.png)
4. Azure Search analizinizin depolandığı tablo depolama hesabının adını girin.
   
   ![Azure depolama hesap adı alanını gösteren, Azure Search’e Bağlan iletişim kutusunun ekran görüntüsü.](media/service-connect-to-azure-search/params.png)
5. Kimlik Doğrulama Yöntemi olarak **Anahtar** seçeneğini belirleyin ve depolama hesabı anahtarınızı girin. **Oturum Aç**'a tıklayın ve yükleme işlemine başlayın.
   
   ![Anahtarın Kimlik doğrulama yöntemi alanına girildiğini gösteren, Azure Search’e Bağlan iletişim kutusunun ekran görüntüsü.](media/service-connect-to-azure-search/creds.png)
6. Yükleme işlemi tamamlandığında gezinti bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
    ![Pano, rapor ve modeli gösteren gezinti bölmesinin ekran görüntüsü.](media/service-connect-to-azure-search/dashboard2.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](../consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](../create-reports/service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](../consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="system-requirements"></a>Sistem Gereksinimleri
Azure Search içerik paketi için hesapta Azure Search Trafik Analizi'nin etkinleştirilmesi gerekir.

## <a name="troubleshooting"></a>Sorun giderme
Depolama hesabı adının, tam erişim anahtarıyla birlikte doğru şekilde sağlandığından emin olun. Depolama hesabı adı, Azure Search Trafik Analizi ile yapılandırılan hesaba karşılık gelmelidir.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI nedir?](../fundamentals/power-bi-overview.md)

[Power BI hizmetinde tasarımcılara yönelik temel kavramlar](../fundamentals/service-basic-concepts.md)
