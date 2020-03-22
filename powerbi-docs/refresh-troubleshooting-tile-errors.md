---
title: Kutucuk hatalarıyla ilgili sorunları giderme
description: Power BI’da kutucuklar yenileme yapmaya çalıştığında karşılaşılabilecek genel hatalar
author: maggiesMSFT
ms.reviewer: kayu
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 12/06/2018
ms.author: maggies
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 79f18faf56fba8afa85afd808f6faa1bd16811d8
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79381158"
---
# <a name="troubleshooting-tile-errors"></a>Kutucuk hatalarıyla ilgili sorunları giderme
Aşağıda kutucuklarla ilgili karşılaşabileceğiniz genel hatalar ve açıklamaları verilmiştir.

> [!NOTE]
> Aşağıda belirtilmemiş bir hatayla karşılaşırsanız ve bu durum sorun yaratırsa daha fazla yardım almak için [topluluk sitesine](https://community.powerbi.com/) başvurabilir veya bir [destek bileti](https://powerbi.microsoft.com/support/) oluşturabilirsiniz.
> 
> 

## <a name="errors"></a>Hatalar
**Power BI, modeli yüklerken beklenmeyen bir hata ile karşılaştı. Lütfen daha sonra tekrar deneyin.**
veya **Veri modeli alınamadı. Veri kaynakları ve veri modelinin mevcut ve erişilebilir olduğundan emin olmak için lütfen pano sahibiyle iletişime geçin.**

Veri kaynağı erişilebilir durumda olmadığından verilerinize erişemedik. Bu sorun veri kaynağının silinmiş, yeniden adlandırılmış, taşınmış, çevrimdışı kalmış olması veya izinlerin değiştirilmesi durumunda ortaya çıkabilir. Kaynağın baktığımız konumda olduğundan ve erişim izniniz olduğundan emin olun. Sorun bu değilse kaynak yavaş olabilir. Kaynak üzerindeki yükün daha az olduğu bir zamanda tekrar deneyin. Kaynak şirket içindeyse veri kaynağı sahibi daha fazla bilgi verebilir.

**Bu kutucuğu görüntüleme veya çalışma kitabını açma izniniz yok.**

Veri kaynaklarıyla veri modelinin mevcut ve hesabınız için erişilebilir olduğundan emin olmak için pano sahibiyle iletişime geçin.

**Power BI görselleri yöneticiniz tarafından devre dışı bırakıldı.**

Power BI yöneticiniz, kuruluşunuz veya güvenlik grubunuz için Power BI görsellerinin kullanımını devre dışı bıraktı.
[Microsoft marketten](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) Power BI görsellerini kullanamazsınız veya dosyadan özel görselleri aktaramazsınız. Yalnızca önceden paketlenmiş görseller kümesini kullanabilirsiniz.


**Veri şekilleri, veri çıkışı sağlayan en az bir grup veya hesaplama içermelidir. Lütfen pano sahibiyle iletişime geçin.**

Sorgu boş olduğundan görüntüleyecek veri bulamıyoruz. Görselinize alan listesinden birkaç alan ekleyip tekrar sabitlemeyi deneyin.

**Power BI iki veya daha fazla alan arasındaki ilişkiyi belirleyemediğinden, veriler görüntülenemiyor.**

Aralarında ilişki olmayan tablolardan iki veya daha fazla alan kullanmaya çalışıyorsunuz. Aralarında ilişki olmayan alanları görselden kaldırıp tablolar arasında ilişki kurmanız gerekiyor. Bu değişikliği yaptıktan sonra alanları yeniden görsele ekleyebilirsiniz. Bu işlemi Power BI Desktop veya Excel için Power Pivot uygulamalarında gerçekleştirebilirsiniz. [Daha fazla bilgi](desktop-create-and-manage-relationships.md)

**Birincil ve ikincil eksendeki gruplar çakışıyor. Birincil eksendeki gruplar, ikincil eksendeki gruplarla aynı anahtarlara sahip olamaz.**

Bu genellikle geçici bir sorundur. Bu durum genelde grupları satırlardan sütunlara taşıdığınızda ortaya çıkar. Bu durumda grupların tamamını taşımayı bitirdiğinizde hatanın ortadan kalkması gerekir. İletiyi görmeye devam ediyorsanız alanları satırlar ve sütunlar ya da eksen açıklaması arasında değiştirmeyi veya alanları görselden kaldırmayı deneyin.  

**Bu görsel kullanılabilir kaynakları aştı. Görüntülenen veri miktarını azaltmak için filtrelemeyi deneyin.**

Görseliniz, sonucu kullanılabilir kaynaklarla tamamlayamayacağımız kadar çok veriyi sorgulamayı denedi. Sonuçtaki veri miktarını azaltmak için görseli filtrelemeyi deneyin.

**Şu alanları tanımlayamıyoruz: {0}. Lütfen veri kümesinde bulunan alanları kullanarak görseli güncelleştirin.**

Alan silinmiş veya yeniden adlandırılmış olabilir. Bozuk alanı görselden kaldırabilir, farklı bir alan ekleyebilir ve tekrar sabitleyebilirsiniz.

**Bu görsel için veri alınamadı. Lütfen daha sonra yeniden deneyin.**

Bu genellikle geçici bir sorundur. Daha sonra yeniden denediğinizde aynı iletiyi görürseniz destek ekibiyle iletişime geçin.

**Kutucuklar, çoklu oturum açma (SSO) etkinleştirildikten sonra filtrelenmemiş verileri göstermeye devam eder.**

Temel alınan veri kümesi, bir şirket içi veri ağ geçidi üzerinden Analysis Services için DirectQuery modunu veya Canlı Bağlantıyı kullanmak üzere yapılandırıldıysa bu durum oluşabilir. Bu durumda kutucuklar, sonraki kutucuk yenileme zamanı gelinceye kadar veri kaynağı için çoklu oturum açma etkinleştirildikten sonra filtrelenmemiş verileri göstermeye devam eder. Sonraki kutucuk yenilemesinde Power BI, yapılandırıldığı şekilde çoklu oturum açmayı kullanır ve kutucuklar, kullanıcı kimliğine göre filtrelenen verileri gösterir. 

Filtrelenen verileri hemen görmek istiyorsanız, panonun sağ üst kısmındaki **Diğer seçenekler** (...) ve **Pano kutucuklarını yenile** seçeneğini belirleyerek kutucuk yenileme işlemi yapabilirsiniz.

Ayrıca veri kümesi sahibi olarak, kutucuk yenilemeyi hızlandırmak için kutucuk yenileme sıklığını değiştirip 15 dakika olarak ayarlayabilirsiniz. Power BI hizmetinin sağ üst köşesinde yer alan dişli simgesini ve ardından **Ayarlar**’ı seçin. **Ayarlar** sayfasında **Veri Kümeleri**’ni seçin. **Zamanlanmış önbellek yenileme**’yi genişletin ve **Yenileme sıklığı**’nı değiştirin. Power BI, sonraki kutucuk yenilemeyi gerçekleştirdikten sonra yapılandırmayı özgün yenileme sıklığına sıfırladığınızdan emin olun.

> [!NOTE]
> **Zamanlanmış önbellek yenileme** bölümü yalnızca DirectQuery/LiveConnection modunda veri kümeleri için kullanılabilir olur. Kutucuklar sonraki zamanlanmış veri yenilemesi sırasında otomatik olarak yenilendiğinden, içeri aktarma modunda veri kümeleri için ayrı bir kutucuk yenilemesi gerekmez.

## <a name="contact-support"></a>Desteğe başvurun
Sorun yaşamaya devam ediyorsanız daha fazla araştırma yapılabilmesi için [destek ekibiyle iletişime geçin](https://support.powerbi.com).

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
[Power BI kişisel ağ geçidiyle ilgili sorunları giderme](service-admin-troubleshooting-power-bi-personal-gateway.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

