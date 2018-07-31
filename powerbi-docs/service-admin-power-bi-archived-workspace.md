---
title: Power BI Arşivlenmiş Çalışma Alanı
description: Office 365 kiracınızı yönetmeye başladıktan sonra Power BI Arşivlenmiş Çalışma Alanı
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 8b9fcf1c6121c4aeecfdf948b77493f1f2a7f825
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34293640"
---
# <a name="power-bi-archived-workspace"></a>Power BI Arşivlenmiş Çalışma Alanı
Tüm kullanıcılar yalnızca birkaç dakika içinde kaydolup Power BI hizmetini kullanmaya başlayabilir.  Daha sonra kuruluşunuzun BT departmanı, kuruluşunuzdaki Power BI kullanıcılarının yönetimini devralabilir.  Böyle bir senaryoda kuruluşunuzdaki kullanıcıların ve izinlerin tek bir merkezden yönetilmesi özelliğinden faydalanabilir, kuruluşunuzdaki diğer hizmetler için kullandığınız kullanıcı adı ve parolanızla oturum açarak kolay oturum açma olanağından yararlanabilirsiniz. 

BT departmanınız Power BI yönetimini devralmadan önce oluşturduğunuz içerikler, [Power BI](https://app.powerbi.com)'ın sol gezinti bölmesindeki menüden erişebileceğiniz bir Power BI Arşivlenmiş Çalışma Alanına eklenir.  Yeni Power BI içeriğini, güvenliği ve yönetimi kuruluşunuzun BT departmanı tarafından sağlanan Çalışma Alanım bölümünde oluşturmanız gerekir.  Arşivlenmiş Çalışma Alanınız var olmaya devam eder ancak Arşivlenmiş Çalışma Alanınızdaki içerikle gerçekleştirebileceğiniz eylemler kısıtlıdır.  Bu kısıtlamaları kaldırmak için Arşivlenmiş Çalışma Alanınızdaki içeriği, BT departmanınız tarafından yönetilen Çalışma Alanım bölümüne geçirmeniz gerekir.

## <a name="restrictions-in-your-archived-workspace"></a>Arşivlenmiş Çalışma Alanınızdaki kısıtlamalar
Arşivlenmiş Çalışma Alanınızdaki içerikler silinmez.  Veri almaya, rapor ve pano oluşturmaya ve veri kümelerini yenilemeye devam edebilirsiniz.  İçerik paylaştığınız mevcut kullanıcılar da içeriği Arşivlenmiş Çalışma Alanınızda görüntülemeye devam edebilir.

Ancak, Arşivlenmiş Çalışma Alanınızdaki içerikle ilgili bazı kısıtlamalar vardır:

* **OneDrive İş.  ** Arşivlenmiş Çalışma Alanınızdaki veri kümeleri için artık OneDrive İş'ten veri alamaz ve var olan verileri yenileyemezsiniz.  Bu kaynağa bağlanmaya çalıştığınızda bir uyarıyla karşılaşırsınız.
* **Pano paylaşımı.  ** Arşivlenmiş Çalışma Alanınızdaki panoları diğer kullanıcılarla paylaşamazsınız.  Erişim sahibi olan kullanıcılar Arşivlenmiş Çalışma Alanlarına giderek, paylaşılan panoları görüntülemeye devam edebilir.
* **Grup oluşturma.  ** Arşivlenmiş Çalışma Alanınızda grup oluşturamazsınız.
* **Power BI mobil uygulamalarından erişim.  **Arşivlenmiş Çalışma Alanınızdaki içeriği web üzerinde görüntülemeye devam edebilirsiniz ancak bu içerik Power BI mobil uygulamalarında görünmez.

## <a name="migrating-content-in-your-archived-workspace"></a>Arşivlenmiş Çalışma Alanınızdaki İçeriği Geçirme
Power BI uygulamasını kullanmaya devam etmek için yeni içeriği, BT departmanınız tarafından yönetilen Çalışma Alanım bölümünde oluşturmanız gerekir.   Arşivlenmiş Çalışma Alanınızdaki içeriği, Çalışma Alanım bölümüne geçirmeyi de planlamanız gerekir.  İçerik geçirme yöntemi içerik türüne göre değişir:

* **Excel veya Power BI Desktop Veri Kümeleri.  ** Bu veri kümelerini geçirmek için, Arşivlenmiş Çalışma Alanınızdan Çalışma Alanım bölümüne geçin ve ardından, "Verilerim" düğmesine tıklayarak Excel veya Power BI Desktop dosyasını tekrar karşıya yükleyin.  Zamanlanmış yenilemeyi ayarladıysanız bu ayarları Çalışma Alanım bölümündeki yeni veri kümesi için tekrar yapılandırmanız gerekir.
* **Diğer Veri Kümeleri.  ** Arşivlenmiş Çalışma Alanınızda oluşturduğunuz diğer veri kümelerine yeniden bağlanmak için Çalışma Alanım bölümüne geçip Veri Al düğmesine tıklayın.  Güvenlik veya bağlantı bilgilerini tekrar girmeniz gerekebilir.
* **Raporlar.  ** Excel veya Power BI Desktop dosyalarında bulunan veya içerik paketleriyle birlikte yüklenen raporlar ilgili Excel veya Power BI Desktop dosyasını tekrar karşıya yüklediğinizde veya içerik paketine yeniden bağlandığınızda otomatik olarak yeniden oluşturulur.  Power BI hizmetini kullanarak kendi raporlarınızı oluşturduysanız bu raporları Çalışma Alanım bölümünde yeniden oluşturmanız gerekir.
* **Panolar.  ** İçerik paketleriyle birlikte yüklenen panolar, Çalışma Alanım bölümünde içerik paketine yeniden bağlandığınızda otomatik olarak tekrar oluşturulur.  Power BI hizmetini kullanarak kendi panolarınızı oluşturduysanız bu panoları Çalışma Alanım bölümünde yeniden oluşturmanız gerekir.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

