---
title: Power BI Desktop’ta örneğe göre bir web sayfasından veri ayıklama
description: Çekmek istediklerinizle ilgili bir örnek vererek web sayfasından veri ayıklama
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 37efc295a3c79286458a862c255d987b0afde6d3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514089"
---
# <a name="get-data-from-a-web-page-by-providing-an-example"></a>Bir örnek vererek web sayfasından veri alma

Bir web sayfasından veri almak, kullanıcıların web sayfalarından kolayca veri ayıklamasına ve bu verileri **Power BI Desktop**’a aktarmasına olanak tanır. Ancak çoğu zaman, web sayfalarındaki veriler kolayca ayıklanabilen düzenli tablolar halinde olmaz. Bu nedenle, yapılandırılmış ve tutarlı olsa bile bu tür sayfalardan veri almak zor olabilir. 

Bunun bir çözümü vardır. **Örneğe göre web’den veri alma** özelliği sayesinde, bağlayıcı iletişim kutusunda bir veya daha fazla örnek vererek ayıklamak istediğiniz verileri **Power BI Desktop**’a gösterebilir, sayfada örneklerinizle eşleşen diğer verileri toplamasını sağlayabilirsiniz. Bu çözüm sayesinde, tablolarda bulunan veriler *ve* diğer tablo dışı veriler dahil olmak üzere Web sayfalarından tüm veri türlerini ayıklayabilirsiniz. 

![Örneğe göre web’den veri alma](media/desktop-connect-to-web-by-example/web-by-example_01.png)



## <a name="using-get-data-from-web-by-example"></a>Örneğe göre Web’den Veri Alma özelliğini kullanma

**Örneğe göre Web’den Veri Alma** özelliğini kullanmak için **Giriş** şerit menüsünden **Veri Al**’ı seçin. Görüntülenen pencerede, sol bölmedeki kategorilerden **Diğer**’i ve sonra **Web**’i seçin.

![Veri Al menüsünden Web’i seçme](media/desktop-connect-to-web-by-example/web-by-example_03.png)

Burada, verileri ayıklamak istediğiniz Web sayfasının URL’sini girin. Bu makalede biz Microsoft Store Web sayfasını kullanacağız ve bu bağlayıcının nasıl çalıştığını göstereceğiz. 

Takip etmek isterseniz bu makalede kullandığımız [Microsoft Store URL'sini](https://www.microsoft.com/store/top-paid/games/xbox?category=classics) kullanabilirsiniz:

    https://www.microsoft.com/store/top-paid/games/xbox?category=classics

![Web iletişim kutusu](media/desktop-connect-to-web-by-example/web-by-example_04.png)

**Tamam**’ı seçtiğinizde, Web sayfasından otomatik olarak algılanan tüm tabloların sunulduğu **Gezgin** iletişim kutusuna gidersiniz. Aşağıdaki görüntüde gösterilen örnekte bir tablo bulunmamıştır ancak sayfanın altında, örnek sağlamanıza olanak tanıyan **Örnekleri kullanarak tablo ayıkla** adlı bir düğme bulunur.


![Gezgin penceresi](media/desktop-connect-to-web-by-example/web-by-example_05.png)

**Örnekleri kullanarak tablo ayıkla** düğmesi seçildiğinde, Web sayfası içeriğinin önizlemesini görebileceğiniz ve ayıklamak istediğiniz verilerin örnek değerlerini girebileceğiniz etkileşimli bir pencere açılır. 

Bu örnekte, sayfadaki her bir oyunun *Ad* ve *Fiyat* verilerini ayıklayacağız. Aşağıdaki görüntüde gösterildiği gibi, her bir sütunun sayfasından birkaç örnek belirterek bunu yapabiliriz. Bu örnekler girildikçe, **Power Query** (Web sayfasından verileri ayıklayan temel teknoloji) akıllı veri ayıklama algoritmalarını kullanarak örnek girişlerinin düzenine uyan verileri ayıklayabilir.

![örneğe göre veriler](media/desktop-connect-to-web-by-example/web-by-example_06.png)

> Not: Değer önerileri yalnızca uzunluğu 128 karakter veya altında olan değerleri içerir.

Web sayfasından ayıklanan verilerden memnun kaldığımızda, daha fazla dönüşüm uygulamak veya bu verileri diğer veri kaynaklarımızla birleştirme gibi veri şekillendirme işlemleri yapmak üzere **Tamam**’ı seçerek **Sorgu Düzenleyicisi**’ne gideriz.

![örneğe göre veriler](media/desktop-connect-to-web-by-example/web-by-example_07.png)

Buradan, görseller oluşturabilir veya **Power BI Desktop** raporlarınızı oluştururken web sayfası verilerini diğer şekillerde kullanabilirsiniz.


## <a name="next-steps"></a>Sonraki adımlar
**Power BI Desktop**'ı kullanarak çok çeşitli türlerdeki verilere bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Örneğe göre sütun ekleme](desktop-add-column-from-example.md)
* [Bir web sayfasına bağlanma](desktop-connect-to-web.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Power BI Desktop'ta CSV dosyalarına bağlanma](desktop-connect-csv.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   

