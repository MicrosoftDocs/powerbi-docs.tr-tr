## <a name="tools-for-troubleshooting"></a>Sorun giderme araçları
<a name="logs" />

### <a name="collecting-logs-from-the-gateway-configurator"></a>Ağ geçidi yapılandırıcısından günlükleri toplama
Ağ geçidi için toplayabileceğiniz birden fazla günlük vardır ve her zaman günlüklerle başlamanız gerekir. Ağ geçidini yükledikten sonra günlükleri toplamanın en kolay yolu, kullanıcı arabirimini kullanmaktır. **Şirket içi veri ağ geçidi** kullanıcı arabiriminde görüntüde belirtilen şekilde **Tanılama**'yı ve ardından sayfanın alt kısmındaki **Günlükleri dışarı aktar** bağlantısını seçin.

![Şirket içi veri ağ geçidi kullanıcı arabirimi günlükleri](./media/gateway-onprem-tshoot-tools-include/gateway-onprem-UI-logs.png)

**Yükleyici günlükleri**

    %localappdata%\Temp\On-premises_data_gateway_*.log

**Yapılandırma günlükleri**

    %localappdata%\Microsoft\On-premises Data Gateway\GatewayConfigurator*.log

**Şirket içi veri ağ geçidi hizmet günlükleri**

    C:\Users\PBIEgwService\AppData\Local\Microsoft\On-premises Data Gateway\Gateway*.log

### <a name="event-logs"></a>Olay Günlükleri
**Şirket içi veri ağ geçidi hizmeti** olay günlükleri, **Uygulama ve Hizmet Günlükleri** altında mevcuttur.

![Şirket içi veri ağ geçidi olay günlükleri](./media/gateway-onprem-tshoot-tools-include/on-prem-data-gateway-event-logs.png)

<a name="fiddler" />

### <a name="fiddler-trace"></a>Fiddler ile İzleme
[Fiddler](http://www.telerik.com/fiddler), Telerik tarafından kullanıma sunulup HTTP trafiğini izleyen ücretsiz bir araçtır.  İstemci makinesinden Power BI hizmetindeki gelen ve giden trafiği görebilirsiniz. Bu sayede hataları ve diğer ilgili bilgileri görüntüleyebilirsiniz.

![](media/gateway-onprem-tshoot-tools-include/fiddler.png)

