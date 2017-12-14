---
title: "Power BI ağ geçitleriyle çalışmaya başlama"
description: "Power BI ile birlikte kullanılan veri ağ geçitleri hakkındaki temel bilgileri öğrenin."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: davidi
ms.openlocfilehash: a93f24dc621dc5b044473fd16cc635fdef987a62
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2017
---
# <a name="getting-started-with-power-bi-gateways"></a>Power BI ağ geçitleriyle çalışmaya başlama
**Power BI ağ geçitleriyle çalışmaya başlama** kılavuzuna hoş geldiniz. Bu kısa kılavuzda veri ağ geçitlerinin işlevleri ve çalışma şeklinin yanı sıra kendi ağ geçidinizi yükleme, yapılandırma ve çalıştırma yöntemleri ele alınmaktadır.  

![](media/service-gateway-getting-started/gw_gettingstarted_0a.png)

Her ağ ve kuruluş birbirinden farklı olduğu için ağ geçitleri karmaşık ve teknik bir konu haline gelebilir. Bu karmaşayı biraz gidermek için temel bilgileri incelemeye başlayalım.

## <a name="how-power-bi-gateways-work"></a>Power BI ağ geçitleri nasıl çalışır?
**Ağ geçidi**, Power BI gibi bir bulut hizmetinde sonradan kullanılmak üzere özel veya şirket içi bir ağda tutulan verilere erişilmesini kolaylaştıran bir yazılımdır. Bağlantı isteklerini dinleyen ve yalnızca belirli ölçütlere (ağ geçidini kullanma iznine sahip olup olmadıkları gibi) uygun olan kullanıcı isteklerini onaylayan bir bekçi gibidir. Bu sistem, kuruluşların veritabanlarını ve ambarlarını şirket içi ağlarında tutarak bu verilerin alt kümelerini Power BI'da etkili raporlar ve panolar oluşturma amacıyla kullanmaya devam etmelerini sağlar.

Ağ geçidi aynı zamanda üzerinden geçen tüm verilerin yanı sıra veri kaynaklarına bağlanmak için kullanılan parolaları şifreleyip sıkıştırarak erişim ve veri güvenliğini de sağlar. Tüm bu bilgilerin oldukça anlaşılır göründüğünden eminim ancak bu konuyla ilgili birçok ayrıntı da mevcut.

Bazen yalnızca kendinize ait olacak bir ağ geçidi isteyebilirsiniz. Belki uzun yıllara ait satış ve pazarlama verilerinin bulunduğu büyük bir Excel çalışma kitabı ve üç SQL veritabanınız vardır ve bu satışları her açıdan ele alan bir Power BI panosu oluşturmak istersiniz. Raporları oluşturan tek kişisiniz, Excel çalışma kitabı size ait ve bu veritabanlarını Power BI raporu oluşturma amacıyla kullanan yalnızca sizsiniz. Yalnızca kişisel kullanım için bir ağ geçidine ihtiyaç duyuyorsunuz, bu veri kaynaklarını başkalarıyla paylaşma isteğiniz yok.

Diğer durumlarda Analysis Services, SAP, Oracle, IBM gibi farklı satıcılardan her türlü veritabanı ile başka birçok veri kaynağına sahip bir kuruluşta olabilirsiniz ve bu verilere çok sayıda kullanıcının erişerek farklı raporlar oluşturmasına ihtiyaç duyabilirsiniz. Bu durumda bu kaynakların tümüne erişimi yapılandırmanıza ve ardından kuruluşunuzdaki çok sayıda kullanıcıyla paylaşmanıza izin veren bir ağ geçidine ihtiyaç duyarsınız. Bu da farklı bir ağ geçidi türüdür.

Neyse ki Power BI bu senaryolara çok iyi uyum sağlayan iki farklı ağ geçidi sunmaktadır. Power BI tarafından sunulan bu iki ağ geçidi seçeneği şunlardır:

* **Şirket içi veri ağ geçidi (kişisel mod)**: Tek kullanıcının kaynaklara bağlantı kurmasını sağlar ve başkalarıyla paylaşılamaz. Yalnızca Power BI ile birlikte kullanılabilir.
* **Şirket içi veri ağ geçidi**: Birden fazla kullanıcının şirket içi veri kaynaklarına bağlanmasını sağlar ve tek bir ağ geçidi yüklemesiyle Power BI, PowerApps, Flow ve Azure Logic uygulamaları tarafından kullanılabilir.

