## <a name="tools-for-troubleshooting"></a>Инструменты для устранения неполадок
<a name="logs" />

### <a name="collecting-logs-from-the-gateway-configurator"></a>Сбор журналов из конфигуратора шлюзов
Для шлюза доступно несколько разных журналов. Всегда начинайте проверку с журналов. Проще всего собирать журналы после установки шлюза через пользовательский интерфейс. В пользовательском интерфейсе **локального шлюза данных** выберите **Диагностика** и щелкните ссылку **Экспортировать журналы** в нижней части страницы, как показано на изображении ниже.

![on-prem-data-gateway-UI-logs](./media/gateway-onprem-tshoot-tools-include/gateway-onprem-UI-logs.png)

**Журналы установщика**

    %localappdata%\Temp\On-premises_data_gateway_*.log

**Журналы конфигурации**

    %localappdata%\Microsoft\on-premises data gateway\GatewayConfigurator*.log

**Журналы службы локального шлюза данных**

    C:\Users\PBIEgwService\AppData\Local\Microsoft\on-premises data gateway\Gateway*.log

### <a name="event-logs"></a>Журналы событий
Журналы событий **службы локального шлюза данных** расположены в разделе **Журналы приложения и служб**.

![on-prem-data-gateway-event-logs](./media/gateway-onprem-tshoot-tools-include/on-prem-data-gateway-event-logs.png)

<a name="fiddler" />

### <a name="fiddler-trace"></a>Трассировка Fiddler
[Fiddler](http://www.telerik.com/fiddler) — это бесплатный инструмент от Telerik, отслеживающий трафик HTTP.  Вы можете просматривать всю работу службы Power BI с клиентского компьютера. Это позволяет найти ошибки и другие связанные сведения.

![](media/gateway-onprem-tshoot-tools-include/fiddler.png)

