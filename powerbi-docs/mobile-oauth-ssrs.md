---
title: "OAuth kullanarak Reporting Services'e bağlanma"
description: "Reporting Services 2016 veya sonraki bir sürüme bağlanmak için ortamınızı Power BI mobil uygulaması ile OAuth kimlik doğrulamasını destekleyecek şekilde yapılandırmayı öğrenin."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: f32fd9585c28fc9a837bea80b57d23f9725a6b49
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="using-oauth-to-connect-to-reporting-services"></a>OAuth kullanarak Reporting Services'e bağlanma
Reporting Services 2016 veya sonraki bir sürüme bağlanmak için ortamınızı Power BI mobil uygulaması ile OAuth kimlik doğrulamasını destekleyecek şekilde yapılandırmayı öğrenin.

![](media/mobile-oauth-ssrs/powerbi-mobile-oauth.png)

Power BI mobil uygulaması daha önce, Mobil Raporların veya KPI'lerin görüntülenmesi için Reporting Services'te yalnızca HTTPS üzerinden temel kimlik doğrulamasını destekliyordu. Birçok kuruluş güvenlikle ilgili nedenlerle bu yapılandırma türüne izin vermemektedir. Power BI mobil uygulamasına yönelik bir güncelleştirme ile artık OAuth kimlik doğrulamasını kullanarak Reporting Services'e bağlanabilirsiniz. Windows Server 2016, bu kimlik doğrulaması türüne izin vermek için Web Uygulaması Ara Sunucusu'na yönelik bazı iyileştirmeler sağlar.

## <a name="requirements"></a>Gereksinimler
Web Uygulaması Ara Sunucusu (WAP) ve Active Directory Federasyon Hizmetleri (ADFS) sunucuları için Windows Server 2016 gerekir. Windows 2016 işlev düzeyi etki alanına sahip olmanız gerekmez.

## <a name="domain-name-services-dns-configuration"></a>Etki Alanı Hizmetleri (DNS) yapılandırması
Power BI mobil uygulamasının bağlanacağı ortak URL'yi belirlemeniz gerekir. Örneğin, URL aşağıdakine benzer olabilir.

```
https://reports.contoso.com
```

**Raporlar** için DNS kaydınızı Web Uygulaması Ara Sunucusu'nun (WAP) genel IP adresine yönlendirmeniz gerekir. Ayrıca, ADFS sunucunuz için bir genel DNS kaydı yapılandırmanız gerekir. Örneğin, ADFS sunucusunu şu URL ile yapılandırmış olabilirsiniz.

```
https://fs.contoso.com
```

WAP uygulamasının bir parçası olarak yayımlanacağından **fs** için DNS kaydınızı Web Uygulaması Ara Sunucusu'nun (WAP) genel IP adresine yönlendirmeniz gerekir.

## <a name="certificates"></a>Sertifikalar
Hem WAP uygulaması hem de ADFS sunucusu için sertifikalar yapılandırmanız gerekir. Her iki sertifika da mobil cihazlarınız tarafından tanınan geçerli bir sertifikanın parçası olmalıdır.

## <a name="reporting-services-configuration"></a>Reporting Services yapılandırması
Reporting Services tarafında yapılandırılacak çok fazla ayar yoktur. Sadece doğru Kerberos kimlik doğrulamasının gerçekleştirilebilmesi için geçerli bir Hizmet Asıl Adı'na (SPN) sahip olduğumuzdan ve Reporting Services sunucusunun, anlaşma kimlik doğrulaması için etkinleştirildiğinden emin olmamız gerekir.

### <a name="service-principal-name-spn"></a>Hizmet Asıl Adı (SPN)
SPN, Kerberos kimlik doğrulaması kullanan bir hizmet için benzersiz bir tanımlayıcıdır. Rapor sunucunuz için doğru bir HTTP SPN'sine sahip olduğunuzdan emin olmanız gerekir.

