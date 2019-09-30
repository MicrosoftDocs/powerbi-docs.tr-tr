---
title: Power BI Arşivlenmiş Çalışma Alanı
description: Office 365 kiracınızı yönetmeye başladıktan sonra Power BI Arşivlenmiş Çalışma Alanı
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/18/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 891ffffd885e2b5d59cba64e6e99ce7fe3cf811b
ms.sourcegitcommit: a6602d84c86d3959731a8d0ba39a522914f13d1a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2019
ms.locfileid: "71175692"
---
# <a name="power-bi-archived-workspace"></a>Power BI Arşivlenmiş Çalışma Alanı

> [!IMPORTANT]
> Power BI 2019 sonunda kaldırılacak Arşivlenmiş Çalışma Alanı özelliğini artık desteklememektedir. Arşivlenmiş Çalışma Alanı kullanıyorsanız, tutmak istediğiniz içerikleri geçerli kiracınızdaki yeni bir çalışma alanında hemen yeniden oluşturmanız gerekir. Arşivlenmiş Çalışma Alanına erişiminizin devam edeceğine güvenemezsiniz. Power BI, [bir Azure AD kiracısının dış devralması](service-admin-faq.md#what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users) şeklindeki ilgili özelliği artık desteklememektedir.

Tüm kullanıcılar yalnızca birkaç dakika içinde kaydolup Power BI hizmetini kullanmaya başlayabilir.  Daha sonra kuruluşunuzun BT departmanı, kuruluşunuzdaki Power BI kullanıcılarının yönetimini devralabilir.  Böyle bir senaryoda kuruluşunuzdaki kullanıcıların ve izinlerin tek bir merkezden yönetilmesi özelliğinden faydalanabilirsiniz. Ayrıca kuruluşunuzdaki diğer hizmetler için kullandığınız kullanıcı adı ve parolanızla oturum açarak kolay oturum açma olanağından da yararlanabilirsiniz.

BT departmanınız Power BI yönetimini devralmadan önce oluşturduğunuz içerikler, [Power BI](https://app.powerbi.com)'ın sol gezinti bölmesindeki menüden erişebileceğiniz bir Power BI Arşivlenmiş Çalışma Alanına eklenir. Yeni Power BI içeriğini, güvenliği ve yönetimi kuruluşunuzun BT departmanı tarafından sağlanan Çalışma Alanım bölümünde oluşturmanız gerekir.  Arşivlenmiş Çalışma Alanınız var olmaya devam eder ancak Arşivlenmiş Çalışma Alanınızdaki içerikle gerçekleştirebileceğiniz eylemler kısıtlıdır.  Bu kısıtlamaları kaldırmak için Arşivlenmiş Çalışma Alanınızdaki içeriği, BT departmanınız tarafından yönetilen Çalışma Alanım bölümüne geçirmeniz gerekir.

## <a name="restrictions-in-your-archived-workspace"></a>Arşivlenmiş Çalışma Alanınızdaki kısıtlamalar

Power BI, Arşivlenmiş Çalışma Alanınızdaki içeriği silmez. Veri almaya, rapor ve pano oluşturmaya ve veri kümelerini yenilemeye devam edebilirsiniz. İçerik paylaştığınız mevcut kullanıcılar da içeriği Arşivlenmiş Çalışma Alanınızda görüntülemeye devam edebilir. Ancak, Arşivlenmiş Çalışma Alanınızdaki içerikle ilgili bazı kısıtlamalar vardır:

* **OneDrive İş**: Arşivlenmiş Çalışma Alanınızdaki veri kümeleri için artık OneDrive İş'ten veri alamaz ve var olan verileri yenileyemezsiniz.  Bu kaynağa bağlanmaya çalıştığınızda bir uyarıyla karşılaşırsınız.

* **Pano paylaşımı**: Arşivlenmiş Çalışma Alanınızdaki panoları diğer kullanıcılarla paylaşamazsınız.  Erişim sahibi olan kullanıcılar Arşivlenmiş Çalışma Alanlarına giderek, paylaşılan panoları görüntülemeye devam edebilir.

* **Grup oluşturma**: Arşivlenmiş Çalışma Alanınızda grup oluşturamazsınız.

* **Power BI mobil uygulamalarından erişim**: Arşivlenmiş Çalışma Alanınızdaki içeriği web üzerinde görüntülemeye devam edebilirsiniz ancak bu içerik artık Power BI mobil uygulamalarında görünmez.

## <a name="migrating-content-in-your-archived-workspace"></a>Arşivlenmiş Çalışma Alanınızdaki İçeriği Geçirme

Power BI'ı kullanmaya devam etmek için Çalışma Alanım bölümünde yeni içerik oluşturmanız gerekir. Arşivlenmiş Çalışma Alanındaki içeriği, Çalışma Alanım bölümüne geçirmeyi de planlamanız gerekir.  İçerik geçirme yöntemi içerik türüne göre değişir:

* **Excel veya Power BI Desktop veri kümeleri**: Bu veri kümelerini geçirmek için, Arşivlenmiş Çalışma Alanınızdan Çalışma Alanım bölümüne geçin ve ardından, **Verilerim** düğmesini seçerek Excel veya Power BI Desktop dosyasını tekrar karşıya yükleyin.  Zamanlanmış yenilemeyi ayarladıysanız bu ayarları Çalışma Alanım bölümündeki yeni veri kümesi için tekrar yapılandırmanız gerekir.

* **Diğer Veri Kümeleri**: Arşivlenmiş Çalışma Alanınızda oluşturduğunuz diğer veri kümelerine yeniden bağlanmak için Çalışma Alanım bölümüne geçip **Veri Al** düğmesini seçin.  Güvenlik veya bağlantı bilgilerini tekrar girmeniz gerekebilir.

* **Raporlar**: Excel veya Power BI Desktop dosyalarını yeniden karşıya yüklediğinizde bu Excel veya Power BI Desktop dosyalarındaki raporlar otomatik olarak yeniden oluşturulur. Bir içerik paketiyle birlikte yüklenen raporlar da içerik paketine tekrar bağlandığınızda yeniden oluşturulur. Power BI hizmetini kullanarak kendi raporlarınızı oluşturduysanız bu raporları Çalışma Alanım bölümünde yeniden oluşturun.

* **Panolar**: İçerik paketleriyle birlikte yüklenen panolar, Çalışma Alanım bölümünde içerik paketine yeniden bağlandığınızda otomatik olarak tekrar oluşturulur. Power BI hizmetini kullanarak kendi panolarınızı oluşturduysanız bu panoları Çalışma Alanım bölümünde yeniden oluşturun.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

