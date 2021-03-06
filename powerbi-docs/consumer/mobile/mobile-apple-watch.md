---
title: Apple Watch'unuzdaki mobil uygulamada Power BI verilerini araştırma
description: Power BI Apple Watch uygulaması
author: paulinbar
ms.author: painbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 03/11/2020
ms.openlocfilehash: 1a2dfd19f2366003555aa5fa673bbf1c81c0a050
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96413277"
---
# <a name="explore-your-data-in-the-power-bi-mobile-app-on-your-apple-watch"></a>Apple Watch'unuzdaki Power BI mobil uygulamasında verilerinizi araştırma
Power BI Apple Watch uygulamasıyla, Power BI panolarınızdaki KPI'leri ve kart kutucuklarını doğrudan saatinizde görüntüleyebilirsiniz. KPI'ler ve kart kutucukları küçük ekranda bir kalp atışı ölçümü sunmak üzere en iyi şekilde yerleştirilir. iPhone'dan veya doğrudan Apple Watch'tan bir panoyu yenileyebilirsiniz.

## <a name="install-the-apple-watch-app"></a>Apple Watch uygulamasını yükleme
Power BI Apple Watch uygulaması iOS için Power BI uygulamasıyla birlikte sunulur, bu nedenle Apple App Store'dan [Power BI uygulamasını iPhone'unuza indirdiğinizde](https://go.microsoft.com/fwlink/?LinkId=522062 "iPhone uygulamasını indirin") Power BI Watch uygulamasını da otomatik olarak indirirsiniz. Apple tarafından sağlanan kılavuzda [Apple Watch uygulamalarının nasıl yükleneceği](https://support.apple.com/HT204784) açıklanmaktadır.

## <a name="use-the-power-bi-app-on-the-apple-watch"></a>Apple Watch'ta Power BI uygulamasını kullanma
Saatin duyuru panosundan veya doğrudan saat kadranındaki Power BI pencere öğesine tıklayarak (yapılandırılmışsa) Power BI Apple Watch uygulamasına gidin.

![Power BI uygulamasının yüklü olduğu Apple Watch cihazını gösteren fotoğraf.](./media/mobile-apple-watch/pbi_aplwatch_complicatn240arrow.png)

Power BI Apple Watch uygulaması iki bölümden oluşur.

* **Dizin ekranı**, eşitlenmiş panodan tüm KPI'lere ve kart kutucuklarına yönelik hızlı bir genel bakış sağlar.
  
  ![Dizin ekranının göründüğü Apple Watch cihazını gösteren fotoğraf.](./media/mobile-apple-watch/pbi_aplwatch_indexscreen240.png)
* **Odak kutucuğu**: Dizin ekranında belirli bir kutucuğa ait kapsamlı bir görünüm için bir kutucuğa tıklayın.
  
  ![Kutucuğun görüntülendiği Apple Watch cihazını gösteren fotoğraf.](./media/mobile-apple-watch/pbi_aplwatch_kpi.png)

## <a name="refresh-a-dashboard-from-your-apple-watch"></a>Bir panoyu Apple Watch'unuzdan yenileme
Eşitlenen bir panoyu doğrudan saatinizden yenileyebilirsiniz.

* Watch Uygulaması'ndaki pano görünümündeyken, ekranınıza basılı tutun ve **yenileme**'yi seçin.

Watch Uygulaması, panonuzu Power BI hizmetindeki verilerle eşitler.

> [!NOTE]
> Watch Uygulaması, iPhone'daki Power BI mobil uygulaması aracılığıyla Power BI ile iletişim kurar. Bu nedenle, Watch Uygulaması'ndaki panonun yenilenmesi için Power BI uygulamasının iPhone'da en azından arka planda çalışması gerekir.
> 
> 

## <a name="refresh-a-dashboard-on-your-apple-watch-from-your-iphone"></a>Apple Watch'unuzdaki bir panoyu iPhone'unuzdan yenileme
Apple Watch'unuzdaki bir panoyu iPhone'unuzdan da yenileyebilirsiniz.

1. iPhone'unuzdaki Power BI'da, Apple Watch ile eşitlemek istediğiniz panoyu açın. 
2. **Diğer seçenekler** (...) > **Saat ile Eşitle**'yi seçin.

Power BI, bir göstergede panonun saat ile eşitlendiğini gösterir.

Bir seferde saat ile yalnızca bir pano eşitleyebilirsiniz.

> [!TIP]
> Saatinizde birden çok panoda bulunan kutucukları görüntülemek için Power BI hizmetinde yeni bir pano oluşturun ve ilgili tüm kutucukları bu panoya ekleyin.
> 
> 

## <a name="set-a-custom-power-bi-widget"></a>Özel bir Power BI pencere öğesi oluşturma
Belli bir Power BI kutucuğunu doğrudan Apple Watch kadranında da görüntüleyebilirsiniz. Bu şekilde kutucuk daima görünür ve erişilebilir durumda olacaktır.

Power BI Apple Watch pencere öğesi, verilerinizin güncelleştirileceği zamana yakın bir noktada güncelleştirilir. Böylece, ihtiyaç duyduğunuz bilgiler her zaman güncel kalır.

### <a name="add-a-power-bi-widget-to-your-watch-face"></a>Saat kadranınıza bir Power BI pencere öğesi ekleme
Apple tarafından sağlanan Kılavuzdaki [Apple Watch kadranınızı özelleştirme](https://support.apple.com/HT205536) bölümüne bakın.

### <a name="change-the-text-on-the-widget"></a>Pencere öğesindeki metni değiştirme
Apple Watch kadranındaki alanın küçüklüğü nedeniyle Power BI Apple Watch uygulaması, pencere öğesinin başlığını bu küçük alana sığacak şekilde değiştirmenizi sağlar.

* iPhone'unuzda, Apple Watch adlı denetim uygulamasına gidin, Power BI'ı seçin, pencere öğesi adı alanına gidin ve yeni bir ad yazın.
  
  ![My Watch uygulamasının açık olduğu ve Power BI simgesinin göründüğü iPhone ekranını gösteren fotoğraf.](./media/mobile-apple-watch/pbi_aplwatch_oniphone.png)

> [!NOTE]
> Adı değiştirmezseniz Power BI pencere öğesi, saat kadranındaki küçük alana sığacak karakter sayısına göre mevcut adı kısaltır. 
> 
> 

## <a name="next-steps"></a>Sonraki adımlar
Geri bildiriminiz, gelecekte neleri kullanıma sunacağımıza karar verme konusunda bize yardımcı olacaktır. Bu nedenle lütfen Power BI mobil uygulamalarında görmek istediğiniz diğer özellikleri belirtmeyi unutmayın. 

* [Power BI iPhone mobil uygulamasını](https://go.microsoft.com/fwlink/?LinkId=522062) indirin
* [Twitter'da @MSPowerBI hesabını takip edin](https://twitter.com/MSPowerBI)
* [Power BI Topluluğu](https://community.powerbi.com/)'ndaki sohbetlere katılın

