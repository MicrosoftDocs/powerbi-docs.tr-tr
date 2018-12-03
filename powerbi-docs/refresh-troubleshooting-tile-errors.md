---
title: Kutucuk hatalarıyla ilgili sorunları giderme
description: Kutucuklar yenileme yapmaya çalıştığında karşılaşabilecek genel hatalar
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 1341caa1f67d01a03128344acd67261abf450f90
ms.sourcegitcommit: 2ae660a7b70fce23eb58b159d049eca44a664f2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/30/2018
ms.locfileid: "52669877"
---
# <a name="troubleshooting-tile-errors"></a>Kutucuk hatalarıyla ilgili sorunları giderme
Aşağıda kutucuklarla ilgili karşılaşabileceğiniz genel hatalar ve açıklamaları verilmiştir.

> [!NOTE]
> Aşağıda belirtilmemiş bir hatayla karşılaşırsanız ve bu durum sorun yaratırsa daha fazla yardım almak için [topluluk sitesine](http://community.powerbi.com/) başvurabilir veya bir [destek bileti](https://powerbi.microsoft.com/support/) oluşturabilirsiniz.
> 
> 

## <a name="errors"></a>Hatalar
**Power BI, modeli yüklerken beklenmeyen bir hata ile karşılaştı. Lütfen daha sonra tekrar deneyin.**
veya **Veri modeli alınamadı. Veri kaynakları ve veri modelinin mevcut ve erişilebilir olduğundan emin olmak için lütfen pano sahibiyle iletişime geçin.**

Veri kaynağı erişilebilir durumda olmadığından verilerinize erişemedik. Bu durum veri kaynağının silinmiş, yeniden adlandırılmış, taşınmış, çevrimdışı olması veya izinlerin değiştirilmesi durumunda ortaya çıkabilir. Kaynağın baktığımız konumda olduğundan ve erişim izniniz olduğundan emin olun. Sorun bu değilse kaynak yavaş olabilir. Kaynak üzerindeki yükün daha az olduğu bir zamanda tekrar deneyin. Kaynak şirket içindeyse veri kaynağı sahibi daha fazla bilgi verebilir.

**Bu kutucuğu görüntüleme veya çalışma kitabını açma izniniz yok.**

Veri kaynakları ve veri modelinin mevcut ve hesabınız için erişilebilir olduğundan emin olmak için lütfen pano sahibiyle iletişime geçin.

**Veri şekilleri, veri çıkışı sağlayan en az bir grup veya hesaplama içermelidir. Lütfen pano sahibiyle iletişime geçin.**

Sorgu boş olduğundan görüntüleyecek veri bulamıyoruz. Görselinize alan listesinden birkaç alan ekleyip tekrar sabitlemeyi deneyin.

**Power BI iki veya daha fazla alan arasındaki ilişkiyi belirleyemediğinden, veriler görüntülenemiyor.**

Aralarında ilişki olmayan tablolardan iki veya daha fazla alan kullanmaya çalışıyorsunuz. Aralarında ilişki olmayan alanları görselden kaldırıp tablolar arasında ilişki kurmanız gerekiyor. Bu işlemi yaptıktan sonra alanları tekrar görsele ekleyebilirsiniz. Bu işlemi Power BI Desktop veya Excel için Power Pivot uygulamalarında gerçekleştirebilirsiniz. [Daha fazla bilgi](desktop-create-and-manage-relationships.md)

**Birincil ve ikincil eksendeki gruplar çakışıyor. Birincil eksendeki gruplar, ikincil eksendeki gruplarla aynı anahtarlara sahip olamaz.**

Bu genellikle geçici bir sorundur. Bu durum genelde grupları satırlardan sütunlara taşıdığınızda ortaya çıkar. Bu durumda grupların tamamını taşımayı bitirdiğinizde hatanın ortadan kalkması gerekir. İletiyi görmeye devam ediyorsanız alanları satırlar ve sütunlar ya da eksen açıklaması arasında değiştirmeyi veya alanları görselden kaldırmayı deneyin.  

**Bu görsel kullanılabilir kaynakları aştı. Görüntülenen veri miktarını azaltmak için filtrelemeyi deneyin.**

Görseliniz, sonucu kullanılabilir kaynaklarla tamamlayamayacağımız kadar çok veriyi sorgulamayı denedi. Sonuçtaki veri miktarını azaltmak için görseli filtrelemeyi deneyin.

**Şu alanları tanımlayamıyoruz: {0}. Lütfen veri kümesinde bulunan alanları kullanarak görseli güncelleştirin.**

Alan silinmiş veya yeniden adlandırılmış olabilir. Bozuk alanı görselden kaldırabilir, farklı bir alan ekleyebilir ve tekrar sabitleyebilirsiniz.

**Bu görsel için veri alınamadı. Lütfen daha sonra yeniden deneyin.**

Bu genellikle geçici bir sorundur. Daha sonra yeniden denediğinizde aynı iletiyi görürseniz lütfen destek ekibiyle iletişime geçin.

## <a name="contact-support"></a>Desteğe başvurun
Sorun yaşamaya devam ediyorsanız daha fazla araştırma yapılabilmesi için lütfen [destek ekibiyle iletişime geçin](https://support.powerbi.com).

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
[Power BI kişisel ağ geçidiyle ilgili sorunları giderme](service-admin-troubleshooting-power-bi-personal-gateway.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

