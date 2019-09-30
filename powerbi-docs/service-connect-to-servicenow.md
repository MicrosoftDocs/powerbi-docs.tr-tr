---
title: Power BI ile ServiceNow'a bağlanma
description: Power BI için ServiceNow
author: KesemSharabi
ms.author: sarinas
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
LocalizationGroup: Connect to services
ms.openlocfilehash: 9fc0360ccf2e036cca1c68cf21bb538b30adf7e6
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71191000"
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

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="system-requirements"></a>Sistem Gereksinimleri
Bağlanmak için şunlar gereklidir:  

* Temel kimlik doğrulaması ile yourorganization.service-now.com adresine erişebilen bir hesap (Çoklu Oturum Açma özelliği bu sürümde desteklenmemektedir)  
* Hesap rest_service rolüne ve olay tablosunu okuma erişimine sahip olmalıdır  

## <a name="troubleshooting"></a>Sorun giderme
Yükleme sırasında bir kimlik bilgisi hatası ile karşılaşıyorsanız lütfen yukarıdaki erişim gereksinimlerini gözden geçirin. Doğru izinlere sahipseniz ve yine de sorunlarla karşılaşıyorsanız lütfen özel örneğiniz için gerekli olabilecek tüm ek izinlere sahip olduğunuzdan emin olmak üzere ServiceNow yöneticiniz ile iletişime geçin.

Yükleme çok uzun sürüyorsa bağlantı sırasında belirttiğiniz olay sayısını ve gün sayısını gözden geçirip bunları azaltmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI nedir?](power-bi-overview.md)

[Power BI hizmetinde tasarımcılar için temel kavramlar](service-basic-concepts.md)

