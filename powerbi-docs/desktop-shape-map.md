---
title: Power BI Desktop'ta Şekil Haritalarını kullanma (Önizleme)
description: Power BI Desktop'ta şekil haritaları kullanarak bölgelere ilişkin göreli karşılaştırmalar oluşturma
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/16/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 2bdd29f664d49dd4628b2f27d0eddf1f5dad1cf7
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="shape-maps-in-power-bi-desktop-preview"></a>Power BI Desktop'ta Şekil Haritaları (Önizleme)
Power BI Desktop'ta, bir harita üzerindeki bölgelerin göreli karşılaştırmalarını göstermek için farklı bölgelere farklı renkler uygulayarak bir **Şekil Haritası** oluşturursunuz. **Harita** görselinin aksine, **Şekil Haritası** bir harita üzerindeki veri noktalarının kesin coğrafi konumlarını gösteremez. Asıl amacı, harita üzerindeki bölgeleri farklı şekilde renklendirerek bunlara ilişkin göreli karşılaştırmalar göstermektir.

**Şekil Haritası** görselleri, ESRI/TopoJSON haritalarını temel alır. Bu haritaların etkileyici özelliği, kendi oluşturabildiğiniz; coğrafi harita, oturma düzeni ve kat planı gibi özel haritaları kullanabilmenize olanak sağlamasıdır. **Şekli Eşlemesi**’nin bu Önizleme sürümünde özel haritalar kullanılamaz.

## <a name="creating-shape-maps"></a>Şekil Haritası Oluşturma
**Şekil Haritası** denetimini, bu Önizleme sürümüyle birlikte sunulan haritalarla test edebilir veya aşağıdaki **Özel Harita Kullanma** adlı bölümde açıklanmış gereksinimleri karşılaması koşuluyla kendi özel haritanızı kullanabilirsiniz.

**Şekil Haritası** görseli Önizleme'dedir ve Power BI Desktop'ta etkinleştirilmesi gerekir. **Şekil Haritası**'nı etkinleştirmek için, **Dosya > Seçenekler ve Ayarlar > Seçenekler > Önizleme Özellikleri**'ni seçin ve ardından **Şekil Haritası** onay kutusunu işaretleyin. Seçiminizi yaptıktan sonra Power BI Desktop'ı yeniden başlatmanız gerekir.

![](media/desktop-shape-map/shape-map_1a.png)

**Şekil Haritası** etkinleştirildiğinde, **Görsel Öğeler** bölmesindeki **Şekil Haritası** denetimine tıklayın.

![](media/desktop-shape-map/shape-map_2.png)

Power BI Desktop, boş bir **Şekil Haritası** görsel tasarım tuvali oluşturur.

![](media/desktop-shape-map/shape-map_3.png)

Bir **Şekil Haritası** oluşturmak için aşağıdaki adımları uygulayın:

1. **Alanlar** bölmesinde, bölge adlarını (veya kısaltmalarını) içeren bir veri alanını **Konum** demetine, bir veri ölçüsü alanını ise **Değerler** demetine sürükleyin. (Henüz bir harita görmezsiniz.)
   
   > [!NOTE]
> **Şekil Haritası**'nı test etmek üzere hızlıca harita verileri alma hakkında bilgi için aşağıdaki **Harita Verileri Alma** başlıklı bölüme bakabilirsiniz.
   > 
   > 
   
   ![](media/desktop-shape-map/shape-map_3a.png)
2. **Biçim** ayarları bölmesinde, **Şekil**'i genişletin ve **Standart Haritalar** açılan menüsünden seçim yaparak verilerinizi gösterin. Bu noktada, aşağıdaki görüntüde olduğu gibi işleme görüntülenir.
   
   ![](media/desktop-shape-map/shape-map_3b.png)
   
   > [!NOTE]
> Bu makalenin sonundaki **Bölge Anahtarları** bölümünde, **Şekil Haritası** görselini test etmek için kullanabileceğiniz harita bölge anahtarlarını içeren bir tablo koleksiyonu bulunur.
   > 
   > 
