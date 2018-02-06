---
title: "Power BI Desktop'ta OneDrive İş bağlantılarını kullanma"
description: "Power BI Desktop'ta OneDrive İş bağlantılarını kullanma"
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
ms.date: 12/05/2017
ms.author: davidi
ms.openlocfilehash: 2c249cac17e8fe6da35634c78837e3ca16e70a5c
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2017
---
# <a name="use-onedrive-for-business-links-in-power-bi-desktop"></a>Power BI Desktop'ta OneDrive İş bağlantılarını kullanma
Pek çok kullanıcının OneDrive İş sürücüsünde Excel çalışma kitapları bulunur, bunlar Power BI Desktop'ta kullanmak için harika bir seçimdir. **Power BI Desktop** ile rapor ve görsel oluşturmak için **OneDrive İş**'te kayıtlı **Excel** dosyalarına ilişkin çevrimiçi bağlantıları kullanabilirsiniz. Bir **OneDrive İş** grup hesabını veya bireysel **OneDrive İş** hesabınızı kullanabilirsiniz.

**OneDrive İş**'ten çevrimiçi bir bağlantı almak için uygulamanız gereken birkaç adım bulunur. Aşağıdaki bölümlerde gruplar arasında, farklı makineler arasında ve iş arkadaşlarınızla dosya bağlantısı paylaşmanıza olanak sağlayan bu adımlar açıklanmaktadır.

## <a name="get-a-link-from-excel-starting-in-the-browser"></a>Tarayıcıyı başlatıp Excel'den bağlantı alma
1. Tarayıcıyı kullanarak OneDrive iş konumunuza gidin. Kullanmak istediğiniz dosyaya sağ tıklayıp **Excel'de Aç**'ı seçin.
   
   > [!NOTE]
> Tarayıcı arabiriminiz tamamen aşağıdaki gibi görünmeyebilir. **OneDrive İş** tarayıcı arabiriminizdeki dosyalar için **Excel'de Aç**'ı seçmenin pek çok yolu vardır. Dosyayı Excel'de açmanıza olanak sağlayan tüm seçenekleri kullanabilirsiniz.
   > 
   > 
   
   ![](media/desktop-use-onedrive-business-links/odb-links_02.png)
2. **Excel**'de **Dosya > Bilgi** öğesini ve **Çalışma Kitabını Koru** düğmesinin üzerindeki bağlantıyı seçin. **Bağlantıyı panoya kopyala**'yı seçin. (Kullandığınız sürümde bunun yerine **Yolu panoya kopyala** seçeneğini görebilirsiniz).
   
   ![](media/desktop-use-onedrive-business-links/odb-links_03.png)

## <a name="use-the-link-in-power-bi-desktop"></a>Power BI Desktop'ta bağlantıyı kullanma
Power BI Desktop'ta, panoya kopyaladığınız bağlantıyı kullanabilirsiniz. Aşağıdaki adımları uygulayın:

1. Power BI Desktop'ta **Veri Al > Web** öğesini seçin.
   
   ![](media/desktop-use-onedrive-business-links/odb-links_04.png)
2. Bağlantıyı **Web'den** adlı iletişim kutusuna yapıştırın. (Henüz Tamam'ı **seçmeyin**.)
   
    ![](media/desktop-use-onedrive-business-links/odb-links_05.png)
3. Bağlantının sonunda *?web=1* dizesine dikkat edin - *Web URL dizesinin bu kısmını kaldırmanız gerekir* **önce** seçme **Tamam**, **Power BI Desktop** 'un dosyanıza doğru şekilde gidebilmesi için.
4. **Power BI Desktop** kimlik bilgilerini girmenizi isterse **Windows** (şirket içi SharePoint siteleri için) ya da **Kuruluş Hesabı** (Office 365 veya OneDrive İş siteleri için) seçeneğini belirleyin.
   
   ![](media/desktop-use-onedrive-business-links/odb-links_06.png)

Excel çalışma kitabında bulunan tablolardan, sayfalardan ve aralıklardan oluşan listeden seçim yapmanıza olanak sağlayan **Gezgin** penceresi görüntülenir. Buradan, OneDrive İş dosyasını diğer tüm Excel dosyaları gibi kullanarak rapor oluşturabilir ve diğer tüm veri kaynaklarında olduğu gibi veri kümelerinde kullanabilirsiniz.

> [!NOTE]
> **OneDrive İş** dosyasını, söz konusu dosya için **Hizmeti Yenileme** özelliği etkinleştirilmiş şekilde Power BI hizmetinde bir veri kaynağı olarak kullanmak için, yenileme ayarlarınızı yapılandırırken **Kimlik doğrulama yöntemi** olarak **OAuth2** seçeneğini belirlediğinizden emin olun. Aksi halde, bağlanma veya yenileme işlemi gerçekleştirmeye çalıştığınızda bir hata (ör. *Veri kaynağı kimlik bilgileri güncelleştirilemedi*) ile karşılaşabilirsiniz. Kimlik doğrulama yöntemi olarak **OAuth2** seçeneği belirlenerek bu kimlik bilgileri hatası önlenebilir.
> 
> 

