---
title: SAP HANA’da çoklu oturum açma (SSO) için Kerberos'u kullanma
description: SAP HANA sunucunuzu Power BI hizmetinden SSO etkinleştirecek şekilde yapılandırma
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: how-to
ms.date: 12/16/2020
LocalizationGroup: Gateways
ms.openlocfilehash: 3f50b174e8293d75a0077e1799cb64ff4fdcd696
ms.sourcegitcommit: 5c09d121d3205e65fb33a2eca0e60bc30e777773
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97675132"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-hana"></a>SAP HANA’da çoklu oturum açma (SSO) için Kerberos'u kullanma

> [!IMPORTANT]
> [SAP artık OpenSSL desteği sunmadığından](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.05/en-US/de15ffb1bb5710148386ffdfd857482a.html) Microsoft da desteğini sonlandırmıştır. Mevcut bağlantılar çalışmaya devam edecek ancak Şubat 2021'den itibaren yeni bağlantı oluşturamayacaksınız. Bundan sonra lütfen onun yerine CommonCryptoLib kullanın.

Bu makalede, Power BI hizmetinden SSO'yu etkinleştirmek için SAP HANA veri kaynağınızın nasıl yapılandırılacağı açıklanır.

> [!NOTE]
> Kerberos SSO’su kullanan SAP HANA tabanlı bir raporu yenilemeyi denemeden önce bu makaledeki adımlara ek olarak [Kerberos SSO’yu Yapılandırma](service-gateway-sso-kerberos.md) bölümündeki adımları tamamlayın.

## <a name="enable-sso-for-sap-hana"></a>SAP HANA için SSO'yu etkinleştirme

SAP HANA için SSO'yu etkinleştirmek üzere aşağıdaki adımları izleyin:

1. SAP HANA sunucusunun, gerekli olan en düşük sürümü çalıştırdığından emin olun. Bu sürüm, SAP HANA sunucusu platform düzeyinize bağlıdır:
   - [HANA 2 SPS 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
   - [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
   - [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)

2. Ağ geçidi makinesine en son SAP HANA ODBC sürücüsünü yükleyin. Yükleyebileceğiniz minimum sürüm Ağustos 2017'de kullanıma sunulan HANA ODBC 2.00.020.00 sürümüdür.

3. SAP HANA sunucusunun Kerberos tabanlı SSO için yapılandırıldığından emin olun. Kerberos kullanarak SAP HANA için SSO’yu ayarlama hakkında daha fazla bilgi almak için SAP HANA Security Guide’daki (SAP HANA Güvenlik Rehberi) [Single Sign-on Using Kerberos](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/1885fad82df943c2a1974f5da0eed66d.html) (Kerberos Kullanarak Çoklu Oturum Açma) konusuna bakın. Aynı sayfada bulunan bağlantılara da göz atın (özellikle SAP Note 1837331 – HOWTO HANA DBSSO Kerberos/Active Directory).

Az da olsa performans artışı sağlayabilecek aşağıdaki ek adımları gerçekleştirmenizi de öneririz:

1. Ağ geçidi yükleme dizininde şu yapılandırma dosyasını bulun ve açın: Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config.

2. `FullDomainResolutionEnabled` özelliğini bulun ve değerini `True` olarak değiştirin.

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

Şimdi [bir Power BI raporu çalıştırın](service-gateway-sso-kerberos.md#run-a-power-bi-report).

## <a name="next-steps"></a>Sonraki adımlar

Şirket içi veri ağ geçidi ve DirectQuery hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Şirket içi veri ağ geçidi nedir?](/data-integration/gateway/service-gateway-onprem)
* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen veri kaynakları](power-bi-data-sources.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
