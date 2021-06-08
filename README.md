### pihole configuration repo
Contains all need information to get my pihole up and running (NO BACKUPS)

#### Blacklisting domain based
[Unified hosts + fakenews + gambling](https://raw.githubusercontent.com/StevenBlack/hosts/master/alternates/fakenews-gambling/hosts)
Source: https://github.com/StevenBlack/hosts

#### Blacklisting regex filter based (one filter rule per line)
```
 ^(.+[_.-])?adse?rv(er?|ice)?s?[0-9]*[_.-]
 (.+[_.-])?telemetry[_.-]
 ^ad([sxv]?[0-9]*|system)[_.-]([^.[:space:]]+\.){1,}|[_.-]ad([sxv]?[0-9]*|system)[_.-]
 ^adim(age|g)s?[0-9]*[_.-]
 ^adtrack(er|ing)?[0-9]*[_.-]
 ^advert(s|is(ing|ements?))?[0-9]*[_.-]
 ^aff(iliat(es?|ion))?[_.-]
 ^analytics?[_.-]
```

### Tips and tricks

#### How to disable pihole for 5 minutes using the pihole api token
1.  Get your API token http://{PIHOLEIP}/admin/scripts/pi-hole/php/api_token.php
2.  Copy token
3.  http://{PIHOLEIP}/admin/api.php?disable=300&auth={APITOKEN}