İki ağ geçidi de benzer işleve sahiptir. Ağ geçitleri özel şirket içi ağ üzerindeki verilere erişim sağlar ve bu sayede veriler Power BI gibi bulut tabanlı hizmetlerde kullanılabilir. Kişisel ağ geçidi tek bir kişi ve yalnızca Power BI tarafından kullanılabilir, **şirket içi veri ağ geçidi** birden fazla kullanıcı ve birden fazla hizmet tarafından kullanılabilir.

Bir ağ geçidini hizmete almak için gerçekleştirilmesi gereken işlemler üç bölüme veya üç aşamaya ayrılabilir:

* Ağ geçidini yükleme
* Kullanıcıları ağ geçidine ekleme (ağ geçidini kullanmalarını sağlama)
* Veri kaynaklarına bağlanma

Ağ geçidi kullanma ayrıca, önemli olabilecek başka bir işlemi de gerçekleştirmenizi sağlar:

* Power BI raporlarındaki verilerin yenilenebilmesi için şirket içi verileri yenileme

Veri yenileme, Power BI panolarınızın ve raporlarınızın güncel olarak en yeni verileri yansıtması anlamına gelir. Bu şekilde şirket içi verilerle oluşturduğunuz bir raporu görüntüleyen kişi, raporu bir süre önce oluşturmuş olsanız dahi en güncel bilgileri görebilir.

Birinci bölüm olan ağ geçidini yükleme adımı oldukça basittir. Kullanıcılara ağ geçidine erişim izni vermek de kolaydır. Tek yapmanız gereken onları Power BI içindeki bir iletişim kutusuna eklemektir. Her biri kendi bağlantı gereksinimlerine ve farklılıklarına sahip birçok farklı veri kaynağı olduğundan veri kaynaklarına bağlanma adımı karmaşık olabilir. Bu makalenin konusunu ağ geçidiyle sınırlamak için yenileme sürecini başka bir kılavuzda ele alacağız.

Öncelikle kolaydan başlayıp ağ geçidi yükleme adımlarını inceleyelim.

## <a name="install-the-gateway"></a>Ağ geçidini yükleme
Bir ağ geçidi yüklemek için Power BI hizmetini açın (bu bağlantıyı kullanarak Power BI hizmetini tarayıcınızdan başlatıp oturum açabilirsiniz) ve Power BI hesabınızla oturum açın. Power BI hizmetinde aşağıdaki resimde gösterildiği gibi **indir simgesini** ve ardından **Data Gateway**'i seçin.

![](media/service-gateway-getting-started/gw_gettingstarted_01.png)

Açılan indirme sayfasındaki **Download gateway** (Ağ geçidini indir) düğmesine tıklayarak indirme işlemini başlatabilirsiniz.

![](media/service-gateway-getting-started/gw_gettingstarted_02.png)

Bu ekranda ağ geçidinin işlevleri hakkında özet bilgiler verilir. Ayrıca birkaç önemli **uyarı** da bulunur. Yüklediğiniz ağ geçidi, yüklemeyi gerçekleştirdiğiniz bilgisayarda çalışır. Bu bilgisayar kapalı olduğunda ağ geçidi de kapalı olur (yani bilgisayar çalışmadığında ağ geçidi çalışmaz). Ayrıca, yüklemeyi kablosuz ağ kullanan bir bilgisayara yapmanız önerilmez, en iyisi kablolu ağa bağlı bir bilgisayar tercih etmektir.

Hazır olduğunuzda kurulum adımlarına geçmek için **İleri**'yi seçin.

![](media/service-gateway-getting-started/gw_gettingstarted_03.png)

Burada şirket içi ağ geçidi mi yoksa kişisel ağ geçidi mi yükleyeceğinizi belirleyebilirsiniz. Bu kılavuzda **Şirket içi veri ağ geçidini** yükleyeceğiz.

Burada dikkat etmeniz gereken bazı noktalar vardır:

