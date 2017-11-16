## <a name="firewall-or-proxy"></a>Брандмауэр или прокси-сервер
Дополнительные сведения о настройке прокси-сервера для шлюза см. в разделе [Настройка параметров прокси-сервера для шлюзов Power BI](../service-gateway-proxy.md).

Возможно, ваш брандмауэр или прокси-сервер блокирует подключения. Чтобы это проверить, выполните команду [Test-NetConnection](https://technet.microsoft.com/library/dn372891.aspx) в командной строке PowerShell. Эта команда выполняет проверку подключения к служебной шине Azure. При этом проверяется только возможность подключения к сети, а не работоспособность облачной серверной службы или шлюза. Этот способ помогает выяснить, подключен ли ваш компьютер к Интернету.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Команда Test-NetConnection доступна только в Windows Server 2012 R2 и более поздних версиях. Ее также можно выполнить в Windows 8.1 и более поздних версиях. Для проверки подключения к порту в более ранних версиях ОС можно использовать Telnet.
> 
> 

Результат должен выглядеть следующим образом. Отличие может быть в значении параметра TcpTestSucceeded. Если значение **TcpTestSucceeded** не *true*, это указывает на блокировку брандмауэра.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Чтобы выполнить более полную проверку, замените значения параметров **ComputerName** и **Port** значениями, указанными для [портов](../service-gateway-onprem.md#ports).

Возможно, брандмауэр также блокирует подключения служебной шины Azure к центрам данных Azure. В этом случае вам придется добавить в список разрешений (разблокировать) IP-адреса центров данных своего региона. Найти список IP-адресов Azure можно [здесь](https://www.microsoft.com/download/details.aspx?id=41653).

