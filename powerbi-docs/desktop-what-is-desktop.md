---
title: Power BI Desktop nedir?
description: Power BI Desktop’ın ne olduğunu ve kullanmaya nasıl başlayacağınızı öğrenin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: overview
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Get started
ms.openlocfilehash: be29d5879ef62ab3d7fcef271e61337a0d2fb050
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34289200"
---
# <a name="what-is-power-bi-desktop"></a>Power BI Desktop nedir?

**Power BI Desktop**, yerel bilgisayarınıza yükleyebileceğiniz ücretsiz bir uygulamadır ve verilerinize bağlanmayı, verileri dönüştürmeyi ve verilerinizi görselleştirmeyi sağlar. **Power BI Desktop** ile birden çok farklı veri kaynağına bağlanabilir ve bunları görseller ve kuruluşunuzdaki diğer kişilerle rapor olarak paylaşabileceğiniz görsel koleksiyonları oluşturmanızı sağlayan bir veri modeli halinde birleştirebilirsiniz (genellikle modelleme adı verilir). İş Zekası projelerinde çalışan çoğu kullanıcı, raporlar oluşturmak için **Power BI Desktop** kullanır ve sonra raporlarını başkalarıyla paylaşmak için **Power BI hizmetini** kullanır.

![Power BI Desktop](media/desktop-what-is-desktop/what-is-desktop_01.png)

**Power BI Desktop**’ın en yaygın kullanım şekilleri aşağıda verilmiştir:

* Verilere bağlanma
* Bir veri modeli oluşturmak için bu verileri dönüştürme ve temizleme
* Verilerin görsel açıklamalarını sağlayan grafik gibi görseller oluşturma
* Bir veya daha fazla rapor sayfasında görsel koleksiyonu olan raporlar oluşturma
* **Power BI hizmetini** kullanarak raporları başkalarıyla paylaşma

Çoğunlukla bu tür görevlerden sorumlu kişilerin *veri çözümleyiciler* (bazı durumlarda yalnızca *çözümleyiciler* olarak anılır) ya da İş Zekası uzmanları (genellikle *rapor oluşturucular* olarak anılır) olduğu düşünülür. Ancak, kendisini çözümleyici veya rapor oluşturucu olarak görmeyen birçok kişi, ilgi çekici raporlar oluşturmak veya çeşitli kaynaklardan verileri çekmek ve veri modelleri oluşturmak için **Power BI Desktop** kullanır.

**Power BI Desktop** ile, birden fazla kaynaktan verileri kullanarak kuruluşunuzdaki diğer kullanıcılarla paylaşabileceğiniz tek bir rapor halinde karmaşık ve görsel açıdan zengin raporlar oluşturabilirsiniz. 

## <a name="connect-to-data"></a>Verilere bağlanma
**Power BI Desktop** kullanmaya başlamak için ilk adım verilere bağlanmaktır. **Power BI Desktop**’tan bağlanabileceğiniz çok çeşitli türlerde veri kaynağı mevcuttur. Verilere bağlanmak için **Giriş** şeridini ve sonra **Veri Al > Daha Fazla** öğesini seçmeniz yeterlidir. Aşağıdaki görüntüde, Power BI Desktop’ın bağlanabildiği çok sayıda kategoriyi içeren **Veri Al** penceresi gösterilmiştir.

