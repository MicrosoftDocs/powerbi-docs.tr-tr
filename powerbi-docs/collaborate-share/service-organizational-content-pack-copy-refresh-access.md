---
title: 'Kurumsal içerik paketleri: Yönetme ve güncelleştirme'
description: Power BI'da kurumsal içerik paketlerinin kopyalarını oluşturma ve erişim sorunlarını gidermeyle ilgili bilgi edinin
author: maggiesMSFT
ms.reviewer: lukaszp, kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/02/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 905e461c69a898b41b45e48405c3aaaa6e09cfec
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83141896"
---
# <a name="organizational-content-packs-copy-refresh-and-get-access"></a>Kurumsal içerik paketleri: kopyalama, yenileme ve erişim elde etme

Bir kurumsal içerik paketi yayımlandığında, bütün alıcılar aynı panoyu, raporları, Excel çalışma kitaplarını, veri kümelerini ve verileri görür (SQL Server Analysis Services (SSAS) veri kaynağı olmadığı sürece).  İçerik paketini, [yalnızca içerik paketi oluşturucusu düzenleyebilir ve yeniden yayımlayabilir](service-organizational-content-pack-manage-update-delete.md).  Ancak, tüm alıcılar, özgün içerik paketiyle birlikte kullanılabilecek bir kopyasını kaydedebilir.

İçerik paketi oluşturma, pano paylaşmaktan veya bir grupta panolar üzerinde işbirliği yapmaktan farklıdır. Kendi durumunuz için en iyi seçeneği belirlemek üzere [Panolar ve raporlar üzerinde nasıl işbirliği yapabilir ve bunları nasıl paylaşabilirim?](service-how-to-collaborate-distribute-dashboards-reports.md) makalesini okuyun.

> [!NOTE]
> Yeni çalışma alanı deneyiminde kurumsal içerik paketleri oluşturamaz veya yükleyemezsiniz. Henüz yapmadıysanız, şimdi içerik paketlerinizi uygulamalara yükseltmek için iyi bir zamandır. [Yeni çalışma alanı deneyimi hakkında daha fazla bilgi](service-create-the-new-workspaces.md) edinin.
>

## <a name="create-a-copy-of-an-organizational-content-pack"></a>Kurumsal içerik paketinin bir kopyasını oluşturma
İçerik paketinin, size ait ve başkalarına görünemeyecek bir kopyasını oluşturun.

1. İçerik paketi panosu yanındaki **Diğer seçenekler**’i (...) ve Kopya oluştur'u seçin.

    ![](media/service-organizational-content-pack-copy-refresh-access/power-bi-create-copy-organizational-content-pack.png)
2. **Kaydet**’i seçin.  

Artık, değiştirebileceğiniz bir kopyanız var. Yaptığınız değişiklikleri sizden başka kimse göremez.

> [!NOTE]
> Daha önce, bir içerik paketini yüklediğinizde veya kopyasını oluşturduğunuzda, çalışma alanı içerik listesinde yeni bir veri kümesi görüntüleniyordu. Kısa bir süre önce yapılan bir güncelleştirme ile deneyim yeni başvurulan veri kümesi simgesi kullanılarak yalnızca bir tane görüntülemek için basitleştirildi:
>
> ![bağlantı simgesi ile veritabanı](media/service-organizational-content-pack-copy-refresh-access/power-bi-dataset-reference-icon.png)
>

## <a name="help--i-can-no-longer-access-the-content-pack"></a>Yardım!  İçerik paketine artık erişemiyorum
Bu durum çeşitli nedenlerle oluşabilir:

* **Üyelik değişiklikleri**: İçerik paketleri e-posta dağıtım gruplarında, güvenlik gruplarında ve [Office 365'i temel alan Power BI gruplarında](https://support.office.com/article/Create-a-group-in-Office-365-7124dc4c-1de9-40d4-b096-e8add19209e9) yayımlanır.  Gruptan çıkarılırsanız içerik paketine erişiminiz olmayacaktır.
* **Dağıtım değişiklikleri**: Dağıtımı, içerik paketi oluşturucusu değiştirir. Örneğin, içerik paketi ilk olarak bütün kuruluşta yayımlanmış ancak oluşturucusu daha küçük bir kitle için onu yeniden yayımlamışsa belki bu kitleye dahil olmayabilirsiniz.
* **Güvenlik ayarları değişiklikleri**: Pano ve raporlar şirket içi SSAS veri kaynaklarına bağlanıyorsa ve güvenlik ayarlarında değişiklik yapılmışsa sunucu izinleriniz iptal edilebilir.

## <a name="how-are-organizational-content-packs-refreshed"></a>Kurumsal içerik paketleri nasıl yenilenir?
İçerik paketi oluşturulduğunda yenileme ayarları veri kümesiyle birlikte devralınır.  İçerik paketinin bir kopyasını oluşturduğunuzda yeni sürüm, özgün veri kümesi ve yenileme zamanlamasına olan bağlantısını korur.

Bkz. [Kurumsal içerik paketlerini yönetme, güncelleştirme ve silme](service-organizational-content-pack-manage-update-delete.md).

## <a name="next-steps"></a>Sonraki adımlar
* [Kurumsal içerik paketlerine giriş](service-organizational-content-pack-introduction.md)
* [Power BI'da grup oluşturma](service-create-distribute-apps.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)