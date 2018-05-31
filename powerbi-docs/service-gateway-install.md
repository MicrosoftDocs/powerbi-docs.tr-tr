---
title: Power BI için ağ geçidi yükleme
description: Power BI’da şirket içi verilere bağlanabilmeniz için bir ağ geçidini nasıl yükleyeceğinizi öğrenin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 04/18/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 936e794b187366e91cf550c16379216ddf1fbf36
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34298562"
---
# <a name="install-a-gateway-for-power-bi"></a>Power BI için ağ geçidi yükleme

Power BI ağ geçidi, şirket içi ağı içine yüklediğiniz bir yazılımdır ve bu ağda verilere erişimi kolaylaştırır. [Genel bakış](service-gateway-getting-started.md) bölümünde açıklandığı gibi, kişisel modda veya standart modda (önerilen) ağ geçidi yükleyebilirsiniz. Standart modda tek başına ağ geçidi yükleyebilir veya yüksek kullanılabilirlik için önerilen bir yöntem olarak bir ağ geçidini *kümeye* ekleyebilirsiniz. Bu makalede, standart bir ağ geçidi yükleme ve sonra başka bir ağ geçidi ekleyerek küme oluşturma işlemi gösterilmektedir.

PowerApps’e kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).


## <a name="download-and-install-a-gateway"></a>Bir ağ geçidi indirme ve yükleme

Ağ geçidi, onu yüklediğiniz bilgisayarda çalışır. Bu nedenle, her zaman açık olan bir bilgisayara yüklediğinizden emin olun. Daha iyi performans ve güvenilirlik için, bilgisayarın kablosuz ağ yerine kablolu bir ağda çalışması önerilir.

1. Power BI hizmetinde sağ üst köşedeki **indirme simgesi** ![İndirme simgesi](media/service-gateway-install/icon-download.png) > **Veri Ağ Geçidi** öğesini seçin.

    ![Veri Ağ Geçidi](media/service-gateway-install/data-gateway.png)

2. İndirme sayfasında **AĞ GEÇİDİNİ İNDİR** düğmesini seçin.

3. **Sonraki** seçeneğini belirleyin.     

    ![Veri ağ geçidi yükleyicisi](media/service-gateway-install/gateway-installer.png)

4. **Şirket içi veri ağ geçidi (önerilen)** > **İleri**’yi seçin.

    ![Ağ geçidi türü](media/service-gateway-install/gateway-type.png)

5. Varsayılan yükleme yolunu değiştirmeyin ve koşulları kabul edin > **Yükle**’yi seçin.

    ![Yükleme yolu](media/service-gateway-install/install-path.png)

6. Power BI’da oturum açmak için kullandığınız hesabı girin > **Oturum aç**’ı seçin.

    ![E-posta adresi](media/service-gateway-install/email-address.png)

    Ağ geçidi, Power BI hesabınızla ilişkilendirilir ve ağ geçitlerini Power BI hizmetinden yönetirsiniz. Artık hesabınızda oturum açtınız.

7. **Bu bilgisayara yeni bir ağ geçidi kaydedin** > **İleri**’yi seçin.

    ![Ağ geçidini kaydetme](media/service-gateway-install/register-gateway.png)

8. Ağ geçidi için bir ad (kiracıda benzersiz olmalıdır) ve kurtarma anahtarı girin. Ağ geçidinizi kurtarmak veya taşımak isterseniz bu anahtar gerekli olur. **Yapılandır**'ı seçin.

    ![Ağ geçidini yapılandırma](media/service-gateway-install/configure-gateway.png)

    **Mevcut bir ağ geçidi kümesi ekleyin** seçeneğine dikkat edin. Makalenin sonraki bölümünde bu seçeneği kullanacaksınız.

9. Son penceredeki bilgileri gözden geçirin. Ağ geçidinin Power BI ve aynı zamanda PowerApps ile Flow için kullanılabilir olduğuna dikkat edin, çünkü üçü için de aynı hesabı kullanıyorum. **Kapat**'ı seçin.

    ![Özet ekranı](media/service-gateway-install/summary-screen.png)

Başarıyla bir ağ geçidi yüklediğinize göre küme oluşturmak için başka bir ağ geçidi ekleyebilirsiniz.


## <a name="add-another-gateway-to-create-a-cluster"></a>Küme oluşturmak üzere başka bir ağ geçidi ekleme

Küme, ağ geçidi yöneticilerinin şirket içi veri erişimi için tek bir hata noktasına sahip olmaktan kaçınmasına olanak tanır. Birincil ağ geçidi kullanılamıyorsa, veri istekleri eklediğiniz ikinci ağ geçidine yönlendirilir vb. Bir bilgisayara yalnızca bir standart ağ geçidi yükleyebilirsiniz; bu nedenle, küme için ikinci ağ geçidini farklı bir bilgisayara yüklemeniz gerekir. Kümede yedeklilik istediğiniz için bunun yapılması mantıklıdır.

Yüksek kullanılabilirlik ağ geçidi kümeleri, Şirket içi veri ağ geçidinin Kasım 2017 güncelleştirmesine veya üzerine sahip olmasını gerektirir.

1. Ağ geçidini farklı bir bilgisayara indirip yükleyin.

2. Power BI hesabınızda oturum açtıktan sonra ağ geçidini kaydedin. **Mevcut bir kümeye ekle**’yi seçin. **Kullanılabilir ağ geçidi kümeleri** altında, yüklediğiniz ilk ağ geçidini (*birincil ağ geçidi*) seçin ve o ağ geçidinin kurtarma anahtarını girin. **Yapılandır**'ı seçin.

    ![Ağ geçidini kümeye ekleme](media/service-gateway-install/add-cluster.png)


## <a name="next-steps"></a>Sonraki adımlar

[Power BI ağ geçidi yönetme](service-gateway-manage.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)