---
title: Power BI Desktop'ta OneDrive İş bağlantılarını kullanma
description: Power BI Desktop'ta OneDrive İş bağlantılarını kullanma
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 706703985242284725fb4fc2d42bf46e54c605c7
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83285820"
---
# <a name="use-onedrive-for-business-links-in-power-bi-desktop"></a>Power BI Desktop'ta OneDrive İş bağlantılarını kullanma
Pek çok kullanıcının OneDrive İş'te depolanan Excel çalışma kitapları bulunur, bunlar Power BI Desktop'ta kullanmak için harika bir seçimdir. Power BI Desktop ile rapor ve görsel oluşturmak için OneDrive İş'te kayıtlı Excel dosyalarına ilişkin çevrimiçi bağlantıları kullanabilirsiniz. Bir OneDrive İş grup hesabını veya bireysel OneDrive İş hesabınızı kullanabilirsiniz.

OneDrive İş'ten çevrimiçi bir bağlantı almak için uygulamanız gereken belirli birkaç adım bulunur. Aşağıdaki bölümlerde gruplar arasında, farklı makineler arasında ve iş arkadaşlarınızla dosya bağlantısı paylaşmanıza olanak sağlayan bu adımlar açıklanmaktadır.

## <a name="get-a-link-from-excel"></a>Excel'den bağlantı alma
1. Tarayıcıyı kullanarak OneDrive iş konumunuza gidin. Kullanmak istediğiniz dosyaya sağ tıklayıp **Excel'de Aç**'ı seçin.
   
   > [!NOTE]
   > Tarayıcı arabiriminiz tamamen aşağıdaki gibi görünmeyebilir. OneDrive İş tarayıcı arabiriminizdeki dosyalar için **Excel'de Aç**'ı seçmenin pek çok yolu vardır. Dosyayı Excel'de açmanıza olanak sağlayan tüm seçenekleri kullanabilirsiniz.
   > 
   > 
   
   ![](media/desktop-use-onedrive-business-links/odb-links_02.png)
2. Excel'de **Dosya** > **Bilgi**'yi ve sonra da **Çalışma Kitabını Koru**'nun üst kısmında **Yolu kopyala**'yı seçin.
   
   ![](media/desktop-use-onedrive-business-links/onedrive-copy-path.png)

## <a name="use-the-link-in-power-bi-desktop"></a>Power BI Desktop'ta bağlantıyı kullanma
Power BI Desktop'ta, panoya kopyaladığınız bağlantıyı kullanabilirsiniz. Aşağıdaki adımları uygulayın:

1. Power BI Desktop’ta **Veri Al** > **Web**’i seçin.
   
   ![](media/desktop-use-onedrive-business-links/power-bi-web-link-onedrive.png)
2. **Temel** seçeneği seçili durumdayken, bağlantıyı **Web'den** iletişim kutusuna yapıştırın.
3. Bağlantının sonundaki *?web=1* dizesini kaldırarak Power BI Desktop'ın dosyanıza düzgün bir şekilde gidebilmesini sağlayın ve sonra da **Tamam**'ı seçin.
   
    ![](media/desktop-use-onedrive-business-links/power-bi-web-link-confirmation.png) 
4. Power BI Desktop kimlik bilgilerini girmenizi isterse **Windows** (şirket içi SharePoint siteleri için) ya da **Kuruluş Hesabı** (Office 365 veya OneDrive İş siteleri için) seçeneğini belirleyin.
   
   ![](media/desktop-use-onedrive-business-links/odb-links_06.png)

   Excel çalışma kitabında bulunan tablolardan, sayfalardan ve aralıklardan oluşan listeden seçim yapmanıza olanak sağlayan **Gezgin** iletişim kutusu görüntülenir. Burada, OneDrive İş dosyasını aynı diğer Excel dosyaları gibi kullanabilirsiniz. Raporlar oluşturabilir ve başka herhangi bir veri kaynağıyla yapabileceğiniz gibi bunu veri kümelerinde kullanabilirsiniz.

> [!NOTE]
> OneDrive İş dosyasını, söz konusu dosya için **Hizmeti Yenile** özelliği etkinleştirilmiş şekilde Power BI hizmetinde bir veri kaynağı olarak kullanmak için, yenileme ayarlarınızı yapılandırırken **Kimlik doğrulama yöntemi** olarak **OAuth2**'yi seçtiğinizden emin olun. Aksi takdirde, bağlanma veya yenileme işlemi gerçekleştirmeye çalıştığınızda bir hata (örneğin *Veri kaynağı kimlik bilgileri güncelleştirilemedi*) ile karşılaşabilirsiniz. Kimlik doğrulama yöntemi olarak **OAuth2** seçeneği belirlenerek bu kimlik bilgileri hatası önlenebilir.
> 
> 

