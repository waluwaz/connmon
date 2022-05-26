# connmon
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/91af8db9cd354643a8ef6a7117be90fb)](https://www.codacy.com/app/jackyaz/connmon?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=jackyaz/connmon&amp;utm_campaign=Badge_Grade)
![Shellcheck](https://github.com/jackyaz/connmon/actions/workflows/shellcheck.yml/badge.svg)

THIS IS AN EXPERIMENT BUILDING UPON THE INCREDIBLE WORK OF JACKYAZ. IT ALLOWS PINGING SEVERAL SERVERS, not always the same. It also allows running ping for more than the maximum duration in Jack's version. It requires "coding" (incl. hard-coding the target servers in the schell script).

There are some hardcoded ping targets (look in the shell script, and adapt the shell script to your needs), plus the target defined in the Web UI
The whole thing is repeated as often as defined in the Web UI (e.g. cron), just as with Jack's version.
Each target is pinged for a duration that is indirectly derived from the value in the Web UI: for instance: pingduration=$(( pingduration*10+3 ))    (so define 22 in the UI and get 223 seconds). The exact formula varies more often than I update the documentation. So, check the code for the actual current formula.
I run the whole thing every 12 minutes and it gives me almost uninterrupted monitoring 24/7.

ALL CREDITS go to Jack, all bugs to me.

THE DOCUMENTATION BELOW is reproduced from the documentation of the original connmon.
My connmon requires you to replace the connmon file in /jffs/scripts, with the shell script from this repository. Having a backup of the script of Jack is a good idea. The file must have the X right. Consider using chmod a+x belmon. My script will roguely stick the ping results in the database of Jack. It might allow switching from the original connmon to this in a rather smooth way.
***************************************

## v3.0.2
### Updated on 2022-01-06
## About
connmon is an internet connection monitoring tool for AsusWRT Merlin with charts for daily, weekly and monthly summaries.

connmon is free to use under the [GNU General Public License version 3](https://opensource.org/licenses/GPL-3.0) (GPL 3.0).

### Supporting development
Love the script and want to support future development? Any and all donations gratefully received!

| [![paypal](https://www.paypalobjects.com/en_GB/i/btn/btn_donate_LG.gif)](https://www.paypal.com/donate/?hosted_button_id=47UTYVRBDKSTL) <br /><br /> [**PayPal donation**](https://www.paypal.com/donate/?hosted_button_id=47UTYVRBDKSTL) | [![paypal](https://puu.sh/IAhtp/3788f3a473.png)](https://www.paypal.com/donate/?hosted_button_id=47UTYVRBDKSTL) |
| :----: | --- |

## Supported firmware versions
You must be running firmware Merlin 384.15/384.13_4 or Fork 43E5 (or later) [Asuswrt-Merlin](https://www.asuswrt-merlin.net/)

## Installation
Using your preferred SSH client/terminal, copy and paste the following command, then press Enter:
```sh
/usr/sbin/curl -fsL --retry 3 "https://jackyaz.io/connmon/master/install/connmon.sh" -o "/jffs/scripts/connmon" && chmod 0755 /jffs/scripts/connmon && /jffs/scripts/connmon install
```

## Usage
### WebUI
connmon can be configured via the WebUI, in the Addons section.

### Command Line
To launch the connmon menu after installation, use:
```sh
connmon
```

If this does not work, you will need to use the full path:
```sh
/jffs/scripts/connmon
```

## Screenshots
![WebUI1](https://puu.sh/I7cBZ/30524b48ae.png)

![WebUI2](https://puu.sh/I7cC0/3433cf06f7.png)

![WebUI3](https://puu.sh/I7cBY/6affedcc64.png)

![WebUI4](https://puu.sh/I7cBX/7f2d2e0ec5.png)

![CLI UI](https://puu.sh/I7cBV/62329495d3.png)

## Help
Please post about any issues and problems here: [Asuswrt-Merlin AddOns on SNBForums](https://www.snbforums.com/forums/asuswrt-merlin-addons.60/?prefix_id=18)

### Scarf Gateway
Installs and updates for this addon are redirected via the [Scarf Gateway](https://about.scarf.sh/scarf-gateway) by [Scarf](https://about.scarf.sh/about). This allows me to gather data on the number of new installations of my addons, how often users check for updates and more. This is purely for my use to actually see some usage data from my addons so that I can see the value provided by my continued work. It does not mean I am going to start charging to use my addons. My addons have been, are, and will always be completely free to use.

Please refer to Scarf's [Privacy Policy](https://about.scarf.sh/privacy) for more information about the data that is collected and how it is processed.
