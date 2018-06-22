---
title: Power BI ile ServiceNow'a bağlanma
description: Power BI için ServiceNow
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 4b05fcc005f821c4fee24071f28651b5df57709c
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249356"
---
# <a name="connect-to-servicenow-with-power-bi-for-incident-reporting"></a>Olay raporlama için Power BI ile ServiceNow'a bağlanma
ServiceNow işinizi geliştirmek için iş, operasyon ve BT yönetimi dahil olmak üzere birden fazla ürün ve çözüm sunar. Bu içerik paketi açık, yakın zamanda çözümlenmiş ve yakın zamanda kapatılan olaylar hakkında birden fazla rapor ve öngörü içerir.  

[ServiceNow Incidents](https://app.powerbi.com/getdata/services/servicenow) için Power BI içerik paketine bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-servicenow/pbi_getdata.png) 
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-servicenow/pbi_getservices.png) 
3. **ServiceNow Incidents** \> **Al**'ı seçin.
   
   ![](media/service-connect-to-servicenow/connect.png)
4. ServiceNow örneğinizin URL'sini ve getirilecek gün/kayıt aralığını belirtin. Bir sınırı girdiğinizde içeri aktarmanın durdurulacağını unutmayın.
   
   ![](media/service-connect-to-servicenow/params.png)
5. İstendiğinde, ServiceNow **Temel** kimlik bilgilerinizi girin. Çoklu oturum açma özelliği şu anda desteklenmemektedir, sistem gereksinimlerine ilişkin daha fazla bilgi için aşağıya bakın.
   
   ![](media/service-connect-to-servicenow/creds.png)
6. Oturum açma akışı tamamlandığında içeri aktarma işlemi başlar. İçeri aktarma işlemi sona erdiğinde, Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
    ![](media/service-connect-to-servicenow/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
Bağlanmak için şunlar gereklidir:  

* Temel kimlik doğrulaması ile yourorganization.service-now.com adresine erişebilen bir hesap (Çoklu Oturum Açma özelliği bu sürümde desteklenmemektedir)  
* Hesap rest_service rolüne ve olay tablosunu okuma erişimine sahip olmalıdır  

## <a name="troubleshooting"></a>Sorun giderme
Yükleme sırasında bir kimlik bilgisi hatası ile karşılaşıyorsanız lütfen yukarıdaki erişim gereksinimlerini gözden geçirin. Doğru izinlere sahipseniz ve yine de sorunlarla karşılaşıyorsanız lütfen özel örneğiniz için gerekli olabilecek tüm ek izinlere sahip olduğunuzdan emin olmak üzere ServiceNow yöneticiniz ile iletişime geçin.

Yükleme çok uzun sürüyorsa bağlantı sırasında belirttiğiniz olay sayısını ve gün sayısını gözden geçirip bunları azaltmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