* İki ağ geçidi için de 64 bit Windows işletim sistemi gerekir.
* Ağ geçitleri etki alanı denetleyicisi üzerine yüklenemez.
* Aynı bilgisayara her biri farklı bir modda çalışan (kişisel ve standart) iki şirket içi veri ağ geçidi yükleyebilirsiniz. 
* Aynı bilgisayara aynı modda çalışan birden fazla ağ geçidi yükleyemezsiniz.
* Farklı bilgisayarlara birden fazla şirket içi veri ağ geçidi yükleyip tümünü aynı Power BI ağ geçidi yönetim arabiriminden yönetebilirsiniz (kişisel hariç, aşağıdaki noktaya bakın).
* Her Power BI kullanıcısı için kişisel modda çalışan yalnızca bir ağ geçidine sahip olabilirsiniz. Başka bir bilgisayarda bile olsa aynı kullanıcı için ikinci bir kişisel mod ağ geçidi yüklediğinizde en son yapılan yükleme önceki yüklemelerin yerini alır.

**İleri**'yi seçtiğinizde ağ geçidi yüklemesi başlar. Yükleneceği konumu belirtmeniz gerekir ve genelde varsayılan konum en iyisidir.

![](media/service-gateway-getting-started/gw_gettingstarted_06.png)

Yükleme işlemi hızla tamamlanır ve ilerleme durumunu görebileceğiniz bir durum çubuğu sunulur.

![](media/service-gateway-getting-started/gw_gettingstarted_06a.png)

İşlem tamamlanmadan önce ağ geçidiyle birlikte kullanılacak hesabı tanımlamanız gerekir. Bunun Power BI oturumu açmak için kullandığınız hesap (kullanıcı adı ve parola) olması gerekir. Ağ geçidi Power BI hesabınızla ilişkilendirilir ve ağ geçitlerini Power BI hizmetinden yapılandırırsınız.

![](media/service-gateway-getting-started/gw_gettingstarted_07.png)

Aşağıdaki resimde gösterilen şekilde oturumunuz açılır.

![](media/service-gateway-getting-started/gw_gettingstarted_08.png)

Oturum açıldıktan sonra bir **Kurtarma anahtarı** oluşturmanız gerekir. Bu adımları başka bir makalede ayrıntılı bir şekilde anlatacağız ancak şimdilik ağ geçidinizi kurtarmak veya taşımak için bu anahtara ihtiyaç duyacağınızı bilmeniz yeterlidir.

![](media/service-gateway-getting-started/gw_gettingstarted_09.png)

Tüm adımlar başarıyla tamamlandığında ağ geçidinizin hazır olduğunu bildiren bir pencere görüntülenir.

![](media/service-gateway-getting-started/gw_gettingstarted_10.png)

Şirket içi ağ geçidi oluşturma adımları bunlardır. Söz verdiğimiz gibi oldukça kolay bir süreç oldu. Sonraki adım **kullanıcı ekleme** veya **veri kaynağı ekleme** adımıdır. İstediğinizi önce yapabilir ve ilk yapılandırma sonrasında istediğinizi ekleyebilirsiniz.

Sonraki bölümde ağ geçidine kullanıcı ekleme adımları anlatılmıştır. Bu işlemin ardından ağ geçidine veri eklemek için neler yapmanız gerektiğini ele alacağız.

## <a name="add-users-to-a-gateway"></a>Ağ geçidine kullanıcı ekleme
Ağ geçidinizi yüklediğimize göre ağ geçidini **Power BI hizmetinden** yönetebiliriz. Ağ geçidi yönetim ekranına ulaşmak için Power BI hizmetinde sağ üst köşedeki dişli simgesini ve ardından **Ağ geçitlerini yönet**'i seçin.

![](media/service-gateway-getting-started/gw_gettingstarted_15.png)

Power BI hizmeti tuvali içinde ağ geçitlerinizi yönetebileceğiniz bir sayfa açılır. **Ağ Geçidi Ayarları** sayfası aşağıdakine benzer.

![](media/service-gateway-getting-started/gw_gettingstarted_12.png)

**Yöneticiler**'e dokunduğunuzda veya tıkladığınızda aşağıdaki yönetici yönetim sayfası açılır. Bunlar yalnızca ağ geçidini *yönetebilecek* kullanıcılardır. Ağ geçidi kullanıcıları ise farklı bir sayfa kullanılarak her bir veri kaynağından eklenir (veya kaldırılır). Bu işlemi sonraki birkaç paragrafta anlatacağız.

![](media/service-gateway-getting-started/gw_gettingstarted_13.png)

