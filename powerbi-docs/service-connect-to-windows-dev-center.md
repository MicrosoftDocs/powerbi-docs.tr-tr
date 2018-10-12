---
title: Power BI ile Windows Dev Center'a bağlanma
description: Power BI için Windows Dev Center
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: ccb878da983aad493efb2cfdfb0d09366964a157
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46545441"
---
# <a name="connect-to-windows-dev-center-with-power-bi"></a>Power BI ile Windows Dev Center'a bağlanma
Power BI içerik paketi ile Power BI'daki Windows Dev Center uygulama analizi verilerini araştırın ve izleyin. Veriler, günde bir kez otomatik olarak yenilenir.

Power BI için [Windows Dev Center içerik paketine](https://app.powerbi.com/getdata/services/devcenter) bağlanın.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmında bulunan **Veri Al**'ı seçin.
   
   ![](media/service-connect-to-windows-dev-center/getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
   ![](media/service-connect-to-windows-dev-center/services.png)
3. **Windows Dev Center** \>  **Al**'ı seçin.
   
   ![](media/service-connect-to-windows-dev-center/windowsdev.png)
4. Sahip olduğunuz uygulama kimliğini girin ve Sonraki seçeneğine tıklayın. [Bu parametreleri bulma](#FindingParams) konusundaki ayrıntılı bilgileri aşağıda bulabilirsiniz.
   
   ![](media/service-connect-to-windows-dev-center/params.png)
5. **Kimlik doğrulama yöntemi** için **OAuth2** \> **Oturum aç** seçeneklerini belirleyin. İstendiğinde, Windows Geliştirme Merkezi hesabınızla ilişkili Azure Active Directory kimlik bilgilerinizi girin ([Sistem Gereksinimleri](#Requirements) bölümünde daha fazla ayrıntıya ulaşabilirsiniz).
   
    ![](media/service-connect-to-windows-dev-center/creds.png)
   
    ![](media/service-connect-to-windows-dev-center/creds2.png)
6. Onayladıktan sonra içeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında Gezinti Bölmesinde yeni bir pano, rapor ve model görünür. İçeri aktarılan verilerinizi görüntülemek için panoyu seçin ve bir kutucuk seçerek bağlantılı raporlara gidin.
   
    ![](media/service-connect-to-windows-dev-center/dashboard.png)
   
    ![](media/service-connect-to-windows-dev-center/report.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](consumer/end-user-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](consumer/end-user-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz.

## <a name="whats-included"></a>Neleri kapsar?
Dev Center Power BI içerik paketi, uygulamanızın yanı sıra IAP edinimlerine, derecelendirmelere, incelemelere ve uygulama durumuna yönelik analiz verileri içerir. Veriler son 3 ayla sınırlıdır. Bu değişken bir aralık olduğundan, dahil edilen tarihler veri kümesi yenilendikçe güncelleştirilir.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Sistem gereksinimleri
Bu içerik paketi, Microsoft Store'da yayımlanmış en az bir uygulama ve Windows Geliştirme Merkezi Hesabı gerektirir ([burada](https://msdn.microsoft.com/windows/uwp/publish/manage-account-users) daha fazla ayrıntıya ulaşabilirsiniz).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Bir uygulamaya ilişkin uygulama kimliğini, App identity (Uygulama kimliği) sayfasındaki App management (Uygulama yönetimi) bölümünde bulabilirsiniz.

Uygulama kimliği, Windows 10 Mağazası'na yönelik URL'nizin sonunda yer alır, https://www.microsoft.com/store/apps/ **{applicationId}**

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

