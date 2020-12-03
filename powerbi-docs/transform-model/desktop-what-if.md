---
title: Değişkenleri görselleştirmek için durum parametrelerini kullanma
description: Power BI raporlarında değişkenlere yönelik varsayımlarda bulunmak ve değişkenleri görselleştirmek için kendi durum değişkeninizi oluşturma
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: pbi-transform-model
ms.topic: how-to
ms.date: 01/21/2020
LocalizationGroup: Create reports
ms.openlocfilehash: 2286edc16995e8fecc3b6ff65a53e2c4007ac470
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96415439"
---
# <a name="create-and-use-what-if-parameters-to-visualize-variables-in-power-bi-desktop"></a>Power BI Desktop'ta değişkenleri görselleştirmek için durum parametresi oluşturma ve kullanma

*Power BI Desktop*'ın Ağustos 2018 sürümünden itibaren, raporlarınız için *durum* değişkenleri oluşturabilir, değişkeni bir dilimleyici olarak kullanabilir ve raporlarınızda farklı anahtar değerlerini görselleştirip ölçebilirsiniz.

![Yeni Parametre seçeneği](media/desktop-what-if/what-if_01.png)

Power BI Desktop'ın *Modelleme* sekmesinde **durum** parametresini oluşturun. Bunu seçtiğinizde, parametreyi yapılandırabileceğiniz bir iletişim kutusu görüntülenir.

## <a name="creating-a-what-if-parameter"></a>Durum parametresi oluşturma

Durum parametresi oluşturmak için Power BI Desktop'taki **Modelleme** sekmesinde **Yeni Parametre**'yi seçin. Aşağıdaki resimde *Discount percentage* adlı bir parametre oluşturup veri türünü **Ondalık sayı** olarak ayarladık. **En düşük değer** sıfırdır. **En büyük değer** 0,50'dir (yüzde 50). **Artış** olarak ise 0,05 (yüzde beş) değerini belirledik. Bu, bir raporda etkileşime geçildiğinde parametrenin ne ölçüde artış göstereceğini belirtir.

![Durum parametresi değerleri](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> Ondalık sayılarda değerin önüne sıfır koymayı (yalnızca ,50 yerine 0,50 kullanın) unutmayın. Aksi takdirde sayı doğrulanmaz ve **Tamam** düğmesi seçilemez.
> 
> 

Size kolaylık sağlamak için, **Bu sayfaya dilimleyici ekle** onay kutusu otomatik olarak, geçerli rapor sayfanıza durum parametrenizi içeren bir dilimleyici ekler.

![Geçerli rapor sayfasında yeni dilimleyici](media/desktop-what-if/what-if_03.png)

Durum parametresi oluşturulduğunda, parametre oluşturmaya ek olarak bir de ölçü oluşturulur. Bu ölçüyü durum parametresinin geçerli değerini görselleştirmek için kullanabilirsiniz.

![Durum parametresi için oluşturulan ölçü](media/desktop-what-if/what-if_04.png)

Durum parametresi oluşturduğunuzda, hem parametrenin hem de ölçünün modelinizin bir parçası haline geldiğini göz önünde bulundurmanızda yarar vardır. Başka bir deyişle, bunlar raporun tamamında ve diğer rapor sayfalarında kullanılabilir. Ayrıca bunlar modelin parçası olduğundan, rapor sayfasından dilimleyiciyi silebilirsiniz. Dilimleyiciyi geri almak isterseniz, **Alanlar** listesinde durum parametresini tutmanız, tuvale sürüklemeniz ve sonra da görseli dilimleyici olarak değiştirmeniz yeterlidir.

## <a name="using-a-what-if-parameter"></a>Durum parametresini kullanma

Şimdi de durum parametresinin kullanımına yönelik bir örnek üzerinden gidelim. Önceki bölümde durum parametresini oluşturduk. Şimdi değerleri dilimleyiciyle ayarlanan yeni bir ölçü oluşturarak bu parametreyi kullanıma alacağız.

![Parametreyle kullanmak üzere yeni ölçü ekleme](media/desktop-what-if/what-if_05.png)

Yeni ölçü, indirim oranının uygulandığı toplam satış tutarı olacak. Raporunuzu kullanan kişilerin durum parametrenize ilişkin değişkeni görselleştirmesine olanak sağlayan daha karmaşık ve ilgi çekici ölçüler oluşturabilirsiniz. Örneğin, satış görevlilerinin, belirli satış hedeflerini veya yüzdelerini yakalamaları halinde alacakları tazminatı ya da daha yüksek indirimlerin satışların artmasına yönelik etkisini görmesini sağlayan bir rapor oluşturabilirsiniz.

Ölçü formülünü formül çubuğuna girin ve formülü *Sales after Discount* olarak adlandırın.

![Sales after Discount tanımı](media/desktop-what-if/what-if_06.png)

Ardından, eksende **OrderDate** bulunan ve hem **SalesAmount**'un hem de yeni oluşturulan **Sales after Discount** ölçüsünün değer olarak yer aldığı bir sütun görseli oluştururuz.

![SalesAmount için görselleştirme](media/desktop-what-if/what-if_07.png)

Ardından, kaydırıcıyı hareket ettirdikçe **Sales after Discount** sütununun, indirim uygulanmış satış tutarını yansıttığını görürüz.

![Kaydırıcı görselleştirmeyle etkileşim kurar](media/desktop-what-if/what-if_08.png)

İşte bu kadar kolay. Durum parametrelerini her tür durumda kullanabilirsiniz. Bu parametreler rapor tüketicilerinin raporlarınızda oluşturduğunuz farklı senaryolarla etkileşime geçmesine olanak tanır.
