---
title: Yenileme ile ilgili sorun giderme senaryoları
description: Yenileme ile ilgili sorun giderme senaryoları
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 09/13/2019
ms.author: mblythe
LocalizationGroup: Data refresh
ms.openlocfilehash: 564c3d03a7879cd7788e19055d8c11e4de46013f
ms.sourcegitcommit: e5cf19e16112c7dad1591c3b38d232267ffb3ae1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72543868"
---
# <a name="troubleshooting-refresh-scenarios"></a>Yenileme ile ilgili sorun giderme senaryoları

Burada Power BI hizmetindeki verileri yenilerken karşılaşabileceğiniz farklı senaryolarla ilgili bilgilere yer verilmiştir.

> [!NOTE]
> Aşağıda listelenmeyen bir senaryoyla karşılaşırsanız ve bu durum sorun yaratırsa daha fazla yardım almak için [topluluk sitesine](http://community.powerbi.com/) başvurabilir veya bir [destek bileti](https://powerbi.microsoft.com/support/) oluşturabilirsiniz.
>
>

## <a name="refresh-using-web-connector-doesnt-work-properly"></a>Web bağlayıcısı kullanılarak gerçekleştirilen yenileme işlemi düzgün bir şekilde gerçekleştirilmiyor

[**Web.Page**](https://msdn.microsoft.com/library/mt260924.aspx) işlevini kullanan bir Web bağlayıcısı betiğiniz varsa ve veri kümenizi veya raporunuzu 18 Kasım 2016'dan sonra güncelleştirdiyseniz yenileme işleminin düzgün çalışması için ağ geçidi kullanmanız gerekir.

## <a name="unsupported-data-source-for-refresh"></a>Yenileme için desteklenmeyen veri kaynakları

Bir veri kümesini yapılandırırken, veri kümesinde yenileme için desteklenmeyen veri kaynaklarının kullanıldığını belirten bir hatayla karşılaşabilirsiniz. Ayrıntılar için bkz. [Yenileme için desteklenmeyen veri kaynaklarıyla ilgili sorunları giderme](service-admin-troubleshoot-unsupported-data-source-for-refresh.md).

## <a name="dashboard-doesnt-reflect-changes-after-refresh"></a>Yenileme sonrasında değişiklikler panoya yansıtılmıyor

Yenileme işleminin pano kutucuklarına yansıtılması için lütfen 10-15 dakika kadar bekleyin. Bu sürenin sonunda da değişiklikler görünmüyorsa görselleştirmeyi panoya yeniden sabitleyin.

## <a name="gatewaynotreachable-when-setting-credentials"></a>Kimlik bilgilerini ayarlarken GatewayNotReachable hatası

Bir veri kaynağı için kimlik bilgilerini ayarlamaya çalışırken `GatewayNotReachable` hatasıyla karşılaşabilirsiniz. Bu durum ağ geçidinin eski bir sürüm olmasından kaynaklanabilir. En son ağ geçidi sürümünü yükleyip yeniden deneyin.

## <a name="processing-error-the-following-system-error-occurred-type-mismatch"></a>İşleme Hatası: Şu sistem hatası oluştu: Tür Uyuşmazlığı

Power BI Desktop dosyanızdaki veya Excel çalışma kitabınızdaki M betiğinde sorun olabilir. Ayrıca sorun Power BI Desktop sürümünün eski olmasından da kaynaklanıyor olabilir.

## <a name="tile-refresh-errors"></a>Kutucuk yenileme hataları

Pano kutucuklarında karşılaşabileceğiniz hatalar ve açıklamaları için bkz. [Kutucuk hatalarıyla ilgili sorunları giderme](refresh-troubleshooting-tile-errors.md).

## <a name="refresh-fails-when-updating-data-from-sources-that-use-aad-oauth"></a>AAD OAuth kullanan kaynaklardaki verilerle güncelleştirme yapılırken yenileme işlemi başarısız oluyor

Birçok farklı veri kaynağı tarafından kullanılan Azure Active Directory (**AAD**) OAuth belirtecinin süresi yaklaşık bir saat içinde dolar. Power BI hizmeti veri yükleme sırasında iki saate kadar beklediğinden veri yükleme işleminin belirtecin ömründen fazla (bir saatten uzun) olduğu durumlarla karşılaşabilirsiniz. Bu durumda veri yükleme işlemi başarısız olabilir ve kimlik bilgileri hatası ile karşılaşılabilir.

**Microsoft Dynamics CRM Online**, **SharePoint Online** (SPO) ve diğer birçok veri kaynağı ile AAD OAuth kullanılmaktadır. Bu tür veri kaynaklarına bağlanıyorsanız ve bir saatten uzun süren veri yükleme işlemlerinde kimlik bilgileri hatası alıyorsanız bu, soruna açıklama getirebilir.

Microsoft, veri yükleme yapılırken belirtecin yenilenip işleme devam edilmesini sağlayacak bir çözüm üzerinde çalışmaktadır. Ancak Dynamics CRM Online veya SharePoint Online örneğiniz (ya da AAD OAuth kullanan başka bir veri kaynağı) iki saatlik veri yükleme eşiğini aşacak kadar büyükse Power BI hizmetinde de veri yükleme zaman aşımı hatasıyla karşılaşabilirsiniz.

Ayrıca yenileme işleminin düzgün çalışmasını sağlamak üzere, AAD OAuth kullanarak **SharePoint Online** veri kaynağına bağlanırken, **Power BI hizmetinde** oturum açmak için kullandığınız hesabı kullanmanız gerekir.

## <a name="uncompressed-data-limits-for-refresh"></a>Yenileme için sıkıştırılmamış veri sınırları

**Power BI hizmetine** aktarılan veri kümeleri için maksimum boyut 1 GB'tır. Yüksek performans için bu veri kümeleri yoğun bir şekilde sıkıştırılır. Ayrıca hizmet, paylaşılan kapasitede, yenileme sırasında işlenebilecek sıkıştırılmamış veri miktarını 10 GB ile sınırlar. Sıkıştırma dikkate alındığından, bu sınır 1 GB'tan çok daha yüksektir. Power BI Premium'daki veri kümeleri bu sınıra tabi değildir. Power BI hizmetinde yenileme işlemi bu nedenle başarısız olursa lütfen Power BI'a aktarılan veri miktarını azaltıp tekrar deneyin.

## <a name="scheduled-refresh-timeout"></a>Zamanlanmış yenileme zaman aşımı

İçerik aktarılan veri kümeleri için zamanlanmış yenileme iki saatin ardından zaman aşımına uğrar. Bu zaman aşımı **Premium** çalışma alanlarındaki veri kümeleri için beş saate yükseltilmiştir. Bu sınırdan etkileniyorsanız veri kümenizin boyutunu veya karmaşıklık düzeyini azaltmayı ya da veri kümesini daha küçük parçalara bölmeyi göz önünde bulundurabilirsiniz.

## <a name="scheduled-refresh-failures"></a>Zamanlanmış yenileme hataları

Zamanlanmış yenileme arka arkaya dört kez başarısız olursa Power BI yenilemeyi devre dışı bırakır. Arka plandaki sorunu çözün ve sonra zamanlanmış yenilemeyi yeniden etkinleştirin.

## <a name="access-to-the-resource-is-forbidden"></a>Kaynağa erişim yasak  

Bu hata, süresi dolan önbelleğe alınmış kimlik bilgileri nedeniyle oluşabilir. Power BI'da oturum açıp https://app.powerbi.com?alwaysPromptForContentProviderCreds=true sayfasına giderek internet tarayıcınızın önbelleğini temizleyin. Bunun yapılması, kimlik bilgilerinizi güncelleştirilmeye zorlar.

## <a name="data-refresh-failure-because-of-password-change-or-expired-credentials"></a>Parola değişikliği veya süresi dolan kimlik bilgileri nedeniyle veri yenileme hatası

Veri yenileme işlemi, süresi dolan önbelleğe alınmış kimlik bilgileri nedeniyle de başarısız olabilir. Power BI'da oturum açıp https://app.powerbi.com?alwaysPromptForContentProviderCreds=true sayfasına giderek internet tarayıcınızın önbelleğini temizleyin. Bunun yapılması, kimlik bilgilerinizi güncelleştirilmeye zorlar.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI'da veri yenileme](refresh-data.md)  
- [Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  
- [Power BI Gateway - Personal ile ilgili sorunları giderme](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Başka bir sorunuz mu var? [Microsoft Power BI Topluluğu'na sormayı deneyin](http://community.powerbi.com/)

