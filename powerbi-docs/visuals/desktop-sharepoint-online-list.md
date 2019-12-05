---
title: SharePoint Listesinde rapor oluşturma
description: Bu öğretici, SharePoint Listesi verilerinizi bir Power BI raporuna nasıl dönüştürebileceğinizi gösterir.
author: AdamDWilson
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 11/27/2019
ms.author: adamw
LocalizationGroup: Visualizations
ms.openlocfilehash: 11cbb04d1aa98a0d0042447da85c6b06a87ad9f2
ms.sourcegitcommit: a21f7f9de32203e3a4057292a24ef9b5ac6ce94b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74565988"
---
# <a name="create-a-report-on-a-sharepoint-list"></a>SharePoint Listesinde rapor oluşturma

Birçok ekip ve kuruluş, kolayca ayarlanabildiğinden ve kullanıcılar tarafından güncelleştirilmesi kolay olduğundan, verileri depolamak için SharePoint Online’daki Listeleri kullanır.  Bazen, kullanıcıların verileri hızlı bir şekilde anlaması için listeye bakmak yerine bir grafiğe bakmak çok daha kolaydır. Bu öğreticide, SharePoint Listesi verilerinizi bir Power BI raporuna nasıl dönüştürebileceğinizi göstereceğiz.

Bu beş dakikalık öğretici videoyu izleyin veya adım adım yönergeler için kaydırarak aşağı doğru ilerleyin.

<iframe width="400" height="450" src="https://www.youtube.com/embed/OZO3x2NF8Ak" frameborder="0" allowfullscreen></iframe>

**Rapor oluşturma işlemi başarılı oldu mu?  Başka geri bildiriminiz var mı?** <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR8M5xArDGsxPhvdGH5o-Ym1UM00wUE8yQ1dFQjUzWEk3VlU4SkhGVVhDWC4u" target="_blank">Bir dakikalık kısa bir ankete katılın.</a>

## <a name="part-1-connect-to-your-sharepoint-list"></a>1\. Bölüm: SharePoint Listenize bağlanma

1. Henüz yapmadıysanız, [Power BI Desktop](https://powerbi.microsoft.com/desktop/)’ı indirin ve yükleyin.
2. Power BI Desktop’ı açın ve şeridin Giriş sekmesinde **Verileri Al** > **Daha fazla**’yı seçin.
3. **Çevrimiçi Hizmetler**’i seçin ve ardından **SharePoint Online Listesi**’ni seçin.  

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-getdata.png" alt="get data" width="350"/>

4. **Bağlan**'ı seçin.
4. Listenizi içeren SharePoint Online sitenizin adresini (URL olarak da bilinir) bulun.  SharePoint Online’daki bir sayfadan, gezinti bölmesinde **Giriş**’i veya en üstteki sitenin simgesini seçerek site adresini alabilir ve ardından adresi web tarayıcınızın adres çubuğundan kopyalayabilirsiniz.

   Bu adımın videosunu izleyin:
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=48&end=90" frameborder="0" allowfullscreen></iframe>

5. Power BI Desktop’ta, adresi Aç iletişim kutusundaki **Site URL’si** alanına yapıştırın.

    **Bu adımı tamamlarken sorun mu yaşıyorsunuz?** <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR8M5xArDGsxPhvdGH5o-Ym1UQjRUUTVLMzdXN0ZBNkZJNjlKOVFYMVhUVS4u" target="_blank">Evet, sorun yaşıyorum</a>

6. Aşağıdaki görüntüde olduğu gibi bir SharePoint erişim ekranı görebilir veya görmeyebilirsiniz.  Bunu görmüyorsanız, 10. adıma atlayın.  Görüyorsanız, sayfanın sol tarafındaki **Microsoft Hesabı**’nı seçin.

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-auth1.png" alt="choose Microsoft account" width="500"/>

7. **Oturum Aç**’ı seçin ve Microsoft Office 365’te oturum açmak için kullandığınız kullanıcı adını ve parolayı girin.

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-auth2.png" alt="sign in" width="500"/>

8. Oturum açmayı bitirdiğinizde **Bağlan**’ı seçin.

    **Bu adımı tamamlarken sorun mu yaşıyorsunuz?** <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR8M5xArDGsxPhvdGH5o-Ym1UQjRUUTVLMzdXN0ZBNkZJNjlKOVFYMVhUVS4u" target="_blank">Evet, sorun yaşıyorum</a>

9. Gezginin sol tarafında, bağlanmak istediğiniz SharePoint listesinin yanındaki onay kutusunu seçin.

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-select-list.png" alt="get data" width="450"/>

10. **Yükle**’yi seçin.  Power BI, liste verilerinizi yeni bir rapora yükler.

## <a name="part-2-create-a-report"></a>2\. Bölüm: Rapor oluşturma

1. SharePoint listesi verilerinizin yüklendiğini görmek için sol tarafta **Veri** simgesini seçin.

2. Numara içeren liste sütunlarınızın, sağdaki **Alanları bölmesinde** Sum veya Sigma simgesini gösterdiğinden emin olun.  Numara içermeyen sütunlar için, tablo görünümünde sütun başlığını seçin, **Modelleme** sekmesini seçin, daha sonra verilere bağlı olarak **Veri türü**’nü **Ondalık Sayı** veya **Tamsayı**olacak şekilde değiştirin.  Değişikliklerinizi onaylamanız istenirse **Evet**’i seçin.  Numaranız para birimi gibi özel bir biçimde ise, **Biçim** ayarlayarak da bu seçeneği belirleyebilirsiniz.

   Bu adımın videosunu izleyin:
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=147&end=204" frameborder="0" allowfullscreen></iframe>

    **Bu adımı tamamlarken sorun mu yaşıyorsunuz?** <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR8M5xArDGsxPhvdGH5o-Ym1UQjRUUTVLMzdXN0ZBNkZJNjlKOVFYMVhUVS4u" target="_blank">Evet, sorun yaşıyorum</a>

3. Sol tarafta **Rapor** simgesini seçin.
4. Sağdaki **Alanlar** bölmesinde yanlarında bulunan onay kutusunu seçerek görselleştirmek istediğiniz sütunları seçin.

   Bu adımın videosunu izleyin:
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=215&end=252" frameborder="0" allowfullscreen></iframe>

5. Gerekirse görsel türünü değiştirin.
6. Mevcut görselin seçimini kaldırıp **Alanlar** bölmesinde diğer sütunlar için onay kutularını seçerek aynı raporda birden çok görselleştirme oluşturabilirsiniz.
7. Raporunuzu kaydetmek için **Kaydet**’i seçin.

**Rapor oluşturma işlemi başarıyla tamamlandı mı?  Başka geri bildiriminiz var mı?** <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR8M5xArDGsxPhvdGH5o-Ym1UM00wUE8yQ1dFQjUzWEk3VlU4SkhGVVhDWC4u" target="_blank">Bir dakikalık kısa bir ankete katılın.</a>
