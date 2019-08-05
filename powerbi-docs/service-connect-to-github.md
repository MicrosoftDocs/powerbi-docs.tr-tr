---
title: Power BI ile GitHub'a bağlanma
description: Power BI için GitHub
author: maggiesMSFT
manager: kfile
ms.reviewer: sarinas
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 07/21/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: f8091892f38f498c8072720ad1a93b0c4b07442b
ms.sourcegitcommit: 390dc3716d5c83385bedde63dd152431a77020e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68380248"
---
# <a name="connect-to-github-with-power-bi"></a>Power BI ile GitHub'a bağlanma
Bu makalede, verileri GitHub hesabınızdan Power BI şablon uygulamasıyla çekme işlemi adım adım açıklanmaktadır. Şablon uygulaması, GitHub verilerinizi araştırmanıza olanak tanımak için pano, rapor kümesi ve veri kümesi içeren bir çalışma alanı oluşturur. Power BI için GitHub uygulaması; yapılan katkılar, sorunlar, çekme istekleri ve etkin kullanıcılar ile ilgili veriler içeren bir GitHub deposuna (depo olarak da bilinir) ilişkin içgörüler gösterir.

Şablon uygulamasını yükledikten sonra panoyu ve raporu değiştirebilirsiniz. Daha sonra bunu, kuruluşunuzdaki iş arkadaşlarınıza bir uygulama olarak dağıtabilirsiniz.

[GitHub şablon uygulamasına](https://app.powerbi.com/groups/me/getapps/services/pbi-contentpacks.pbiapps-github) bağlanın veya Power BI ile [GitHub tümleştirmesi](https://powerbi.microsoft.com/integrations/github) hakkında daha fazla bilgi edinin.

Ayrıca [GitHub öğreticisini](service-tutorial-connect-to-github.md) de deneyebilirsiniz. Power BI belgeleri için ortak depoyla ilgili gerçek GitHub verilerini yükler.

>[!NOTE]
>Şablon uygulama, depoya erişim için bir GitHub hesabı gerektirir. Aşağıda, gereksinimlerle ilgili daha ayrıntılı bilgi verilmiştir.

## <a name="how-to-connect"></a>Bağlanma
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]
   
3. **GitHub** \> **Şimdi edinin**’i seçin.
4. **Bu Power BI uygulaması yüklensin mi?** iletişim kutusunda **Yükle**’yi seçin.
4. **Uygulamalar** bölmesinde **GitHub** kutucuğunu seçin.

    ![Power BI GitHub kutucuğu](media/service-connect-to-github/power-bi-github-tile.png)

6. **Yeni uygulamanızı kullanmaya başlayın** alanında **Verileri bağla** seçeneğini belirleyin.

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

