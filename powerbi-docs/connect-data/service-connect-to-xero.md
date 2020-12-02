---
title: Power BI ile Xero'ya bağlanma
description: Power BI için Xero
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 03/06/2020
LocalizationGroup: Connect to services
ms.openlocfilehash: c942e399eb32fd7118d515f0d072972e3a820578
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96410494"
---
# <a name="connect-to-xero-with-power-bi"></a>Power BI ile Xero'ya bağlanma
Xero, özellikle küçük ölçekli işletmeler için tasarlanmış kullanımı kolay bir çevrimiçi muhasebe yazılımıdır. Bu Power BI şablon uygulamasıyla, Xero finansal bilgilerinizi temel alan ilgi çekici görselleştirmeler oluşturun. Varsayılan panonuz nakit pozisyonu, geliri ve giderleri, kâr zarar eğilimi, borçlu günleri ve yatırım getirisi gibi çok sayıda küçük işletme ölçümleri içerir.

Power BI için [Xero şablon uygulamasına](https://app.powerbi.com/getdata/services/xero) bağlanın veya [Xero ve Power BI](https://help.xero.com/Power-BI) tümleştirmesi hakkında daha fazla bilgi edinin.

## <a name="how-to-connect"></a>Bağlanma

[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]

3. **Xero** \> **Şimdi edinin**'i seçin.
4. **Bu Power BI uygulaması yüklensin mi?** iletişim kutusunda **Yükle**’yi seçin.

    ![Xero'yu yükleme](media/service-connect-to-xero/power-bi-install-xero.png)

4. **Uygulamalar** bölmesinde **Xero** kutucuğunu seçin.

   ![Xero kutucuğunu seçin](media/service-connect-to-xero/power-bi-start-xero.png)

6. **Yeni uygulamanızı kullanmaya başlayın** alanında **Bağlan** seçeneğini belirleyin.

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

4. Xero hesabınızla ilişkilendirilen kuruluş için bir takma ad girin. Herhangi bir şey yazabilirsiniz; bu, birden çok Xero kuruluşuna sahip kullanıcılara yardımcı olmak için yapılmaktadır. Ayrıntılar için bu makalenin devamındaki [parametreleri bulma](#FindingParams) bölümünü inceleyin.

    ![Kuruluş takma adı](media/service-connect-to-xero/params.png)

5. **Kimlik Doğrulama Yöntemi** alanında **OAuth**'u seçin. İstendiğinde Xero hesabınızda oturum açıp bağlanacağınız kuruluşu seçin. Oturum açma işlemi tamamlandığında, yükleme işlemini başlatmak için **Oturum Aç**'ı seçin.
   
    ![Kimlik doğrulama yöntemi](media/service-connect-to-xero/creds.png)
   
    ![Xero'ya hoş geldiniz](media/service-connect-to-xero/creds2.png)
6. Onay vermenizin ardından, içeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında gezinti bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
     ![Xero panosu](media/service-connect-to-xero/power-bi-xero-dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](../consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](../create-reports/service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](../consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="whats-included"></a>Neleri kapsar?
Şablon uygulaması panosu çeşitli alanlarda kutucuklar ve ölçümler ile bunlar hakkında daha fazla bilgi edinmek için raporlar içerir:  

| Alan | Pano Kutucukları | Rapor |
| --- | --- | --- |
| Nakit |Günlük nakit akışı <br>Nakit girişi <br>Nakit çıkışı <br>Hesaba göre kapanış bakiyesi <br>Bugün kapanış bakiyesi |Banka hesabı |
| Müşteri |Faturalanan Satışlar <br>Müşteri tarafından Faturalanan Satışlar <br>Faturalanan Satış artışı eğilimi <br>Son faturalar <br>Bekleyen Alacaklar <br>Vadesi dolmuş Alacaklar |Müşteri <br>Sayım |
| Sağlayıcı |Faturalandırılan satın alma işlemleri <br>Sağlayıcı tarafından faturalanan satın alma <br>Faturalandırılan satın alma işlemleri büyüme eğilimi <br> Son faturalar <br>Ödenmemiş Borçlar <br>Vadesi geçmiş Borçlar |Üreticiler <br>Sayım |
| Sayım |Aylık, ürüne göre satış miktarı |Sayım |
| Kar ve zarar |Aylık kar ve zarar <br>NET kar Bu mali yıl <br>NET kar bu ay <br>En çok harcama hesapları |Kar ve zarar |
| Bilanço |Toplam varlıklar <br>Toplam Borçlar <br>Hisse senedi |Bilanço |
| Sistem durumu |Cari Oran <br>Brüt kâr yüzdesi <br> Toplam varlıklar üzerinde döndürür <br>Toplam Borçlar hisse senedi/oranı |Sistem durumu <br>Sözlük ve teknik notlar |

Veri kümesi, raporlarınızı ve panolarınızı özelleştirmek için şu tabloları da içerir:  

* Adresleri  
* Uyarılar  
* Banka deyimi günlük bakiyesi  
* Banka deyimleri  
* Kişiler  
* Harcama talepleri  
* Fatura Satır öğeleri  
* Faturalar  
* Öğeleri  
* Ay sonu  
* Kuruluş  
* Deneme bakiyesi  
* Xero hesapları

## <a name="system-requirements"></a>Sistem Gereksinimleri
Xero şablon uygulamasına erişmek için şu roller gereklidir: "Standard + Reports" (Standart + Raporlar) veya "Advisor" (Danışman).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Kuruluşunuza Power BI'da izlemek için bir ad sağlayın. Ad belirlemek, birden çok farklı kuruluşa bağlanmanıza olanak sağlar. Zamanlanmış yenilemeyi etkileyeceğinden birden çok kez aynı kuruluşa bağlanamazsınız.   

## <a name="troubleshooting"></a>Sorun giderme
* Xero kullanıcılarının Power BI için Xero şablon uygulamasına erişmeleri için şu rollere sahip olması gerekir: "Standard + Reports" (Standart + Raporlar) veya "Advisor" (Danışman). Şablon uygulaması, Power BI aracılığıyla raporlama verilerine erişmek için kullanıcı temelli izinler kullanır.
* Yükleme sırasında panodaki kutucuklar genel yükleme durumunda olur. Yükleme tamamlanana kadar bu şekilde kalır. Yüklemenizin tamamlandığı ancak kutucukların yüklenmeye devam ettiğiyle ilgili bir bildirim alırsanız panonuzun en üst sağında bulunan ... simgesini kullanarak pano kutucuklarını yenilemeyi deneyin.
* Şablon uygulamanız yenilenmezse Power BI'da aynı kuruluşa birden fazla kez bağlanıp bağlanmadığınızı kontrol edin. Xero bir kuruluşa yalnızca tek bir etkin bağlantı kurulmasına izin verir ve aynı kuruluşa birden fazla kez bağlanırsanız kimlik bilgilerinizin geçersiz olduğunu belirten bir hata görebilirsiniz.  
* Hata iletileri veya uzun yükleme süreleri gibi, Power BI için Xero şablon uygulamasıyla bağlantı kurma konusundaki sorunlar için, ilk olarak önbelleği/tanımlama bilgilerini temizleyin ve tarayıcıyı yeniden başlayıp Power BI'a yeniden bağlanın.  

Sorun devam ederse diğer sorunlar için https://support.powerbi.com adresinde bir bilet oluşturun.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](../fundamentals/service-get-started.md)

[Power BI'da veri alma](service-get-data.md)