![Power BI Desktop'ta Veri Al](media/desktop-what-is-desktop/what-is-desktop_02.png)

Bir veri türü seçtiğinizde, Power BI Desktop’ın sizin adınıza veri kaynağına bağlanması için gereken URL ve kimlik bilgileri gibi bilgiler istenir.

![Power BI Desktop'ta bir SQL Server veritabanına bağlanma](media/desktop-what-is-desktop/what-is-desktop_03.png)

Bir veya daha fazla veri kaynağına bağlandıktan sonra verileri sizin için yararlı olacak şekilde dönüştürmek isteyebilirsiniz.

## <a name="transform-and-clean-data-create-a-model"></a>Verileri dönüştürme ve temizleme, model oluşturma

Power BI Desktop’ta yerleşik **Sorgu Düzenleyicisi**’ni kullanarak verileri temizleyebilir ve dönüştürebilirsiniz. Sorgu Düzenleyicisi ile verilerinizde, veri türünü değiştirme, sütunları kaldırma veya birden çok kaynaktan veri birleştirme gibi değişiklikler yapabilirsiniz. Biraz heykeltıraşlık gibidir; büyük bir kil (veya veri) bloğu ile başlayabilir, sonra verilerin şekli istediğiniz duruma gelene kadar gerektikçe parçaları tıraş edebilir ya da ekleyebilirsiniz. 

![Power BI Desktop’ta Sorgu Düzenleyicisi](media/desktop-getting-started/designer_gsg_editquery.png)

Verileri dönüştürürken uyguladığınız her adım (bir tabloyu yeniden adlandırma, bir veri türünü dönüştürme veya sütunları silme gibi) **Sorgu Düzenleyicisi** tarafından kaydedilir ve bu sorgu, veri kaynağına her bağlandığında bu adımlar uygulanır. Böylece veriler her zaman sizin belirttiğiniz gibi şekillendirilir.

Aşağıdaki görüntüde, şekillendirilmiş ve bir modele dönüştürülmüş sorgunun **Sorgu Ayarları** bölmesi gösterilmektedir.

 ![](media/desktop-getting-started/shapecombine_querysettingsfinished.png)

Verileriniz istediğiniz gibi olana kadar görseller oluşturabilirsiniz. 

## <a name="create-visuals"></a>Görsel oluşturma 

Bir veri modeli elde ettikten sonra *alanları* rapor tuvalinin üzerine sürükleyerek *görseller* oluşturabilirsiniz. *Görsel*, modelinizdeki verilerin grafiksel bir açıklamasıdır. Aşağıdaki görsel basit bir sütun grafiğini göstermektedir. 

![Power BI Desktop'ta görsel](media/desktop-what-is-desktop/what-is-desktop_04.png)

Power BI Desktop'ta seçebileceğiniz farklı türde görseller vardır. Bir görsel oluşturmak veya görseli değiştirmek için **Görselleştirmeler** bölmesinden görsel simgesini seçmeniz yeterlidir. Rapor tuvalinde seçili bir görseliniz varsa, seçili görsel seçtiğiniz türle değiştirilir. Bir görsel seçilmezse, seçiminize göre yeni bir görsel oluşturulur.

![Power BI Desktop'ta Görselleştirmeler bölmesi](media/desktop-what-is-desktop/what-is-desktop_05.png)

## <a name="create-reports"></a>Rapor oluşturma

Çoğunlukla, Power BI Desktop’ta modelinizi oluşturmak için kullandığınız verilerin çeşitli yönlerini gösteren bir görsel koleksiyonu oluşturmak istersiniz. Tek bir Power BI Desktop dosyasındaki bir görsel koleksiyonu *rapor* olarak adlandırılır. Tıpkı bir Excel dosyasında bir veya daha fazla çalışma sayfası olabileceği gibi bir raporda bir veya daha fazla sayfa olabilir. Aşağıdaki görüntüde bir Power BI Desktop raporunun Genel Bakış adlı birinci sayfasını görebilirsiniz (sekmeyi görüntünün altında görebilirsiniz). Bu raporda on sayfa vardır.

![On sayfalı Power BI Desktop raporu](media/desktop-what-is-desktop/what-is-desktop_01.png)

## <a name="share-reports"></a>Rapor paylaşma

Bir rapor başkalarıyla paylaşmaya hazır olduğunda raporu **Power BI hizmetinde** **Yayımlayabilir** ve kuruluşunuzda bir Power BI lisansına sahip olan herkesin kullanımına sunabilirsiniz. Bir Power BI Desktop raporu yayımlamak için Power BI Desktop’taki **Giriş** şeridinden **Yayımla** düğmesini seçin.

![Power BI Desktop'tan rapor yayımlama](media/desktop-what-is-desktop/what-is-desktop_06.png)

**Yayımla**’yı seçtikten sonra Power BI Desktop, Power BI hesabınızı kullanarak sizi **Power BI hizmetine** bağlar ve sonra çalışma alanınız, bir ekip çalışma alanı ya da Power BI hizmetindeki başka bir konum gibi Power BI hizmetinde raporu paylaşmak istediğiniz yeri seçmenizi ister. Power BI hizmetinde rapor paylaşmak için bir Power BI lisansına sahip olmanız gerekir.


## <a name="next-steps"></a>Sonraki adımlar

**Power BI Desktop** kullanmaya başlamak için ilk olarak uygulamayı indirip yüklemeniz gerekir. **Power BI Desktop**’ı edinmenin iki yolu vardır:

* [Web’den Power BI Desktop'ı indirme](desktop-get-the-desktop.md)
* [Microsoft Store’dan Power BI Desktop’ı edinme](http://aka.ms/pbidesktopstore)
