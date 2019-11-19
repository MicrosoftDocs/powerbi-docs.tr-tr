---
title: Power BI'da klasik çalışma alanları oluşturma
description: Kuruluşunuza ana ölçümler sunmayı amaçlayan çalışma alanları, pano koleksiyonları, raporlar ve sayfalandırılmış raporlar oluşturmayı öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/10/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 1087ac4301a172500c997e78ee3a16695f6b0d73
ms.sourcegitcommit: 2aa83bd53faad6fb02eb059188ae623e26503b2a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73021123"
---
# <a name="create-classic-workspaces-in-power-bi"></a>Power BI'da klasik çalışma alanları oluşturma

Power BI'da, çalışma arkadaşlarınızla işbirliği yaparak pano koleksiyonları, raporlar ve sayfalandırılmış raporlar oluşturabildiğiniz ve bunları geliştirebildiğiniz bir yer olarak *çalışma alanları* oluşturabilirsiniz. Sonra, koleksiyonu *uygulamaların* içinde birlikte paketler ve kuruluşunuzun tamamına veya belirli kişi veya gruplara dağıtabilirsiniz. 

**Biliyor muydunuz?** Power BI, artık varsayılan olan yeni bir çalışma alanı deneyimi sunmaktadır. Yeni çalışma alanlarıyla ilgili ayrıntılar için [Yeni çalışma alanlarında çalışmayı düzenleme](service-new-workspaces.md) konusunu okuyun. 

Klasik bir çalışma alanı oluşturduğunuzda, temel, ilişkili bir Office 365 grubu oluşturmuş olursunuz. Çalışma alanı yönetiminin tamamı Office 365'tedir. Bu çalışma alanlarına iş arkadaşlarınızı üye veya yönetici olarak ekleyebilirsiniz. Çalışma alanında, hep birlikte daha geniş bir kitleye dağıtmayı planladığınız panolar, raporlar ve diğer makaleler üzerinde işbirliği yapabilirsiniz. Bir çalışma alanına eklediğiniz herkesin Power BI Pro lisansına ihtiyacı vardır. 

## <a name="video-apps-and-workspaces"></a>Video: Uygulamalar ve çalışma alanları
<iframe width="640" height="360" src="https://www.youtube.com/embed/Ey5pyrr7Lk8?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-classic-workspace-based-on-an-office-365-group"></a>Office 365 grubu temelinde klasik çalışma alanı oluşturma

Bir çalışma alanı oluşturduğunuzda, bu çalışma alanı bir Office 365 grubu üzerinde oluşturulur.

[!INCLUDE [powerbi-service-create-app-workspace](./includes/powerbi-service-create-app-workspace.md)]

Çalışma alanını ilk oluşturduğunuzda, Office 365'e yayılması için yaklaşık bir saat beklemeniz gerekebilir. 

### <a name="add-an-image-to-your-office-365-workspace-optional"></a>Office 365 çalışma alanınıza görüntü ekleme (isteğe bağlı)
Varsayılan olarak Power BI, uygulamanız için uygulamanın baş harflerini içeren küçük ve renkli bir daire oluşturur. Ancak, bunu bir görüntüyle özelleştirmek isteyebilirsiniz. Bir görüntü eklemek için Exchange Online lisansı gerekir.

1. **Çalışma Alanları**'nı, çalışma alanı adının yanındaki **Diğer seçenekler**'i (...), sonra da **Üyeler**’i seçin. 
   
     ![Çalışma Alanı Üyelerini seçme](media/service-create-workspaces/power-bi-workspace-old-members.png)
   
    Çalışma alanı için Office 365 Outlook hesabı yeni bir tarayıcı penceresinde açılır.
2. **Düzenleme** kalemini seçin.
   
     ![Office 365 kalem simgesi](media/service-create-workspaces/power-bi-workspace-old-edit-group.png)
3. Kamera görüntüsünü seçin ve kullanmak istediğiniz görüntüyü bulun.
   
     ![Kamera görüntüsünü seçin](media/service-create-workspaces/power-bi-workspace-old-camera.png)

     Görüntüler .png, .jpg veya .bmp dosyaları olabilir. Dosya boyutu 3 MB'a varan büyüklükte olabilir. 

4. **Tamam**'ı, sonra da **Kaydet**'i seçin.
   
    Görüntü, Office 365 Outlook penceresindeki renkli dairenin yerine geçer. 
   
     ![Özelleştirilmiş görüntü](media/service-create-workspaces/power-bi-workspace-old-new-image.png)
   
    Birkaç dakika sonra Power BI'daki uygulamada da görünecektir.

## <a name="add-content-to-your-workspace"></a>Çalışma alanınıza içerik ekleme

