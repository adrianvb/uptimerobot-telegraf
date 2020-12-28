# uptimerobot-telegraf

telegraf config to ingest uptimerobot stats

get your api key from uptimerobot.com and set an environment variable
```
export UPTIMEROBOT_KEY=xxx
```
or if you are using Windows/PowerShell
```
$Env:UPTIMEROBOT_KEY=xxx
```

the included config simply fetches all monitors from uptimerobot and outputs the state and type of the monitor and the last response time to stdout. 
```
telegraf --config uptimerobot.conf --test --quiet
```

looks like this
```
2020-12-28T12:35:20Z I! Starting Telegraf 1.17.0
> uptimerobot,monitor=Website,status=up,type=HTTP,url=https://www.example.com response_time=605 1609160415000000000
```