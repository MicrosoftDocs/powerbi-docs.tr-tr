---
title: "Power BI ile Azure Search'e bağlanma"
description: "Power BI için Azure Search"
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
ms.openlocfilehash: eb106547efa67accacd3c955d53bc9ac4d114d8e
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-azure-search-with-power-bi"></a>Power BI ile Azure Search'e bağlanma
Azure Search Trafik Analizi, Azure Search hizmetinize ilişkin trafiği izleyip anlamanıza olanak sağlar. Power BI için Azure Search içerik paketi, son 30 güne ait Arama ve Dizin Oluşturma verilerinin yanı sıra Hizmet İstatistikleri ve Gecikme Süreleri de dahil olmak üzere Search verilerinize ilişkin ayrıntılı öngörüler sağlar. Daha ayrıntılı bilgiye [Azure blog gönderisinden](https://azure.microsoft.com/en-us/blog/analyzing-your-azure-search-traffic/) ulaşabilirsiniz.

Power BI için [Azure Search içerik paketine](https://app.powerbi.com/getdata/services/azure-search) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmındaki **Veri Al**'ı seçin.
   
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

* Panonun üst kısmındaki [Soru-Cevap kutusunu kullanarak bir soru sormayı](service-q-and-a.md) deneyin
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

