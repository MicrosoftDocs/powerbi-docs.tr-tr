---
title: Yeni çalışma alanları oluşturma (önizleme) - Power BI
description: Kuruluşunuza ana ölçümler sunmayı amaçlayan yeni çalışma alanlarını, pano ve rapor koleksiyonlarını oluşturmayı öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/19/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: a93c676775fe6e826ea83cfad91498b7fe3e2103
ms.sourcegitcommit: 5206651c12f2b91a368f509470b46f3f4c5641e6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53983612"
---
# <a name="create-the-new-workspaces-preview-in-power-bi"></a>Power BI'da yeni çalışma alanları oluşturma (önizleme)

Power BI yeni bir çalışma alanı deneyimini önizleme olarak sunuyor. Çalışma alanları hala iş arkadaşlarıyla işbirliği yapıp pano ve rapor koleksiyonları oluşturma yeridir. Bu pano ve raporları *uygulamalarınızın* içinde paketleyebilir ve kuruluşunuzun tamamına ya da belirli kişi veya gruplara dağıtabilirsiniz. 

![Power BI yeni çalışma alanları önizlemesi](media/service-create-the-new-workspaces/power-bi-new-workspaces-preview.png)

Yeni çalışma alanları önizlemesiyle şimdi şunları yapabilirsiniz:

- Çalışma alanı rollerini kullanıcı gruplarına atayabilirsiniz: güvenlik grupları, dağıtım listeleri, Office 365 grupları ve bireyler.
- Office 365 grubu oluşturmadan Power BI'da bir çalışma alanı oluşturabilirsiniz.
- Çalışma alanında daha esnek bir izin yönetimi için daha ayrıntılı çalışma alanı rolleri kullanabilirsiniz.

Daha fazla arka plan bilgisi için, [yeni çalışma alanları (önizleme)](service-new-workspaces.md) makalesine bakın.

## <a name="create-one-of-the-new-app-workspaces"></a>Yeni uygulama çalışma alanlarından birini oluşturma

1. İşe uygulama çalışma alanını oluşturarak başlayın. **Çalışma alanları** > **Uygulama çalışma alanı oluşturma**'yı seçin.
   
     ![Uygulama çalışma alanı oluştur](media/service-create-the-new-workspaces/power-bi-create-app-workspace.png)

2. **Geliştirilmiş çalışma alanlarını önizle** altında **Şimdi dene**'yi seçin.
   
     ![Geliştirilmiş çalışma alanlarını önizle](media/service-create-the-new-workspaces/power-bi-preview-improved-workspaces.png)

2. Çalışma alanına bir ad verin. Ad kullanılamıyorsa, düzenleyerek benzersiz bir kimlik haline getirin.
   
     Uygulamanın adı çalışma alanının adıyla aynı olur.
   
1. İsterseniz bir resim ekleyin. Dosya boyutu 45 KB'tan küçük olmalıdır.
 
    ![Çalışma alanını adlandırma ve resim ekleme](media/service-create-the-new-workspaces/power-bi-name-workspace.png)

1. **Kaydet**'i seçin.

    Burada, yeni çalışma alanınızın **Hoş Geldiniz** ekranında verileri ekleyebilirsiniz. 

    ![Yeni çalışma alanı Hoş Geldiniz ekranı](media/service-create-the-new-workspaces/power-bi-workspace-welcome-screen.png)

1. Örneğin, **Örnekler** > **Müşteri Kârlılığı Örneği**'ni seçin.

    Şimdi çalışma alanı içerik listesinde **Yeni çalışma alanları önizleme**'yi görürsünüz. Yönetici olduğunuz için yeni **Erişim** eylemini de görürsünüz.

    ![Çalışma alanları önizleme içerik listesi](media/service-create-the-new-workspaces/power-bi-workspaces-preview-content-list.png)

1. **Erişim**'i seçin.

