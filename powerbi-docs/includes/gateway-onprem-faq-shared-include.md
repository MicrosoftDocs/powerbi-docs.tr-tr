## <a name="general"></a>Genel
**Soru:** Asıl Windows hizmetinin adı nedir?  
**Cevap:** Hizmetler bağlamında ağ geçidi, şirket içi veri ağ geçidi hizmeti olarak adlandırılır

**Soru:** Ağ geçidine ilişkin gereksinimler nelerdir?  
**Cevap:** [Ağ geçidi ile ilgili temel bilgilerin ele alındığı makaledeki](../service-gateway-onprem.md) gereksinimler bölümüne göz atın.

**Soru:** Ağ geçidi ile hangi veri kaynakları desteklenir?  
**Cevap:** [Ağ geçidi ile ilgili temel bilgilerin ele alındığı makaledeki](../service-gateway-onprem.md) veri kaynakları tablosuna bakın.

**Soru:** Azure SQL Veritabanı gibi bulut veri kaynakları için bir ağ geçidine ihtiyacım var mı?  
**Cevap:** Hayır! Hizmet bu veri kaynağıyla bir ağ geçidi olmadan bağlantı kurar.

**Soru:** Buluttan ağ geçidine herhangi bir gelen bağlantı var mı?  
**Cevap:** Hayır. Ağ geçidi, Azure Service Bus'a yönelik giden bağlantılar kullanır.

