---
title: "Power BI Desktop'ta değişkenleri görselleştirmek için Durum parametrelerini kullanma"
description: "Power BI raporlarında değişkenlere yönelik varsayımlarda bulunmak ve değişkenleri görselleştirmek için kendi Durum değişkeninizi oluşturma"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 5222b6ba99c9e61d1070f66115b90aa29099fd8d
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="create-and-use-a-what-if-parameter-to-visualize-variables-in-power-bi-desktop"></a>Power BI Desktop'ta değişkenleri görselleştirmek için Durum parametresi oluşturma ve kullanma
**Power BI Desktop**'ın Ağustos 2017 sürümünden itibaren, raporlarınız için **Durum** değişkenleri oluşturabilir, değişkeni bir dilimleyici olarak kullanabilir ve böylece raporlarınızda farklı anahtar değerlerini görselleştirip ölçebilirsiniz.

![](media/desktop-what-if/what-if_01.png)

**Durum** parametresi, **Power BI Desktop**'taki **Modelleme** sekmesinde bulunur. Bu, sizi parametreyi yapılandırabileceğiniz bir iletişim kutusuna götürür.

## <a name="creating-a-what-if-parameter"></a>Durum parametresi oluşturma
**Durum** parametresi oluşturmak için, **Power BI Desktop**'taki **Modelleme** sekmesinde bulunan **Durum** düğmesini seçin. Aşağıdaki görüntüde, *Discount percentage* adlı bir parametre oluşturup veri türünü *Ondalık sayı* olarak ayarladık. *Minimum* değer sıfır, *Maksimum* değer ise 0,50'dir (yüzde elli). *Artış* olarak ise 0,05 (yüzde beş) değerini belirledik. Bu, bir raporda etkileşime geçildiğinde parametrenin ne ölçüde artış göstereceğini belirtir.

![](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> Ondalık sayıların önüne sıfır koymayı (kutudaki gibi, yalnızca ,50 yerine 0,50 kullanın) unutmayın. Aksi halde sayı doğrulanmaz ve **Tamam** düğmesi seçilemez.
> 
> 

Size kolaylık sağlamak adına, **Bu sayfaya dilimleyici ekle** onay kutusu otomatik olarak, geçerli rapor sayfanıza **Durum** parametrenizi içeren bir dilimleyici ekler.

![](media/desktop-what-if/what-if_03.png)

**Durum** paremetresi oluşturulduğunda bir ölçü de oluşturulur. Bu ölçüyü **Durum** parametresinin geçerli değerini görselleştirmek için kullanabilirsiniz.

![](media/desktop-what-if/what-if_04.png)

**Durum** parametresi oluşturduğunuzda, hem parametrenin hem de ölçünün modelinizin bir parçası haline geldiğini göz önünde bulundurmanızda yarar vardır. Başka bir deyişle, bunlar raporun tamamında ve diğer rapor sayfalarında kullanılabilir. Ayrıca modelin bir parçası olduklarından, rapor sayfasından dilimleyiciyi silebilir, geri almak istemeniz durumunda ise **Alanlar** listesindeki **Durum** parametresini tuvale sürükleyerek (ardından görseli bir dilimleyici olarak değiştirerek) **Durum** parametresini raporunuzda kolayca tekrar kullanabilirsiniz.

## <a name="using-a-what-if-parameter"></a>Durum parametresi kullanma
Şimdi de **Durum** parametresinin kullanımına yönelik bir örnek üzerinden gidelim. **Durum** parametresini bir önceki bölümde oluşturduğumuza göre, şimdi de değeri kaydırıcı ile ayarlanan yeni bir ölçü oluşturarak bu parametreyi kullanalım. Bunu gerçekleştirmek için yeni bir ölçü oluştururuz.

![](media/desktop-what-if/what-if_05.png)

Yeni ölçü, indirim oranının uygulandığı toplam satış tutarı olacak. Elbette raporunuzu kullanan kişilerin **Durum** parametrenize ilişkin değişkeni görselleştirmesine olanak sağlayan daha karmaşık ve ilgi çelici ölçüler oluşturabilirsiniz. Örneğin, satış görevlilerinin, belirli satış hedeflerini veya yüzdelerini yakalamaları halinde alacakları tazminatı ya da daha yüksek indirimlerin satışların artmasına yönelik etkisini görmesini sağlayan bir rapor oluşturabilirsiniz.

Ölçü formülünü formül çubuğuna yazmamızın ve **Sales after Discount** olarak adlandırmamızın ardından formülün sonucunu görürüz:

![](media/desktop-what-if/what-if_06.png)

Ardından, eksende *OrderDate* bulunan ve hem *SalesAmount*'un hem de yeni oluşturulan *Sales after Discount* ölçüsünün değer olarak yer aldığı bir sütun görseli oluştururuz.

![](media/desktop-what-if/what-if_07.png)

Ardından, kaydırıcıyı hareket ettirdikçe *Sales after Discount* sütununun, indirim uygulanmış satış tutarını yansıttığını görürüz.

![](media/desktop-what-if/what-if_08.png)

İşte bu kadar kolay. Rapor kullanıcılarının, raporlarınızda oluşturduğunuz farklı senaryolarla etkileşime geçmesine olanak sağlamak üzere, **Durum** parametrelerinden çok çeşitli durumlarda yararlanabilirsiniz.

