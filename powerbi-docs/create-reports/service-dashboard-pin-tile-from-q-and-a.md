---
title: Soru-Cevap bölümünden bir kutucuğu panoya sabitleme
description: Soru-Cevap soru kutusundan kutucukları Power BI panolarına sabitlemeye ilişkin belge
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 01/05/2021
LocalizationGroup: Dashboards
ms.openlocfilehash: 5ae148feaa294c8779a7140ef450c832bd3376d8
ms.sourcegitcommit: 932f6856849c39e34229dc9a49fb9379c56a888a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97927166"
---
# <a name="pin-a-tile-to-a-dashboard-from-qa"></a>Soru-Cevap'tan kutucukları panolara sabitleme

Soru-Cevap; verilerinizi doğal bir dil kullanarak keşfetmenizi sağlayan bir Power BI aracıdır. Belirli bir öngörüyü bulmanız mı gerekiyor? Verileriniz hakkında soru sorun ve görselleştirme şeklinde yanıt alın.

Bu nasıl yapılır makalesinde, Power BI hizmetinde (app.powerbi.com) bir [panoyu](../consumer/end-user-dashboards.md) açacak, bir görselleştirme oluşturmak için doğal dille bir soru soracak ve bu görselleştirmeyi panoya sabitleyeceğiz. Panolar Power BI Desktop'ta bulunmaz. Soru-Cevap özelliğini diğer Power BI araçları ve içerikleri ile kullanma hakkında bilgi edinmek için bkz. [Power BI Soru-Cevap özelliğine genel bakış](../consumer/end-user-q-and-a.md). 

Örneği takip etmek için [Retail Analysis sample panosunu](sample-retail-analysis.md) açın.

## <a name="how-to-pin-a-tile-from-qa"></a>Soru-Cevap'tan kutucuk sabitleme

1. Raporlardan sabitlenmiş en az bir kutucuk içeren bir panoyu açın. Soru sorduğunuzda Power BI, ilgili panoya sabitlenmiş kutucuğa sahip olan veri kümelerinde yanıt arar.
2. Panonuzun en üstündeki soru kutusuna verilerinizle ilgili olarak öğrenmek istediklerinizi yazmaya başlayın.  
   ![Soru-Cevap soru kutusu](media/service-dashboard-pin-tile-from-q-and-a/power-bi-question-box.png)
3. Örneğin, "last year sales by month and territory" (aya ve bölgeye göre geçen yılın satışları)...  
   ![soru yazma](media/service-dashboard-pin-tile-from-q-and-a/power-bi-type-q-and-a.png)

   yazdığınızda soru kutusunda öneriler görüntülenir.
4. Grafiği panonuza kutucuk olarak eklemek için ![Raptiye simgesi](media/service-dashboard-pin-tile-from-q-and-a/pbi_pintile.png) tuvalin sağ üst kısmındaki raptiyeyi seçin. Sizinle paylaşılmış olan panolara herhangi bir görselleştirme sabitleyemezsiniz.

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
[Pano kutucuğunuzu Odak modunda görüntüleme](../consumer/end-user-focus.md)     
[Power BI'da Soru-Cevap özelliğine genel bakış](../consumer/end-user-q-and-a.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
