---
title: "Özel görselleri güvenlik ve gizlilik bakımından gözden geçirme"
description: "Bir özel görseli etkinleştirmeden önce kuruluşunuzun standartlarına uygun olduğundan emin olmak için görseli güvenlik ve gizlilik bakımından gözden geçirmeniz gerekir."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/05/2017
ms.author: asaxton
ms.openlocfilehash: 20a697cbc4698e237f3ac09b031ea0c4cb734a52
ms.sourcegitcommit: 12236d08c27c7ee3fabb7ef9d767e9dee693f8aa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="review-custom-visuals-for-security-and-privacy"></a>Özel görselleri güvenlik ve gizlilik bakımından gözden geçirme
Bir özel görseli etkinleştirmeden önce kuruluşunuzun standartlarına uygun olduğundan emin olmak için görseli güvenlik ve gizlilik bakımından gözden geçirmeniz gerekir.

## <a name="enable-a-custom-visual"></a>Özel görselleri etkinleştirme
<a name="enable"></a>Raporda bulunan bir özel görsel, aşağıda gösterildiği gibi **Özel görselleri etkinleştir** seçeneği belirlenmediği sürece devre dışıdır.  

![](media/service-custom-visuals-review-for-security-and-privacy/emptyvisual.png)

## <a name="considerations-before-you-enable-a-custom-visual"></a>Bir özel görseli etkinleştirmeden önce göz önünde bulundurulması gereken önemli noktalar
<a name="considerations"></a>

> [!WARNING]
> Bir özel görsel, güvenlik veya gizlilik riskleri taşıyan kod içerebilir. Bu nedenle, raporda bulunan bir özel görsel, Özel görselleri etkinleştir seçeneği belirlenene kadar devre dışıdır. Bir özel görselin etkinleştirilip etkinleştirilmeyeceğine karar vermeden önce göz önünde bulundurulması gereken önemli noktalar şunlardır:
> 
> 

1. Raporda kullanılan özel görsellerin yazarına ve kaynağına güvendiğinizden emin olun
2. Ne yapacağınızdan emin değilseniz görüntülediğiniz rapordaki özel görselleri etkinleştirmenin gerekli olup olmadığını değerlendirmek üzere BT ekibinize başvurmanız gerekir.
3. Biri sizinle özel görsel içeren bir rapor paylaşırsa bu kişi yakın bir iş arkadaşınız olsa bile kendinizi özel görseli etkinleştirme konusunda zorunlu hissetmeyin. Her zaman bir an durup düşünerek bunun söz konusu görev için gerçekten gerekli olup olmadığını değerlendirmekte fayda vardır. Ayrıca, özel görsel konusunda emin değilseniz ilgili kişiden size özel görsel içermeyen bir rapor sağlamasını da isteyebilirsiniz.

## <a name="security-best-practices-for-it-professionals-to-enable-a-custom-visual"></a>BT Uzmanları için bir özel görseli etkinleştirme ile ilgili en iyi güvenlik uygulamaları
<a name="security"></a>

> [!WARNING]
> Bir özel görsel, güvenlik veya gizlilik riskleri taşıyan kod içerebilir. Bu nedenle, raporda bulunan bir özel görsel, Özel görselleri etkinleştir seçeneği belirlenene kadar devre dışıdır. Bir özel görseli güvenlik ve gizlilik bakımından değerlendirmeye yönelik birçok en iyi uygulama vardır.
> 
> 

1. Kuruluşta özel görseller için bir güvenlik incelemesi işlemi gerçekleştirin. Güvenlik incelemesinden geçen özel görseller, SharePoint belge kitaplığı veya OneNote belgesi gibi bir iç web sitesi aracılığıyla iç kullanıcılarla paylaşılabilir.
2. İşletme kullanıcılarına, özel görsellerin uygun kullanımı konusunda yol gösterin ve güvenlik veya gizlilikle ilgili sorularını gönderebilecekleri bir e-posta grubu sağlayın.
3. Özel görselli pbiviz dosyasındaki JavaScript kodunu değerlendirin.

**Bir özel görseldeki JavaScript kodunu değerlendirmek için**

Özel görseller JavaScript kullanır ve bu nedenle güvenlik veya gizlilik riskleri taşıyabilir. Bilinmeyen bir kaynaktan bir özel görsel veya özel görsel içeren bir pbix dosyası alırsanız güvenli olup olmadığını görmek için JavaScript'i incelemek isteyebilirsiniz.

Bir özel görseldeki JavaScript kodunu değerlendirmek için özel görsel kodunu ayıklayın. Kod şu şekilde ayıklanır:  

1. .pbiviz dosyasını bir klasöre kaydedin.
2. Dosyayı bir .zip dosyası olarak yeniden adlandırın.
3. Zip dosyasını yerel bir klasöre çıkarın.

## <a name="custom-visual-file-contents"></a>Özel görsel dosyasının içeriği
Bir .pbiviz dosyasının içeriği şu şekildedir:

