---
title: Power BI'da çalışma arkadaşlarınızla çalışma alanları oluşturma
description: Kuruluşunuza ana ölçümler sunmayı amaçlayan çalışma alanlarını, yani pano ve rapor koleksiyonlarını oluşturmayı öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/06/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: b40933e085cf81528a28e9eedb4260351f657323
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46548408"
---
# <a name="create-workspaces-with-your-colleagues-in-power-bi"></a>Power BI'da çalışma arkadaşlarınızla çalışma alanları oluşturma

Power BI'da, çalışma arkadaşlarınızla işbirliği yaparak pano ve rapor koleksiyonları oluşturabildiğiniz ve bunları geliştirebildiğiniz bir yer olarak *çalışma alanları* oluşturabilirsiniz. Sonra, bunları *uygulamaların* içinde birlikte paketler ve kuruluşunuzun tamamına veya belirli kişi veya gruplara dağıtabilirsiniz. 

![Power BI uygulamaları](media/service-create-workspaces/power-bi-apps-left-nav.png)

Çalışma alanı oluşturduğunuzda, temel, ilişkili bir Office 365 grubu oluşturmuş olursunuz. Çalışma alanı yönetiminin tamamı Office 365'tedir. Bu çalışma alanlarına iş arkadaşlarınızı üye veya yönetici olarak ekleyebilirsiniz. Çalışma alanında hep birlikte daha geniş bir kitleye dağıtmayı planladığınız panolar, raporlar ve diğer makaleler üzerinde işbirliği yapabilirsiniz. Bir uygulama çalışma alanına eklediğiniz herkesin Power BI Pro lisansına ihtiyacı vardır. 

**Biliyor muydunuz?** Power BI yeni bir çalışma alanı deneyiminin önizlemesini sunuyor. Çalışma alanlarının gelecekte nasıl bir değişim geçireceğini görmek için [Yeni çalışma alanları oluşturma (önizleme)](service-create-the-new-workspaces.md) konusunu okuyun. 

## <a name="video-apps-and-app-workspaces"></a>Video: Uygulamalar ve uygulama çalışma alanları
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="create-an-app-workspace-based-on-an-office-365-group"></a>Office 365 grubu temelinde uygulama çalışma alanı oluşturma

Bir uygulama çalışma alanı oluşturduğunuzda, bu çalışma alanı bir Office 365 grubu üzerinde oluşturulur.

[!INCLUDE [powerbi-service-create-app-workspace](./includes/powerbi-service-create-app-workspace.md)]

Çalışma alanını ilk oluşturduğunuzda, Office 365'e yayılması için yaklaşık bir saat beklemeniz gerekebilir. 

### <a name="add-an-image-to-your-office-365-app-workspace-optional"></a>Office 365 uygulama çalışma alanınıza resim ekleme (isteğe bağlı)
Varsayılan olarak Power BI, uygulamanız için uygulamanın baş harflerini içeren küçük ve renkli bir daire oluşturur. Ancak, bunu bir görüntüyle özelleştirmek isteyebilirsiniz. Bir görüntü eklemek için Exchange Online lisansı gerekir.

1. **Çalışma Alanı**'nı ve ardından çalışma alanı adının yanındaki üç nokta (...) simgesiyle **Üyeler**'i seçin. 
   
     ![Çalışma Alanı Üyelerini seçme](media/service-create-distribute-apps/power-bi-apps-workspace-members.png)
   
    Çalışma alanı için Office 365 Outlook hesabı yeni bir tarayıcı penceresinde açılır.
2. Sol üstteki renkli dairenin üzerine gelirseniz daire bir kalem simgesine dönüşür. Kalem simgesini seçin.
   
     ![Office 365 kalem simgesi](media/service-create-distribute-apps/power-bi-apps-workspace-edit-image.png)
3. Kalem simgesini yeniden seçin ve kullanmak istediğiniz görüntüyü bulun.
   
     ![Kalemi yeniden seçin](media/service-create-distribute-apps/power-bi-apps-workspace-edit-group.png)

