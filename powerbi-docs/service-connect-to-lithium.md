---
title: "Power BI ile Lithium'a bağlanma"
description: "Power BI için Lithium"
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
ms.openlocfilehash: ed7255df535cf2e6703fe9235b192c85d98d92d3
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-lithium-with-power-bi"></a>Power BI ile Lithium'a bağlanma
Lithium, kullanıcıların, sorularına ilişkin cevaplar almasına ve deneyimlerini paylaşmasına yardımcı olarak dünyanın en iyi markaları ile müşterileri arasında güvenilir ilişkiler inşa eder. Lithium içerik paketini Power BI'a ekleyerek satışların ve müşteri bağlılığının artırılmasına ve hizmet maliyetlerinin azaltılmasına yardımcı olmak üzere çevrimiçi topluluğunuza ilişkin ana ölçümler gerçekleştirebilirsiniz. 

Power BI için [Lithium içerik paketine](https://app.powerbi.com/getdata/services/lithium) bağlanın.

>[!NOTE]
>Power BI içerik paketi Lithium API'sini kullanır. Belirli sayıyı aşan API çağrıları Lithium'un ek ücret uygulamasına neden olabilir; lütfen Lithium yöneticinize danışın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmındaki **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. **Hizmetler** kutusundaki **Al**'ı seçin.
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. **Lithium** \> **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Lithium topluluğunuzun URL'sini girin. URL biçimi *https://community.siteniz.com* şeklindedir.
   
   ![](media/service-connect-to-lithium/params.png)
5. İstendiğinde Lithium kimlik bilgilerinizi girin. Kimlik doğrulama yöntemi olarak **OAuth2**'yi seçin ve **Oturum aç**'a tıklayıp Lithium kimlik doğrulaması akışındaki adımları uygulayın.
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. Oturum açma akışı tamamlandığında içeri aktarma işlemi başlar. İçeri aktarma işlemi sona erdiğinde, Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
    ![](media/service-connect-to-lithium/lithium.png)

**Sırada ne var?**

* Panonun üst kısmındaki [Soru-Cevap kutusunda soru sormayı](service-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenmeye zamanlanacak olsa da yenileme zamanlamasını değiştirebilir veya **Şimdi Yenile** ile istediğiniz zaman yenileme yapabilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
Lithium içerik paketi için Lithium Community v15.9 veya sonraki bir sürümü gerekir. Doğrulamak için lütfen Lithium yöneticinize danışın.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

