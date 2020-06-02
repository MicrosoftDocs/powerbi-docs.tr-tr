---
title: Yeni çalışma alanları oluşturma - Power BI
description: Kuruluşunuza ana ölçümler sunmayı amaçlayan yeni çalışma alanları, pano koleksiyonları, raporlar ve sayfalandırılmış raporlar oluşturmayı öğrenin.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/26/2020
ms.author: maggies
ms.custom: contperfq4
LocalizationGroup: Share your work
ms.openlocfilehash: edc06d7a46589c999e4bf18613c0c75f6d5bf983
ms.sourcegitcommit: a7b142685738a2f26ae0a5fa08f894f9ff03557b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84120583"
---
# <a name="create-the-new-workspaces-in-power-bi"></a>Power BI'da yeni çalışma alanları oluşturma

Bu makalede, *klasik* çalışma alanı yerine *yeni bir çalışma alanının* nasıl oluşturulacağı açıklanmaktadır. İki tür çalışma alanı da iş arkadaşlarınızla işbirliği yaptığınız yerlerdir. Bu çalışma alanlarında pano, rapor ve sayfalandırılmış rapor koleksiyonları oluşturursunuz. Dilerseniz bu koleksiyonu bir *uygulamaya* paketleyip daha geniş bir kitleye dağıtabilirsiniz.

Yeni çalışma alanları ile eski çalışma alanları arasındaki farklar aşağıda açıklanmaktadır. Yeni çalışma alanlarında şunları yapabilirsiniz:

- Çalışma alanı rollerini kullanıcı gruplarına ve bireylere atama.
- Microsoft 365 grubu oluşturmadan Power BI'da bir çalışma alanı oluşturabilirsiniz.
- Daha esnek bir izin yönetimi için daha ayrıntılı çalışma alanı rolleri kullanma.

:::image type="content" source="media/service-create-the-new-workspaces/power-bi-workspace-sales-marketing.png" alt-text="Satış ve Pazarlama örnek çalışma alanı":::

Daha fazla arka plan bilgisi için [yeni çalışma alanları](service-new-workspaces.md) makalesine bakın.

