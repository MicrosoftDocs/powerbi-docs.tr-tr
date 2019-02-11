---
title: Raporları PDF dosyasına dışarı aktarma
description: Bir Power BI raporunu PDF’ye nasıl aktaracağınızı öğrenin.
author: mihart
manager: kvivek
ms.custom: ''
ms.reviewer: cmfinlan
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/04/2019
ms.author: mihart
LocalizationGroup: Share your work
ms.openlocfilehash: c18257f1f4e4e3f325c8d4d895e3b6abf88e900c
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55795014"
---
# <a name="export-reports-from-power-bi-to-pdf"></a>Raporları Power BI'dan PDF’ye aktarma
Power BI sayesinde raporunuzu PDF biçiminde yayımlayabilir ve kolayca Power BI raporunuzu temel alan bir belge oluşturabilirsiniz. **PDF'ye dışarı aktardığınızda** Power BI raporundaki her sayfa PDF belgesinde ayrı sayfalara dönüşür.

## <a name="how-to-export-your-power-bi-report-to-pdf"></a>Power BI raporunuzu PDF'ye aktarma
Power BI hizmetinde, tuval üzerinde görüntülenecek bir rapor seçin. Giriş sayfanızdan, Uygulamalar’dan veya sol gezinti bölmenizdeki başka bir bölümden bir rapor seçebilirsiniz.

1. Menü çubuğundan **Dosya** > **PDF’ye aktar**’ı seçin.

    ![Menü çubuğundan Dosya'yı seçme, PDF’ye Aktar'a işaret eden bir ok](media/end-user-pdf/power-bi-export-pdf.png)

    Sağ üst köşede bir ilerleme çubuğu görüntülenir. Dışarı aktarma işlemi birkaç dakika sürebilir ve rapor dışarı aktarılırken Power BI'da çalışmaya devam edebilirsiniz.

    ![Dışarı aktarma ilerleme durumu iletisi](media/end-user-pdf/power-bi-export-message.png)

    İşlem tamamlandıktan sonra bildirim başlığı, Power BI hizmetinin dışarı aktarma işlemini tamamladığını belirtecek şekilde değişir.

2. Dosyanız artık, tarayıcınızın indirilen dosyaları görüntülediği konumda kullanılabilir. Aşağıdaki görüntüde, tarayıcı pencerenizin alt kısmında bulunan bir indirme başlığı olarak gösterilmektedir.

    ![İndirilen dosyanın konumu](media/end-user-pdf/power-bi-save-file.png)

İşte bu kadar kolay. Dosyayı indirebilir ve Microsoft Edge'de sağlanan görüntüleyici gibi herhangi bir PDF görüntüleyicisiyle açabilirsiniz.


## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar
**PDF’ye Aktar** özelliğiyle çalışırken dikkat edilmesi gereken bazı önemli noktalar ve sınırlamalar vardır.

- Vurgulama ve filtreleme, detaya gitme gibi oturum içi etkileşim özellikleri, PDF’ye aktarma işleminde henüz desteklenmiyor. Dışarı aktarılan PDF, özgün görselleri raporda kaydedildiği şekilde gösterir. Filtreler ve dilimleyiciler uyguladıysanız ve bunların dışa aktarma işleminde korunmasını istiyorsanız raporu kaydedin ve dışa aktarma işlemini ondan sonra gerçekleştirin.

* **R görselleri** şu anda desteklenmemektedir. PDF’de bu görseller boş olacak ve bir hata raporu görüntüleyecektir.  

* **Sertifikalanmış** **özel görseller** desteklenir. Bir özel görseli nasıl sertifikalatacağınız dahil olmak üzere, sertifikalı özel görseller hakkında daha fazla bilgi için bkz. [getting a custom visual certified (Özel görselleri sertifikalatma)](../power-bi-custom-visuals-certified.md). Sertifikalanmamış özel görseller desteklenmez. PDF’de bunlar bir hata iletisiyle görüntülenir.   

* 30'dan fazla rapor sayfası içeren raporlar şu anda dışarı aktarılamaz.

* Raporu PDF’ye aktarma işlemi birkaç dakika sürebilir, bu nedenle sabırlı olun. Raporun yapısı ve Power BI hizmeti üzerindeki geçerli yük gibi etmenler gereken zamanı etkileyebilir.

* Power BI hizmetinde **PDF'ye aktar** menü öğesi kullanılamıyorsa bunun nedeni büyük olasılıkla kiracı yöneticisinin özelliği devre dışı bırakmış olmasıdır. Ayrıntılar için kiracı yöneticinizle iletişime geçin.

* Arka plan görüntüleri grafiğin sınırlayıcı alanına göre kırpılır. PDF’ye aktarmadan önce arka plan görüntülerini kaldırmanız kesinlikle önerilir.

* Power BI kiracı etki alanınızın dışındaki bir kullanıcıya ait raporlar (örneğin, kuruluşunuzun dışındaki birine ait olan ve sizinle paylaşılan raporlar) PDF’de yayımlanamaz.

* Panoyu kuruluşunuzun dışındaki biriyle (yani Power BI kiracınızda bulunmayan bir kullanıcıyla) paylaştığınızda bu kullanıcı, paylaşılan panonun ilişkili raporlarını PDF'ye aktaramaz. Örneğin, siz aaron@contoso.com iseniz cassie@cohowinery.com ile paylaşımda bulunabilirsiniz. Ancak, cassie@cohowinery.com ilişkili raporları PDF’ye aktaramaz.

* Power BI hizmeti, PDF dışa aktarma dili olarak Power BI dil ayarınızı kullanır. Dil tercihinizi görmek veya ayarlamak için dişli simgesini seçin ve **Ayarlar** > **Genel** > **Dil** seçeneğini belirtin.

## <a name="next-steps"></a>Sonraki adımlar
[Rapor yazdırma](end-user-print.md)