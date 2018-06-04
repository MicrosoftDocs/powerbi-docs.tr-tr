---
title: Power BI ile Webtrends'e Bağlanma
description: Power BI için Webtrends
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 89eda507e0b908fe746cb13c0c6477baed07ba3c
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34243036"
---
# <a name="connect-to-webtrends-with-power-bi"></a>Power BI ile Webtrends'e Bağlanma
Power BI için Webtrends içerik paketi, toplam sayfa görüntüleme sayısı ve trafik kaynağına göre ziyaretler gibi kullanıma hazır ölçümler içerir. Webtrends verilerinizi Power BI'da görselleştirmeye başlamak için, Webtrends hesabınıza bağlanmanız gerekir. Sağlanan panoyu ve raporları kullanabilir veya bunları, en çok önem verdiğiniz bilgileri öne çıkaracak şekilde özelleştirebilirsiniz.  Veriler günde bir kez otomatik olarak yenilenir.

[Power BI için Webtrends içerik paketine](https://app.powerbi.com/getdata/services/webtrends) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-webtrends/getdata3.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-webtrends/services.png)
3. **Webtrends** \> **Al**'ı seçin.
   
   ![](media/service-connect-to-webtrends/webtrends.png)
4. İçerik paketi, belirli bir Webtrends profil kimliğine bağlanır. [Bu parametreyi bulma](#FindingParams) ile ilgili ayrıntılar için aşağıya bakın.
   
   ![](media/service-connect-to-webtrends/parameters.png)
5. Bağlanmak için Webtrends kimlik bilgilerinizi girin. Kullanıcı adı alanına, hesap ve kullanıcı adınızı girmeniz gerektiğini unutmayın. [Ayrıntıları](#FindingParams) aşağıda bulabilirsiniz.
   
   ![](media/service-connect-to-webtrends/creds.png)
6. Onay vermenizin ardından, içeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
   ![](media/service-connect-to-webtrends/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
<a name="Included"></a>

Webtrends içerik paketi, aşağıdaki raporlardan veri çeker:  

| Rapor Adı | Rapor Kimliği |
| --- | --- |
| Ana Ölçümler | |
| Sitedeki Aramalar |34awBVEP0P6 |
| Çıkış Sayfaları |7FshY8eP0P6 |
| Sonraki Sayfalar |CTd5rpeP0P6 |
| Önceki Sayfalar |aSdOeaUgnP6 |
| Site Sayfaları |oOEWQj3sUo6 |
| Sitedeki Reklamlar için Geçişli Tıklamalar |41df19b6d9f |
| Şehirler |aUuHskcP0P6 |
| Ülkeler |JHWXJNcP0P6 |
| Ziyaretçiler |xPcmTDDP0P6 |
| Ziyaret Süresi |U5KAyqdP0P6 |
| Arama Tümcecikleri |IKYEDxIP0P6 |
| Trafik Kaynakları |JmttAoIP0P6 |
| Arama Motorları |yGz3gAGP0P6 |
| Giriş Sayfaları |i6LrkNVRUo6 |

>[!NOTE]
>SharePoint profilleri için ölçüm adları, Webtrends kullanıcı arabiriminde görünenlerden biraz farklı olabilir. SharePoint ve Web profilleri arasında tutarlılık sağlamak için aşağıdaki eşleme yapılmıştır:   

    - Oturumlar = Ziyaretler  
    - Yeni Kullanıcılar = Yeni Ziyaretçiler  
    - Oturum başına Görüntülemeler = Ziyaret başına Sayfa Görüntülemeleri  
    - Günlük Ortalama Kullanıcı Süresi = Sitedeki Ziyaretçi başına Ortalama Süre  

## <a name="system-requirements"></a>Sistem gereksinimleri
İçerik paketinin, [doğru rapor kümesine](#Included) sahip bir Webtrends profiline erişmesi gerekir.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Profil seçtikten sonra Webtrends profil kimliğiniz URL'de bulunabilir:

![](media/service-connect-to-webtrends/webtrendsparameters.png)

Kimlik bilgileriniz Webtrends'de oturum açmak için kullandıklarınızla aynıdır, ancak hesap ve kullanıcı adınızın aynı satırda ve ters eğik çizgiyle bölünerek yazılması beklenir:

![](media/service-connect-to-webtrends/webtrendscreds.png)

## <a name="troubleshooting"></a>Sorun giderme
Kimlik bilgilerinizi sağladıktan sonra içerik paketi yüklenirken bir sorunla karşılaşabilirsiniz. Yükleme sırasında "Hata" iletisini görürseniz, lütfen aşağıdaki sorun giderme önerilerini gözden geçirin. Sorun yaşamaya devam ediyorsanız lütfen https://support.powerbi.com'da bir destek bileti oluşturun

1. Doğru profil kimliğinin kullanıldığından emin olun, daha fazla ayrıntı için [Parametreleri bulma](#FindingParams) bölümüne bakın.
2. Kullanıcının ["Neleri kapsar?"](#Included) bölümünde listelenen raporlara erişiminin bulunduğundan emin olun.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

