---
title: Performans İpuçları
description: Yüksek performanslı Power BI görseli oluşturma
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 04/20/2020
ms.openlocfilehash: c22c634ef59a1aae2994dcacaae62dc8ebed7474
ms.sourcegitcommit: 6bc66f9c0fac132e004d096cfdcc191a04549683
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91746091"
---
# <a name="how-to-build-a-high-performance-power-bi-visual"></a>Yüksek performanslı Power BI görseli oluşturma
Bu makalede, bir geliştiricinin görselleri işlerken yüksek performans elde edebilmesine yönelik teknikler ele alınır. 

Hiç kimse bir görselin işleme sırasında zamanını almasını istemez. Koddan çıkarabileceğiniz her performans düşüşü, işleme sırasında kritik öneme sahiptir. 

> [!NOTE]
> Biz platformu iyileştirip geliştirmeye devam ederken, API’nin yeni sürümleri sürekli olarak yayımlanmaktadır. Power BI görselleri platformundan en iyi şekilde yararlanmak için, en güncel sürümlerle çalışmanız önerilir.
>
> En güncel **sürüm 2.1** olduğundan, Power BI görsel yükleme süreleri ortalama %20 oranında iyileştirilmiştir.

## <a name="power-bi-visual-performance-tips"></a>Power BI görsel performansı ipuçları
En iyi görsel performansı elde etmeye yönelik bazı önerileri burada bulabilirsiniz. 

### <a name="use-user-timing-api"></a>Kullanıcı Zamanlama API’sini kullanma
Uygulamanızın JavaScript performansını ölçmek için **Kullanıcı Zamanlama API’sini** kullanmak, betikte iyileştirme yapılması gereken kısımlara karar vermenize yardımcı olabilir.

Daha fazla bilgi için bkz. [Kullanıcı Zamanlama API’si](https://msdn.microsoft.com/library/hh772738(v=vs.85).aspx).

### <a name="review-animation-loops"></a>Animasyon döngülerini gözden geçirme
Animasyon, değiştirilmemiş öğeleri yeniden çizer mi? 

 - Sorun: Çerçeveden çerçeveye değişmeyen öğeleri çizmek için zaman harcar.

 - Çözüm: Çerçeveleri seçmeli olarak güncelleştirin. 
 
Statik görselleştirmelere animasyon ekleme zamanı geldiğinde, kodu tek bir güncelleştirme işlevinde toplu olarak çizmek ve animasyon döngüsünün her yinelemesi için yeni verilerle çağırmak çekici gelebilir.

Bunun yerine aşağıdaki güncelleştirme desenini ele alıp her şeyi statik bir biçimde çizmek için görsel oluşturucu yöntemini kullandığınızda, güncelleştirme işlevinin yalnızca değişen görselleştirme öğelerini çizmesi gerekir. 

   > [!TIP]
   > Eksenlerde ve göstergelerde verimsiz animasyon döngülerine sıkça rastlanır.

### <a name="cache-dom-nodes"></a>DOM Düğümlerini önbelleğe alma 
DOM’dan bir düğüm veya düğümlerin olduğu bir liste aldığınızda, bunları daha sonraki hesaplamalarda (hatta bazen sonraki düğüm yinelemesinde) kullanıp kullanamayacağınızı düşünmeniz gerekir. İlgili alanda ek düğümler ekleyip silmeye gerek duymadığınız sürece, bunları önbelleğe almak uygulamanızın genel verimliliğini iyileştirebilir.

Kodunuzun hızlı olduğundan ve tarayıcıyı yavaşlatmadığından emin olmak için DOM erişimini en düşük düzeyde tutun. 

- Önce: 

   ```javascript
   public update(options: VisualUpdateOptions) { 
       let axis = $(".axis"); 
   }
   ```

- Sonra: 

   ```javascript
   public constructor(options: VisualConstructorOptions) { 
       this.$root = $(options.element); 
       this.xAxis = this.$root.find(".xAxis"); 
   } 
 
   public update(options: VisualUpdateOptions) { 
       let axis = this.axis; 
   }
   ```

### <a name="avoid-dom-manipulation"></a>DOM işlemesini önleme 
DOM işlemesini mümkün olduğunca fazla düzeyde sınırlayın.  `prepend()`, `append()` ve `after()` gibi ekleme işlemleri zaman alır ve gerekli olmadıkça kullanılmamalıdır.

Örneğin:

  ```javascript
  for (let i=0; i<1000; i++) { 
      $('#list').append('<li>'+i+'</li>');
  }
  ```

Yukarıdaki örnek, `html()` kullanılarak ve listeyi önceden oluşturarak hızlandırılabilir: 

  ```javascript
  let list = ''; 
  for (let i=0; i<1000; i++) { 
      list += '<li>'+i+'</li>'; 
  } 

  $('#list').html(list); 
  ```

### <a name="reconsider-jquery"></a>JQuery’yi yeniden ele alma

JS çerçevelerinizi sınırlandırma ve mümkün olan her seferinde yerel JS kullanma, kullanılabilir bant genişliğini artırıp işleme ek yükünüzü azaltabilir. Bu, eski tarayıcılarla olan uyumluluk sorunlarını da sınırlayabilir. 

JQuery’nin `show`, `hide`, `addClass` ve diğer işlevlerine yönelik alternatif çözümler hakkında daha fazla bilgi için bkz. [youmightnotneedjquery.com](http://youmightnotneedjquery.com/).  

### <a name="use-canvas-or-webgl"></a>Tuval veya WebGL kullanma 
Animasyonların yinelenen kullanımı için SVG yerine **Tuval** veya **WebGL** kullanmayı tercih edin. Bu seçenekler sayesinde performans, SVG’nin aksine içerik yerine boyuta göre belirlenir. 

[SVG ile Canvas Karşılaştırması: Seçim Yapma](/previous-versions/windows/internet-explorer/ie-developer/samples/gg193983(v=vs.85)) bölümünde farklar hakkında daha fazla bilgi edinebilirsiniz. 

### <a name="use-requestanimationframe-instead-of-settimeout"></a>setTimeout yerine requestAnimationFrame kullanma 
Ekrandaki animasyonlarınızı güncelleştirmek için [requestAnimationFrame](https://www.w3.org/TR/animation-timing/) kullanırsanız animasyon işlevleriniz tarayıcı başka bir yeniden çizim çağırmadan **önce** çağrılır.

Daha fazla bilgi için, `requestAnimationFrame` kullanarak düzgün animasyon elde etme hakkındaki [bu örneğe](https://testdrive-archive.azurewebsites.net/Graphics/RequestAnimationFrame/Default.html) göz atın.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI için iyileştirme kılavuzundaki](../../guidance/power-bi-optimization.md) iyileştirme teknikleri hakkında daha fazla bilgi edinin.