5. Depo adını ve sahibini girin. [Bu parametreleri bulmaya](#FindingParams) ilişkin ayrıntılı bilgi için aşağıya bakın.
   
    ![Power BI GitHub depo adı](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. GitHub kimlik bilgilerinizi girin (tarayıcınızda önceden oturum açtıysanız bu adımı atlayabilirsiniz). 
6. **Kimlik doğrulama yöntemi** için **OAuth2** \> **Oturum aç** seçeneklerini belirleyin. 
7. GitHub kimlik doğrulaması ekranlarındaki yönergeleri uygulayın. Power BI için GitHub şablon uygulamasına, GitHub verilerine erişim izni verin.
   
   ![Power BI GitHub yetkilendirmesi](media/service-connect-to-github/github_authorize.png)
   
    Power BI GitHub’a ve verilerinize bağlanır.  Veriler, günde bir kez yenilenir. Power BI verileri içeri aktardıktan sonra yeni GitHub çalışma alanınızın içeriklerini görürsünüz.

## <a name="modify-and-distribute-your-app"></a>Uygulamanızı değiştirme ve dağıtma

GitHub şablon uygulamasını yüklediniz. Yani GitHub uygulama çalışma alanını da oluşturmuş oldunuz. Çalışma alanında, raporu ve panoyu değiştirebilir ve sonra kuruluşunuzdaki iş arkadaşlarınıza bir *uygulama* olarak dağıtabilirsiniz. 

1. Sol gezinti çubuğunda çalışma alanı adının yanındaki oku seçin. Çalışma alanının bir pano ve rapor içerdiğini görürsünüz.

    ![Sol gezinti bölmesindeki uygulama](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

8. Yeni [GitHub panosunu](https://powerbi.microsoft.com/integrations/github) seçin.    
    ![Power BI’da GitHub panosu](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

3. Yeni GitHub çalışma alanınızın tüm içeriğini görüntülemek için, sol gezinti çubuğunda **Çalışma alanları** > **GitHub**’ı seçin.
 
   ![Sol gezinti bölmesindeki GitHub çalışma alanı seçeneği](media/service-connect-to-github/power-bi-github-left-nav.png)

    Bu görünüm çalışma alanı için içerik listesidir. Sağ üst köşede, **Uygulamayı güncelleştir** seçeneğini görürsünüz. Uygulamanızı iş arkadaşlarınıza dağıtmaya hazır olduğunuzda, buradan başlayacaksınız. 

    ![GitHub içerik listesi](media/service-connect-to-github/power-bi-github-content-list.png)

2. Çalışma alanındaki diğer öğeleri görmek için **Raporlar**’ı ve **Veri kümeleri**’ni seçin.

    İş arkadaşlarınıza [uygulama dağıtma](service-create-distribute-apps.md) hakkında bilgi edinin.

## <a name="whats-included-in-the-app"></a>Uygulamaya dahil olan özellikler
Aşağıdaki verilere Power BI ile GitHub'dan erişilebilir:     

| Tablo adı | Açıklama |
| --- | --- |
| Katkılar |Katkılar tablosunda, katkıda bulunan kişi tarafından gerçekleştirilen ve haftalık olarak hesaplanan toplam ekleme, silme ve yürütme işlemi sayısı gösterilir. En çok katkıda bulunan 100 kişi tabloya dahil edilir. |
| Issues |Seçili depo ile ilgili tüm sorunları listeler ve bir sorunun kapatılmasına kadar geçen toplam ve ortalama süre, toplam açık sorun sayısı ve toplam kapalı sorun sayısı gibi hesaplar içerir. Depoda herhangi bir sorun olmadığında bu tablo boş olur. |
| Pull requests |Bu tabloda, depo için gerçekleştirilen tüm Çekme İstekleri ve çekme isteğini kimin gerçekleştirdiği gösterilir. Açık, kapalı ve toplam çekme isteği sayısı, çekme isteklerinin gerçekleştirilmesinin ne kadar sürdüğü ve bir çekme isteğinin ortalama ne kadar sürdüğü ile ilgili hesaplamalar da içerir. Depoda herhangi bir sorun olmadığında bu tablo boş olur. |
| Kullanıcılar |Bu tabloda katkı yapmış, sorun bildirmiş veya seçili depo için Çekme isteklerini çözmüş GitHub kullanıcılarının ya da katkıda bulunan kişilerin bir listesi bulunmaktadır. |
| Milestones |Seçili depo ile ilgili tüm kilometre taşlarını gösterir. |
| DateTable |Bu tabloda, GitHub verilerinizi tarihe göre çözümleme konusunda yararlanabileceğiniz, güncel ve geçmiş tarihler bulunur. |
| ContributionPunchCard |Bu tablo, seçili depo için yapılan katkıları gösteren bir ödül kartı olarak kullanılabilir. Haftanın günlerine ve saatlere göre yürütmeleri gösterir. Bu tablo, modeldeki diğer tablolara bağlı değildir. |
| RepoDetails |Bu tabloda, seçili depo ile ilgili ayrıntılar sunulur. |

## <a name="system-requirements"></a>Sistem gereksinimleri
* Depoya erişimi bulunan bir GitHub hesabı.  
* İlk oturum açma işlemi sırasında Power BI için GitHub uygulamasına izin verme. Erişim iptali ile ilgili aşağıdaki ayrıntılı bilgilere bakın.  
* Veri çekme ve yenileme için kullanılabilen yeterli miktarda API çağrısı.  

### <a name="de-authorize-power-bi"></a>Power BI yetkisini kaldırma
Power BI'ın GitHub deponuza bağlanma yetkisini kaldırmak üzere GitHub için Erişimi iptal et işlemini gerçekleştirebilirsiniz. Ayrıntılar için [GitHub yardımı](https://help.github.com/articles/keeping-your-ssh-keys-and-application-access-tokens-safe/#reviewing-your-authorized-applications-oauth) konusuna bakın.

<a name="FindingParams"></a>
## <a name="finding-parameters"></a>Parametreleri bulma
GitHub'daki depoya bakarak sahibi ve depoyu belirlemeniz mümkündür:

![Depo adı ve sahibi](media/service-connect-to-github/github_ownerrepo.png)

İlk parça olan "Azure" sahibi, ikinci parça olan "azure-sdk-for-php" ise depoyu göstermektedir.  Depo URL'sinde aynı iki öğeyi görürsünüz:

    <https://github.com/Azure/azure-sdk-for-php> .

## <a name="troubleshooting"></a>Sorun giderme
Gerekirse GitHub kimlik bilgilerinizi doğrulayabilirsiniz.  

1. Başka bir tarayıcı penceresinde GitHub web sitesine gidin ve GitHub'da oturum açın. GitHub sitesindeyken sağ üst köşeye bakarak, oturum açmış olduğunuzu görebilirsiniz.    
2. GitHub'da, Power BI'ı kullanarak erişmek istediğiniz deponun URL'sine gidin. Örneğin: https://github.com/dotnet/corefx.  
3. Power BI'da GitHub'a bağlanmayı deneyin. GitHub Yapılandırma iletişim kutusunda, deponun ve sahibinin adını kullanın.  

## <a name="next-steps"></a>Sonraki adımlar

* [Öğretici: Power BI ile bir GitHub deposuna bağlanma](service-tutorial-connect-to-github.md)
* [Power BI'da yeni çalışma alanları oluşturma](service-create-the-new-workspaces.md)
* [Power BI'da uygulamaları yükleme ve kullanma](consumer/end-user-apps.md)
* [Dış hizmetler için Power BI uygulamalarına bağlanma](service-connect-to-services.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

