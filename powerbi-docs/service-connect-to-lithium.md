---
title: Power BI ile Lithium'a bağlanma
description: Power BI için Lithium
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 1d41ce3ff0c73675793e872170914b96a1d73d14
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="connect-to-lithium-with-power-bi"></a>Power BI ile Lithium'a bağlanma
Lithium, kullanıcıların, sorularına ilişkin cevaplar almasına ve deneyimlerini paylaşmasına yardımcı olarak dünyanın en iyi markaları ile müşterileri arasında güvenilir ilişkiler inşa eder. Lithium içerik paketini Power BI'a ekleyerek satışların ve müşteri bağlılığının artırılmasına ve hizmet maliyetlerinin azaltılmasına yardımcı olmak üzere çevrimiçi topluluğunuza ilişkin ana ölçümler gerçekleştirebilirsiniz. 

Power BI için [Lithium içerik paketine](https://app.powerbi.com/getdata/services/lithium) bağlanın.

>[!NOTE]
>Power BI içerik paketi Lithium API'sini kullanır. Belirli sayıyı aşan API çağrıları Lithium'un ek ücret uygulamasına neden olabilir; lütfen Lithium yöneticinize danışın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. **Hizmetler** kutusundaki **Al**'ı seçin.
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. **Lithium** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Lithium topluluğunuzun URL'sini girin. *https://community.yoursite.com* biçiminde olur.
   
   ![](media/service-connect-to-lithium/params.png)
5. İstendiğinde Lithium kimlik bilgilerinizi girin. Kimlik doğrulama yöntemi olarak **OAuth2**'yi seçin ve **Oturum aç**'a tıklayıp Lithium kimlik doğrulaması akışındaki adımları uygulayın.
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. Oturum açma akışı tamamlandığında içeri aktarma işlemi başlar. İçeri aktarma işlemi sona erdiğinde, Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
    ![](media/service-connect-to-lithium/lithium.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
Lithium içerik paketi için Lithium Community v15.9 veya sonraki bir sürümü gerekir. Doğrulamak için lütfen Lithium yöneticinize danışın.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

