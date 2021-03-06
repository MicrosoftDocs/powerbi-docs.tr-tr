---
title: Power BI sayfalandırılmış raporu için tümleşik veri kümesi oluşturma
description: Bu makalede, Power BI hizmetindeki sayfalandırılmış bir rapor için tümleşik bir veri kaynağını temel alan tümleşik bir veri kümesi oluşturma işlemini öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: how-to
ms.date: 11/5/2018
ms.openlocfilehash: 81d755a529edb2f4fdae0ae6dbe90026b5b290d8
ms.sourcegitcommit: ccf53e87ff7cba1fcd9d2cca761a561e62933f90
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2020
ms.locfileid: "93297667"
---
# <a name="create-an-embedded-dataset-for-a-paginated-report-in-the-power-bi-service"></a>Sayfalandırılmış rapor için Power BI hizmetinde tümleşik veri kümesi oluşturma

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-service](../includes/yes-service.md)] [!INCLUDE [yes-paginated](../includes/yes-paginated.md)] [!INCLUDE [yes-premium](../includes/yes-premium.md)] [!INCLUDE [no-desktop](../includes/no-desktop.md)] 

Bu makalede, Power BI hizmetindeki sayfalandırılmış bir rapor için tümleşik bir veri kaynağını temel alan tümleşik bir veri kümesi oluşturma işlemini öğreneceksiniz. Tümleşik veri kümeleri tek bir sayfalandırılmış raporda kullanılmak üzere o raporda yer alır. Şu anda, Power BI hizmetinde yayımlanan sayfalandırılmış raporlar için tümleşik veri kümeleri ve tümleşik veri kaynakları gereklidir. Tümleşik veri kaynağını ve veri kümesini, raporunuzu oluştururken Power BI Rapor Oluşturucusu’nda oluşturursunuz. 

Veri kümesini oluşturabilmeniz için bir veri kaynağı oluşturmak gerekir. Nasıl yapıldığını öğrenmek için Power BI hizmetinde [Sayfalandırılmış raporlar için tümleşik veri kaynakları](paginated-reports-embedded-data-source.md) bölümüne bakın.
  
## <a name="create-an-embedded-dataset"></a>Eklenmiş veri kümesi oluşturma
  
1. Power BI Rapor Oluşturucusu'ndaki Rapor Verileri bölmesinde **Yeni** > **Veri Kümesi** ’ni seçin.

1. **Veri Kümesi Özellikleri** iletişim kutusunun **Sorgu** sekmesinde veri kümesine bir ad verin. Tümleşik veri kaynağı zaten **Veri kaynağı** kutusundadır veya **Yeni** ’yi seçerek farklı bir tümleşik veri kaynağı seçebilirsiniz.
 
   ![Yeni Veri Kümesi](media/paginated-reports-create-embedded-dataset/power-bi-paginated-new-dataset.png)  

3. **Sorgu türü** altında veri kümesi için kullanılacak komut türünü veya sorguyu seçin. 
    - **Metin** , veritabanından veri almak için bir sorgu çalıştırır. Varsayılandır ve sorguların çoğu için kullanılır. Bir sorgu yazın veya **İçeri Aktar** ’ı seçerek önceden mevcut olan bir sorguyu içeri aktarın. Sorguyu grafiksel olarak oluşturmak için **Sorgu Tasarımcısı** ’nı seçin. Bir sorgu oluşturmak için sorgu tasarımcısını kullanırsanız bu kutuda sorgunun metni görünür. Sorguyu dinamik olarak oluşturmak üzere bir ifade kullanmak için **İfade** ( **fx** ) düğmesini seçin. 
    - **Tablo** bir tablonun içindeki tüm alanları seçer. Veri kümesi olarak kullanmak istediğiniz tablonun adını girin.
    - **Saklı Yordam** , ada göre bir saklı yordam çalıştırır.

4. Sorgu Tasarımcısı'nda, veri kümesindeki tablo ve alanları görüp bunlarla etkileşimde bulunabilir, bir sorguyu içeri aktarabilir veya metin olarak düzenleyebilirsiniz. Ayrıca, buraya filtre ve parametreler de ekleyebilirsiniz. 

    ![Sorgu tasarımcısı](media/paginated-reports-create-embedded-dataset/power-bi-paginated-embedded-dataset-edit-query.png)

5. Sorgu Tasarımcısı'nda sorguyu test etmek için **Sorgu Çalıştır** ’ı ve **Tamam** ’ı seçin.

1. Veri Kümesi Özellikleri iletişim kutusunda geri dönerek **Zaman aşımı (saniye cinsinden)** kutusuna sorgu zaman aşımına uğrayana kadar geçen saniye sayısını yazın. Varsayılan değer 30 saniyedir. **Zaman aşımı** değeri boş ya da sıfırdan büyük olmalıdır. Boş ise sorgu zaman aşımına uğramaz.

7.  Diğer sekmelerde veri kümesinin diğer özelliklerini ayarlayabilirsiniz:
    - **Alanlar** sekmesinde hesaplanan alanlar oluşturun.
    - **Seçenekler** sekmesinde gelişmiş seçenekleri ayarlayın.
    - İlgili sekmelerde **Filtreler** ve **Parametreler** ekleyin ya da güncelleştirin.

8. **Tamam** 'ı seçin
 
   Rapor, Rapor Tasarım Görünümünde açılır. Veri kaynağı, veri kümesi ve veri kümesi alan koleksiyonu, Rapor Verileri bölmesinde görünür ve sayfalandırılmış raporunuzu tasarlamaya devam edebilirsiniz.  

    ![Rapor Tasarımı Görünümünde veri kümesi](media/paginated-reports-create-embedded-dataset/power-bi-paginated-embedded-dataset-report-design-view.png) 
 
## <a name="next-steps"></a>Sonraki adımlar 

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)  
- [Öğretici: Sayfalandırılmış rapor oluşturma ve bu raporu Power BI hizmetine yükleme](paginated-reports-quickstart-aw.md)
- [Power BI hizmetinde sayfalandırılmış rapor yayımlama](paginated-reports-save-to-power-bi-service.md)

