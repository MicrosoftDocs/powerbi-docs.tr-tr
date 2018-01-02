---
title: "Microsoft Intune ile mobil uygulamaları yapılandırma"
description: "Power BI Mobil uygulamalarını Microsoft Intune ile yapılandırma. Bu makalede, uygulamayı ekleme ve dağıtma işlemleri açıklanır. Ayrıca güvenliği denetlemeye yönelik mobil uygulama ilkesinin nasıl oluşturulacağı da ele alınır."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 06/28/2017
ms.author: asaxton
ms.openlocfilehash: 793734acf8e5d5a11747ec850cdf0faeda8448dd
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="configure-mobile-apps-with-microsoft-intune"></a>Microsoft Intune ile mobil uygulamaları yapılandırma
Microsoft Intune, kuruluşların cihazları ve uygulamaları yönetmesine olanak sağlar. iOS ve Android için Power BI mobil uygulamaları Intune ile tümleşik bir biçimde çalışarak cihazlarınızda uygulamayı yönetmenizi ve güvenliği denetlemenizi sağlar. Yapılandırma ilkeleri aracılığıyla, erişim PIN'i gerektirme, verilerin uygulama tarafından nasıl işlendiğini denetleme ve hatta uygulama kullanılmadığı sırada uygulama verilerini şifreleme gibi öğeleri denetleyebilirsiniz.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9HF-qsdQvHw?list=PLv2BtOtLblH1nPVPU2etFzTNmpz49dwXm" frameborder="0" allowfullscreen></iframe>