Rapor sunucunuz için doğru Hizmet Asıl Adı'nı (SPN) yapılandırma hakkında bilgi almak isterseniz bkz. [Register a Service Principal Name (SPN) for a Report Server (Rapor Sunucusu için bir Hizmet Asıl Adı (SPN) kaydı yapma)](https://msdn.microsoft.com/library/cc281382.aspx).

### <a name="enabling-negotiate-authentication"></a>Anlaşma kimlik doğrulamasını etkinleştirme
Kerberos kimlik doğrulamasını kullanmak üzere bir rapor sunucusunu etkinleştirmek için rapor sunucusunun Kimlik Doğrulaması Türü'nü RSWindowsNegotiate olacak şekilde yapılandırmanız gerekir. Bu, rsreportserver.config dosyasında gerçekleştirilir.

```
<AuthenticationTypes>  
    <RSWindowsNegotiate />  
    <RSWindowsKerberos />  
    <RSWindowsNTLM />  
</AuthenticationTypes>
```

Daha fazla bilgi için bkz. [Modify a Reporting Services Configuration File (Bir Reporting Services Yapılandırma Dosyasını değiştirme)](https://msdn.microsoft.com/library/bb630448.aspx) ve [Configure Windows Authentication on a Report Server (Bir Rapor Sunucusunda Windows Kimlik Doğrulamasını yapılandırma)](https://msdn.microsoft.com/library/cc281253.aspx).

## <a name="active-directory-federation-services-adfs-configuration"></a>Active Directory Federasyon Hizmetleri (ADFS) Yapılandırması
ADFS'yi ortamınızda bir Windows 2016 sunucusunda yapılandırmanız gerekir. Bu işlem, Sunucu Yöneticisi aracılığıyla ve Yönet bölümündeki Rol ve Özellik Ekle seçeneği belirlenerek gerçekleştirilebilir. Daha fazla bilgi için bkz. [Active Directory Federasyon Hizmetleri](https://technet.microsoft.com/windows-server-docs/identity/active-directory-federation-services).

### <a name="create-an-application-group"></a>Bir uygulama grubu oluşturma
AD FS Yönetimi ekranında, Reporting Services için Power BI Mobil uygulamalarına yönelik bilgiler içeren bir uygulama grubu oluşturmak istiyorsunuz.

Uygulama grubunu, aşağıdaki adımları uygulayarak oluşturabilirsiniz.

1. AD FS Yönetimi uygulamasında **Uygulama Grupları**'na sağ tıklayın ve **Uygulama Grubu ekle…** seçeneğini belirleyin.
   
   ![](media/mobile-oauth-ssrs/adfs-add-application-group.png)
2. Uygulama Grubu Sihirbazı Ekle penceresinde, uygulama grubu için bir **ad** belirtin ve **Bir Web API'sine erişen yerel uygulama**'yı seçin.
   
   ![](media/mobile-oauth-ssrs/adfs-application-group-wizard1.png)
3. **Sonraki** seçeneğini belirleyin.
4. Eklediğiniz uygulama için bir **ad** girin. 
5. **İstemci Kimliği** sizin için otomatik olarak oluşturulacak olsa da hem iOS hem de Android için *484d54fc-b481-4eee-9505-0258a1913020* girin.
6. Aşağıdaki **Yeniden Yönlendirme URL'lerini** ekleyebilirsiniz:
   
   **Power BI Mobil – iOS için girişler:**  
   msauth://code/mspbi-adal://com.microsoft.powerbimobile  
   msauth://code/mspbi-adalms://com.microsoft.powerbimobilems  
   mspbi-adal://com.microsoft.powerbimobile  
   mspbi-adalms://com.microsoft.powerbimobilems
   
   **Android Uygulamaları için yalnızca şunlar gerekir:**  
   urn:ietf:wg:oauth:2.0:oob
   
   ![](media/mobile-oauth-ssrs/adfs-application-group-wizard2.png)
7. **Sonraki** seçeneğini belirleyin.
8. Rapor Sunucunuzun URL'sini sağlayın. Bu, Web Uygulaması Ara Sunucunuza yönelik dış URL'dir. Aşağıdaki biçimde olmalıdır.
   
   > [!NOTE]
   > URL büyük/küçük harfe duyarlıdır!
   > 
   > 
   
   *https://<url to report server>/reports*
   
   ![](media/mobile-oauth-ssrs/adfs-application-group-wizard3.png)
9. **Sonraki** seçeneğini belirleyin.
10. Kuruluşunuzun gereksinimlerine uyan **Erişim Denetimi İlkesi**'ni seçin.
    
    ![](media/mobile-oauth-ssrs/adfs-application-group-wizard4.png)
11. **Sonraki** seçeneğini belirleyin.
12. **Sonraki** seçeneğini belirleyin.
13. **Sonraki** seçeneğini belirleyin.
14. **Kapat**'ı seçin.

Tamamlandığında, aşağıda gösterilen şekilde uygulama grubunuzun özelliklerini görürsünüz.

![](media/mobile-oauth-ssrs/adfs-application-group.png)

## <a name="web-application-proxy-wap-configuration"></a>Web Uygulaması Ara Sunucusu (WAP) Yapılandırması
Ortamınızdaki bir sunucuda Web Uygulaması Ara Sunucusu (Rol) Windows Rolünü etkinleştirmeniz gerekir. Bu bir Windows 2016 sunucusu olmalıdır. Daha fazla bilgi için bkz. [Web Application Proxy in Windows Server 2016 (Windows Server 2016'daki Web Uygulaması Ara Sunucusu)](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/web-application-proxy-windows-server) ve [Publishing Applications using AD FS Preauthentication (AD FS Ön Kimlik Doğrulaması ile Uygulama Yayımlama)](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/publishing-applications-using-ad-fs-preauthentication#a-namebkmk14apublish-an-application-that-uses-oauth2-such-as-a-windows-store-app).

### <a name="constrained-delegation-configuration"></a>Kısıtlanmış temsil yapılandırması
OAuth kimlik doğrulamasından Windows kimlik doğrulamasına geçmek için protokol geçişi ile kısıtlanmış temsil kullanmamız gerekir. Bu, Kerberos yapılandırmasının bir parçasıdır. Reporting Services SPN'sini Reporting Services yapılandırmasında zaten tanımladık.

Active Directory'deki WAP Sunucusu makine hesabında kısıtlanmış temsil yapılandırması gerçekleştirmemiz gerekir. Active Directory'ye yönelik haklara sahip değilseniz bir etki alanı yöneticisiyle birlikte çalışmanız gerekebilir.

Kısıtlanmış temsil yapılandırması gerçekleştirmek için şunları yapmanız gerekir.

1. Active Directory araçlarının yüklü olduğu bir makinede **Active Directory Kullanıcıları ve Bilgisayarları**'nı başlatın.
2. WAP sunucunuzun makine hesabını bulun. Varsayılan olarak bu, bilgisayarlar kapsayıcısındadır.
3. WAP sunucusuna sağ tıklayıp **Özellikler** seçeneğine gidin.
4. **Temsilci Seçme** sekmesini seçin.
5. **Bu bilgisayara yalnızca belirtilen hizmetlere temsilci seçmek için güven** ve ardından **Herhangi bir kimlik doğrulama protokolünü kullan** seçeneklerini belirleyin.
   
   ![](media/mobile-oauth-ssrs/wap-contrained-delegation1.png)
   
   Bu işlem, bu WAP Sunucusu makine hesabı için kısıtlanmış temsili ayarlar. Ardından, bu makinenin temsilci olarak seçebileceği hizmetleri belirtmemiz gerekir.
6. Hizmetler kutusu altındaki **Ekle...** seçeneğini belirleyin.
   
   ![](media/mobile-oauth-ssrs/wap-contrained-delegation2.png)
7. **Kullanıcı/Bilgisayar...** seçeneğini belirleyin.
8. Reporting Services için kullandığınız hizmet hesabını girin. Bu hesap, Reporting Services yapılandırmasında SPN'yi eklediğiniz hesaptır.
9. Reporting Services SPN'sini seçip **Tamam** seçeneğini belirleyin.
   
   > [!NOTE]
   > Yalnızca NetBIOS SPN'sini görebilirsiniz. Varsa hem NetBIOS hem de FQDN SPN'si seçilir.
   > 
   > 
   
   ![](media/mobile-oauth-ssrs/wap-contrained-delegation3.png)
10. **Genişletilmiş** onay kutusu işaretli olduğunda sonuç aşağıdaki gibi görünür.
    
    ![](media/mobile-oauth-ssrs/wap-contrained-delegation4.png)
11. **Tamam**'ı seçin.

### <a name="add-wap-application"></a>WAP Uygulaması ekleme
Report Access Management Console'dan (Rapor Erişimi Yönetim Konsolu) uygulama yayımlayabiliyor olsanız da uygulamayı PowerShell aracılığıyla oluşturmak istiyoruz. Uygulama ekleme komutu aşağıdaki gibidir.

```
Add-WebApplicationProxyApplication -Name "Contoso Reports" -ExternalPreauthentication ADFS -ExternalUrl https://reports.contoso.com/reports/ -ExternalCertificateThumbprint "0ff79c75a725e6f67e3e2db55bdb103efc9acb12" -BackendServerUrl http://ContosoSSRS/reports/ -ADFSRelyingPartyName "Reporting Services - Web API" -BackendServerAuthenticationSPN "http/ContosoSSRS.contoso.com" -UseOAuthAuthentication
```

| Parametre | Yorumlar |
| --- | --- |
| **ADFSRelyingPartyName** |Bu, ADFS'de Uygulama Grubu'nun parçası olarak oluşturduğunuz WEB API'si adıdır. |
| **ExternalCertificateThumbprint** |Bu, dış kullanıcılar için kullanılacak sertifikadır. Bu sertifikanın mobil cihazlarda geçerli olması ve güvenilir bir sertifika yetkilisi tarafından verilmiş olması önemlidir. |
| **BackendServerUrl** |Bu, WAP sunucusundan Rapor Sunucusu'na bağlanılmasını sağlayan URL'dir. WAP sunucusu bir DMZ ise bir tam etki alanı adı kullanmanız gerekebilir. Bu URL'yi WAP sunucusundaki web tarayıcısından açabileceğinizden emin olun. |
| **BackendServerAuthenticationSPN** |Bu, Reporting Services yapılandırmasının parçası olarak oluşturduğunuz SPN'dir. |

### <a name="setting-integrated-authentication-for-the-wap-application"></a>WAP Uygulaması için Tümleşik Kimlik Doğrulaması ayarlama
WAP Uygulaması'nı ekledikten sonra BackendServerAuthenticationMode ayarını IntegratedWindowsAuthentication'ı kullanabilecek şekilde yapmanız gerekir. Bunu ayarlamak için WAP Uygulaması'ndan kimlik bilgisini edinmeniz gerekir.

```
Get-WebApplicationProxyApplication “Contoso Reports” | fl
```

![](media/mobile-oauth-ssrs/wap-application-id.png)

BackendServerAuthenticationMode'u ayarlamak için WAP Uygulaması Kimliği'ni kullanarak aşağıdaki komutu çalıştırın.

```
Set-WebApplicationProxyApplication -id 30198C7F-DDE4-0D82-E654-D369A47B1EE5 -BackendServerAuthenticationMode IntegratedWindowsAuthentication
```

![](media/mobile-oauth-ssrs/wap-application-backendauth.png)

## <a name="connecting-with-the-power-bi-mobile-app"></a>Power BI Mobil Uygulaması ile bağlanma
Power BI mobil uygulamasında Reporting Services örneğinize bağlanmak istiyorsunuz. Bunun için WAP Uygulamanıza yönelik **Dış URL**'yi sağlayın.

![](media/mobile-oauth-ssrs/powerbi-mobile-app1.png)

**Bağlan**'ı seçtiğinizde ADFS oturum açma sayfasına yönlendirilirsiniz. Etki alanınız için geçerli olan kimlik bilgilerini girin.

![](media/mobile-oauth-ssrs/powerbi-mobile-app2.png)

**Oturum aç**'ı seçtikten sonra Reporting Services sunucunuzdaki öğeleri görürsünüz.

![](media/mobile-oauth-ssrs/powerbi-mobile-app2.png)

## <a name="multi-factor-authentication"></a>Çok faktörlü kimlik doğrulaması
Ortamınıza yönelik ek güvenlik sağlamak için çok faktörlü kimlik doğrulamasını etkinleştirebilirsiniz. Daha fazla bilgi için bkz. [Configure AD FS 2016 and Azure MFA (AD FS 2016 ve Azure MFA'yı yapılandırma)](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/configure-ad-fs-2016-and-azure-mfa).

## <a name="troubleshooting"></a>Sorun giderme
**Şu hatayı alırsınız: SSRS Sunucusunda oturum açılamadı. Lütfen sunucu yapılandırmasını doğrulayın.**

![](media/mobile-oauth-ssrs/powerbi-mobile-error.png)

[Fiddler](http://www.telerik.com/fiddler)'i mobil cihazlarınız için bir ara sunucu görevi görecek şekilde ayarlayarak isteğin ne ölçüde başarılı olduğunu görebilirsiniz. Telefonunuz için bir Fiddler ara sunucusu etkinleştirmek üzere Fiddler çalıştıran makinede [iOS ve Android için CertMaker](http://www.telerik.com/fiddler/add-ons) kurulumunu yapmanız gerekir. Bu, Fiddler için Telerik tarafından sağlanan bir eklentidir.

Fiddler kullandığınızda oturum açma işlemi başarılı olursa WAP uygulaması veya ADFS sunucusu ile ilgili bir sertifika sorununuz olabilir. [Microsoft Message Analyzer](https://www.microsoft.com/download/details.aspx?id=44226) gibi bir araç kullanarak sertifikaların geçerliliğini doğrulayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
[Register a Service Principal Name (SPN) for a Report Server (Rapor Sunucusu için bir Hizmet Asıl Adı (SPN) kaydı yapma)](https://msdn.microsoft.com/library/cc281382.aspx)  
[Modify a Reporting Services Configuration File (Bir Reporting Services Yapılandırma Dosyasını değiştirme)](https://msdn.microsoft.com/library/bb630448.aspx)  
[Configure Windows Authentication on a Report Server (Bir Rapor Sunucusunda Windows Kimlik Doğrulamasını yapılandırma)](https://msdn.microsoft.com/library/cc281253.aspx)  
[Active Directory Federation Services (Active Directory Federasyon Hizmetleri)](https://technet.microsoft.com/windows-server-docs/identity/active-directory-federation-services)  
[Web Application Proxy in Windows Server 2016 (Windows Server 2016'daki Web Uygulaması Ara Sunucusu)](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/web-application-proxy-windows-server)  
[Publishing Applications using AD FS Preauthentication (AD FS Ön Kimlik Doğrulaması ile Uygulama Yayımlama)](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/publishing-applications-using-ad-fs-preauthentication#a-namebkmk14apublish-an-application-that-uses-oauth2-such-as-a-windows-store-app)  
[Configure AD FS 2016 and Azure MFA (AD FS 2016 ve Azure MFA'yı yapılandırma)](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/configure-ad-fs-2016-and-azure-mfa)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