**Soru:** Giden bağlantıları engellersem ne olur? Neyi açmam gerekir?  
**Cevap:** Ağ geçidinin kullandığı [bağlantı noktalarının listesine](../service-gateway-onprem.md#ports) ve ana bilgisayarlara bakın.

**Soru:** Ağ geçidi, veri kaynağıyla aynı makineye mi yüklenmelidir?  
**Cevap:** Hayır. Ağ geçidi, sağlanan bağlantı bilgilerini kullanarak veri kaynağına bağlanır. Ağ geçidini bu anlamda bir istemci uygulaması olarak düşünün. Yalnızca, sağlanan sunucu adına bağlanabilmesi gerekir.

**Soru:** Ağ geçidinden bir veri kaynağına yönelik sorgular çalıştırılırken karşılaşılan gecikme süresi nedir? En iyi mimari nedir?  
**Cevap:** Ağ gecikmesini önlemek için ağ geçidinin veri kaynağına mümkün olduğunca yakın tutulması tavsiye edilir. Ağ geçidini gerçek veri kaynağına yükleyebilirseniz gecikme süresi en aza indirilir. Veri merkezlerini de göz önünde bulundurun. Örneğin, hizmetiniz West US veri merkezini kullanıyorsa ve bir Azure VM'de SQL Server barındırıyorsanız söz konusu Azure VM'nin de West US'te bulunmasında yarar vardır. Bu, gecikme süresini en aza indirir ve Azure VM'de çıkışlar için ücretlendirme yapılmasını önler.

**Soru:** Ağ bant genişliğine yönelik herhangi bir gereksinim var mıdır?  
**Cevap:** Ağ bağlantınız için iyi bir aktarım hızının olması önerilir. Her ortam farklıdır ve bu durum gönderilmekte olan veri miktarına da bağlıdır. ExpressRoute'un kullanılması, şirket içi ve Azure veri merkezleri arasında belirli bir aktarım hızı düzeyinin garanti edilmesine yardımcı olabilir.

Aktarım hızınızı ölçmenize yardımcı olması için 3. taraf [Azure Speed Test uygulamasını](http://azurespeedtest.azurewebsites.net/) kullanabilirsiniz.

**Soru:** Ağ geçidi Windows hizmeti, bir Azure Active Directory hesabıyla çalıştırılabilir mi?  
**Cevap:** Hayır. Windows hizmetinin geçerli bir Windows hesabının olması gerekir. Varsayılan olarak, *NT SERVICE\PBIEgwService* Hizmet SID'si ile çalışır.

**Soru:** Sonuçlar buluta nasıl geri gönderilir?  
**Cevap:** Bu, Azure Service Bus aracılığıyla gerçekleştirilir. Daha fazla bilgi için, ağ geçidinin [nasıl çalıştığına](../service-gateway-onprem.md#how-the-gateway-works) göz atın.

**Soru:** Kimlik bilgilerim nerede depolanır?  
**Cevap:** Bir veri kaynağı için girdiğiniz kimlik bilgileri, ağ geçidi bulut hizmetinde şifrelenmiş olarak depolanır. Şirket içi ağ geçidinde kimlik bilgilerinin şifresi çözülür.

**Soru:** Ağ geçidini bir çevre ağına (ayrıca DMZ, arındırılmış bölge ve denetimli alt ağ olarak da bilinir) yerleştirebilir miyim?  
**Cevap:** Ağ geçidi için veri kaynağı bağlantısı gerekir. Çevre ağınızda veri kaynağına erişilemiyorsa ağ geçidi, veri kaynağına bağlanamayabilir. Örneğin, SQL Server'ınız çevre ağınızda olmayabilir. Bu durumda, çevre ağından SQL Server'ınıza bağlanamazsınız. Ağ geçidini çevre ağınıza yerleştirdiyseniz SQL Server'a erişemeyebilir.

**Soru:** Azure Service Bus ile iletişim kurulurken ağ geçidini, TCP yerine HTTPS trafiğini kullanmaya zorlamak mümkün müdür?  
**Cevap:** Evet. Ancak bu, performansı önemli ölçüde azaltır. *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* dosyasını değiştirmeniz gerekir. `AutoDetect` değerini `Https` olarak değiştirmeniz gerekir. Bu dosya varsayılan olarak *C:\Program Files\On-premises data gateway* konumunda bulunur.

**Soru:** Azure Veri Merkezi IP listesini beyaz listeye eklemem gerekir mi? Listeyi nereden bulabilirim?  
**Cevap:** Giden IP trafiğini engelliyorsanız Azure Veri Merkezi IP listesini beyaz liste eklemeniz gerekebilir. Şu anda ağ geçidi, Azure Service Bus ile iletişim kurmak için tam etki alanı adının yanı sıra IP adresini kullanır. Azure Veri Merkezi IP listesi haftalık olarak güncelleştirilir. [Microsoft Azure Veri Merkezi IP listesini](https://www.microsoft.com/download/details.aspx?id=41653) indirebilirsiniz.

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="high-availabilitydisaster-recovery"></a>Yüksek Kullanılabilirlik/Olağanüstü Durum Kurtarma
**Soru:** Ağ geçidi için yüksek kullanılabilirlik senaryolarını hayata geçirmeye yönelik herhangi bir plan var mı?  
**Cevap:** Evet, Power BI ekibi bununla ilgili olarak sürekli çalışmaktadır. Bu özellikle ilgili güncel bilgiler edinmek için [Power BI blogunu](https://powerbi.microsoft.com/blog/) takip edin.

**Soru:** Olağanüstü durum kurtarma için hangi seçenekler kullanılabilir?  
**Cevap:** Bir ağ geçidini geri yüklemek veya taşımak için kurtarma anahtarını kullanabilirsiniz. Ağ geçidini yüklerken kurtarma anahtarını belirtin.

**Soru:** Kurtarma anahtarının avantajı nedir?  
**Cevap:** Ağ geçidi ayarlarınızı geçirmek veya kurtarmak için kullanabileceğiniz bir yol sunar. Bu, olağanüstü durum kurtarma için de kullanılır.

## <a name="troubleshooting"></a>Sorun Giderme
**Soru:** Ağ geçidi günlükleri nerede bulunur?  
**Cevap:** [Sorun giderme makalesindeki](../service-gateway-onprem-tshoot.md#tools-for-troubleshooting) araçlar bölümüne bakın.

**Soru:** Şirket içi veri kaynağına hangi sorguların gönderildiğini nasıl görebilirim?  
**Cevap:** Sorgu izlemeyi etkinleştirebilirsiniz.  Bu sayede, gönderilen sorguları görebilirsiniz. Sorun giderme işlemi tamamlandıktan sonra bu özelliğe ilişkin ayarı özgün değere getirmeyi unutmayın. Sorgu izleme özelliğinin etkin şekilde bırakılması, günlüklerin daha büyük boyutta olmasına neden olur.

Veri kaynağınızda bulunan, sorguları izlemeye yönelik araçlara da göz atabilirsiniz. Örneğin, SQL Server ve Analysis Services için Genişletilmiş Olaylar'ı veya SQL Profiler'ı kullanabilirsiniz.