## <a name="general-mobile-device-management-configuration"></a>Genel mobil cihaz yönetim yapılandırması
Bu makale, Microsoft Intune için tam bir yapılandırma kılavuzu olarak hazırlanmamıştır. Intune ile tümleşik çalışmaya yeni başladıysanız, ayarlandığından emin olmak isteyeceğiniz birkaç nokta vardır. [Daha fazla bilgi](https://technet.microsoft.com/library/jj676587.aspx)

Microsoft Intune, Office 365'te Mobil Cihaz Yönetimi (MDM) ile birlikte bulunabilir. [Daha fazla bilgi](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365/)

Bu makalede Intune'un düzgün yapılandırıldığı ve Intune'da kayıtlı cihazlarınızın bulunduğu varsayılmaktadır. Intune ile MDM'yi birlikte kullanıyorsanız cihaz, MDM'de kayıtlı olarak görünür ancak Intune'da yönetilebilir.

> [!NOTE]
> Kuruluşunuzda Microsoft Intune MAM yapılandırıldıktan sonra iOS veya Android cihazlarda Power BI mobil uygulaması kullanılırken, arka planda veri yenileme özelliği kapalıdır. Uygulamaya bir sonraki girişinizde Power BI, web üzerindeki Power BI hizmetinden verileri yeniler.
> 
> 

## <a name="step-1-get-the-url-for-the-application"></a>1. Adım: Uygulamanın URL'sini alma
Intune'da uygulamayı oluşturmadan önce uygulamaların URL'lerini almamız gerekir. iOS cihazları için URL'leri iTunes'dan alırız. Android cihazlar için ise URL'leri Power BI mobil sayfasından alabilirsiniz.

Uygulamayı oluştururken ihtiyaç duyacağımız için URL'yi kaydedin.

### <a name="ios"></a>iOS
iOS için uygulama URL'sini iTunes'dan almamız gerekir.

1. iTunes'u açın.
2. *Power BI* için arama yapın.
3. **iPhone Uygulamaları** ve **iPad Uygulamaları** altında **Microsoft Power BI**'ı görmeniz gerekir. Aynı URL'yi alacağınız için bunlardan herhangi birini kullanabilirsiniz.
4. **Al** açılan listesini ve **Bağlantıyı Kopyala**'yı seçin.
   
    ![](media/service-admin-mobile-intune/itunes-url.png)

URL'nin aşağıdakine benzer şekilde görünmesi gerekir.

    https://itunes.apple.com/us/app/microsoft-power-bi/id929738808?mt=8

### <a name="android"></a>Android
[Power BI mobil sayfasını](https://powerbi.microsoft.com/mobile/) kullanarak Google Play URL'sini de alabilirsiniz. **Google Play'den indirin** simgesine tıkladığınızda uygulama sayfasına yönlendirilirsiniz. Tarayıcınızın adres çubuğundan URL'yi kopyalayabilirsiniz. URL'nin aşağıdakine benzer şekilde görünmesi gerekir.

    https://play.google.com/store/apps/details?id=com.microsoft.powerbim

## <a name="step-2-create-a-mobile-application-management-policy"></a>2. Adım: Mobil uygulama yönetim ilkeleri oluşturma
Mobil uygulama yönetimi ilkesi sayesinde erişim PIN'i gibi öğeleri zorunlu tutabilirsiniz. Intune portalında bir ilke oluşturabilirsiniz. 

İlk olarak uygulamayı veya ilkeyi oluşturmayı tercih edebilirsiniz. Eklenme sıraları önemli değildir. Dağıtım adımı için ikisinin de mevcut olması yeterlidir.

1. **İlke** > **Yapılandırma İlkeleri**'ni seçin.
   
    ![](media/service-admin-mobile-intune/intune-policy.png)
2. **Ekle...**'yi seçin.
3. **Yazılım** bölümünde Android veya iOS için Mobil Uygulama Yönetimi seçeneğini belirleyebilirsiniz. Hemen başlamak için, **Önerilen Ayarlarla İlke Oluştur**'u seçebilir veya özel bir ilke oluşturabilirsiniz.
4. Uygulamada istediğiniz kısıtlamaları yapılandırmak için ilkeyi düzenleyin.

## <a name="step-3-create-the-application"></a>3. Adım: Uygulamayı oluşturma
Uygulama, dağıtım için Intune'a kaydedilen bir başvuru veya pakettir. Bir uygulama oluşturmamız ve Google Play'den veya iTunes'dan aldığımız uygulama URL'sine başvurmamız gerekir.

İlk olarak uygulamayı veya ilkeyi oluşturmayı tercih edebilirsiniz. Eklenme sıraları önemli değildir. Dağıtım adımı için ikisinin de mevcut olması yeterlidir.

1. Intune portalına gidin ve soldaki menüden **Uygulamalar**'ı seçin.
2. **Uygulama Ekle**'yi seçin. Bu işlem, **Yazılım Ekle** uygulamasını başlatır.

### <a name="ios"></a>iOS
1. Açılan listeden **Uygulama Mağazası'ndan Yönetilen iOS Uygulaması**'nı seçin.
2. [1. Adım](#step-1-get-the-url-for-the-application)'da aldığımız uygulama URL'sini girin ve **İleri**'yi seçin.
   
    ![](media/service-admin-mobile-intune/intune-add-software-ios1.png)
3. Bir **Yayımcı**, **Ad** ve **Açıklama** seçin. İsteğe bağlı olarak bir **Simge** de belirleyebilirsiniz. **Kategori** alanı, Şirket Portalı uygulamasına yöneliktir. İşiniz bittiğinde **İleri**'yi seçin.
4. Uygulamayı **Herhangi bir** (varsayılan), **iPad** veya **iPhone** seçeneklerinden birini belirleyerek yayımlamayı tercih edebilirsiniz. Varsayılan olarak, **Herhangi bir** seçeneği belirlenmiştir ve her iki cihaz türü için de kullanılabilir. Power BI uygulamasının URL'si iPhone ve iPad için aynıdır. **İleri**'yi seçin.
5. **Karşıya Yükle**'yi seçin.

> [!NOTE]
> Uygulama, sayfa yenilenene kadar uygulama listesinde görünmeyebilir. Sayfanın yeniden yüklenmesi için **Genel Bakış**'a ve ardından tekrar **Uygulamalar**'a tıklayabilirsiniz.
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-ios2.png)

### <a name="android"></a>Android
1. Açılan listeden **Dış Bağlantı**'yı seçin.
2. [1. Adım](#step-1-get-the-url-for-the-application)'da aldığımız uygulama URL'sini girin ve **İleri**'yi seçin.
   
    ![](media/service-admin-mobile-intune/intune-add-software-android1.png)
3. Bir **Yayımcı**, **Ad** ve **Açıklama** girin. İsteğe bağlı olarak bir **Simge** de belirleyebilirsiniz. **Kategori** alanı, Şirket Portalı uygulamasına yöneliktir. İşiniz bittiğinde **İleri**'yi seçin.
4. **Karşıya Yükle**'yi seçin.

> [!NOTE]
> Uygulama, sayfa yenilenene kadar uygulama listesinde görünmeyebilir. Sayfanın yeniden yüklenmesi için **Genel Bakış**'a ve ardından tekrar **Uygulamalar**'a tıklayabilirsiniz.
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-android2.png)

## <a name="step-4-deploy-the-application"></a>4. Adım: Uygulamayı dağıtma
Uygulamayı ekledikten sonra, son kullanıcılarınızın kullanabilmesi için dağıtmanız gerekir. Bu, oluşturduğunuz ilkeyi uygulamaya bağlayacağınız adımdır.

### <a name="ios"></a>iOS
1. Uygulamalar ekranında, oluşturduğunuz uygulamayı seçin. Ardından, **Dağıtımı Yönet...** bağlantısını seçin.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios1.png)
2. **Grup Seç** ekranında, bu uygulamayı dağıtmak istediğiniz grupları seçebilirsiniz. **İleri**'yi seçin.
3. **Dağıtım Eylemi** ekranında, bu uygulamayı nasıl dağıtmak istediğinizi seçebilirsiniz. **Kullanılabilir Yükleme** veya **Gerekli Yükleme** seçenekleri arasında yapılacak tercih, uygulamanın kullanıcılar tarafından isteğe bağlı olarak yüklenmesi için Şirket Portalı'nda bulunmasını sağlar. Seçiminizi yaptıktan sonra, **İleri**'yi seçin.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios2.png)
4. **Mobil Uygulama Yönetimi** ekranında, [2. Adım](#step-2-create-a-mobile-application-management-policy)'da oluşturduğumuz Mobil Uygulama Yönetimi ilkesini seçebilirsiniz. Mevcut tek iOS ilkesi olması halinde, oluşturduğunuz ilke varsayılan olarak kullanılır. **İleri**'yi seçin.
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios3.png)
5. Kuruluşunuza yönelik bir ilke varsa **VPN Profili** ekranında bunu seçebilirsiniz. Varsayılan olarak **Yok** seçeneği belirlenir. **İleri**'yi seçin.
6. **Mobil Uygulama Yapılandırması** ekranında, bir **Uygulama Yapılandırma İlkesi** (oluşturduysanız) seçebilirsiniz. Varsayılan olarak **Yok** seçeneği belirlenir. Bu gerekli değildir. **Son**'u seçin.

