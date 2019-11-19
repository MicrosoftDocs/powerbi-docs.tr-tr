---
title: Power BI şablon uygulaması güncelleştirme, silme ve ayıklama
description: Şablon uygulamasını güncelleştirme, silme ve ayıklama.
author: teddybercovitz
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/23/2019
ms.author: tebercov
ms.openlocfilehash: a15a27255f15bdce39ddb14a6cda798d170ba3ad
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73871375"
---
# <a name="update-delete-and-extract-template-app"></a>Şablon uygulamasını güncelleştirme, silme ve ayıklama

Uygulamanız artık üretim ortamında olduğundan, üretimdeki uygulamaya müdahale etmeden test aşamasının üzerinden geçebilirsiniz.
## <a name="update-your-app"></a>Uygulamanızı güncelleştirme

Power BI Desktop’ta değişiklikler yaptıysanız (1). adımdan başlayın. Power BI Desktop’ta değişiklikler yapmadıysanız (4). adımdan başlayın.

1. Güncelleştirilmiş veri kümesini karşıya yükleyin ve mevcut veri kümesinin üzerine yazın. **Tam olarak aynı veri kümesi adını kullandığınızdan emin olun**. Farklı bir ad kullanmak, uygulamayı güncelleştiren kullanıcılar için yeni bir veri kümesi oluşturur.
![veri kümesinin üzerine yazma](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset.png)
1. Pbix dosyasını bilgisayarınızdan içeri aktarın.
![veri kümesinin üzerine yazma](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset2.png)
1. Üzerine yazmayı onaylayın.
![veri kümesinin üzerine yazma](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset3.png)

1. **Sürüm yönetimi** bölmesinde **Uygulama oluştur**’u seçin.
1. Uygulama oluşturma sürecine en baştan yeniden başlayın.
1. **Markalama**, **İçerik**, **Denetim** ve **Erişim**’i ayarladıktan sonra tekrar **Uygulama oluştur**’u seçin.
1. **Kapat**’ı seçin ve **Sürüm yönetimi**’ne dönün.

   Şimdi iki sürümünüz olduğunu görürsünüz: üretimdeki sürüm ve test aşamasındaki yeni sürüm.

    ![Şablon uygulamasının iki sürümü](media/service-template-apps-update-extract-delete/power-bi-template-app-update.png)

5. Uygulamanızı kiracınızın dışında test etmek amacıyla üretim öncesi aşamaya yükseltmek için, Sürüm Yönetimi bölmesine dönün ve **Test**’in yanındaki **Uygulamayı yükselt**’i seçin.
6. Bağlantınız artık canlıdır. [Power BI Uygulama teklifi güncelleştirmesi](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-update-existing-offer) altındaki adımları izleyerek bağlantıyı yeniden Bulut İş Ortağı Portalı'na (CPP) gönderin.
7. Bulut İş Ortağı Portalı’nda teklifinizi tekrar **yayımlamanız** ve yeniden doğrulamanız gerekir.

   >[!NOTE]
   >Uygulamanızı üretim aşamasına yükseltmek için uygulamanın Bulut İş Ortağı Portalı tarafından onaylanmasını ve uygulamayı yayımlamayı bekleyin.

### <a name="update-behavior"></a>Güncelleştirme davranışı

1. Uygulamanın güncelleştirilmesi, şablon uygulaması yükleyicisinin bağlantı yapılandırmasını kaybetmeden zaten yüklü olan çalışma alanında [Şablon uygulamasını güncelleştirmesine](service-template-apps-install-distribute.md#update-a-template-app) olanak tanır.
1. Veri kümesindeki değişikliklerin yüklü şablon uygulamasını nasıl etkilediğini öğrenmek için yükleyicinin [üzerine yazma davranışına](service-template-apps-install-distribute.md#overwrite-behavior) bakın.
1. Bir şablon uygulaması güncelleştirilirken (üzerine yazılırken) ilk olarak örnek verilere geri döner ve kullanıcı yapılandırmasıyla (parametreler ve kimlik doğrulaması) otomatik olarak yeniden bağlanır. Yenileme tamamlanana kadar raporlar, panolar ve kuruluş uygulaması, örnek veri başlığını sunar.
1. Kullanıcı girişi gerektiren güncelleştirilmiş veri kümesine yeni bir sorgu parametresi eklediyseniz, *gerekli* onay kutusunu işaretlemeniz gerekir. Bu işlem, uygulamayı güncelleştirdikten sonra yükleyiciye bağlantı dizesini sorar.
 ![gerekli parametreler](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset4.png)

## <a name="extract-workspace"></a>Çalışma alanını ayıklama
Ayıklama özelliği sayesinde artık bir şablon uygulamasını önceki sürümüne geri almak hiç olmadığı kadar kolaylaştı. Aşağıdaki adımlar, çeşitli yayın aşamalarındaki belirli bir uygulama sürümünü yeni çalışma alanına ayıklayacaktır:

1. Yayın yönetimi bölmesinde diğer simgesine **(...)** ve ardından **Ayıkla**’ya basın.

    ![şablon uygulaması sürümünü ayıklama](media/service-template-apps-update-extract-delete/power-bi-template-app-extract.png) ![şablon uygulaması sürümünü ayıklama](media/service-template-apps-update-extract-delete/power-bi-template-app-extract-dialog.png)
2. İletişim kutusunda, ayıklanan çalışma alanının adını girin. yeni bir çalışma alanı eklenir.

Yeni çalışma alanı sürümünüz sıfırlanır ve şablon uygulamasını yeni ayıklanan çalışma alanından geliştirmeye ve dağıtmaya devam edebilirsiniz.

## <a name="delete-template-app-version"></a>Şablon uygulaması sürümünü silme
Şablon çalışma alanı, etkin bir dağıtılmış şablon uygulamasının kaynağıdır. Şablon uygulaması kullanıcılarını korumak için, bir çalışma alanını, çalışma alanında oluşturulan tüm uygulama sürümlerini kaldırmadan silmek mümkün değildir.
Bir uygulama sürümü silindiğinde, artık çalışmayan uygulama url’si de silinir.

1. Yayın yönetimi bölmesinde üç noktaya **(...)** ve ardından **Sil**’e basın.
 ![Şablon uygulaması sürümünü silme](media/service-template-apps-update-extract-delete/power-bi-template-app-delete.png)
 ![Şablon uygulaması sürümünü silme](media/service-template-apps-update-extract-delete/power-bi-template-app-delete-dialog.png)

>[!NOTE]
>Müşteriler veya **AppSource** tarafından kullanılan uygulama sürümünü silmemeye özen gösterin. Aksi takdirde uygulama çalışmayacaktır.

## <a name="next-steps"></a>Sonraki adımlar

Müşterilerinizin şablon uygulamanızla nasıl etkileşim kurduğunu görmek için bkz. [Kuruluşunuzda şablon uygulamalarını yükleme, özelleştirme ve dağıtma](service-template-apps-install-distribute.md).

Uygulamanızı dağıtma işleminin ayrıntıları için bkz. [Power BI Uygulama teklifi](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).