Klasik çalışma alanınızı geçirmeye hazır mısınız? Ayrıntılar için bkz. [Power BI'da klasik çalışma alanlarını yeni çalışma alanlarına yükseltme](service-upgrade-workspaces.md).

> [!NOTE]
> Çalışma alanındaki içeriğe göz atan Power BI Pro kullanıcılarında satır düzeyi güvenliği (RLS) zorunlu tutmak için kullanıcılara Görüntüleyici Rolü atayın.

## <a name="create-one-of-the-new-workspaces"></a>Yeni çalışma alanlarından birini oluşturma

1. İşe çalışma alanını oluşturarak başlayın. **Çalışma alanları** > **Çalışma alanı oluştur**'u seçin.
   
     ![Çalışma alanı oluşturma](media/service-create-the-new-workspaces/power-bi-workspace-create.png)

2. **Klasik sürüme geri al**'ı seçmediğiniz müddetçe otomatik olarak yükseltilmiş bir çalışma alanı oluşturacaksınız.
   
     ![Yeni çalışma alanı deneyimi](media/service-create-the-new-workspaces/power-bi-new-workspace.png)
     
     **Klasik sürüme geri al**’ı seçerseniz Microsoft 365 grubunu temel alan bir [klasik çalışma alanı](service-create-workspaces.md) oluşturursunuz.

2. Çalışma alanına benzersiz bir ad verin. Ad kullanılamıyorsa, düzenleyerek benzersiz bir ad haline getirin.
   
     Çalışma alanından oluşturduğunuz uygulama, çalışma alanıyla aynı ada ve simgeye sahip olacaktır.
   
1. Aşağıda, çalışma alanınız için ayarlayabileceğiniz bazı isteğe bağlı öğeler verilmiştir:

    Bir **Çalışma alanı görüntüsü** yükleyin. Dosyalar .png veya .jpg biçiminde olabilir. Dosya boyutu 45 KB'tan küçük olmalıdır.
    
    [Bir **Kişi listesi**](#create-a-contact-list) ekleyin. Varsayılan olarak, çalışma alanı yöneticileri kişiler arasındadır. 
    
    [Microsoft 365 grubu dosya depolama konumu kullanmak için bir **OneDrive Çalışma Alanı**](#set-a-workspace-onedrive) belirtin. 

    Çalışma alanını bir **Ayrılmış kapasiteye** atamak için **Premium** sekmesinde **Ayrılmış kapasite**'yi seçin.
     
    ![Ayrılmış kapasite](media/service-create-the-new-workspaces/power-bi-workspace-premium.png)

1. **Kaydet**'i seçin.

    Power BI çalışma alanını oluşturur ve açar. Üyesi olduğunuz çalışma alanlarının listesinde bunu görürsünüz. 

## <a name="create-a-contact-list"></a>Kişi listesi oluşturma

Çalışma alanında oluşan sorunlar hakkında hangi kullanıcıların bildirim alacağını belirtebilirsiniz. Varsayılan olarak, çalışma alanı yöneticisi olarak belirtilen tüm kullanıcı veya gruplar bildirim alır, ancak *kişi listesine* başkalarını da ekleyebilirsiniz. Kullanıcıların çalışma alanıyla ilgili yardım alabilmesi için kişi listesinde yer alan kullanıcılar veya gruplar kullanıcı arabiriminde listelenir.

1. Yeni **Kişi listesi** ayarına iki şekilde erişebilirsiniz:

    İlk kez oluşturduğunuzda **Çalışma alanı oluştur** bölmesinden.

    Gezinti bölmesinde, **Çalışma alanları**’nın yanındaki oku ve sonra çalışma alanı adı > **Çalışma alanı ayarları**’nın yanındaki **Diğer seçenekler** (...) düğmesini seçin. **Ayarlar** bölmesi açılır.

    ![Çalışma alanı ayarları](media/service-create-the-new-workspaces/power-bi-workspace-new-settings.png)

2. **Gelişmiş** > **Kişi listesi** altında **Çalışma alanı yöneticileri** varsayılan değerini kabul edin veya **Belirli kullanıcılar veya gruplar** listesini ekleyin. 

    ![Çalışma alanı kişileri](media/service-create-the-new-workspaces/power-bi-workspace-contacts.png)

3. **Kaydet**'i seçin.

## <a name="set-a-workspace-onedrive"></a>OneDrive çalışma alanı ayarlama

OneDrive Çalışma Alanı özelliği, SharePoint Belge Kitaplığı dosya depolama alanının çalışma alanı kullanıcıları tarafından kullanılabildiği bir Microsoft 365 grubu yapılandırmanızı sağlar. Grubu önce Power BI dışında oluşturacaksınız. 

Power BI, Microsoft 365 grubu üyeliğiyle çalışma alanı erişimi olacak şekilde yapılandırılmış kullanıcı veya grupların izinlerini eşitlemez. En iyi yöntem, bu ayarda dosya depolama alanını yapılandırdığınız aynı Microsoft 365 Grubuna [çalışma alanı erişim izni](#give-access-to-your-workspace) vermektir. Ardından Microsoft 365 grubunun üyeliğini yöneterek çalışma alanı erişimini yönetin. 

1. Yeni **Çalışma Alanı OneDrive** ayarına iki şekilde erişebilirsiniz:

    İlk kez oluşturduğunuzda **Çalışma alanı oluştur** bölmesinden.

    Gezinti bölmesinde, **Çalışma alanları**’nın yanındaki oku ve sonra çalışma alanı adı > **Çalışma alanı ayarları**’nın yanındaki **Diğer seçenekler** (...) düğmesini seçin. **Ayarlar** bölmesi açılır.

    ![Çalışma alanı ayarları](media/service-create-the-new-workspaces/power-bi-workspace-new-settings.png)

2. **Gelişmiş** > **Workspace OneDrive** altında, daha önce oluşturduğunuz Microsoft 365 grubunun adını yazın. URL’yi değil, yalnızca adı yazın. Power BI, grup için otomatik olarak OneDrive'ı seçer.

    ![OneDrive konumu belirtme](media/service-create-the-new-workspaces/power-bi-new-workspace-onedrive.png)

3. **Kaydet**'i seçin.

### <a name="access-the-workspace-onedrive-location"></a>Çalışma alanı OneDrive konumuna erişim

OneDrive konumunuzu yapılandırdıktan sonra, bunu tıpkı Power BI hizmetindeki diğer veri kaynaklarını aldığınız gibi alırsınız.

1. Gezinti bölmesinde **Veri Al**’ı seçip **Dosyalar** kutusunda **Al** seçeneğini belirleyin.

    ![Verileri ve dosyaları alma](media/service-create-the-new-workspaces/power-bi-get-data-files.png)

1.  **OneDrive – İş** girişi kendi OneDrive İş kopyanızdır. İkinci OneDrive, eklediğiniz kopyadır.

    ![Çalışma alanı dosyalarının konumu - veri alma](media/service-create-the-new-workspaces/power-bi-new-workspace-get-data-onedrive.png)

### <a name="connect-to-apps-in-new-workspaces"></a>Yeni çalışma alanlarındaki uygulamalara bağlanma

Yeni çalışma alanı deneyimlerinde içerik paketleri yerine *uygulamalar* oluşturulup kullanılır. Uygulamalar, üçüncü taraf hizmetlere ve kurumsal verilere bağlanan pano, rapor ve veri kümesi koleksiyonlarıdır. Uygulamalar, Microsoft Dynamics CRM, Salesforce ve Google Analytics gibi hizmetlerden veri almayı kolaylaştırır.

Yeni çalışma alanı deneyimiyle, kurumsal içerik paketleri oluşturamaz veya kullanamazsınız. İç ekiplerinizin, kullanmakta olduğunuz içerik paketlerine yönelik uygulamalar sağlamasını isteyin. 

## <a name="give-access-to-your-workspace"></a>Çalışma alanınıza erişim izni verme

Bir çalışma alanında yönetici rolüne sahip herkes başkalarına çalışma alanı erişimi verebilir.

1. Yönetici olduğunuzdan, çalışma alanı içerik listesi sayfasında **Erişim**’i görürsünüz.

    ![Çalışma alanları içerik listesi](media/service-create-the-new-workspaces/power-bi-workspace-access-icon.png)

1. Bu çalışma alanlarına güvenlik gruplarını, dağıtım listelerini, Microsoft 365 gruplarını veya kişileri yönetici, üye, katkıda bulunan ya da görüntüleyici olarak ekleyin. Farklı rollerin açıklamaları için [Yeni çalışma alanlarındaki roller](service-new-workspaces.md#roles-in-the-new-workspaces) bölümüne bakın.

    ![Çalışma alanlarına üye, yönetici, katkıda bulunan ekleme](media/service-create-the-new-workspaces/power-bi-workspace-add-members.png)

9. **Ekle** > **Kapat**'ı seçin.


## <a name="distribute-an-app"></a>Uygulamayı dağıtma

Kuruluşunuzda büyük bir hedef kitleye resmi içerik dağıtmak istiyorsanız, çalışma alanınızdan bir *uygulama* yayımlayabilirsiniz.  İçerik hazır olduğunda, yayımlamak istediğiniz panoları ve raporları seçip bunu bir uygulama olarak yayımlarsınız. Her çalışma alanından bir uygulama oluşturabilirsiniz.

[Yeni çalışma alanlarından uygulama yayımlama](service-create-distribute-apps.md) hakkında bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da yeni çalışma alanlarında çalışmayı düzenleme deneyimi](service-new-workspaces.md) makalesini okuyun
* [Klasik çalışma alanları oluşturma](service-create-workspaces.md)
* [Power BI’da yeni çalışma alanlarından uygulama yayımlama](service-create-distribute-apps.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
