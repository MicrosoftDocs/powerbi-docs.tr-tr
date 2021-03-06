---
title: Veri kaynağı etki analizi
description: Veri kaynağınızın nerede kullanıldığını anlayın.
author: paulinbar
ms.author: painbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 07/20/2020
LocalizationGroup: ''
ms.openlocfilehash: 8c8a2a701415d9e937c5b592c915e51a4921840b
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96411897"
---
# <a name="data-source-impact-analysis"></a>Veri kaynağı etki analizi

Veri kaynağı etki analizi kuruluşunuz genelinde veri kaynaklarınızın nerede kullanıldığını görmenize yardımcı olur. Veri kaynağı geçici veya kalıcı olarak çevrimdışı bırakılırsa kimlerin etkilendiğini görmek isterseniz bu yararlı olabilir. Kaç çalışma alanı, veri akışı ve veri kümesinin veri kaynağını kullandığını gösterir ve etkilenen veri akışı ve veri kümelerinin bulunduğu çalışma alanlarına kolay erişim sağlar; böylece daha ayrıntılı olarak araştırabilirsiniz.

Veri kaynağı etki analizi kiracıdaki veri yinelemesini belirlemenize de yardımcı olur (örneğin farklı kullanıcılar aynı veri kaynağının üstüne benzer modeller kuruyorsa). Veri kaynağı etki analizi, bu yedekli veri kümelerini ve veri akışlarını bulmanıza yardımcı olarak “tek gerçeklik kaynağı” hedefini destekler.

## <a name="perform-data-source-impact-analysis"></a>Veri kaynağı etki analizi gerçekleştirme

Veri kaynağı etki analizi gerçekleştirmek için:

1. İlgilendiğiniz veri kaynağını içeren çalışma alanına gidin ve [köken görünümünü](service-data-lineage.md) açın.
1. Veri kaynağının kartını bulun ve etki analizi simgesine tıklayın.

    ![Veri kaynağı kartının etki analizi düğmesini gösteren ekran görüntüsü.](media/service-data-source-impact-analysis/data-source-impact-analysis-button.png)
 
Etki analizi yan paneli açılır.

![Veri kaynağı etki analizi yan bölmesinin ekran görüntüsü.](media/service-data-source-impact-analysis/data-source-impact-analyis-side-pane.png)
 
* **Veri kaynağı türü**: Veri kaynağı türünü gösterir
* **Veri kaynağı yolu**: Power BI Desktop’ta tanımlanan veri kaynağı yolu. Örneğin yukarıdaki resimde SQL sunucusu veritabanı veri kaynağının yolu Power BI Desktop’ta tanımlandığı gibi (aşağıda gösterilmiştir) "twitterDB-yaronctestingdb1.database.windows.net" bağlantı dizesidir. “twitterDB” veritabanı adından ve “yaronctestingdb1.database.windows.net” sunucu adından oluşur.

    ![Power B I Desktop'ta bağlantı dizesi tanımının ekran görüntüsü.](media/service-data-source-impact-analysis/connection-string-definition-in-desktop.png)
 
* **Etki özeti**: Etkilenme olasılığı olan çalışma alanlarının, veri akışlarının ve veri kümelerinin sayısını gösterir. Bu sayı erişiminiz olmayan çalışma alanlarını içerir.
* **Kullanım dökümü**: Size her çalışma alanı için etkilenen veri akışlarının ve veri kümelerinin adlarını gösterir. Belirli bir çalışma alanındaki etkiyi daha ayrıntılı incelemek için çalışma alanı adına tıklayarak çalışma alanını açın. Etkilenen çalışma alanına geldiğinizde bağlı raporların ve panoların ayrıntılarını görmek için [veri kümesi etki analizini](service-dataset-impact-analysis.md) kullanın.

## <a name="notify-contacts"></a>Kişilere bildirme

Veri kaynağında değişiklik yaptıysanız veya yapmayı düşünüyorsanız, ilgili kullanıcılarla iletişim kurup onları bilgilendirmek isteyebilirsiniz. Kişilere bildirimde bulunduğunuzda, etkilenen tüm çalışma alanlarının [kişi listelerine](service-create-the-new-workspaces.md#create-a-contact-list) e-posta gönderilir (klasik çalışma alanlarında e-posta, çalışma alanı yöneticilerine gönderilir). Adınız e-postada görüntülendiğinden kişiler sizi bulabilir ve yeni bir e-posta yazışmasında yanıtlayabilir. 

1. Etki analizi yan bölmesinde **Kişilere bildir**’e tıklayın. Kişilere bildir iletişim kutusu görüntülenir.

   ![Veri kaynağının Kişilere bildir iletişim kutusunun ekran görüntüsü.](media/service-data-source-impact-analysis/notify-contacts-dialog.png)

1. Metin kutusunda değişikliklerle ilgili bazı ayrıntılar girin.
1. İleti hazır olduğunda **Gönder**’e tıklayın.

## <a name="privacy"></a>Gizlilik

Etki analizi yan bölmesinde yalnızca erişiminiz olan çalışma alanlarının, veri kümelerinin ve veri akışlarının gerçek adlarını görürsünüz. Erişiminiz olmayan öğeler Sınırlı erişim olarak listelenir. Bunun nedeni bazı öğe adlarının kişisel bilgiler içermesidir.
Etki özeti sayımları erişiminiz olmayan çalışma alanlarında bulunanlar da dahil olmak üzere tüm veri akışlarını ve veri kümelerini içerir.

## <a name="limitations"></a>Sınırlamalar

Veri kaynağı etki analizi henüz sayfalandırılmış raporlar için desteklenmemektedir, bu nedenle veri kaynağının kiracıdaki bu tür raporları doğrudan etkileyip etkilemediğini görmezsiniz.

## <a name="next-steps"></a>Sonraki adımlar

* [Veri kümesi etki analizi](service-dataset-impact-analysis.md)
* [Veri kökeni](service-data-lineage.md)