3. Ardından, **Biçim** ayarları bölmesini kullanarak, veri noktası renklerinin yanı sıra harita izdüşümü ve yakınlaştırma ayarlarını değiştirebilirsiniz. Yakınlaştırma ayarlarını da değiştirebilirsiniz. Örneğin, renkleri değiştirebilir, maksimum ve minimum değerleri belirleyebilir ve daha fazlasını yapabilirsiniz.
   
   ![](media/desktop-shape-map/shape-map_3d.png)
4. Ayrıca **Açıklama** demetine bir kategori veri sütunu ekleyebilir ve harita bölgelerini kategorilere göre sınıflandırabilirsiniz.

## <a name="use-custom-maps"></a>Özel harita kullanma
**TopoJSON** biçimindeki özel haritaları **Şekil Haritası** ile kullanabilirsiniz. Haritanız başka bir biçimdeyse [**Map Shaper**](http://mapshaper.org/) gibi çevrimiçi araçları kullanarak *şekil dosyalarınızı* ve *GeoJSON* haritalarınızı **TopoJSON** biçimine dönüştürebilirsiniz.

**TopoJSON** harita dosyanızı kullanmak için, raporunuza bir Şekil Haritası görseli, *Konum* ve *Değerler* demetlerine ise bazı veriler ekleyin. Ardından **Görselleştirmeler** bölmesinde **Biçim** bölümü seçiliyken (aşağıdaki görüntüde (1) olarak gösterilen boya fırçası simgesi) **Şekil** bölümünü genişletin ve **+Harita Ekle** seçeneğini belirleyin.

![](media/desktop-shape-map/shape-map_6.png)

## <a name="sample-custom-map"></a>Örnek Özel Eşleme
*ABD Savcılar Bürosu*, dava ve dosya yükü verileriyle ilgili yıllık mali rapor yayınlar.  Tüm raporlarına aşağıdaki bağlantıdan erişilebilir,

https://www.justice.gov/usao/resources/annual-statistical-reports

Eyaletler birden çok bölgeye ayrılabildiğinden, özel şekil haritası kullanmamız gerekir.  ABD yargı bölgelerinin **TopoJSON** haritasını **Power BI Desktop**’a içeri aktararak, yıllık mali bölge savcı verilerini görselleştirebiliriz.  Aşağıdaki resimde bu haritanın bir örneği gösterilmektedir.

![](media/desktop-shape-map/shape-map_7a.png)

Tek tek eyalet haritalarıyla ilgi çekici şeyler yapabilir ve içerdiği bölgelere dayalı daha fazla ayrıntı gösterebilirsiniz. 

![](media/desktop-shape-map/shape-map_7b.png)

Bu veri kümesi ve görselleştirme ile deneme yapmak istiyorsanız, aşağıdaki bağlantıyı kullanarak bu raporu oluşturmak için kullanılan özgün PBIX dosyasını indirebilirsiniz.

* [Özel şekil haritası .PBIX dosyası](http://download.microsoft.com/download/1/2/8/128943FB-9231-42BD-8A5D-5E2362C9D589/DistrictAttorneyFiscalReport.pbix)

## <a name="getting-map-data"></a>Harita verileri alma
**Şekil Haritası**'nı test etmek üzere bir modele hızlıca veri almak için, bu makalenin sonundaki tablolardan birini kopyalayabilir ve ardından **Giriş** şeridindeki **Verileri Girin** seçeneğini belirleyebilirsiniz.

![](media/desktop-shape-map/shape-map_4.png)

Ardından, tabloyu Power BI Desktop'a yapıştırabilirsiniz. En üst satır otomatik bir şekilde başlık olarak tanımlanır.

![](media/desktop-shape-map/shape-map_5.png)

Yeni bir sütun girmek için yeni bir sütun adı yazıp (sağdaki boş sütuna) her hücreye tıpkı Excel'de yapabildiğiniz gibi değer eklemeniz yeterlidir. İşlemi tamamladığınızda, **Yükle**'yi seçerek tablonun Power BI Desktop için veri modeline eklenmesini sağlayın.

> [!NOTE]
> Ülkelerle veya bölgelerle çalışırken harita görselleştirmelerinde coğrafi kodlamanın düzgün çalışmasını sağlamak için üç harfli kısaltmalar kullanın. Bazı ülkeler veya bölgeler düzgün şekilde tanınmayabileceğinden iki harfli kısaltmalar *kullanmayın*.
> 
> Yalnızca iki harfli kısaltmalara sahipseniz iki harfli ülke/bölge kısaltmalarınızı üç harfli ülke/bölge kısaltmalarıyla nasıl ilişkilendireceğiniz ile ilgili adımların açıklandığı [bu harici blog gönderisine](https://blog.ailon.org/how-to-display-2-letter-country-data-on-a-power-bi-map-85fc738497d6#.yudauacxp) göz atın.
> 
> 

## <a name="preview-behavior-and-requirements"></a>Önizleme davranışı ve gereksinimleri
**Şekil Haritası**'nın bu Önizleme sürümü için akılda bulundurulması gereken bazı önemli noktalar ve gereksinimler vardır:

* **Şekil Haritası** görseli Önizleme'dedir ve Power BI Desktop'ta etkinleştirilmesi gerekir. **Şekil Haritası**'nı etkinleştirmek için, **Dosya > Seçenekler ve Ayarlar > Seçenekler > Önizleme Özellikleri**'ni seçin ve ardından **Şekil Haritası** onay kutusunu işaretleyin.
* Şu anda **Açıklama** sınıflandırmasının düzgün bir şekilde çalışabilmesi için **Değerler** demetini de ayarlamanız gerekir
* **Şekil Eşlemesi**'nin son yayın sürümünde, seçili durumdaki eşlemeye ilişkin eşleme anahtarlarını gösteren bir kullanıcı arabirimi bulunacaktır (Son yayın için belirlenmiş bir tarih yoktur ve **Şekil Eşlemesi** hala Önizleme sürümündedir). Bu Önizleme sürümünde, bu makalenin **Bölge Anahtarları** bölümündeki tablolarda yer alan bölge anahtarlarına başvurabilirsiniz.
* **Şekil Eşlemesi** görseli en fazla 1.000 veri noktasına kadar çizim yapar.

## <a name="region-keys"></a>Bölge anahtarları
Bu Önizleme sürümünde **Şekil Haritası**'nı test etmek için aşağıdaki **Bölge Anahtarları**'nı kullanın.

### <a name="australia-states"></a>Avustralya: eyaletler
| id | abbr | iso | name | postal |
| --- | --- | --- | --- | --- |
| au-wa |WA |AU-WA |Western Australia |WA |
| au-vic |Vic |AU-VIC |Victoria |VIC |
| au-tas |Tas |AU-TAS |Tasmania |TAS |
| au-sa |SA |AU-SA |South Australia |SA |
| au-qld |Qld |AU-QLD |Queensland |QLD |
| au-nt |NT |AU-NT |Northern Territory |NT |
| au-nsw |NSW |AU-NSW |New South Wales |NSW |
| au-act |ACT |AU-ACT |Australian Capital Territory |ACT |

### <a name="austria-states"></a>Avusturya: eyaletler
| id | iso | name | name-en | postal |
| --- | --- | --- | --- | --- |
| at-wi |AT-9 |Wien |Vienna |WI |
| at-vo |AT-8 |Vorarlberg |Vorarlberg |VO |
| at-tr |AT-7 |Tirol |Tyrol |TR |
| at-st |AT-6 |Steiermark |Styria |ST |
| at-sz |AT-5 |Salzburg |Salzburg |SZ |
| at-oo |AT-4 |Oberösterreich |Upper Austria |OO |
| at-no |AT-3 |Niederösterreich |Lower Austria |NO |
| at-ka |AT-2 |Kärnten |Carinthia |KA |
| at-bu |AT-1 |Burgenland |Burgenland |BU |

### <a name="brazil-states"></a>Brezilya: eyaletler
| id |
| --- |
| Tocantins |
| Pernambuco |
| Goias |
| Sergipe |
| Sao Paulo |
| Santa Catarina |
| Roraima |
| Rondonia |
| Rio Grande do Sul |
| Rio Grande do Norte |
| Rio de Janeiro |
| Piaui |
| Parana |
| Paraiba |
| Para |
| Minas Gerais |
| Mato Grosso |
| Maranhao |
| Mato Grosso do Sul |
| Distrito Federal |
| Ceara |
| Espirito Santo |
| Bahia |
| Amazonas |
| Amapa |
| Alagoas |
| Acre |
| Litigated Zone 1 |
| Litigated Zone 2 |
| Litigated Zone 3 |
| Litigated Zone 4 |

### <a name="canada-provinces"></a>Kanada: bölgeler
| id | iso | name | postal |
| --- | --- | --- | --- |
| ca-nu |CA-NU |Nunavut |NU |
| ca-nt |CA-NT |Northwest Territories |NT |
| ca-yt |CA-YT |Yukon |YT |
| ca-sk |CA-SK |Saskatchewan |SK |
| ca-qc |CA-QC |Quebec |QC |
| ca-pe |CA-PE |Prince Edward Island |PE |
| ca-on |CA-ON |Ontario |ON |
| ca-ns |CA-NS |Nova Scotia |NS |
| ca-nl |CA-NL |Newfoundland and Labrador |NL |
| ca-nb |CA-NB |New Brunswick |NB |
| ca-mb |CA-MB |Manitoba |MB |
| ca-bc |CA-BC |British Columbia |BC |
| ca-ab |CA-AB |Alberta |AB |

### <a name="france-regions"></a>Fransa: bölgeler
| id | name | name-en |
| --- | --- | --- |
| Alsace |Alsace |Alsace |
| Rhone-Alpes |Rhône-Alpes |Rhone-Alpes |
| Provence-Alpes-Cote d'Azur |Provence-Alpes-Côte d'Azur |Provence-Alpes-Cote d'Azur |
| Poitou-Charentes |Poitou-Charentes |Poitou-Charentes |
| Picardie |Picardie |Picardy |
| Pays de la Loire |Pays de la Loire |Pays de la Loire |
| Nord-Pas-de-Calais |Nord-Pas-de-Calais |Nord-Pas-de-Calais |
| Midi-Pyrenees |Midi-Pyrénées |Midi-Pyrenees |
| Lorraine |Lorraine |Lorraine |
| Limousin |Limousin |Limousin |
| Languedoc-Roussillon |Languedoc-Roussillon |Languedoc-Roussillon |
| Ile-del-France |Île-de-France |Ile-de-France |
| Haute-Normandie |Haute-Normandie |Upper Normandy |
| Franche-Comte |Franche-Comté |Franche-Comte |
| Corse |Corse |Corsica |
| Champagne-Ardenne |Champagne-Ardenne |Champagne-Ardenne |
| Centre-Val de Loire |Centre-Val de Loire |Centre-Val de Loire |
| Bretagne |Bretagne |Brittany |
| Bourgogne |Bourgogne |Burgundy |
| Basse-Normandie |Basse-Normandie |Lower Normandy |
| Auvergne |Auvergne |Auvergne |
| Aquitaine |Aquitaine |Aquitaine |

### <a name="germany-states"></a>Almanya: eyaletler
| id | iso | name | name-en | postal |
| --- | --- | --- | --- | --- |
| de-be |DE-BE |Berlin |Berlin |BE |
| de-th |DE-TH |Thüringen |Thuringia |TH |
| de-st |DE-ST |Sachsen-Anhalt |Saxony-Anhalt |ST |
| de-sn |DE-SN |Sachsen |Saxony |SN |
| de-mv |DE-MV |Mecklenburg-Vorpommern |Mecklenburg-Vorpommern |MV |
| de-bb |DE-BB |Brandenburg |Brandenburg |BB |
| de-sh |DE-SH |Schleswig-Holstein |Schleswig-Holstein |SH |
| de-sl |DE-SL |Saarland |Saarland |SL |
| de-rp |DE-RP |Rheinland-Pfalz |Rhineland-Palatinate |RP |
| de-nw |DE-NW |Nordrhein-Westfalen |North Rhine-Westphalia |NW |
| de-ni |DE-NI |Niedersachsen |Lower Saxony |NI |
| de-he |DE-HE |Hessen |Hesse |HE |
| de-hh |DE-HH |Hamburg |Hamburg |HH |
| de-hb |DE-HB |Bremen |Bremen |HB |
| de-by |DE-BY |Bayern |Bavaria |BY |
| de-bw |DE-BW |Baden-Württemberg |Baden-Wurttemberg |BW |

### <a name="ireland-counties"></a>İrlanda: yerel idare bölgeleri
| id |
| --- |
| Wicklow |
| Wexford |
| Westmeath |
| Waterford |
| Sligo |
| Tipperary |
| Roscommon |
| Offaly |
| Monaghan |
| Meath |
| Mayo |
| Louth |
| Longford |
| Limerick |
| Leitrim |
| Laoighis |
| Kilkenny |
| Kildare |
| Kerry |
| Galway |
| Dublin |
| Donegal |
| Cork |
| Clare |
| Cavan |
| Carlow |

### <a name="italy-regions"></a>İtalya: bölgeler
| id | iso | name | name-en | postal |
| --- | --- | --- | --- | --- |
| it-vn |IT-34 |Veneto |Veneto |VN |
| it-vd |IT-23 |Valle d'Aosta |Aosta Valley |VD |
| it-um |IT-55 |Umbria |Umbria |UM |
| it-tt |IT-32 |Trentino-Alto Adige |Trentino-South Tyrol |TT |
| it-tc |IT-52 |Toscana |Tuscany |TC |
| it-sc |IT-82 |Sicilia |Sicily |SC |
| it-sd |IT-88 |Sardegna |Sardinia |SD |
| it-pm |IT-21 |Piemonte |Piedmont |PM |
| it-ml |IT-67 |Molise |Molise |ML |
| it-mh |IT-57 |Marche |Marche |MH |
| it-lm |IT-25 |Lombardia |Lombardy |LM |
| it-lg |IT-42 |Liguria |Liguria |LG |
| it-lz |IT-62 |Lazio |Lazio |LZ |
| it-fv |IT-36 |Friuli-Venezia Giulia |Friuli-Venezia Giulia |FV |
| it-er |IT-45 |Emilia-Romagna |Emilia-Romagna |ER |
| it-cm |IT-72 |Campania |Campania |CM |
| it-lb |IT-78 |Calabria |Calabria |LB |
| it-bc |IT-77 |Basilicata |Basilicata |BC |
| it-pu |IT-75 |Apulia |Puglia |PU |
| it-ab |IT-65 |Abruzzo |Abruzzo |AB |

### <a name="mexico-states"></a>Meksika: eyaletler
| id | abreviatura | iso | name | name-en | postal |
| --- | --- | --- | --- | --- | --- |
| mx-zac |Zac. |MX-ZAC |Zacatecas |Zacatecas |ZA |
| mx-yuc |Yuc. |MX-YUC |Yucatán |Yucatan |YU |
| mx-ver |Ver. |MX-VER |Veracruz |Veracruz |VE |
| mx-tla |Tlax. |MX-TLA |Tlaxcala |Tlaxcala |TL |
| mx-tam |Tamps. |MX-TAM |Tamaulipas |Tamaulipas |TM |
| mx-tab |Tab. |MX-TAB |Tabasco |Tabasco |TB |
| mx-son |Son. |MX-SON |Sonora |Sonora |SO |
| mx-sin |Sin. |MX-SIN |Sinaloa |Sinaloa |SI |
| mx-slp |S.L.P. |MX-SLP |San Luis Potosí |San Luis Potosi |SL |
| mx-roo |Q.R. |MX-ROO |Quintana Roo |Quintana Roo |QR |
| mx-que |Qro. |MX-QUE |Querétaro |Queretaro |QE |
| mx-pue |Pue. |MX-PUE |Puebla |Puebla |PU |
| mx-oax |Oax. |MX-OAX |Oaxaca |Oaxaca |OA |
| mx-nle |N.L. |MX-NLE |Nuevo León |Nuevo Leon |NL |
| mx-nay |Nay. |MX-NAY |Nayarit |Nayarit |NA |
| mx-mor |Mor. |MX-MOR |Morelos |Morelos |MR |
| mx-mic |Mich. |MX-MIC |Michoacán |Michoacan |MC |
| mx-mex |Méx. |MX-MEX |Estado de México |Mexico State |MX |
| mx-jal |Jal. |MX-JAL |Jalisco |Jalisco |JA |
| mx-hid |Hgo. |MX-HID |Hidalgo |Hidalgo |HI |
| mx-gro |Gro. |MX-GRO |Guerrero |Guerrero |GR |
| mx-gua |Gto. |MX-GUA |Guanajuato |Guanajuato |GT |
| mx-dur |Dgo. |MX-DUR |Durango |Durango |DU |
| mx-dif |Col. |MX-DIF |Ciudad de México |Mexico City |DF |
| mx-col |Coah. |MX-COL |Colima |Colima |CL |
| mx-coa |Chis. |MX-COA |Coahuila |Coahuila |CA |
| mx-chh |Chih. |MX-CHH |Chihuahua |Chihuahua |CH |
| mx-chp |CDMX. |MX-CHP |Chiapas |Chiapas |CP |
| mx-cam |Camp. |MX-CAM |Campeche |Campeche |CM |
| mx-bcs |B.C.S. |MX-BCS |Baja California Sur |Baja California Sur |BS |
| mx-bcn |B.C. |MX-BCN |Baja California |Baja California |BN |
| mx-agu |Ags. |MX-AGU |Aguascalientes |Aguascalientes |AG |

### <a name="netherlands-provinces"></a>Hollanda: bölgeler
| id | iso | name | name-en |
| --- | --- | --- | --- |
| nl-zh |NL-ZH |Zuid-Holland |South Holland |
| nl-ze |NL-ZE |Zeeland |Zeeland |
| nl-ut |NL-UT |Utrecht |Utrecht |
| nl-ov |NL-OV |Overijssel |Overijssel |
| nl-nh |NL-NH |Noord-Holland |North Holland |
| nl-nb |NL-NB |Noord-Brabant |North Brabant |
| nl-li |NL-LI |Limburg |Limburg |
| nl-gr |NL-GR |Groningen |Groningen |
| nl-ge |NL-GE |Gelderland |Gelderland |
| nl-fr |NL-FR |Fryslân |Friesland |
| nl-fl |NL-FL |Flevoland |Flevoland |
| nl-dr |NL-DR |Drenthe |Drenthe |

### <a name="uk-countries"></a>Birleşik Krallık: Ülkeler
| id | iso | name |
| --- | --- | --- |
| gb-wls |GB-WLS |Galler |
| gb-sct |GB-SCT |Scotland |
| gb-nir |GB-NIR |Northern Ireland |
| gb-eng |GB-ENG |England |

### <a name="usa-states"></a>ABD: eyaletler
| id | name | postal |
| --- | --- | --- |
| us-mi |Michigan |MI |
| us-ak |Alaska |AK |
| us-hi |Hawaii |HI |
| us-fl |Florida |FL |
| us-la |Louisiana |LA |
| us-ar |Arkansas |AR |
| us-sc |South Carolina |SC |
| us-ga |Georgia |GA |
| us-ms |Mississippi |MS |
| us-al |Alabama |AL |
| us-nm |New Mexico |NM |
| us-tx |Texas |TX |
| us-tn |Tennessee |TN |
| us-nc |North Carolina |NC |
| us-ok |Oklahoma |OK |
| us-az |Arizona |AZ |
| us-mo |Missouri |MO |
| us-va |Virginia |VA |
| us-ks |Kansas |KS |
| us-ky |Kentucky |KY |
| us-co |Colorado |CO |
| us-md |Maryland |MD |
| us-wv |West Virginia |WV |
| us-de |Delaware |DE |
| us-dc |District of Columbia |DC |
| us-il |Illinois |IL |
| us-oh |Ohio |OH |
| us-ca |California |CA |
| us-ut |Utah |UT |
| us-nv |Nevada |NV |
| us-in |Indiana |IN |
| us-nj |New Jersey |NJ |
| us-ri |Rhode Island |RI |
| us-ct |Connecticut |CT |
| us-pa |Pennsylvania |PA |
| us-ny |New York |NY |
| us-ne |Nebraska |NE |
| us-ma |Massachusetts |MA |
| us-ia |Iowa |IA |
| us-nh |New Hampshire |NH |
| us-or |Oregon |OR |
| us-mn |Minnesota |MN |
| us-vt |Vermont |VT |
| us-id |Idaho |ID |
| us-wi |Wisconsin |WI |
| us-wy |Wyoming |WY |
| us-sd |South Dakota |SD |
| us-nd |North Dakota |ND |
| us-me |Maine |ME |
| us-mt |Montana |MT |
| us-wa |Washington |WA |

