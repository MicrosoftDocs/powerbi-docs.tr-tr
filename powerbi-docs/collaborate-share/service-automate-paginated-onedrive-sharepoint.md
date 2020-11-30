---
title: Sayfalandırılmış raporları OneDrive İş'e veya SharePoint Online'a kaydetme
description: Bu makalede Power Automate'i kullanarak Power BI sayfalandırılmış raporlarını OneDrive İş'e veya SharePoint Online klasörüne kaydetme sürecini otomatikleştireceksiniz.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 11/17/2020
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 67f49d19e3488b80a980719220fcc4715a6952e7
ms.sourcegitcommit: b2693047fce6a4e0c3ea07013404e99fc9cc1901
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2020
ms.locfileid: "94905346"
---
# <a name="save-a-paginated-report-to-onedrive-for-business-or-sharepoint-online"></a>Sayfalandırılmış raporları OneDrive İş'e veya SharePoint Online'a kaydetme

[Power Automate](/power-automate/getting-started) ile Power BI sayfalandırılmış raporlarını birçok farklı biçim ve senaryo kapsamında dışarı aktarma ve dağıtma işlemlerini otomatikleştirebilirsiniz. Bu makalede Power Automate'i kullanarak Power BI sayfalandırılmış raporlarını OneDrive İş'e veya SharePoint Online klasörüne kaydetme sürecini otomatikleştireceksiniz.

:::image type="content" source="media/service-automate-paginated-onedrive-sharepoint/paginated-onedrive-flow.png" alt-text="Sayfalandırılmış raporu OneDrive'a veya SharePoint Online'a kaydetmeye yönelik Power Automate akışının ekran görüntüsü":::

Power BI sayfalandırılmış raporlarına yönelik farklı Power Automate şablonları mı arıyorsunuz? Bkz. [Power Automate ile Power BI sayfalandırılmış raporlarını dışarı aktarma](service-automate-paginated-integration.md). 

## <a name="prerequisites"></a>Önkoşullar  

Buradaki adımları takip etmek için aşağıdakilere sahip olduğunuzdan emin olun:

- Power BI kiracınızda ayrılmış kapasiteye sahip olan en az bir çalışma alanı. Bu kapasite A4/P1 - A6/P3 arası SKU'lardan herhangi biri olabilir. [Power BI Premium'daki ayrılmış kapasiteler](../admin/service-premium-what-is.md) hakkında daha fazla bilgi edinin.
- Power Automate'teki standart bağlayıcılara erişim (tüm Office 365 abonelikleriyle sunulur).

## <a name="save-a-paginated-report-to-onedrive-for-business-or-a-sharepoint-online-folder"></a>Sayfalandırılmış raporları OneDrive İş'e veya SharePoint Online klasörüne kaydetme 

Bu şablonlardan birini kullanarak sayfalandırılmış raporların istenen biçimde OneDrive İş'e veya SharePoint Online klasörüne yinelenen bir şekilde dışarı aktarılması için gerekli ayarları yapabilirsiniz. Power Automate akışında Sayfalandırılmış Raporlar için Dosyaya Aktarma eylemini ilk kez kullanıyorsanız önkoşullara bakın. 

> [!NOTE]
> Aşağıdaki adımlarda ve görüntülerde **Power BI sayfalandırılmış raporunu OneDrive İş'e kaydetme** şablonunu kullanarak akışı ayarlama süreci gösterilmiştir. Aynı adımları kullanarak **Power BI sayfalandırılmış raporunu SharePoint Online klasörüne kaydetme** şablonuyla da bir akış oluşturabilirsiniz. Sayfalandırılmış raporunuzu dışarı aktarmak istediğiniz yeri seçerken OneDrive İş klasörü yerine SharePoint Online klasörü seçin. 

