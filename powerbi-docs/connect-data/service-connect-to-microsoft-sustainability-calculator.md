---
title: Microsoft Sürdürülebilirlik Hesaplayıcısı'na bağlanma
description: Power BI için Microsoft Sürdürülebilirlik Hesaplayıcısı
author: joshthor3222
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 01/06/2020
ms.author: v-tikid
LocalizationGroup: Connect to services
ms.openlocfilehash: cffb7ecc195f5ce803ec2dfc81c794bac75c9448
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85230018"
---
# <a name="connect-the-microsoft-sustainability-calculator"></a>Microsoft Sürdürülebilirlik Hesaplayıcısı'na bağlanma
Sürdürülebilir konusunda daha etkili bilgi işlem kararları almak için BT altyapınızın karbon ayrıntılarına yönelik içgörüler elde edin

Microsoft Sürdürülebilirlik Hesaplayıcısı, Azure hizmetleriyle ilişkili karbon emisyonlarını verileri için yeni içgörüler sağlar. Kuruluşlarda sürdürülebilirliği sağlama ve bu konuda rapor verme alanında sorumlu olan çalışanlar artık her bir Azure aboneliğinin karbon etkisini belirleyebilir ve iş yüklerini Azure'da çalıştırmanın şirket içi veri merkezlerine kıyasla tahmini olarak ne kadar karbon tasarrufu sağlayabileceğini görebilir. Bu veriler, kapsam 3 emisyonlarının sera gazı raporları için kullanılabilir. Microsoft Sürdürülebilirlik Hesaplayıcısı'na erişmek için kiracı kimliğinizi ve erişim anahtarınızı kullanmanız gerekir. Bu bilgileri kuruluşunuzun Azure yöneticisinden edinebilirsiniz.

Bu uygulamayı kullanmak için Azure Enterprise Portal'daki bilgilere ihtiyacınız olacaktır. Kuruluşunuzun sistem yöneticileri bu bilgileri elde etmenize yardımcı olabilir. Lütfen uygulamayı yüklemeden önce bu yönergeleri gözden geçirin ve gerekli bilgileri alın. 

Bu bağlayıcı sürümü yalnızca [https://ea.azure.com](https://ea.azure.com/) sayfasından gelen kurumsal kayıtları destekler. Çin'e ait kayıtlar şu anda desteklenmemektedir.

## <a name="how-to-connect"></a>Bağlanma
[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]

1. **Microsoft Sürdürülebilirlik Hesaplayıcısı** \> **Şimdi edinin**'i seçin.
1. **Bu Power BI uygulaması yüklensin mi?** iletişim kutusunda **Yükle**’yi seçin.
1. **Uygulamalar** bölmesinde **Microsoft Sürdürülebilirlik Hesaplayıcısı** kutucuğunu seçin.
1. **Yeni uygulamanızı kullanmaya başlayın** alanında **Bağlan** seçeneğini belirleyin.

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

1. **Şirket adı, Kullanıcı kayıt numarası** ve **Ay sayısı\> bilgilerini girip oturum açın.** [Bu parametreleri bulmaya](#finding-parameters) ilişkin ayrıntılı bilgi için aşağıya bakın.

    ![Şirket kaydı](media/service-connect-to-microsoft-sustainability-calculator/company-enrollment.png)

1. **Kimlik doğrulama yöntemi** için **Anahtar**, **Gizlilik düzeyi** için ise **Kurumsal**'ı seçin.
1. **Anahtar** alanına **Erişim anahtarınızı\> yazın ve oturum açın**.

    ![Erişim anahtarını girme](media/service-connect-to-microsoft-sustainability-calculator/access-key-entry.png)

1. İçeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında **Gezinti Bölmesinde** yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için raporu seçin.

## <a name="finding-parameters"></a>Parametreleri bulma

Şirketinize ait **Kayıt kimliği** ve **Erişim anahtarı** bilgilerine ulaşmak için Azure yöneticinizden destek alın. Yöneticiniz için yönergeler:

1. [Azure Enterprise Portal](https://ea.azure.com)'da oturum açıp sol taraftaki şeritten **Yönet**'e tıklayın ve aşağıda gösterildiği gibi **Kayıt Numarası** bilgisini alın
2. Aşağıda gösterildiği gibi [Azure Enterprise Portal](https://ea.azure.com)'da **Raporlar**'a ve ardından API Erişim Anahtarı'na tıklayarak Birincil Kayıt Hesap Anahtarı bilgisini alın

## <a name="using-the-app"></a>Uygulamayı kullanma

İstediğiniz zaman parametreleri değiştirmek için **Veri kümesi** ayarlarına gidip uygulama çalışma alanıyla ilişkili ayarlara erişebilir; kiracı kimliği, şirket adı veya verilerin dikkate alınacağı aylar gibi bilgileri değiştirebilirsiniz. Parametrelerinizi uyguladıktan sonra yeni parametrelere göre filtrelenmiş verileri yüklemek için **Yenile**'ye tıklayın.