---
title: Pano veri sınıflandırması
description: Pano veri sınıflandırması ile ilgili bilgi (sınıflandırmanın Yöneticiler tarafından nasıl ayarlanması gerektiği ve pano sahipleri tarafından nasıl değiştirilebileceği de dahil olmak üzere) edinin.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 08/10/2017
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: d8c7a8532122487bdf3bcd718eb4089cb7c67008
ms.sourcegitcommit: e8ed3d120699911b0f2e508dc20bd6a9b5f00580
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2020
ms.locfileid: "86262807"
---
# <a name="dashboard-data-classification"></a>Pano veri sınıflandırması
Her pano farklıdır. Bağlandığınız veri kaynağına bağlı olarak, sizin ve panoyu paylaştığınız iş arkadaşlarınızın, verilerin gizlilik durumuna göre farklı önlemler alması gerekebilir. Bazı panoların hiçbir zaman şirket dışındaki kişilerle paylaşılmaması veya yazdırılmaması gerekir, bazılarının paylaşılmasında ise bir sakınca yoktur. Pano veri sınıflandırmasını kullanarak, panolarınızı görüntüleyen kişilerin, hangi güvenlik düzeyinin kullanılması gerektiğine dair farkındalığını artırabilirsiniz. Panolarınızı şirketinizin BT departmanı tarafından tanımlanan sınıflandırmalar ile etiketleyebilir ve içeriği görüntüleyen herkesin, verilerin gizliliği konusunda ortak bir bilince sahip olmasını sağlayabilirsiniz.

![Bir örnekteki veri sınıflandırmasını gösteren panonun ekran görüntüsü.](media/service-data-classification/dashboard_tagged_as_hbi.png)

## <a name="data-classification-tags"></a>Veri sınıflandırma etiketleri
Pano adının yanında görünen veri sınıflandırma etiketleri, panoyu görüntüleyen kişilerin, pano ve içerdiği veriler için uygulanması gereken güvenlik düzeyinin bilincinde olmasına olanak sağlar.

![Pano adının yanında bir veri sınıflandırması etiketi gösteren panonun ekran görüntüsü.](media/service-data-classification/tag_next_to_title.png)

Ayrıca söz konusu etiketler, Sık Kullanılanlar listenizdeki pano kutucuğunun yanında da görünür.

![Sık Kullanılanlar listenizdeki pano kutucuğunun yanında bir veri sınıflandırması etiketi gösteren Sık Kullanılanlar listesinin ekran görüntüsü.](media/service-data-classification/tag_on_dashboard_tile.png)

Etiketin üzerine geldiğinizde sınıflandırmanın tam adını görürsünüz.

![Etiketin üzerine geldiğinizde sınıflandırmanın tam adını gösteren HBI etiketinin ekran görüntüsü. ](media/service-data-classification/tag_tooltip.png)

Yöneticiler, ek bilgi sağlamak amacıyla etiket için bir URL de ayarlayabilir.

> [!NOTE]
> Yöneticiniz tarafından belirlenen sınıflandırma ayarlarına bağlı olarak bazı sınıflandırma türleri, panoda bir etiket olarak gösterilmeyebilir. Bir pano sahibiyseniz pano sınıflandırma türünüzü pano ayarlarından denetleyebilirsiniz.
> 
> 

## <a name="setting-a-dashboards-classification"></a>Pano sınıflandırmasını ayarlama
Şirketiniz için veri sınıflandırma etkinleştirilmişse başlangıçta tüm panolar varsayılan bir sınıflandırma türüne sahip olur ancak pano sahibi olarak sınıflandırmayı, panolarınızın güvenlik düzeyi ile eşleşecek şekilde değiştirebilirsiniz.

Sınıflandırma türünü değiştirmek için aşağıdaki adımları uygulayın:

1. Pano adının yanındaki **üç nokta** simgesini seçip **Ayarlar** seçeneğini belirleyerek pano ayarlarına gidin.
   
    ![Ayarlar seçimini gösteren panonun ekran görüntüsü.](media/service-data-classification/dashboard_settings.png)