4. **Kaydet**'i seçin.
   
     ![Kaydet'i seçme](media/service-create-distribute-apps/power-bi-apps-workspace-save-image.png)
   
    Görüntü, Office 365 Outlook penceresindeki renkli dairenin yerine geçer. 
   
     ![Özelleştirilmiş görüntü](media/service-create-distribute-apps/power-bi-apps-workspace-image-in-office-365.png)
   
    Birkaç dakika sonra Power BI'daki uygulamada da görünecektir.
   
     ![Özelleştirilmiş görüntü](media/service-create-distribute-apps/power-bi-apps-image.png)

## <a name="add-content-to-your-app-workspace"></a>Uygulama çalışma alanınıza içerik ekleme

Uygulama çalışma alanını oluşturduktan sonra, buna içerik eklemenin zamanı gelir. Bu tıpkı Çalışma Alanım bölümünüze içerik eklemeye benzer ancak çalışma alanındaki diğer kişiler de bu içeriği görüp onunla çalışabilir. İçeriği tamamladığınızda bir uygulama olarak yayımlayabilecek olmanız büyük bir farktır. Uygulama çalışma alanının içerik listesinde içeriği görüntülediğinizde, uygulama çalışma alanının adı içerik sahibi olarak listelenir.

### <a name="connect-to-third-party-services-in-app-workspaces"></a>Uygulama çalışma alanlarında üçüncü taraf hizmetlere bağlanma

Uygulamalar Power BI'ın desteklediği tüm üçüncü taraf hizmetler için sağlandığından, kullandığınız Microsoft Dynamics CRM, Salesforce Google Analytics gibi hizmetlerden veri almanız kolaylaşır. Kullanıcılarınıza ihtiyaçları olan verileri vermek için kurumsal uygulamalar yayımlayabilirsiniz.

Geçerli çalışma alanlarında, kurumsal içerik paketlerini ve Microsoft Dynamics CRM, Salesforce veya Google Analytics gibi üçüncü taraf içerik paketlerini kullanarak da bağlanabilirsiniz. Kurumsal içerik paketlerinizi uygulamalara geçirmeyi göz önünde bulundurun.

## <a name="distribute-an-app"></a>Uygulamayı dağıtma

İçerik hazır olduğunda, yayımlamak istediğiniz panoları ve raporları seçer ve ardından bunu bir *uygulama* olarak yayımlarsınız. İş arkadaşlarınız uygulamalarınızı birkaç farklı yolla alabilir. Power BI yöneticiniz izin verirse, uygulamayı otomatik olarak iş arkadaşlarınızın Power BI hesaplarına yükleyebilirsiniz. Buna alternatif olarak, iş arkadaşlarınız, uygulamalarınızı Microsoft AppSource'tan bulabilir ve yükleyebilir veya iş arkadaşlarınıza bir doğrudan bağlantı gönderebilirsiniz. Güncelleştirmeleri otomatik olarak alırlar ve verinin ne sıklıkla yenileneceğini denetleyebilirsiniz. Ayrıntılar için bkz. [Power BI'da panolar ve raporlar içeren uygulamalar yayımlama](consumer/end-user-create-apps.md).

## <a name="power-bi-apps-faq"></a>Power BI uygulamaları hakkında SSS

### <a name="how-are-apps-different-from-organizational-content-packs"></a>Uygulamalarla kurumsal içerik paketlerinin farkı nedir?
Uygulamalar, kurumsal içerik paketlerinin gelişmiş halidir. Zaten kurumsal içerik paketleriniz varsa bu paketler, uygulamalarla yan yana çalışmaya devam ederler. Uygulamalarla içerik paketlerinde birkaç önemli farklılık vardır. 

* İş kullanıcıları bir içerik paketi yükledikten sonra paket, gruplandırılmış kimliğini kaybeder: Başka panolar ve raporlara karışmış bir pano ve rapor listesinden ibaret olur. Buna karşın uygulamalar, gruplandırılmış halleri ve kimliklerini yüklemeden sonra bile korur. Böylece iş kullanıcıları zaman geçtikten sonra bile uygulamalara kolayca gidebilir.
* Herhangi bir çalışma alanında birden çok içerik paketi oluşturabilirsiniz ancak bir uygulamanın çalışma alanıyla bire bir ilişkisi vardır. 
* Zaman içinde kurumsal içerik paketlerini kullanımdan kaldırmayı planlıyoruz. Bu nedenle bundan sonra uygulama oluşturmanızı öneririz.  
* Yeni çalışma alanı deneyimi önizlemesiyle, kurumsal içerik paketlerinin kullanımdan kaldırılması yönünde ilk adımları atıyoruz. Önizleme çalışma alanlarında bunları kullanamaz veya oluşturamazsınız.

Geçerli uygulama çalışma alanlarıyla yenilerini karşılaştırmak için bkz. [Yeni uygulama çalışma alanlarıyla var olan uygulama çalışma alanları arasında ne fark vardır?](service-create-the-new-workspaces.md#how-are-the-new-app-workspaces-different-from-current-app-workspaces) 

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da uygulamaları yükleme ve kullanma](consumer/end-user-apps.md)
* [Dış hizmetler için Power BI uygulamaları](consumer/end-user-connect-to-services.md)
- [Yeni çalışma alanları oluşturma (önizleme)](service-create-the-new-workspaces.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
