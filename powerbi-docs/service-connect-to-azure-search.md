---
title: Power BI ile Azure Search'e bağlanma
description: Power BI için Azure Search
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 1d67b100620d4517e657f92acb37e370f2bb540e
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34480969"
---
# <a name="connect-to-azure-search-with-power-bi"></a>Power BI ile Azure Search'e bağlanma
Azure Search Trafik Analizi, Azure Search hizmetinize ilişkin trafiği izleyip anlamanıza olanak sağlar. Power BI için Azure Search içerik paketi, son 30 güne ait Arama ve Dizin Oluşturma verilerinin yanı sıra Hizmet İstatistikleri ve Gecikme Süreleri de dahil olmak üzere Search verilerinize ilişkin ayrıntılı öngörüler sağlar. Daha ayrıntılı bilgiye [Azure blog gönderisinden](https://azure.microsoft.com/blog/analyzing-your-azure-search-traffic/) ulaşabilirsiniz.

Power BI için [Azure Search içerik paketine](https://app.powerbi.com/getdata/services/azure-search) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-azure-search/pbi_getdata.png) 
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-azure-search/pbi_getservices.png) 
3. **Azure Search** \> **Al**'ı seçin.
   
   ![](media/service-connect-to-azure-search/azuresearch.png)
4. Azure Search analizinizin depolandığı tablo depolama hesabının adını girin.
   
   ![](media/service-connect-to-azure-search/params.png)
5. Kimlik Doğrulama Yöntemi olarak **Anahtar** seçeneğini belirleyin ve depolama hesabı anahtarınızı girin. **Oturum Aç**'a tıklayın ve yükleme işlemine başlayın.
   
   ![](media/service-connect-to-azure-search/creds.png)
6. Yükleme işlemi tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
    ![](media/service-connect-to-azure-search/dashboard2.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
Azure Search içerik paketi için hesapta Azure Search Trafik Analizi'nin etkinleştirilmesi gerekir.

## <a name="troubleshooting"></a>Sorun giderme
Depolama hesabı adının, tam erişim anahtarıyla birlikte doğru şekilde sağlandığından emin olun. Depolama hesabı adı, Azure Search Trafik Analizi ile yapılandırılan hesaba karşılık gelmelidir.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