2. Pano ayarları bölümünde panonuzun geçerli sınıflandırmasını görebilir ve açılan listeyi kullanarak sınıflandırma türünü değiştirebilirsiniz.
   
    ![Geçerli bir sınıflandırmayı ve Veri sınıflandırması açılır menü seçimini gösteren pano ayarlarının ekran görüntüsü.](media/service-data-classification/classification_setting_dropdown.png)
3. Değiştirme işlemini tamamladıktan sonra **Uygula** düğmesini seçin.

Değişiklik uygulandıktan sonra, panoyu paylaştığınız kişiler panoyu yeniden yüklediğinde güncelleştirmeyi görür.

## <a name="working-with-data-classification-tags-as-an-admin"></a>Yönetici olarak sınıflandırma etiketleri ile çalışma
Veri sınıflandırma, kuruluşunuzun genel yöneticisi tarafından ayarlanır. Veri sınıflandırmayı etkinleştirmek için aşağıdaki adımları uygulayın:

1. Ayarlar dişli simgesini ve ardından **Yönetici portalı**'nı seçin.
   
    ![Yönetim Portalı seçimini gösteren Ayarlar dişlisinin ekran görüntüsü.](media/service-data-classification/admin_portal_in_settings.png)
2. **Kiracı ayarları** sekmesindeki **Panolar ve raporlar için veri sınıflandırma** ayarını *Açık* olarak değiştirin.
   
    ![Kiracı ayarlarını ve hem panolar hem de raporlar için Veri sınıflandırması seçimini gösteren Yönetim Portalının ekran görüntüsü.](media/service-data-classification/data_classification_switch_location.png)

Sınıflandırma etkinleştirildikten sonra, kuruluşunuz için çeşitli sınıflandırmalar oluşturabileceğiniz bir form açılır.

![Kuruluşunuzdaki çeşitli sınıflandırmalara yönelik alan girişlerini gösteren formun ekran görüntüsü.](media/service-data-classification/blank_classification_form.png)

Her sınıflandırmanın panoda görünecek bir **adı** ve **kısaltması** vardır. **Etiketi göster**'i seçerek her sınıflandırma için kısaltma etiketinin panoda görünüp görünmeyeceğini belirleyebilirsiniz. Sınıflandırma türünün panoda gösterilmemesini tercih etmeniz durumunda pano sahibi yine de pano ayarlarını denetleyerek sınıflandırma türünü görebilir. Ayrıca dilerseniz kuruluşunuzun sınıflandırma yönergeleri ve kullanım gereksinimleri ile ilgili daha fazla bilgi içeren bir **URL** de ekleyebilirsiniz.  

Son olarak, varsayılan sınıflandırma türünün hangisi olacağına karar vermeniz gerekir.  

Forma sınıflandırma türlerini girdikten sonra değişiklikleri kaydetmek için **Uygula** düğmesini seçin.

![Uygulanacak sınıflandırma türleriyle doldurulmuş girişleri gösteren formun ekran görüntüsü.](media/service-data-classification/filled_in_classification_form.png)

Bu noktada, tüm panolara varsayılan sınıflandırma atanır. Pano sahipleri artık sınıflandırma türünü içerikleri için uygun olan tür ile güncelleştirebilir. Daha sonra buraya geri dönerek sınıflandırma türü ekleyip kaldırabilir veya varsayılan sınıflandırma türünü değiştirebilirsiniz.  

> [!NOTE]
> Değişiklik yapmak için geri döndüğünüzde hatırlamanız gereken birkaç önemli nokta vardır:
> 
> * Veri sınıflandırmayı devre dışı bırakırsanız etiketlerin hiçbiri anımsanmaz. Daha sonra yeniden etkinleştirmeye karar verirseniz baştan başlamanız gerekir.  
> * Bir sınıflandırma türünü kaldırırsanız, söz konusu sınıflandırma türünün atandığı tüm panolara varsayılan sınıflandırma türü tekrar atanır ve pano sahibi yeni bir tür atayana kadar bu tür geçerli olur.  
> * Varsayılan türü değiştirirseniz pano sahibi tarafından bir sınıflandırma türü atanmamış olan tüm panolara yeni varsayılan tür atanır.
> 
> 