Yükleyip doğruladığınız (başarıyla bağlandığınız) veri kaynakları aşağıdaki resimde gösterildiği şekilde bu **Ağ geçitlerini yönet** ekranının sol tarafındaki ilgili ağ geçidinin altında görünür. Sağ taraftaki bölmede arasında geçiş yapabileceğiniz iki bölüm olduğuna dikkat edin: **Veri Kaynağı Ayarları** ve **Kullanıcılar**. Aşağıdaki ekranda **Veri Kaynağı Ayarları** bölümü gösterilmektedir.

![](media/service-gateway-getting-started/gw_gettingstarted_16.png)

**Kullanıcılar**'ı seçtiğinizde açılan metin kutusuna kuruluşunuzdaki kullanıcılardan seçilen veri kaynağına erişim izni vermek istediklerinizi yazabilirsiniz. Aşağıdaki ekranda gördüğünüz üzere Maggie ve Adam'ı ekledim.

Metin kutusuna e-posta adresi yazmaya başladığınızda Power BI, e-posta adresi yazdıklarınızla eşleşen kullanıcıların listesini gösterir ve bu adlara tıklayarak listeye ekleme yapabilirsiniz.

Bir grup içindeki kullanıcılara erişim izni vermek için e-posta gruplarını (takma adlar) veya tek kullanıcıları ekleyebilirsiniz.

![](media/service-gateway-getting-started/gw_gettingstarted_17.png)

**Ekle**'yi seçtiğinizde eklenen üyeler kutuda görüntülenir ve dilerseniz ekleme yapabilirsiniz. Kullanıcıları kaldırmak da oldukça kolaydır. Kullanıcı adının yanındaki onay kutusunu işaretleyip kutunun altındaki **Kaldır** düğmesini seçmeniz yeterlidir.

![](media/service-gateway-getting-started/gw_gettingstarted_18.png)

İşte bu kadar kolay. Kullanıcıları, erişim izni vermek istediğiniz her bir veri kaynağına eklemeniz gerektiğini unutmayın. Her veri kaynağının kullanıcı listesi ayrıdır ve kullanıcıları her veri kaynağına ayrıca eklemeniz gerekir.

## <a name="adding-data-sources"></a>Veri kaynaklarını ekleme
Elbette ağ geçidinizi işe yarar hale getirmek için veri kaynağı eklemeniz gerekir. Power BI ağ geçitlerinin karmaşıklığı burada başlar. Kullanılabilecek birçok farklı veri kaynağı vardır ve her birinin gereksinimleri (ve genelde gerekli sürücüsü) diğerlerinden farklıdır.

Sizi başka bir makaleye göndermeden önce veri kaynağı ekleme konusunda bilgi vermek istiyoruz. **Power BI hizmetinin** **Ağ geçitlerini yönet** sayfasında veri kaynağı eklemek istediğiniz ağ geçidini seçip sayfanın sol üst köşesinde, kullanılabilir ağ geçitleri listenizin hemen üzerinde yer alan **Veri Kaynağı Ekle**'yi seçin.

Bu işlemi gerçekleştirdiğinizde aşağıdaki resimde gösterildiği şekilde sağ taraftaki bölmede **Veri Kaynağı Ayarları** bölmesi görünür. Buradan veri kaynağınızı adlandırabilir (**Veri Kaynağı Adı** metin kutusuna girerek) ve **Veri Kaynağı Türü** açılan listesinden türünü seçebilirsiniz.

![](media/service-gateway-getting-started/gw_gettingstarted_14.png)

Ağ geçidinizi yüklediniz ve veri kaynağı eklemeye hazırsınız. Harika! Veri kaynakları hakkında bilgiler, ağ geçidi kullanma hakkında ayrıntılar ve diğer yararlı bilgiler için aşağıdaki bölümde yer alan kaynakları inceleyin.

## <a name="next-steps"></a>Sonraki adımlar
[Şirket içi veri ağ geçidini kullanma](service-gateway-onprem.md)  
[Şirket içi veri ağ geçidi (ayrıntılı)](service-gateway-onprem-indepth.md)  
[Şirket içi veri ağ geçidi (kişisel mod)](service-gateway-personal-mode.md)
[Şirket içi veri ağ geçidiyle ilgili sorunları giderme](service-gateway-onprem-tshoot.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

