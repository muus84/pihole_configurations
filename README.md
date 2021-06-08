# description 
Contains all needed information to get a pihole up and running (NO BACKUPS)

## pihole installation
A High Endurance microSD card should definitely be used. [Amazon link](https://www.amazon.de/gp/product/B07PLVV1QH/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1)
1. Install pi image image: [Link](https://www.raspberrypi.org/software/)
2. Install pihole: Those who want to get started quickly and conveniently may install Pi-hole using the following command:
```bash
curl -sSL https://install.pi-hole.net | bash
```

## pihole configuration 

### blacklisting domain based
[Unified hosts + fakenews + gambling](https://raw.githubusercontent.com/StevenBlack/hosts/master/alternates/fakenews-gambling/hosts)

Source: https://github.com/StevenBlack/hosts

### blacklisting regex filter based (one filter rule per line)
```regex
 ^(.+[_.-])?adse?rv(er?|ice)?s?[0-9]*[_.-]
 (.+[_.-])?telemetry[_.-]
 ^ad([sxv]?[0-9]*|system)[_.-]([^.[:space:]]+\.){1,}|[_.-]ad([sxv]?[0-9]*|system)[_.-]
 ^adim(age|g)s?[0-9]*[_.-]
 ^adtrack(er|ing)?[0-9]*[_.-]
 ^advert(s|is(ing|ements?))?[0-9]*[_.-]
 ^aff(iliat(es?|ion))?[_.-]
 ^analytics?[_.-]
```

## tips and tricks

### how to disable pihole for 5 minutes using the pihole api token
1.  Get your API token http://{PIHOLEIP}/admin/scripts/pi-hole/php/api_token.php
2.  Copy token
3.  http://{PIHOLEIP}/admin/api.php?disable=300&auth={APITOKEN}