1. Bu çalışma alanlarına güvenlik gruplarını, dağıtım listelerini, Office 365 gruplarını veya kişileri üye, katkıda bulunan veya yönetici olarak ekleyin. Farklı rollerin açıklamaları için bu makalenin devamındaki [Yeni çalışma alanlarındaki roller](#roles-in-the-new-workspaces) bölümüne bakın.

    ![Çalışma alanlarına üye, yönetici, katkıda bulunan ekleme](media/service-create-the-new-workspaces/power-bi-access-add-members.png)

9. **Ekle** > **Kapat**'ı seçin.

1. Power BI çalışma alanını oluşturur ve açar. Üyesi olduğunuz çalışma alanlarının listesinde bunu görürsünüz. Yönetici olduğunuz için üç nokta (…) simgesini seçerek geri gidebilir, çalışma alanı ayarlarında değişiklik yapabilir, yani yeni üye ekleyebilir veya üye izinlerini değiştirebilirsiniz.

     ![Çalışma alanının ayarlarını ve erişimini düzenleme](media/service-create-the-new-workspaces/power-bi-edit-workspace.png)

## <a name="add-content-to-your-app-workspace"></a>Uygulama çalışma alanınıza içerik ekleme

Yeni stilde bir uygulama çalışma alanı oluşturduktan sonra, buna içerik eklemenin zamanı gelir. Yeni ve eski stil çalışma alanlarına içerik ekleme işlemi, tek bir özel durum dışında aynıdır. Her iki uygulama çalışma alanında da, tıpkı Çalışma Alanım bölümünüzde olduğu gibi dosyaları karşıya yükleyebilir veya dosyalara bağlanabilirsiniz. Yeni çalışma alanlarında, kurumsal içerik paketlerine ya da Microsoft Dynamics CRM, Salesforce veya Google Analytics gibi üçüncü taraf içerik paketlerine bağlanamazsınız. Geçerli çalışma alanlarında içerik paketlerine bağlanabilirsiniz.

Uygulama çalışma alanının içerik listesinde içeriği görüntülediğinizde, uygulama çalışma alanının adı içerik sahibi olarak listelenir.

### <a name="connecting-to-third-party-services-in-new-workspaces-preview"></a>Yeni çalışma alanlarında (önizleme) üçüncü taraf hizmetlere bağlanma

Yeni çalışma alanları deneyiminde, uygulamalara *odaklanmak* için bir değişiklik yapıyoruz. Üçüncü taraf hizmetlerine yönelik uygulamalar, kullanıcıların kullandıkları Microsoft Dynamics CRM, Salesforce veya Google Analytics gibi hizmetlerden veri almasını kolaylaştırır.
Kurumsal uygulamalar kullanıcılarınıza ihtiyaçları olan şirket içi verilerini getirir. Kurumsal uygulamalara, kullanıcıların uygulama içinde buldukları içeriği özelleştirebilmelerine olanak tanıyan özellikler eklemeyi planlıyoruz. Bu özellikler, içerik paketlerine duyulan ihtiyacı ortadan kaldıracaktır. 

Yeni çalışma alanı önizlemesiyle, kurumsal içerik paketleri oluşturamaz veya kullanamazsınız. Bunun yerine, üçüncü taraf hizmetlere bağlanmak için sağlanan uygulamaları kullanabilir veya şirket içindeki ekiplerinizden şu anda kullandığınız tüm içerik paketleri için uygulamalar sağlamalarını isteyebilirsiniz. 

## <a name="distribute-an-app"></a>Uygulamayı dağıtma

İçerik hazır olduğunda, yayımlamak istediğiniz panoları ve raporları seçer ve ardından bunu bir *uygulama* olarak yayımlarsınız. Her çalışma alanından bir uygulama oluşturabilirsiniz. İş arkadaşlarınız uygulamanızı birkaç farklı yolla alabilir. Power BI yöneticiniz izin verirse, uygulamayı otomatik olarak iş arkadaşlarınızın Power BI hesaplarına yükleyebilirsiniz. Buna alternatif olarak, iş arkadaşlarınız, uygulamanızı Microsoft AppSource'tan bulabilir ve yükleyebilir veya iş arkadaşlarınıza bir doğrudan bağlantı gönderebilirsiniz. Güncelleştirmeleri otomatik olarak alırlar ve verinin ne sıklıkla yenileneceğini denetleyebilirsiniz. Ayrıntılar için bkz. [Power BI'da panolar ve raporlar içeren uygulamalar yayımlama](service-create-distribute-apps.md).

## <a name="convert-old-app-workspaces-to-new-app-workspaces"></a>Eski uygulama çalışma alanlarını yeni uygulama çalışma alanlarına dönüştürme

Önizleme döneminde, eski uygulama çalışma alanlarınızı otomatik olarak yenilerine dönüştüremezsiniz. Öte yandan yeni bir uygulama çalışma alanı oluşturabilir ve içeriğinizi yeni konumda yayımlayabilirsiniz. 

Yeni çalışma alanları genel kullanıma sunulduğunda, eskilerin otomatik olarak geçirilmesini tercih edebilirsiniz. Genel kullanıma sunulduktan sonra, bir noktada bunları geçirmeniz gerekecektir.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da yeni çalışma alanlarında çalışmayı düzenleme (önizleme)](service-new-workspaces.md) makalesini okuyun.
* [Geçerli çalışma alanlarını oluşturma](service-create-workspaces.md)
* [Power BI'da uygulamaları yükleme ve kullanma](service-create-distribute-apps.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