Uygulamayı dağıttıktan sonra, uygulamalar sayfasındaki Dağıtıldı bölümünde **Evet** seçeneğinin gösterilmesi gerekir.

### <a name="android"></a>Android
1. Uygulamalar ekranında, oluşturduğunuz uygulamayı seçin. Ardından, **Dağıtımı Yönet...** bağlantısını seçin.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android1.png)
2. **Grup Seç** ekranında, bu uygulamayı dağıtmak istediğiniz grupları seçebilirsiniz. **İleri**'yi seçin.
3. **Dağıtım Eylemi** ekranında, bu uygulamayı nasıl dağıtmak istediğinizi seçebilirsiniz. **Kullanılabilir Yükleme** veya **Gerekli Yükleme** seçenekleri arasında yapılacak tercih, uygulamanın kullanıcılar tarafından isteğe bağlı olarak yüklenmesi için Şirket Portalı'nda bulunmasını sağlar. Seçiminizi yaptıktan sonra, **İleri**'yi seçin.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android2.png)
4. **Mobil Uygulama Yönetimi** ekranında, [2. Adım](#step-2-create-a-mobile-application-management-policy)'da oluşturduğumuz Mobil Uygulama Yönetimi ilkesini seçebilirsiniz. Kullanılabilir tek Android ilkesi ise oluşturduğunuz ilkeyi varsayılan olarak kullanır. **Son**'u seçin.
   
    ![](media/service-admin-mobile-intune/intune-deploy-android3.png)

Uygulamayı dağıttıktan sonra, uygulamalar sayfasındaki Dağıtıldı bölümünde **Evet** seçeneğinin gösterilmesi gerekir.

## <a name="step-5-install-the-application-on-a-device"></a>5. Adım: Uygulamayı bir cihaza yükleme
Uygulamayı, Şirket Portalı uygulaması aracılığıyla yüklersiniz. Şirket Portalı uygulamasını henüz yüklemediyseniz iOS veya Android platformundaki uygulama mağazasını kullanarak edinebilirsiniz. Şirket Portalı'nda oturum açmak için kurumsal oturum açma bilgilerinizi kullanırsınız.

1. Şirket Portalı uygulamasını açın.
2. Listelenen uygulamalar arasında Power BI uygulamasını görmüyorsanız **Şirket Uygulamaları**'nı açın.
   
    ![](media/service-admin-mobile-intune/intune-companyportal1.png)
3. Dağıttığınız Power BI uygulaması seçin.
   
    ![](media/service-admin-mobile-intune/intune-companyportal2.png)
4. **Yükle**'yi seçin.
   
    ![](media/service-admin-mobile-intune/intune-companyportal3.png)
5. iOS kullanıyorsanız uygulama size iletilir. Gönderim iletişim kutusundaki **Yükle**'yi seçin.
   
    ![](media/service-admin-mobile-intune/intune-companyportal5.png)

Yükleme gerçekleştikten sonra, bunun **Şirketiniz tarafından yönetilen** bir uygulama olduğunu görürsünüz. İlkede PIN kullanarak erişimi etkinleştirdiyseniz aşağıdaki ekranla karşılaşırsınız.

![](media/service-admin-mobile-intune/intune-powerbi-pin.png)

## <a name="next-steps"></a>Sonraki adımlar
[Configure and deploy mobile application management policies in the Microsoft Intune console (Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma)](https://technet.microsoft.com/library/dn878026.aspx)  
[Mobil cihazlar için Power BI uygulamaları](mobile-apps-for-mobile-devices.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