1. [flow.microsoft.com](https://flow.microsoft.com/) adresinden Power Automate'te oturum açın. 
1. **Şablonlar**'ı seçip  **sayfalandırılmış raporlar** araması yapın. 

    :::image type="content" source="media/service-automate-paginated-integration/power-bi-paginate-automate.png" alt-text="Power BI sayfalandırılmış raporlarına yönelik Power Automate şablonlarının ekran görüntüsü.":::

1. **Power BI sayfalandırılmış raporunu OneDrive İş'e kaydetme** veya **Power BI sayfalandırılmış raporunu SharePoint Online klasörüne kaydetme**'yi seçin. Power BI ve OneDrive İş veya SharePoint Online oturumu açtığınızdan emin olun.

    :::image type="content" source="media/service-automate-paginated-onedrive-sharepoint/onedrive-template-step1.png" alt-text="Power BI ve OneDrive İş şablonunu seçme adımının ekran görüntüsü.":::
1. **Devam**’ı seçin.  


1. Akışınızın **Yinelenme** değerini ayarlamak için **Sıklık** alanından bir seçenek belirleyip istediğiniz **Aralık** değerini girin.

    :::image type="content" source="media/service-automate-paginated-onedrive-sharepoint/onedrive-template-2-recurrence.png" alt-text="Akışın Yinelenme değerini seçme.":::

1. (İsteğe bağlı) **Gelişmiş seçenekleri göster**'i seçerek ek **Yinelenme** parametrelerini ayarlayabilirsiniz. Bunların arasında **Saat dilimi**, **Başlangıç saati**, **Şu günlerde**, **Şu saatlerde** ve **Şu dakikalarda** parametreleri bulunur.  

    :::image type="content" source="media/service-automate-paginated-onedrive-sharepoint/onedrive-template-3-advanced-recurrence.png" alt-text="Yinelenme için gelişmiş seçenekler gösteriliyor.":::

1. **Çalışma alanı** kutusunda ayrılmış kapasitede bulunan bir çalışma alanını seçin. **Rapor** kutusunda seçtiğiniz çalışma alanında bulunan ve dışarı aktarmak istediğiniz sayfalandırılmış raporu seçin. **Dışarı Aktarma Biçimi** kutusunda istediğiniz dışarı aktarma biçimini seçin. İsteğe bağlı olarak sayfalandırılmış rapora yönelik parametreler belirtebilirsiniz. Parametrelerle ilgili ayrıntılı açıklamalar için bkz. [Power BI Rest API için bağlayıcı başvurusu](/connectors/powerbi/#export-to-file-for-paginated-reports).  

    :::image type="content" source="media/service-automate-paginated-onedrive-sharepoint/onedrive-template-4-export-format.png" alt-text="Sayfalandırılmış raporu, çalışma alanını ve dışarı aktarma biçimini seçme.":::

1. **Klasör Yolu** bölümünde sayfalandırılmış raporunuzu dışarı aktarmak istediğiniz OneDrive İş veya SharePoint Online klasörünü seçin.

    :::image type="content" source="media/service-automate-paginated-onedrive-sharepoint/onedrive-template-5-create-file.png" alt-text="Hedefi seçme ve dosyayı oluşturma.":::

1. Power Automate, **Dosya Adı** ve **Dosya İçeriği** alanlarını sizin için otomatik olarak oluşturur. Dosya adını değiştirebilirsiniz ancak dinamik olarak oluşturulan **Dosya İçeriği** değerini bırakın. 

1. İşlemleri tamamladığınızda  **Sonraki adım** veya **Kaydet**'i seçin. Power Automate akışı oluşturup değerlendirir ve varsa hataları bildirir. 

1. Hatalar varsa **Akışı düzenle** ile düzeltin. Yoksa **Geri** okunu seçerek akış ayrıntılarını görüntüleyin ve yeni akışı çalıştırın. 

    Akışı çalıştırdığınızda Power Automate, sayfalandırılmış raporu istediğiniz biçimde OneDrive İş veya SharePoint Online klasörüne dışarı aktarır.  

## <a name="next-steps"></a>Sonraki adımlar

- [Power Automate ile Power BI sayfalandırılmış raporlarını dışarı aktarma](service-automate-paginated-integration.md)
- [Power Automate kullanmaya başlama](/power-automate/getting-started/)
- Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