Çalışma alanını oluşturduktan sonra, buna içerik eklemenin zamanı gelir. Bu tıpkı Çalışma Alanım bölümünüze içerik eklemeye benzer ancak çalışma alanındaki diğer kişiler de bu içeriği görüp onunla çalışabilir. İçeriği tamamladığınızda bir uygulama olarak yayımlayabilecek olmanız büyük bir farktır. Çalışma alanının içerik listesinde içeriği görüntülediğinizde, çalışma alanının adı içerik sahibi olarak listelenir.

### <a name="connect-to-third-party-services-in-workspaces"></a>Çalışma alanlarında üçüncü taraf hizmetlere bağlanma

Uygulamalar Power BI'ın desteklediği tüm üçüncü taraf hizmetler için sağlandığından, kullandığınız Microsoft Dynamics CRM, Salesforce Google Analytics gibi hizmetlerden veri almanız kolaylaşır. Kullanıcılarınıza ihtiyaçları olan verileri vermek için kurumsal uygulamalar yayımlayabilirsiniz.

Geçerli çalışma alanlarında, kurumsal içerik paketlerini ve Microsoft Dynamics CRM, Salesforce veya Google Analytics gibi üçüncü taraf içerik paketlerini kullanarak da bağlanabilirsiniz. Kurumsal içerik paketlerinizi uygulamalara geçirmeyi göz önünde bulundurun.

## <a name="distribute-an-app"></a>Uygulamayı dağıtma

Kuruluşunuzda büyük bir hedef kitleye resmi içerik dağıtmak istiyorsanız, çalışma alanınızdan bir uygulama yayımlayabilirsiniz.  İçerik hazır olduğunda, yayımlamak istediğiniz panoları ve raporları seçer ve ardından bunu bir *uygulama* olarak yayımlarsınız. Her çalışma alanından bir uygulama oluşturabilirsiniz.

Sol gezinti bölmesinde bulunan uygulamalar listesinde, yüklediğiniz tüm uygulamalar gösterilir. İş arkadaşlarınız uygulamanızı birkaç farklı yolla alabilir. 
- Uygulamanızı Microsoft AppSource’tan da bulabilir ve yükleyebilir
- Onlara bir doğrudan bağlantı gönderebilirsiniz. 
- Power BI yöneticiniz izin verirse, uygulamayı otomatik olarak iş arkadaşlarınızın Power BI hesaplarına yükleyebilirsiniz. 

Çalışma alanınızdan bir güncelleştirme yayımladıktan sonra kullanıcılar otomatik olarak güncelleştirilmiş uygulama içeriğini görür. Çalışma alanınızdaki uygulama içeriği tarafından kullanılan veri kümelerinde yenileme zamanlamasını ayarlayarak verilerin ne sıklıkla yenilendiğini denetleyebilirsiniz. Ayrıntılar için bkz. [Power BI’da yeni çalışma alanlarından uygulama yayımlama](service-create-distribute-apps.md).

## <a name="power-bi-classic-apps-faq"></a>Power BI klasik uygulamaları hakkında SSS

### <a name="how-are-apps-different-from-organizational-content-packs"></a>Uygulamalarla kurumsal içerik paketlerinin farkı nedir?
Uygulamalar, kurumsal içerik paketlerinin gelişmiş halidir. Zaten kurumsal içerik paketleriniz varsa bu paketler, uygulamalarla yan yana çalışmaya devam ederler. Uygulamalarla içerik paketlerinde birkaç önemli farklılık vardır. 

* İş kullanıcıları bir içerik paketi yükledikten sonra paket, gruplandırılmış kimliğini kaybeder: Başka panolar ve raporlara karışmış bir pano ve rapor listesinden ibaret olur. Buna karşın uygulamalar, gruplandırılmış halleri ve kimliklerini yüklemeden sonra bile korur. Bu gruplandırma sayesinde iş kullanıcıları zaman geçtikten sonra bile uygulamalara kolayca gidebilir.
* Herhangi bir çalışma alanında birden çok içerik paketi oluşturabilirsiniz ancak bir uygulamanın çalışma alanıyla bire bir ilişkisi vardır. 
* Zaman içinde kurumsal içerik paketlerini kullanımdan kaldırmayı planlıyoruz. Bu nedenle bundan sonra uygulama oluşturmanızı öneririz.  
* Yeni çalışma alanı deneyimiyle, kurumsal içerik paketlerinin kullanımdan kaldırılması yönünde ilk adımları atıyoruz. Yeni çalışma alanlarında bunları kullanamaz veya oluşturamazsınız.

İkisini karşılaştırmak için bkz. [Yeni çalışma alanlarıyla var olan çalışma alanları arasında ne fark vardır?](service-new-workspaces.md#how-the-new-workspaces-are-different) 

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da uygulamaları yükleme ve kullanma](service-create-distribute-apps.md)
- [Yeni çalışma alanlarını oluşturma](service-create-the-new-workspaces.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
