---
title: Power BI ile Xero'ya bağlanma
description: Power BI için Xero
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 98250e30d1ca944aa536e0d8a05e6ee6c227fc61
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46546775"
---
# <a name="connect-to-xero-with-power-bi"></a>Power BI ile Xero'ya bağlanma
Xero, özellikle küçük ölçekli işletmeler için tasarlanmış kullanımı kolay bir çevrimiçi muhasebe yazılımıdır. Bu Power BI içerik paketiyle, Xero finansal bilgilerinizi temel alan ilgi çekici görselleştirmeler oluşturun. Varsayılan panonuz nakit pozisyonu, geliri ve giderleri, kâr zarar eğilimi, borçlu günleri ve yatırım getirisi gibi çok sayıda küçük işletme ölçümleri içerir.

Power BI için [Xero içerik paketine](https://app.powerbi.com/getdata/services/xero) bağlanın veya [Xero ve Power BI](https://help.xero.com/Power-BI) tümleştirmesi hakkında daha fazla bilgi edinin.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-xero/getdata.png)
2. **Hizmetler** kutusundaki **Al**'ı seçin.
   
   ![](media/service-connect-to-xero/services.png)
3. **Xero** \>  **Al**'ı seçin.
   
   ![](media/service-connect-to-xero/connect.png)
4. Xero hesabınızla ilişkilendirilen kuruluş için bir takma ad girin. Herhangi bir şey yazabilirsiniz; bu, birden çok Xero kuruluşuna sahip kullanıcılara yardımcı olmak için yapılmaktadır. [Aşağıda](#FindingParams) ayrıntılara göz atabilirsiniz.
   
   ![](media/service-connect-to-xero/params.png)
5. **Kimlik Doğrulama Yöntemi** için **OAuth** seçeneğini belirleyin ve istendiğinde Xero hesabınızda oturum açıp bağlanacağınız kuruluşu seçin. Oturum açma tamamlandığında, yükleme işlemini başlatmak için **Oturum Aç**'ı seçin.
   
    ![](media/service-connect-to-xero/creds.png)
   
    ![](media/service-connect-to-xero/creds2.png)
6. Onayladıktan sonra içeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
     ![](media/service-connect-to-xero/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="whats-included"></a>Neleri kapsar?
İçerik paketi panosu çeşitli alanlarda kutucuklar ve ölçümler ile bunlar hakkında daha fazla bilgi edinmek için raporlar içerir:  

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
* Uyarıları  
* Banka deyimi günlük bakiyesi  
* Banka deyimleri  
* Kişiler  
* Harcama talepleri  
* Fatura Satır öğeleri  
* Faturalar  
* Öğeleri  
* Ay sonu  
* Kurum  
* Deneme bakiyesi  
* Xero hesapları

## <a name="system-requirements"></a>Sistem Gereksinimleri
Xero içerik paketine erişmek için şu roller gereklidir: "Standard + Reports" (Standart + Raporlar) veya "Advisor" (Danışman).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Kuruluşunuza Power BI'da izlemek için bir ad sağlayın. Bu, birden çok farklı kuruluşa bağlanmanıza olanak sağlar. Zamanlanmış yenilemeyi etkileyeceğinden birden çok kez aynı kuruluşa bağlanamayacağınızı unutmayın.   

## <a name="troubleshooting"></a>Sorun giderme
* Xero kullanıcılarının Power BI için Xero içerik paketine erişmeleri için şu rollere sahip olması gerekir: "Standard + Reports" (Standart + Raporlar) veya "Advisor" (Danışman). İçerik paketi, Power BI aracılığıyla raporlama verilerine erişmek için kullanıcı temelli izinler kullanır.  
* Yüklemeden sonra bir süre boyunca hata alırsanız ilgili hata iletisini görene kadar geçen süreyi doğrulayın. Xero tarafından sağlanan erişim belirtecinin yalnızca 30 dakika geçerli olduğunu ve bu nedenle, bu süre içerisinde yüklenebilenden fazla veriye sahip hesapların başarısız olacağını unutmayın. Bu sorunu iyileştirmek için etkin bir şekilde çalışıyoruz.
* Yükleme sırasında panodaki kutucuklar genel yükleme durumunda olacaktır. Tam yükleme tamamlanana kadar bu durumun değişmesi beklenmez. Yüklemenizin tamamlandığı ancak kutucukların yüklenmeye devam ettiğiyle ilgili bir bildirim alırsanız panonuzun en üst sağında bulunan ... simgesini kullanarak pano kutucuklarını yenilemeyi deneyin.
* İçerik paketiniz yenilenmezse Power BI'da aynı kuruluşa birden fazla kez bağlanıp bağlanmadığınızı kontrol edin. Xero bir kuruluşa yalnızca tek bir etkin bağlantı kurulmasına izin verir ve aynı kuruluşa birden fazla kez bağlanırsanız kimlik bilgilerinizin geçersiz olduğunu belirten bir hata görebilirsiniz.  
* Hata iletileri veya oldukça yavaş yükleme süreleri gibi, Power BI için Xero içerik paketleriyle bağlantı kurma konusundaki sorunlar için, ilk olarak önbelleği / tanımlama bilgilerini temizleyin ve tarayıcıyı yeniden başlayıp Power BI'a yeniden bağlanın.  

Sorun devam ederse diğer sorunlar için http://support.powerbi.com adresinde bir bilet oluşturun.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

