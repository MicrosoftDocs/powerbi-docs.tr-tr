## <a name="firewall-or-proxy"></a>Güvenlik Duvarı veya Ara Sunucu
Ağ geçidinize ara sunucu bilgilerini girme hakkında daha fazla bilgi için bkz. [Power BI ağ geçitleri için ara sunucu ayarlarını yapılandırma](../service-gateway-proxy.md).

Güvenlik duvarınızın veya ara sunucunuzun bağlantıları engelleyip engellemediğini test etmek için PowerShell isteminden [Test-NetConnection](https://docs.microsoft.com/powershell/module/nettcpip/test-netconnection) komutunu çalıştırabilirsiniz. Bu komut, Azure Service Bus bağlantısını test eder. Bu yalnızca ağ bağlantısını test eder ve bulut sunucusu hizmeti veya ağ geçidi ile ilgili değildir. Makinenizin gerçekten İnternet'e bağlanıp bağlanamadığını belirlemenize yardımcı olur.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Test-NetConnection komutu yalnızca Windows Server 2012 R2 ve üzerinde kullanılabilir. Windows 8.1 ve üzeri sürümlerde de kullanılabilir. Daha eski işletim sistemi sürümlerinde bağlantı noktalarının durumunu kontrol etmek için Telnet uygulamasını kullanabilirsiniz.
> 
> 

Sonuçlar aşağıdakine benzer olmalıdır. Fark TcpTestSucceeded bölümünde olacaktır. **TcpTestSucceeded** değeri *true* değilse bir güvenlik duvarı sizi engelliyor olabilir.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Testin daha kapsamlı olmasını istiyorsanız **ComputerName** ve **Port** değerlerini [bağlantı noktaları](../service-gateway-onprem.md#ports) bölümünde listelenen değerlerle değiştirin.

Güvenlik duvarı, Azure Service Bus'ın Azure veri merkezleriyle bağlantısını da engelliyor olabilir. Bu durumda, söz konusu veri merkezleri için bölgenize yönelik IP adreslerini beyaz listeye almak (engellemesini kaldırmak) istersiniz. [Buradan](https://www.microsoft.com/download/details.aspx?id=41653) Azure IP adreslerinin listesine ulaşabilirsiniz.

