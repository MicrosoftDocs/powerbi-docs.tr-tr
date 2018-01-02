## <a name="how-the-gateway-works"></a>Ağ geçidi nasıl çalışır?
![Şirket içi ağ geçidi nasıl çalışır?](./media/gateway-onprem-how-it-works-include/on-prem-data-gateway-how-it-works.png)

Öncelikle bir kullanıcı, şirket içi veri kaynağına bağlı bir öğeyle etkileşim kurduğunda gerçekleşen işlemlere göz atalım. 

> [!NOTE]
> Power BI'da ağ geçidi için bir veri kaynağı yapılandırmanız gerekir.
> 
> 

1. Bulut hizmeti tarafından bir sorgu oluşturulur ve şirket içi veri kaynağı için şifrelenmiş kimlik bilgileriyle birlikte ağ geçidinin işlemesi için kuyruğa gönderilir.
2. Ağ geçidi bulut hizmeti, sorguyu çözümler ve isteği [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/)'a gönderir.
3. Şirket içi veri ağ geçidi, [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/)'ta bekleyen istekler olup olmadığını yoklar.
4. Ağ geçidi sorguyu alır, kimlik bilgilerinin şifresini çözer ve bu kimlik bilgileriyle veri kaynaklarına bağlanır.
5. Ağ geçidi, yürütme için sorguyu veri kaynağına gönderir.
6. Sonuçlar, veri kaynağından ağ geçidine ve ardından bulut hizmetine geri gönderilir. Ardından, hizmet bu sonuçları kullanır.

