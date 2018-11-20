---
title: Şirket içi veri kaynaklarında çoklu oturum açma (SSO) için SAML kullanma
description: Power BI'dan şirket içi veri kaynaklarında çoklu oturum açmayı (SSO) etkinleştirmek için ağ geçidinizde Security Assertion Markup Language (SAML) yapılandırması gerçekleştirin.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2018
LocalizationGroup: Gateways
ms.openlocfilehash: 8762e575574b717965ac55d4cf32a5c925c298ab
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51507796"
---
# <a name="use-security-assertion-markup-language-saml-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>Power BI'dan şirket içi veri kaynaklarına çoklu oturum açma (SSO) ile erişmek için ağ geçidinizde Security Assertion Markup Language (SAML) protokolünü kullanma

Sorunsuz çoklu oturum açma deneyimi için [Security Assertion Markup Language (SAML)](https://www.onelogin.com/pages/saml) protokolünü kullanın. SSO'yu etkinleştirmek, Power BI raporlarının ve panolarının şirket içi kaynaklardan alınan verileri yenilemesini kolaylaştırır.

## <a name="supported-data-sources"></a>Desteklenen veri kaynakları

Şu anda SAML ile SAP HANA desteği sunuyoruz. SAML kullanarak SAP HANA için çoklu oturum açma ayarlarını ve yapılandırmasını gerçekleştirme hakkında daha fazla bilgi için SAP HANA belgelerindeki [SAML SSO for BI Platform to HANA](https://wiki.scn.sap.com/wiki/display/SAPHANA/SAML+SSO+for+BI+Platform+to+HANA) (BI Platformundan HANA bağlantısı yapmak için SAML SSO) konusuna bakın.

[Kerberos](service-gateway-sso-kerberos.md) ile ek veri kaynakları için destek sunuyoruz.

## <a name="configuring-the-gateway-and-data-source"></a>Ağ geçidini ve veri kaynağını yapılandırma

SAML protokolünü kullanmak için öncelikle SAML kimlik sağlayıcısı için bir sertifika oluşturmanız, ardından bir Power BI kullanıcısını kimlikle eşlemeniz gerekir.

1. Bir sertifika oluşturun. *Ortak adı* yazarken SAP HANA sunucusunun FQDN bilgisini kullandığınızdan emin olun. Sertifikanın süresi 365 gün sonra dolar.

    ```
    openssl req -newkey rsa:2048 -nodes -keyout samltest.key -x509 -days 365 -out samltest.crt
    ```

1. SAP HANA Studio'da SAP HANA sunucunuza sağ tıklayıp **Güvenlik** > **Güvenlik Konsolunu Aç** > **SAML Kimlik Sağlayıcısı** > **OpenSSL Şifreleme Kitaplığı** yolunu izleyin.

1. **İçeri aktar**'ı seçin, samltest.crt dosyasını bulun ve içeri aktarın.

    ![Kimlik sağlayıcıları](media/service-gateway-sso-saml/identity-providers.png)

1. SAP HANA Studio'da **Güvenlik** klasörünü seçin.

    ![Güvenlik klasörü](media/service-gateway-sso-saml/security-folder.png)

1. **Kullanıcılar**'ı genişletin ve Power BI kullanıcınızı eşlemek istediğiniz kullanıcıyı seçin.

1. **SAML** ve ardından **Yapılandır**'ı seçin.

    ![SAML yapılandırması](media/service-gateway-sso-saml/configure-saml.png)

1. 2. adımda oluşturduğunuz kimlik sağlayıcısını seçin. **Dış Kimlik** alanında Power BI kullanıcınızın UPN bilgisini girip **Ekle**'yi seçin.

    ![Kimlik sağlayıcısını seçme](media/service-gateway-sso-saml/select-identity-provider.png)

Ardından [xmlsec1 aracını](http://sgros.blogspot.com/2013/01/signing-xml-document-using-xmlsec1.html) kullanarak kurulumu bir *SAML onayıyla* doğrulayın.

1. Onaylama işlemini assertion-template.xml olarak kaydedin. \<MyUserId\> değerini 7. adımda girdiğiniz Power BI kullanıcısının UPN değeriyle değiştirin.

    ```xml
    <?xml version="1.0" encoding="UTF-8" ?>
    <saml2:Assertion ID="Assertion12345789" IssueInstant="2015-07-16T04:47:49.858Z" Version="2.0" xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion">
      <saml2:Issuer></saml2:Issuer> 
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">
        <SignedInfo>
          <CanonicalizationMethod Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315"/>
          <SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#rsa-sha1"/>
          <Reference URI="">
            <Transforms>
              <Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"/>
              <Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>
            </Transforms>
            <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>
            <DigestValue />
          </Reference>
        </SignedInfo>
        <SignatureValue />
        <KeyInfo>
          <X509Data />
        </KeyInfo>
      </Signature>
      <saml2:Subject>
        <saml2:NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified"><MyUserId></saml2:NameID>
      </saml2:Subject>
      <saml2:Conditions NotBefore="2010-01-01T00:00:00Z" NotOnOrAfter="2050-01-01T00:00:00Z"/>
    </saml2:Assertion>
    ```

1. Aşağıdaki komutu çalıştırın. saltest.key ve samltest.crt, 1. adımda oluşturduğunuz anahtar ve sertifikadır.

    ```
    xmlsec1 --sign --privkey-pem samltest.key, samltest.crt --output signed.xml assertion-template.xml
    ```

1. SAP HANA Studio'da bir SQL konsol penceresi açın ve aşağıdaki komutu çalıştırın. \<SAMLAssertion\> yerine önceki adımdan xml içeriğini ekleyin.

    ```SQL
    CONNECT WITH SAML ASSERTION '<SAMLAssertion>'
    ```

Sorgunun başarılı olması, SAP HANA SAML SSO kurulumunuzun başarılı olduğunu gösterir.

Sertifikayı ve kimliği başarıyla yapılandırdığınıza göre sertifikayı pfx biçimine dönüştürüp ağ geçidi makinesini sertifikayı kullanacak şekilde yapılandırmanız gerekir.

1. Sertifikayı pfx biçimine dönüştürmek için aşağıdaki komutu çalıştırın.

    ```
    openssl pkcs12 -inkey samltest.key -in samltest.crt -export -out samltest.pfx
    ```

1. pfx dosyasını ağ geçidi makinesine kopyalayın:

    1. samltest.pfx dosyasına çift tıklayıp **Yerel Makine** > **İleri**'yi seçin.

    1. Parolayı girin ve **İleri**'yi seçin.

    1. **Tüm sertifikaları aşağıdaki depolama alanına yerleştir**'i seçip **Gözat** > **Kişisel** > **Tamam** yolunu izleyin.

    1. **İleri**'yi ve ardından **Son**'u seçin.

    ![Sertifikayı içeri aktarma](media/service-gateway-sso-saml/import-certificate.png)

1. Ağ geçidi hizmet hesabına sertifikanın özel anahtarına erişim izni verin:

    1. Ağ geçidi makinesinde Microsoft Yönetim Konsolu'nu (MMC) çalıştırın.

        ![MMC'yi çalıştırın](media/service-gateway-sso-saml/run-mmc.png)

    1. **Dosya** menüsünde **Ek Bileşen Ekle/Kaldır**'ı seçin.

        ![Ek bileşen ekle](media/service-gateway-sso-saml/add-snap-in.png)

    1. **Sertifikalar** > **Ekle**'yi ve ardından **Bilgisayar hesabı** > **İleri**'yi seçin.

    1. **Yerel Bilgisayar** > **Son** > **Tamam**'ı seçin.

    1. **Sertifikalar** > **Kişisel** > **Sertifikalar**'ı genişletin ve sertifikayı bulun.

    1. Sertifikaya sağ tıklayın ve **Tüm Görevler** > **Özel Anahtarları Yönet** yolunu izleyin.

        ![Özel anahtarları yönetme](media/service-gateway-sso-saml/manage-private-keys.png)

    1. Ağ geçidi hizmet hesabını listeye ekleyin. Bu hesap varsayılan olarak **NT SERVICE\PBIEgwService** şeklindedir. **services.msc** komutunu çalıştırıp **Şirket içi veri ağ geçidi hizmeti**'ni bularak ağ geçidi hizmetini çalıştıran hesabı bulabilirsiniz.

        ![Ağ geçidi hizmeti](media/service-gateway-sso-saml/gateway-service.png)

Son olarak aşağıdaki adımları izleyerek sertifika parmak izini ağ geçidi yapılandırmasına ekleyin.

1. Makinenizdeki sertifikaları listelemek için aşağıdaki PowerShell komutunu çalıştırın.

    ```powershell
    Get-ChildItem -path cert:\LocalMachine\My
    ```
1. Oluşturduğunuz sertifikanın parmak izini kopyalayın.

1. Ağ geçidi dizinine gidin, varsayılan dizin: C:\Program Files\On-premises data gateway.

1. PowerBI.DataMovement.Pipeline.GatewayCore.dll.config dosyasını açın ve \*SapHanaSAMLCertThumbprint\* bölümünü bulun. Kopyaladığınız parmak izini yapıştırın.

1. Ağ geçidi hizmetini yeniden başlatın.

## <a name="running-a-power-bi-report"></a>Power BI raporu çalıştırma

Artık Power BI'daki **Ağ Geçidini Yönet** sayfasından veri kaynağını yapılandırabilir ve **Gelişmiş Ayarlar** sayfasından SSO özelliğini etkinleştirebilirsiniz. Ardından bu veri kaynağında raporları ve veri kümesi bağlamasını yayımlayabilirsiniz.

![Gelişmiş ayarlar](media/service-gateway-sso-saml/advanced-settings.png)

## <a name="next-steps"></a>Sonraki adımlar

**Şirket içi veri ağ geçidi** ve **DirectQuery** hakkında daha fazla bilgi için aşağıdaki kaynaklara göz atın:

* [Şirket içi veri ağ geçidi](service-gateway-onprem.md)
* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)