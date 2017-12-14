---
title: "Power BI ile Microsoft Azure Kurumsal'a bağlanma"
description: "Power BI için Microsoft Azure Kurumsal"
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
ms.openlocfilehash: 39c3fd776e3aed821c7c10c1e905d7400ca64efd
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-microsoft-azure-enterprise-with-power-bi"></a>Power BI ile Microsoft Azure Kurumsal'a bağlanma
Power BI içerik paketi ile Power BI'da Microsoft Azure Kurumsal verilerinizi araştırın ve izleyin. Veriler günde bir kez otomatik olarak yenilenir.

Power BI için [Microsoft Azure Kurumsal içerik paketine](https://app.powerbi.com/getdata/services/azure-enterprise) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmındaki **Veri Al**'ı seçin.
   
    ![](media/service-connect-to-azure-enterprise/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-azure-enterprise/services.png)
3. **Microsoft Azure Enterprise** \> **Al**'ı seçin.
   
   ![](media/service-connect-to-azure-enterprise/mazureenterprise.png)
4. Azure Ortamı URL'sini, son kaç aya ilişkin veriyi içeri aktarmak istediğinizi ve Azure Kurumsal aboneliğinizin kayıt numarasını girin. Azure Ortamı URL'niz `https://ea.azure.com` veya `https://ea.windowsazure.cn` olacaktır. [Bu parametreleri bulmaya](#FindingParams) ilişkin ayrıntılı bilgi için aşağıya bakın.
   
    ![](media/service-connect-to-azure-enterprise/params.png)
5. Bağlanmak için Erişim anahtarınızı girin. Kaydınıza ilişkin anahtarı Azure EA Portalı'nda bulabilirsiniz.
   
    ![](media/service-connect-to-azure-enterprise/creds.png)
6. İçeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
   ![](media/service-connect-to-azure-enterprise/dashboard.png)

**Sırada ne var?**

* Panonun üst kısmındaki [Soru-Cevap kutusunu kullanarak bir soru sormayı](service-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
Azure Enterprise içerik paketi, bağlantı akışı sırasında sağladığınız ay aralığına ilişkin aylık raporlama verilerini içerir. Bu değişken bir aralık olduğundan, dahil edilen tarihler veri kümesi yenilendikçe güncelleştirilir.

## <a name="system-requirements"></a>Sistem Gereksinimleri
İçerik paketi için Azure Portal'da Kurumsal özelliklerine erişim gereklidir.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Power BI raporlama özelliği, fatura bilgilerini görüntüleyebilen EA Doğrudan, İş Ortağı ve Dolaylı Müşterileri tarafından kullanılabilir. Bağlantı akışında sağlamanız gereken değerlerin her birini nasıl bulacağınız hakkında ayrıntılı bilgi almak için lütfen aşağıdaki bölümü okuyun.

**Azure Ortamı URL'si**

* Bu değer genellikle https://ea.azure.com'dur ancak onaylamak için, oturum açtıktan sonra URL'yi kontrol edebilirsiniz.
  
    ![](media/service-connect-to-azure-enterprise/params3.png)

**Ay Sayısı**

* Bu değer, (içinde bulunduğunuz günden itibaren) son kaç aya ilişkin veriyi içeri aktarmak istediğinizi belirten, 1 ila 36 arasında bir sayı olmalıdır.

**Kayıt Numarası**

* Bu numara, [Azure Enterprise Portal](https://ea.azure.com/)'ın giriş ekranındaki "Kayıt Ayrıntıları" bölümünde bulabileceğiniz Azure Kurumsal kayıt numaranızdır.
  
    ![](media/service-connect-to-azure-enterprise/params2.png)

**Erişim Anahtarı**

* Anahtarınızı, Azure Enterprise Portal'da "İndirme Kullanımı" > "API Erişim Anahtarı" bölümünde bulabilirsiniz
  
    ![](media/service-connect-to-azure-enterprise/creds2.png)

**Daha Fazla Yardım**

* Azure Enterprise Power BI Paketini ayarlama hakkında daha fazla yardım almak istiyorsanız Azure Enterprise Portal'da oturum açın, "Yardım" bölümündeki API Yardım Dosyasını ve Raporlar -> İndirme Kullanımı -> API Erişim Anahtarı bölümündeki ek yönergeleri görüntüleyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

