---
title: Power BI ile Acumatica'ya Bağlanma
description: Power BI için Acumatica
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 9366eff71e09b1f6c71c1f2519feb3d2392e3c58
ms.sourcegitcommit: 695c65629d6d1faba61db2e1570324f65f235dde
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37092656"
---
# <a name="connect-to-acumatica-with-power-bi"></a>Power BI ile Acumatica'ya Bağlanma
Power BI Acumatica içerik paketi, fırsat verilerinizle ilgili hızla öngörü elde etmenize olanak sağlar. Power BI; fırsatlar, hesaplar ve müşteriler de dahil olmak üzere verilerinizi alır ve bu verilere dayalı olarak, varsayılan bir pano ve ilgili raporları oluşturur.

[Acumatica içerik paketine](https://app.powerbi.com/getdata/services/acumatica) bağlanın veya Power BI ile [Acumatica tümleştirmesi](https://powerbi.microsoft.com/integrations/acumatica) hakkında daha fazla bilgi edinin.

>[!NOTE]
>Bu içerik paketi için Acumatica v5.2 veya sonraki bir sürümü gereklidir.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-acumatica/getdata3.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-acumatica/getdata2.png)
3. **Acumatica** \> **Al**'ı seçin.
   
   ![](media/service-connect-to-acumatica/acumatica.png)
4. Acumatica OData uç noktanızı girin. OData uç noktaları, bir dış sistemin Acumatica'dan veri istemesine olanak sağlar. Acumatica OData uç noktası aşağıdaki gibi biçimlendirilir ve HTTPS ifadesinin kullanılması gerekir:
   
     https://[siteetkialanı]/odata/[şirketadı]
   
   Şirket Adı bilgisi yalnızca çoklu şirket dağıtımınız varsa gereklidir. Aşağıda, Acumatica hesabınızda bu parametreyi nasıl bulacağınız konusunda daha fazla bilgi yer almaktadır.
   
   ![](media/service-connect-to-acumatica/parameters.png)
5. Kimlik doğrulama yöntemi için **Temel**'i seçin. Acumatica hesabınıza ilişkin kullanıcı adınızı ve parolanızı girip **Oturum Aç**'a tıklayın.
   
    ![](media/service-connect-to-acumatica/creds2.png)
6. Veriler Power BI tarafından içeri aktarıldıktan sonra sol gezinti bölmesinde yeni bir pano, rapor ve veri kümesi görürsünüz. Yeni öğeler, sarı bir yıldız işaretiyle \* işaretlenir. Öğeler bir kez seçildiğinde bu işaret kaybolur. Panoyu seçtiğinizde aşağıdakine benzer bir düzen görürsünüz:
   
    ![](media/service-connect-to-acumatica/dashboard.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="system-requirements"></a>Sistem gereksinimleri
Bu içerik paketi için Acumatica v5.2 veya sonraki bir sürümü gereklidir. Lütfen Acumatica yöneticinizle iletişime geçerek sürümünüzü kontrol edin.

## <a name="finding-parameters"></a>Parametreleri bulma
**Acumatica OData Uç Noktası**

Acumatica OData uç noktası aşağıdaki gibi biçimlendirilir ve HTTPS ifadesinin kullanılması gerekir:

    https://[sitedomain]/odata/[companyname]

Acumatica'da oturum açtığınızda, Uygulama Site Etki Alanı bilgisini tarayıcınızdaki adres çubuğunda görebilirsiniz. Aşağıdaki örnekte site etki alanı adı `https://pbi.acumatica.com` olduğundan, sağlanacak OData uç noktası `https://pbi.acumatica.com/odata` olur.

 ![](media/service-connect-to-acumatica/url.png)

Şirket Adı bilgisi yalnızca çoklu şirket dağıtımınız varsa gereklidir. Bu bilgileri Acumatica oturum açma sayfanızda bulabilirsiniz.

![](media/service-connect-to-acumatica/signin2.png)

## <a name="troubleshooting"></a>Sorun giderme
Oturum açamıyorsanız, girdiğiniz Acumatica OData uç noktasının doğru olduğundan emin olun.

    https://<application site domain>/odata/<company name>

Bağlanırken sorun yaşıyorsanız lütfen yöneticinizle iletişime geçerek Acumatica sürümünüzü onaylayın. Bu içerik paketi için 5.2 veya sonraki bir sürüm gereklidir.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