| **Dosya** | **Açıklama** |
|:--- |:--- |
| ./package.json |Özel görsel için yüklenecek dosyaları belirten bir bildirim dosyası. |
| ./resources |Özel görsel tarafından kullanılan CSS, TypeScript ve JavaScript'i içerir. |
| ./resources/&lt;ad&gt; |&lt;Ad&gt;, özel görselin adıdır. |
| ./resources/&lt;ad&gt;.css |Özel görsel için css kaynak dosyası. |
| ./resources/&lt;ad&gt;.js |Bir kullanıcı Özel görselleri etkinleştir seçeneğine tıkladığında veya bir özel görseli İçeri aktardıktan sonra yürütülen kod. Uyarı! JavaScript kodu güvenlik veya gizlilik riskleri taşıyabilir. |
| ./resources/&lt;ad&gt;.ts |Görsel için TypeScript biçimindeki JavaScript kaynak kodu. Uyarı! JavaScript veya TypeScript kodu güvenlik veya gizlilik riskleri taşıyabilir. |
| ./resources/&lt;ad&gt;.png |Görsel için kullanıcıya gösterilen simge. |

pbiviz dosyasını ayıkladıktan sonra kodu değerlendirebilirsiniz. Bazı en iyi uygulamalar ve aranacak tehditler aşağıda verilmiştir.

## <a name="best-practices-to-evaluate-the-javascript-or-typescript-code"></a>JavaScript veya TypeScript kodunu değerlendirmeye ilişkin en iyi uygulamalar
**JavaScript** veya **TypeScript** kodu güvenlik veya gizlilik riskleri taşıyabilir. Bazı en iyi uygulamalar ve aranacak tehditler aşağıda verilmiştir.

### <a name="best-practices-to-evaluate-javascript-code"></a>JavaScript kodunu değerlendirmeye ilişkin en iyi uygulamalar
* .js dosyasının içeriğini her zaman değerlendirin. Gerçekte çalıştırılan kod budur. .ts dosyasının içeriğinin özel görseldeki .js dosyasına derlenmemesi gibi bir durum söz konusu olabilir.
* .ts dosyasının içeriğini her zaman değerlendirin. .ts dosyasını **Geliştirici Araçları**'na yükleyebilir, görseli dışarı aktarabilir ve yeni oluşturulan .pbiviz dosyasında elde edilen .js dosyasını, görseldeki özgün .js dosyası ile karşılaştırabilirsiniz
* Özel görsel simgesinin, kullanıcının alışkın olduğu diğer görsellere çok benzeyip benzemediğini kontrol edin.
* Görseli her zaman en az ayrıcalığa sahip olan ve gizli verilere erişimi bulunmayan bir test hesabında değerlendirin. İdeal olan, test hesabının Power BI dışındaki hizmetlere ilişkin oturum açma bilgisi içermeyen bir yerel hesap olmasıdır.

### <a name="threats-to-look-for-in-javascript-code"></a>JavaScript kodunda aranacak tehditler
* Görsel hem düzenleme hem de görüntüleme modunda kullanılırken ağ etkinliğini denetleyin. Yapılan isteklerde herhangi bir sorunla karşılaşmadığınızdan emin olun. Görsel yazarı bunu önceden belirtmediği sürece Power BI etki alanı dışındaki kaynaklara yönelik istekler görmemeniz gerekir.
* Power BI etki alanından ayrılmaya neden olduğunu gördüğünüz tüm veriler, "normal" kullanıma yönelik beklentilerinizi karşılamalıdır. Örneğin; görsel, başka bir sitedeki bir videoyu görüntülemek için iFrame kullanan bir video oynatıcı uyguluyorsa videonun doğru şekilde işlenmesi için bazı bilgiler iFrame istekleri kapsamında aktarılmalıdır. Ancak, veri kümesinin tamamının aktarıldığını görürseniz bunun gerekli ve beklenilen bir işlem olup olmadığını anlamak için daha ayrıntılı bir araştırma yapabilirsiniz.
* Özel görsel tarafından kişisel veri gönderilip gönderilmediğini veya depolanıp depolanmadığını kontrol edin.
* Özel görselin dosyaları diske yazma veya tanımlama bilgilerine erişme gibi işlemlerle yerel makine kaynaklarına erişmeye çalışıp çalışmadığını kontrol edin.
* Özel görselin gizli kod veya açık bir amacı olmayan kod gibi görünen bir kod içerip içermediğini kontrol edin.
* Geçmişte gözden geçirdiğiniz her görselin kopyasını kaydedin.
* Daha önce gözden geçirdiğiniz görsellere ilişkin güncelleştirmeleri gözden geçiriyorsanız değişiklikleri denetlediğinizden emin olun. Görseli gözden geçirmek için ilk aldığınızda yaptığınız gibi, güncelleştirmeler için de her zaman aynı özeni gösterin.
* Şüpheli veya belirsiz bir durumla karşılaştığınızda lütfen yardım almak için bize ulaşın.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki görselleştirmeler](power-bi-report-visualizations.md)  
[Power BI'daki Özel Görselleştirmeler](power-bi-custom-visuals.md)  
[Özel görselleri Office Mağazası'nda yayımlama](developer/office-store.md)  
[Özel görseller geliştirici araçları ile çalışmaya başlama](service-custom-visuals-getting-started-with-developer-tools.md)  
[Bir özel görseli sertifikalandırma](power-bi-custom-visuals-certified.md)    
[Video: Creating custom visualizations for Power BI with Sachin Patney and Nico Cristache (Sachin Patney ve Nico Cristache ile Power BI için özel görselleştirmeler oluşturma)](https://www.youtube.com/watch?v=kULc2VbwjCc)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

