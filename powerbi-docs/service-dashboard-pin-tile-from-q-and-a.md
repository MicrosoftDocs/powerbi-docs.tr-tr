---
title: Soru-Cevap bölümünden bir kutucuğu panoya sabitleme
description: Soru-Cevap soru kutusundan kutucukları Power BI panolarına sabitlemeye ilişkin belge
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 77be727de3cda1d3b6fd5c34b6e572b1d505fc54
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "76282017"
---
# <a name="pin-a-tile-to-a-dashboard-from-qa"></a>Soru-Cevap'tan kutucukları panolara sabitleme
## <a name="how-to-pin-a-tile-from-qa"></a>Soru-Cevap'tan kutucuk sabitleme
Soru-Cevap, Power BI'daki özel raporlama aracıdır. Belirli bir öngörüyü bulmanız mı gerekiyor? Verileriniz hakkında soru sorun ve görselleştirme şeklinde yanıt alın.

Bu Nasıl yapılır makalesinde bir panoyu açmak, doğal dil kullanıp soru sorarak görselleştirme oluşturmak ve bu görselleştirmeyi bir panoya sabitlemek için Power BI hizmetini (app.powerbi.com) kullanacağız. Panolar Power BI Desktop'ta kullanılamaz. Soru-Cevap özelliğini diğer Power BI araçları ve içerikleri ile kullanma hakkında bilgi edinmek için bkz. [Power BI Soru-Cevap özelliğine genel bakış](consumer/end-user-q-and-a.md). 

Örneği takip etmek için [Retail Analysis sample panosunu](sample-retail-analysis.md) açın.


1. Raporlardan sabitlenmiş en az bir kutucuk içeren bir [panoyu](consumer/end-user-dashboards.md) açın. Soru sorduğunuzda Power BI, ilgili panoya sabitlenmiş kutucuğa sahip olan veri kümelerinde yanıt arar.  Daha fazla bilgi edinmek için bkz. [Veri alma](service-get-data.md).
2. Panonuzun en üstündeki soru kutusuna verilerinizle ilgili olarak öğrenmek istediklerinizi yazmaya başlayın.  
   ![Soru-Cevap soru kutusu](media/service-dashboard-pin-tile-from-q-and-a/power-bi-question-box.png)
3. Örneğin, "last year sales by month and territory" (aya ve bölgeye göre geçen yılın satışları)...  
   ![soru yazma](media/service-dashboard-pin-tile-from-q-and-a/power-bi-type-q-and-a.png)

   yazdığınızda soru kutusunda öneriler görüntülenir.
4. Grafiği panonuza kutucuk olarak eklemek için tuvalin sağ üst kısmında bulunan raptiye ![](media/service-dashboard-pin-tile-from-q-and-a/pbi_pintile.png) simgesini seçin. Sizinle paylaşılmış olan panolara herhangi bir görselleştirme sabitleyemezsiniz.

5. Kutucuğu, mevcut bir panoya veya yeni bir panoya sabitleyin.

   ![Panoya sabitle iletişim kutusu](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin-to-dashboard.png)

   * Var olan pano: Açılan listeden panonun adını seçin. Seçimleriniz, geçerli çalışma alanındaki panolarla sınırlı olacaktır.
   * Yeni pano: Yeni panonun adını yazarak geçerli çalışma alanınıza eklenmesini sağlayabilirsiniz.

6. **Sabitle**'yi seçin.

   Sağ üst köşeye yakın bir noktada çıkan bir başarı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.  

   ![Panoya sabitlendi](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin.png)
7. Yeni kutucuğu görmek için **Panoya git**'i seçin. Ardından panonuzda [kutucuğu yeniden adlandırabilir, yeniden boyutlandırabilir, köprü ekleyebilir, kutucuğu yeniden konumlandırabilir ve daha pek çok şey yapabilirsiniz](service-dashboard-edit-tile.md).

   ![kutucuklar içeren pano](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Soru yazmaya başladığınızda Soru-Cevap özelliği, geçerli panoyla ilişkilendirilmiş olan tüm veri kümelerinden en iyi yanıtı bulmak üzere arama yapmaya başlar.  "Geçerli pano", üst gezinti bölmesinde listelenen panodur. Örneğin, bu soru, **mihart** çalışma alanının bir parçası olan **Retail Analysis Sample** panosunda sorulmaktadır.

  ![içerik haritaları](media/service-dashboard-pin-tile-from-q-and-a/power-bi-navbar.png)
* **Soru-Cevap hangi veri kümelerinin kullanılacağına nasıl karar veriyor**?  Soru-Cevap özelliği, ilgili panoya sabitlenmiş en az bir görselleştirmeye sahip olan tüm veri kümelerine erişim sahibidir.

* **Soru kutusunu göremiyor musunuz**? Power BI yöneticinizle iletişime geçin. Yönetici Soru-Cevap özelliğini devre dışı bırakabilir.


## <a name="next-steps"></a>Sonraki adımlar
[Kutucukla ilgili yeniden adlandırma, yeniden boyutlandırma, köprü ekleme, yeniden konumlandırma ve diğer işlemleri gerçekleştirme](service-dashboard-edit-tile.md)    
[Pano kutucuğunuzu Odak modunda görüntüleme](consumer/end-user-focus.md)     
[Power BI'daki Soru-Cevap özelliği](consumer/end-user-q-and-a.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
