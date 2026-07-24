# Nmap 7.99 Expert Option Breakdown (မြန်မာဘာသာဖြင့် ကျွမ်းကျင်သူရှင်းလင်းချက်)

## ၁. TARGET SPECIFICATION (ပစ်မှတ်သတ်မှတ်ခြင်း)

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-iL <file>` | ပစ်မှတ်စာရင်းပါသည့် ဖိုင်မှ scan လုပ်ခြင်း။ | **ဘယ်အချိန်သုံးမလဲ**: ကွန်ရက်ကြီးများ (/16) သို့မဟုတ် စာရင်းရှည်ကြီးများကို scan လုပ်ရန်။ ၎င်းကို `nmap -iL targets.txt -oA scan_result` ဖြင့် အလိုအလျောက် သိမ်းဆည်းပါ။ |
| `-iR <num>` | ကျပန်း (Random) ပစ်မှတ်များကို ရွေးချယ်ခြင်း။ | **သတိပေးချက်**: Internet ပေါ်ရှိ ကျပန်း IP များကို ရိုက်ခတ်ခြင်းသည် **တရားမဝင်နိုင်**ပါ။ Shodan ကဲ့သို့ စူးစမ်းလေ့လာရန်အတွက်သာ ရည်ရွယ်သည်။ |
| `--exclude` | သတ်မှတ်ထားသော host များကို scan မှ ဖယ်ရှားခြင်း။ | **လက်တွေ့အသုံး**: `nmap 192.168.1.0/24 --exclude 192.168.1.1,192.168.1.254` (Gateway နှင့် DNS ကို မထိမိစေရန်)။ |

---

## ၂. HOST DISCOVERY (ကွန်ရက်ရှာဖွေခြင်း)

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-sL` | List Scan - IP စာရင်းကိုသာ စစ်ဆေးပြီး packet မပို့ပါ။ | DNS ပြန်ဆိုခြင်း (Reverse DNS) ကို စမ်းသပ်ရန် သုံးသည်။ ကွန်ရက်အတွင်း မည်သူက မည်သည့် hostname ရှိသည်ကို သိရန် အသုံးဝင်သည်။ |
| `-sn` | Ping Scan - Port scan ကို ကျော်ပြီး host ရှိမရှိသာ စစ်ဆေးသည်။ | **အရေးကြီးဆုံး**: Local LAN တွင် ၎င်းသည် **ARP Request** ကို အသုံးပြုသည်။ Firewall က ICMP ပိတ်ထားသော်လည်း ARP ကြောင့် host ကို ရှာတွေ့နိုင်သည်။ |
| `-Pn` | Host Discovery ကို လုံးဝကျော်ပြီး "အားလုံးအသက်ဝင်သည်" ဟု ယူဆသည်။ | **မဖြစ်မနေသုံးရမည့်နေရာ**: Cloud (AWS/Azure) သို့မဟုတ် ပြင်ပ Firewall များသည် ICMP ကို ပိတ်ထားတတ်သည်။ ဤ flag မပါဘဲ scan လုပ်ပါက "Host seems down" ဟုပြပြီး ရပ်သွားမည်။ |
| `-PS/PA/PU/PY` | TCP SYN, ACK, UDP, SCTP discovery probes များ။ | **နည်းဗျူဟာ**: Firewall က SYN ကိုပိတ်ထားလျှင် `-PA` (ACK) ဖြင့် စမ်းပါ။ အချို့ Firewall များသည် ACK packet ကို "ပြန်လာသော ဆက်သွယ်မှု" ဟု ထင်မှတ်ကာ ဖြတ်သန်းခွင့်ပြုတတ်သည်။ |
| `-PE/PP/PM` | ICMP Echo (Ping), Timestamp, Netmask request များ။ | ရှေးကျသော ကွန်ရက်များတွင် Timestamp (PP) သည် Echo ထက် ပိုမိုထိရောက်နိုင်သည်။ |
| `-n / -R` | `-n` က DNS ကိုလုံးဝမသုံးပါ။ `-R` က အမြဲတမ်း ပြန်ဆိုစေသည်။ | **စွမ်းဆောင်ရည်မြှင့်တင်ရန်**: External scan လုပ်ပါက `-n` ကို အမြဲထည့်ပါ။ DNS ပြန်ဆိုချိန်သည် scan ကို ၂ ဆ နှေးကွေးစေနိုင်သည်။ |
| `--traceroute` | ပစ်မှတ်သို့ သွားရောက်သည့် လမ်းကြောင်း (Hops) ကို ဖော်ပြသည်။ | `-A` flag တွင် ပါဝင်ပြီးသားဖြစ်သည်။ Internal network တွင် Firewall ရှိမရှိ သိရန် အသုံးဝင်သည်။ |

---

## ၃. SCAN TECHNIQUES (Port Scan နည်းလမ်းများ) - **အရေးအကြီးဆုံးအပိုင်း**

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-sS` | **TCP SYN Scan (Half-Open)** | **မူလတန်းပစ္စည်း (Default Weapon)**။ Root လိုအပ်သည်။ 3-way handshake ကို အပြီးမသတ်ဘဲ RST ပို့ချလိုက်သောကြောင့် ပုံမှန် application log များတွင် မပါဝင်တတ်ပါ။ မြန်ဆန်သည်။ |
| `-sT` | **TCP Connect Scan** | Root မလိုအပ်ပါ။ Handshake ကို အပြည့်အဝပြုလုပ်သည်။ Log တွင်ကျန်ရစ်ပြီး IDS က အလွယ်တကူသိရှိနိုင်သည်။ `-sS` မရသောအခါမှသာ သုံးပါ။ |
| `-sA` | **TCP ACK Scan** | **Open ရှိမရှိကို မပြနိုင်ပါ**။ ၎င်းက **Firewall Rule** ကို စစ်ဆေးသည်။ ACK ပြန်လာပါက port က "unfiltered" (Firewall မရှိ)၊ ပြန်မလာပါက "filtered" ဖြစ်သည်။ Firewall စစ်ဆေးရန်သာ သုံးသည်။ |
| `-sW` | **TCP Window Scan** | ACK scan နှင့်ဆင်သော်လည်း TCP Window Size ကို ကြည့်သည်။ ရှေးကျသော OS များတွင် Open port ကို Window size ပြောင်းလဲခြင်းဖြင့် ခွဲခြားနိုင်သည်။ ယနေ့ခေတ်တွင် ယုံကြည်ရမှုနည်းသည်။ |
| `-sM` | **Maimon Scan** | FIN/ACK flag များကို ပို့သည်။ အလွန်ရှေးကျသော BSD စနစ်များအတွက်သာ သက်ဆိုင်သည်။ |
| `-sU` | **UDP Scan** | **နှေးကွေးပြီး ယုံကြည်ရခက်သည်**။ DNS (53), SNMP (161), DHCP (67) တို့အတွက် အရေးကြီးသည်။ မြန်ဆန်စေရန် `--min-rate 100` နှင့် `--max-retries 1` ထည့်သုံးပါ။ |
| `-sN/sF/sX` | **Null, FIN, Xmas Scans** | TCP Header ကို ပုံမှန်မဟုတ်သော Flag များဖြင့် ပို့သည်။ **Stateful Firewall** များကို ကျော်လွှားရန် ရည်ရွယ်သည်။ သို့သော် Windows OS များသည် ဤ packet များကို လျစ်လျူရှုသောကြောင့် ရလဒ်မှားတတ်သည်။ |
| `--scanflags` | Custom TCP Flag (URG, ACK, PSH, etc.) ကိုယ်တိုင်သတ်မှတ်ခြင်း။ | **Advanced Evasion**: ဥပမာ `--scanflags SYNACK` ဖြင့် SYN+ACK ပို့ပါ။ Firewall Signature များကို ရှောင်ရန် ကိုယ်တိုင် စမ်းသပ်ချက်များအတွက် သုံးသည်။ |
| `-sI <zombie>` | **Idle Scan (Zombie Scan)** | **အဆင့်မြင့်ဆုံး Stealth**။ သင်၏ Real IP ကို လုံးဝမပြဘဲ "Zombie" Host (IPID ပြောင်းလဲမှုကို ခန့်မှန်းနိုင်သော) ကို အသုံးပြု၍ scan လုပ်သည်။ အလွန်နှေးကွေးပြီး စနစ်တကျ ပြင်ဆင်မှုလိုအပ်သည်။ |
| `-sO` | **IP Protocol Scan** | TCP/UDP မဟုတ်ဘဲ IP Protocol (ICMP, IGMP, OSPF - Protocol Number 1,2,89) များကို ရှာဖွေသည်။ |
| `-b <FTP>` | **FTP Bounce Scan** | ခေတ်နောက်ကျသော FTP Server များကို အသုံးပြု၍ ပစ်မှတ်ကို scan လုပ်ခြင်း။ ယနေ့ခေတ် Firewall များက ပိတ်ဆို့ထားသောကြောင့် ထိရောက်မှုနည်းသည်။ |

---

## ၄. PORT SPECIFICATION (Port သတ်မှတ်ခြင်း)

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-p <range>` | သတ်မှတ် Port များကိုသာ scan လုပ်ခြင်း။ | **Syntax အရေးကြီး**: `-p U:53,T:80,443` (UDP 53 နှင့် TCP 80,443)။ `-p-` သည် **Port 1-65535** အားလုံးကို scan လုပ်သည် (အချိန်ကြာမြင့်နိုင်)။ |
| `-F` | Fast mode - Top 100 ports ကိုသာ scan လုပ်သည်။ | မူလအခြေအနေတွင် Top 1000 ဖြစ်သည်။ အချိန်တိုအတွင်း ခြုံငုံကြည့်ရန် `-F` ကို အသုံးပြုပါ။ |
| `--top-ports <num>` | လူသုံးအများဆုံး Port ဦးရေကို သတ်မှတ်ခြင်း။ | ဥပမာ `--top-ports 200` သည် လူသုံးအများဆုံး port ၂၀၀ ကို scan လုပ်သည်။ `-F` ထက် ပိုမိုပြောင်းလွယ်သည်။ |
| `--exclude-ports` | သတ်မှတ် Port များကို ကျော်သွားခြင်း။ | Port 22 (SSH) ကို မထိစေလိုပါက `-p- --exclude-ports 22` ဟုသုံးပါ။ |

---

## ၅. SERVICE/VERSION DETECTION (ဝန်ဆောင်မှု ဗားရှင်းဖော်ထုတ်ခြင်း)

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-sV` | Open port များပေါ်ရှိ Service အမည်နှင့် Version ကို ဖော်ထုတ်သည်။ | **Exploit ရှာရန် အခြေခံ**။ Apache 2.2.8 နှင့် 2.4.50 ကွာခြားချက်သည် အားနည်းချက်ရှိမရှိကို ဆုံးဖြတ်ပေးသည်။ |
| `--version-intensity` | 0 (ပေါ့ပါး) မှ 9 (အပြည့်အစုံ) အထိ သတ်မှတ်သည်။ | **အမြန်ဆုံး**: `--version-light` (intensity 2) သည် မြန်ဆန်ပြီး ၉၀% ခန့် တိကျသည်။ `--version-all` (intensity 9) သည် အချိန်ကြာမြင့်ပြီး ကွန်ရက်ပေါ်တွင် ဆူညံသံများစွာ ဖြစ်စေသည်။ |

---

## ၆. SCRIPT SCAN (NSE - Nmap Scripting Engine) - **အစွမ်းထက်ဆုံးကိရိယာ**

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-sC` | Default (Safe) script များကို run သည်။ | `--script=default` နှင့် အတူတူပင်။ ဘေးကင်းသော (crash မဖြစ်စေသော) script များသာ ပါဝင်သည်။ |
| `--script <file/category>` | သတ်မှတ် script သို့မဟုတ် category ကို run ခြင်း။ | **Categories**: `safe`, `intrusive`, `vuln`, `exploit`, `auth`, `brute`, `discovery`။ ဥပမာ `--script vuln` သည် အားနည်းချက်အားလုံးကို ရှာဖွေပေးသည် (သို့သော် ဆူညံနိုင်သည်)။ |
| `--script-args` | Script များသို့ argument များ ပေးပို့ခြင်း။ | ဥပမာ `--script http-enum --script-args http-enum.fingerprintfile=./myfile.txt` |
| `--script-trace` | Script ပို့သမျှ packet အားလုံးကို ပြသသည်။ | Debugging အတွက် အထူးအသုံးဝင်သည်။ |
| `--script-updatedb` | NSE Script Database ကို အပ်ဒိတ်လုပ်ခြင်း။ | Nmap အဟောင်းသုံးပါက တစ်ခါလောက် သုံးသင့်သည်။ |

---

## ၇. OS DETECTION (Operating System ခန့်မှန်းခြင်း)

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-O` | OS Detection ကို ဖွင့်သည်။ | Root အခွင့်အရေး လိုအပ်သည်။ TTL (Linux=64, Windows=128) ကိုကြည့်ရုံမဟုတ်ဘဲ TCP/IP Stack ၏ ထူးခြားချက် (Fingerprint) ကို ခွဲခြမ်းစိတ်ဖြာသည်။ |
| `--osscan-guess` | အတိအကျမသေချာပါက အရိုင်းခန့်မှန်းခြင်း။ | **အသုံးဝင်သည်**: အကယ်၍ Nmap က "Linux 2.6.32 - 3.10" ဟုပြပါက ၎င်းသည် အတိအကျမဟုတ်သော်လည်း ခြုံငုံသိရန် လုံလောက်သည်။ |

---

## ၈. TIMING AND PERFORMANCE (အချိန်နှင့် စွမ်းဆောင်ရည်) - **မြန်ဆန်စေရန် သော့ချက်**

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-T<0-5>` | Timing Template (0=Paranoid, 5=Insane) | **အကောင်းဆုံး**: LAN အတွက် `-T4`၊ Internet အတွက် `-T3`။ `-T5` သည် packet အများအပြား ကျွတ်ထွက်စေနိုင်သည်။ |
| `--min-rate` / `--max-rate` | တစ်စက္ကန့်လျှင် packet အရေအတွက် သတ်မှတ်ခြင်း။ | **အဆင့်မြင့်ထိန်းချုပ်**: `--min-rate 10000` ဖြင့် /24 ကွန်ရက်ကို စက္ကန့်ပိုင်းအတွင်း scan နိုင်သည်။ Firewall ကို မထိခိုက်စေရန် `--max-rate 100` ဖြင့် ကန့်သတ်ပါ။ |
| `--host-timeout` | Host တစ်ခုစီအတွက် အချိန်ကန့်သတ်ချက်။ | နှေးကွေးသော host ကြောင့် scan တစ်ခုလုံး ရပ်မနေစေရန် `--host-timeout 5m` (၅ မိနစ်) သတ်မှတ်ပါ။ |

---

## ၉. FIREWALL/IDS EVASION (ရှောင်ကွင်းနည်းဗျူဟာများ) - **Red Team Core**

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-f` / `--mtu` | Packet ကို အပိုင်းပိုင်းခွဲခြင်း (Fragmentation)။ | ခေတ်မီ Firewall များသည် fragment reassembly ကိုလုပ်သော်လည်း၊ IDS/IPS အဟောင်းများကို ရှောင်ရန် ထိရောက်သည်။ `--mtu 8` ဖြင့် စမ်းသပ်ပါ။ |
| `-D <decoy>` | **Decoy IP များ** ဖြင့် ဖုံးကွယ်ခြင်း။ | `-D RND:10,ME` ဆိုသည်မှာ အတုအယောင် IP ၁၀ ခုနှင့် သင်၏ Real IP ကို ရောနှောပို့ခြင်း။ Target Log တွင် မည်သည်က Real ဖြစ်သည်ကို ခွဲခြားရခက်စေသည်။ **သို့သော်** scan အလွန်နှေးကွေးသွားနိုင်သည်။ |
| `-S <IP>` | Source IP Address ကို အတုလုပ်ခြင်း (Spoofing)။ | ပြန်လာသော packet များကို သင်မမြင်ရသောကြောင့် `-e` (interface) နှင့်တွဲသုံးရမည်။ Internal network တွင် စစ်ဆေးရန်သာ သင့်တော်သည်။ |
| `-g` / `--source-port` | Source Port ကို အတုလုပ်ခြင်း။ | Firewall များသည် Port 53 (DNS) သို့မဟုတ် 80 (HTTP) ကို ယုံကြည်တတ်သည်။ `--source-port 53` ဖြင့် ထို Firewall Rule ကို အလွယ်တကူ ကျော်နိုင်သည်။ |
| `--proxies` | HTTP/SOCKS4 Proxy များမှတစ်ဆင့် ပို့ဆောင်ခြင်း။ | **အထီးကျန် (Anonymity)**: `--proxies socks4://127.0.0.1:9050` (Tor) ဖြင့် သုံးနိုင်သည်။ `proxychains` ထက် ပိုမိုတည်ငြိမ်သည်။ |
| `--spoof-mac` | MAC Address ကို အတုလုပ်ခြင်း။ | Local Switch ပေါ်ရှိ MAC Filtering ကို ကျော်လွှားရန်။ `--spoof-mac 0` က ကျပန်း MAC ပေးသည်။ `--spoof-mac Apple` က Apple Vendor MAC ကိုပေးသည်။ |
| `--badsum` | Checksum မှားယွင်းသော Packet ပို့ခြင်း။ | အချို့ Firewall/IDS များသည် checksum မှားပါက packet ကို လျစ်လျူရှုတတ်သည်။ ၎င်းကို အခွင့်ကောင်းယူ၍ ရှောင်နည်းဖြစ်သည်။ |

---

## ၁၀. OUTPUT (ရလဒ်သိမ်းဆည်းခြင်း)

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-oA <basename>` | **Normal, XML, Grepable** သုံးမျိုးလုံးကို တစ်ပြိုင်နက် သိမ်းဆည်းခြင်း။ | **အကောင်းဆုံး အလေ့အကျင့်**: `-oA scan` ဟုသိမ်းပါ။ XML ကို Metasploit သို့မဟုတ် ElasticSearch သို့ တင်သွင်းနိုင်သည်။ |
| `--resume <file>` | ရပ်သွားသော Scan ကို ပြန်လည်စတင်ခြင်း။ | ကြီးမားသော scan တစ်ခု ပြတ်တောက်သွားပါက `nmap --resume scan.nmap` ဖြင့် အဆက်မပြတ် ပြန်လုပ်နိုင်သည် (အလွန်အသုံးဝင်)။ |
| `--open` | Open (သို့) Possibly open ဖြစ်သော port များကိုသာ ပြသခြင်း။ | ရလဒ်စာရင်းကို တိုစေပြီး အာရုံစိုက်ရန် လွယ်ကူစေသည်။ |
| `-v` (Verbose) | အသေးစိတ် အချက်အလက်များကို ပြသခြင်း။ | `-vv` ဖြင့် ပိုမိုအသေးစိတ်မြင်ရသည်။ Script များ run နေစဉ် တိုးတက်မှုကို မြင်လိုပါက သုံးပါ။ |

---

## ၁၁. MISC (အထွေထွေ)

| Option | အဓိပ္ပါယ် | ကျွမ်းကျင်သူမှတ်ချက် (Pro Tip) |
| :--- | :--- | :--- |
| `-6` | IPv6 Scanning ကို ဖွင့်သည်။ | သတိပြုရန် - IPv6 ကွန်ရက်များတွင် ARP မရှိဘဲ NDP ကို သုံးသည်။ နည်းပညာအရ ကွဲပြားသောကြောင့် LAN တွင် သုံးလျှင် သတိထားပါ။ |
| `-A` | **Aggressive Scan**: OS, Version, Script, Traceroute အားလုံးကို တစ်ပါတည်းလုပ်ဆောင်သည်။ | **အချိန်တိုအတွင်း အချက်အလက်အပြည့်ရရန်**: `sudo nmap -A -T4 target` သည် ကျွမ်းကျင်သူများ၏ နေ့စဉ်သုံး အမိန့်ဖြစ်သည်။ သို့သော် ဆူညံသံများစွာ ဖြစ်စေသောကြောင့် Stealth မလိုအပ်သောနေရာတွင်သာ သုံးပါ။ |
| `--datadir` | Nmap ၏ ပုံမှန် fingerprint နှင့် script ဖိုင်တည်နေရာကို ပြောင်းလဲခြင်း။ | ကိုယ်ပိုင် Custom NSE Script များ ရေးသားပါက ဤနေရာတွင် ထည့်သွင်းနိုင်သည်။ |
| `--privileged` / `--unprivileged` | Raw Socket အခွင့်အရေးကို အတင်းသတ်မှတ်ခြင်း။ | Virtual Environment များတွင် Nmap က "Permission denied" ပြပါက `--unprivileged` ဖြင့် `-sT` သို့ ပြောင်းသွားစေသည်။ |

---

# နိဂုံးနှင့် စစ်ဆင်ရေးအဆင့် Command ပေါင်းစပ် (Pro Combo)

အထက်ပါ Options များကို ပေါင်းစပ်၍ အောက်ပါအတိုင်း **Ultimate Stealth & Performance** Command ကို ရေးဆွဲနိုင်သည်။

**အခြေအနေ**: ပစ်မှတ်သည် Firewall နောက်ကွယ်တွင် ရှိပြီး၊ IDS က စောင့်ကြည့်နေသည်။ ကျွန်ုပ်တို့သည် အမြန်ဆုံးနှင့် ဖုံးကွယ်မှုအမြင့်ဆုံး scan လိုအပ်သည်။

```bash
sudo nmap -sS -Pn -T4 --min-rate 5000 --max-retries 2 -f --mtu 16 --data-length 25 --source-port 53 -D RND:8,ME --spoof-mac 0 -p- --open -sV --version-light -O --osscan-guess --script=vuln,exploit -oA final_stealth_scan 192.168.56.102
```

**ရှင်းလင်းချက်**:
- `-sS`: Stealth SYN
- `-Pn`: Ping ကိုကျော် (Firewall အတွက်)
- `-T4 --min-rate 5000`: အမြန်ဆုံးဖြစ်စေရန်
- `-f --mtu 16`: Packet များကို အကွဲအပြဲဖြစ်စေရန်
- `--data-length 25`: ပုံမှန်မဟုတ်သော packet များဖြင့် IDS ကိုရှုပ်ထွေးစေရန်
- `--source-port 53`: DNS Port အတုလုပ်၍ Firewall ကိုဖြတ်ရန်
- `-D RND:8,ME`: Decoy များဖြင့် Source ကိုဖုံးကွယ်ရန်
- `--spoof-mac 0`: MAC Address အသစ်ဖြင့် Local Switch ကိုရှောင်ရန်
- `-sV --version-light`: ဗားရှင်းကို အမြန်ဆုံးဖော်ထုတ်ရန်
- `--script=vuln,exploit`: အားနည်းချက်များကို အလိုအလျောက်ရှာဖွေရန်

---

# Nmap ကျွမ်းကျင်သူသင်ခန်းစာ (Expert Nmap Tutorial)

## နိဒါန်း (Introduction)

Nmap (Network Mapper) သည် **ကွန်ရက်ရှာဖွေတွေ့ရှိမှုနှင့် လုံခြုံရေးစစ်ဆေးခြင်း (Security Auditing)** အတွက် အသုံးပြုသော အစွမ်းထက်ဆုံးသော open-source ကိရိယာတစ်ခုဖြစ်သည်။ ၎င်းကို Gordon Lyon မှ ၁၉၉၇ ခုနှစ် စက်တင်ဘာလတွင် စတင်တီထွင်ခဲ့ပြီး ယနေ့အချိန်အထိ လုံခြုံရေးကျွမ်းကျင်သူများ၊ ကွန်ရက်စီမံခန့်ခွဲသူများနှင့် Penetration Tester များ၏ မရှိမဖြစ်လက်နက်တစ်ခုဖြစ်နေဆဲဖြစ်သည်။

ဤသင်ခန်းစာသည် Nmap ၏ **အခြေခံမှအဆင့်မြင့်အထိ** ကျယ်ကျယ်ပြန့်ပြန့် သိရှိနိုင်စေရန် ရည်ရွယ်ပါသည်။

## အခန်း ၁: Nmap ထည့်သွင်းခြင်း (Installation)

### Windows တွင် ထည့်သွင်းခြင်း
1.  Nmap တရားဝင် [Download Page](https://nmap.org/download.html) မှ `nmap-<version>-setup.exe` ကိုဒေါင်းလုဒ်လုပ်ပါ။
2.  ဖိုင်ကို run ပြီး installation လုပ်ပါ။
3.  **အရေးကြီး:** Npcap ကို installation လုပ်စဉ် check လုပ်ထားရန် လိုအပ်သည်။ ၎င်းသည် Windows တွင် raw packet ဖမ်းယူနိုင်ရန် ကူညီပေးသည်။

### Linux (Debian/Ubuntu) တွင် ထည့်သွင်းခြင်း
```bash
sudo apt-get update
sudo apt-get install nmap
```

### macOS တွင် ထည့်သွင်းခြင်း
```bash
brew install nmap
```

## အခန်း ၂: အခြေခံအသုံးပြုနည်း (Basic Usage)

Nmap ၏ အခြေခံ syntax မှာ အောက်ပါအတိုင်းဖြစ်သည်:
```bash
nmap <scan_type> <options> <target>
```

### Target (ပစ်မှတ်) သတ်မှတ်နည်းများ

| ပုံစံ | ဥပမာ | ဖော်ပြချက် |
| :--- | :--- | :--- |
| **IP Address တစ်ခုတည်း** | `nmap 192.168.1.1` | တစ်ခုတည်းသော host ကို scan လုပ်ရန်။ |
| **Domain Name** | `nmap scanme.nmap.org` | website တစ်ခုကို scan လုပ်ရန်။ |
| **IP Range** | `nmap 192.168.1.1-50` | IP range တစ်ခုကို scan လုပ်ရန်။ |
| **Subnet (CIDR)** | `nmap 192.168.1.0/24` | ကွန်ရက်တစ်ခုလုံးကို scan လုပ်ရန်။ |
| **ဖိုင်မှ ဖတ်ခြင်း** | `nmap -iL targets.txt` | ပစ်မှတ်များစာရင်းပါသည့် ဖိုင်ကို အသုံးပြုရန်။ |

## အခန်း ၃: Host Discovery (ကွန်ရက်ရှာဖွေခြင်း)

ကွန်ရက်အတွင်း အသက်ဝင်နေသော (live) host များကို ရှာဖွေခြင်းဖြစ်သည်။

*   **Ping Scan (အခြေခံအဆင့်)**: `-sn` flag ကို သုံးသည်။ ၎င်းသည် port scan မလုပ်ဘဲ host ရှိမရှိကိုသာ စစ်ဆေးသည်။
    ```bash
    nmap -sn 192.168.1.0/24
    ```
    > **မှတ်ချက်**: Local network (layer-2) တွင် Nmap သည် ICMP အစား **ARP requests** ကို ဦးစားပေးအသုံးပြုသည်။ ၎င်းသည် firewall ကို ကျော်လွှားပြီး MAC address ကို တိုက်ရိုက်မေးမြန်းနိုင်သည်။

*   **No Ping Scan (Firewall ရှိသည့်နေရာတွင်)**: host အားလုံးကို အသက်ဝင်နေသည်ဟု ယူဆပြီး scan လုပ်သည်။ Firewall က ping ကိုပိတ်ထားလျှင် အသုံးဝင်သည်။
    ```bash
    nmap -Pn 192.168.1.1
    ```

## အခန်း ၄: Port Scanning Techniques (အဆင့်မြင့် Port Scan နည်းလမ်းများ)

### ၄.၁ TCP SYN Scan (Stealth Scan) - `-sS`
"Half-open" scan ဟုလည်းခေါ်သည်။ TCP 3-way handshake ကို အပြည့်အဝမလုပ်ဆောင်ဘဲ SYN packet ပို့ပြီး SYN-ACK ပြန်လာပါက RST packet ဖြင့် connection ကိုချက်ချင်းဖြတ်တောက်သည်။
*   **အားသာချက်**: မြန်ဆန်ပြီး၊ ပုံမှန် connection log များတွင် မပါဝင်တတ်သောကြောင့် **ရှာဖွေတွေ့ရှိရန် ခက်ခဲသည် (Stealth)**။
*   **အားနည်းချက်**: Root/Administrator အခွင့်အရေး လိုအပ်သည်။
    ```bash
    sudo nmap -sS 192.168.1.1
    ```

### ၄.၂ TCP Connect Scan - `-sT`
TCP 3-way handshake ကို အပြည့်အဝပြုလုပ်သည်။
*   **အားသာချက်**: Root အခွင့်အရေး မလိုအပ်ပါ။
*   **အားနည်းချက်**: နှေးကွေးပြီး၊ ရှာဖွေတွေ့ရှိရန် **လွယ်ကူသည် (Detectable)**။
    ```bash
    nmap -sT 192.168.1.1
    ```

### ၄.၃ UDP Scan - `-sU`
UDP protocol ကို အသုံးပြုသည့် port များ (DNS, SNMP, DHCP) ကို ရှာဖွေရန် သုံးသည်။
*   **သတိပြုရန်**: UDP scan သည် TCP scan ထက် **နှေးကွေးပြီး ယုံကြည်ရမှုနည်းသည် (Unreliable)**။
    ```bash
    sudo nmap -sU 192.168.1.1
    ```

### ၄.၄ Firewall Evasion Scans (Null, FIN, Xmas)
ဤနည်းလမ်းများသည် TCP header ရှိ flag များကို ပုံမှန်မဟုတ်သော ပုံစံဖြင့် ပို့ဆောင်ကာ firewall သို့မဟုတ် IDS ကို ရှောင်ရှားရန် ရည်ရွယ်သည်။
*   **Null Scan (`-sN`)**: Flag အားလုံးကို 0 ပို့သည်။
*   **FIN Scan (`-sF`)**: FIN flag ကိုသာ ပို့သည်။
*   **Xmas Scan (`-sX`)**: FIN, PSH, URG flag များကို တစ်ပြိုင်နက် ပို့သည် (Christmas tree ပုံစံ)။
    ```bash
    sudo nmap -sN 192.168.1.1
    sudo nmap -sF 192.168.1.1
    sudo nmap -sX 192.168.1.1
    ```
    > **သတိပြုရန်**: ဤ scan အမျိုးအစားများသည် port တစ်ခုကို "open" သို့မဟုတ် "filtered" ဟု ခွဲခြားသတ်မှတ်နိုင်သော်လည်း တိကျမှုနည်းပါသည်။

## အခန်း ၅: Service နှင့် OS Detection

*   **Service/Version Detection (`-sV`)**: open port များတွင် လည်ပတ်နေသော service ၏ အမည်နှင့် version ကို ရှာဖွေသည် (Banner Grabbing)။
    ```bash
    nmap -sV 192.168.1.1
    ```
*   **OS Detection (`-O`)**: target host ၏ operating system ကိ် ခန့်မှန်းတွက်ချက်သည်။
    ```bash
    sudo nmap -O 192.168.1.1
    ```
*   **Aggressive Scan (`-A**)**: OS Detection, Version Detection, Script Scanning, Traceroute တို့ကို **တစ်ပါတည်းလုပ်ဆောင်ပေးသည်**။ အလွန်အသုံးဝင်သော်လည်း ဆူညံသံ (Noise) များစေနိုင်သည်။
    ```bash
    nmap -A -T4 192.168.1.1
    ```

## အခန်း ၆: Nmap Scripting Engine (NSE)

NSE သည် Nmap ၏ **အစွမ်းထက်ဆုံးသော အင်္ဂါရပ်** ဖြစ်သည်။ ၎င်းသည် Lua-based framework ဖြစ်ပြီး ပုံမှန် scan များထက် ပိုမိုအဆင့်မြင့်သော အလိုအလျောက်လုပ်ဆောင်မှုများ (Automation) ကို ပြုလုပ်နိုင်သည်။
*   **Default Scripts (`-sC`)**: ဘေးကင်းလုံခြုံသော (safe) script များကို run သည်။
    ```bash
    nmap -sC 192.168.1.1
    ```
*   **Vulnerability Scan**: အားနည်းချက်များကို ရှာဖွေသည်။
    ```bash
    nmap --script vuln 192.168.1.1
    ```
*   **Brute Force Attack**: စကားဝှက်များကို ခန့်မှန်းတိုက်ခိုက်သည် (ဥပမာ - SSH)။
    ```bash
    nmap --script ssh-brute -p 22 192.168.1.1
    ```
*   **Specific Script**:
    ```bash
    nmap --script http-enum -p 80 192.168.1.1
    ```

## အခန်း ၇: Output Management (ရလဒ်သိမ်းဆည်းခြင်း)

ရလဒ်များကို ပုံစံအမျိုးမျိုးဖြင့် သိမ်းဆည်းနိုင်သည်။

| Flag | ပုံစံ | ဥပမာ |
| :--- | :--- | :--- |
| `-oN` | ပုံမှန် (Normal) | `nmap 192.168.1.1 -oN scan.txt` |
| `-oX` | XML | `nmap 192.168.1.1 -oX scan.xml` |
| `-oA` | **ပုံစံအားလုံး** (Normal, XML, Grepable) | `nmap 192.168.1.1 -oA output` |

## အခန်း ၈: Timing and Performance (အချိန်နှင့် စွမ်းဆောင်ရည်)

Nmap သည် `-T<0-5>` ဖြင့် scan အမြန်နှုန်းကို သတ်မှတ်ပေးသည်။

*   **`-T0` (Paranoid)**: အလွန်နှေးကွေးသည်။ IDS ရှောင်ရန်။
*   **`-T1` (Sneaky)**: နှေးကွေးသည်။
*   **`-T2` (Polite)**: ကွန်ရက်အသွားအလာ လျှော့ချရန်။
*   **`-T3` (Normal)**: **မူလအခြေအနေ (Default)**။
*   **`-T4` (Aggressive)**: မြန်ဆန်သည်။ ယုံကြည်ရသော ကွန်ရက်များတွင် သုံးသည်။
*   **`-T5` (Insane)**: အလွန်မြန်ဆန်သည်။ packet များ ကျွတ်ထွက်နိုင်သည်။

```bash
nmap -T4 192.168.1.1
```

## အခန်း ၉: Firewall Evasion Techniques (Firewall ရှောင်နည်းများ)

*   **Decoy Scans (`-D`)**: အတုအယောင် IP အများအပြားဖြင့် scan လုပ်ခြင်းဖြင့် မည်သည့် IP က true source ဖြစ်သည်ကို ဖုံးကွယ်ပေးသည်။
    ```bash
    nmap -D RND:10 192.168.1.1
    ```
*   **Fragment Packets (`-f`)**: packet များကို အပိုင်းပိုင်းခွဲ၍ ပို့ခြင်းဖြင့် firewall ကို ရှောင်သည်။
    ```bash
    nmap -f 192.168.1.1
    ```
*   **Spoof IP Address (`-S`)**: source IP address ကို အတုလုပ်သည်။
    ```bash
    nmap -S 192.168.1.100 192.168.1.1
    ```
*   **အဆင့်မြင့် Evasion Command ပေါင်းစပ်**:
    ```bash
    sudo nmap -sS -Pn -T1 --scan-delay 500ms --max-retries 2 --data-length 20 -f --mtu 16 --source-port 53 -D RND:5 -p- 192.168.1.1
    ```

## အခန်း ၁၀: ကျင့်ဝတ်နှင့်တရားဝင်ဖြစ်မှု (Ethical and Legal Considerations)

**အရေးကြီးဆုံးသတိပေးချက်**: Nmap သည် အစွမ်းထက်သောလက်နက်ဖြစ်သည်။ **သင့်ကိုယ်ပိုင် ကွန်ရက် သို့မဟုတ် ခွင့်ပြုချက်ရရှိထားသော ကွန်ရက်များကိုသာ** scan ပြုလုပ်ပါ။ အခြားသူများ၏ ကွန်ရက်ကို ခွင့်ပြုချက်မရှိဘဲ scan လုပ်ခြင်းသည် **တရားမဝင်သော လုပ်ရပ်** ဖြစ်ပြီး ပြစ်မှုထင်ရှားစီရင်ခြင်းခံရနိုင်သည်။ ဤသင်ခန်းစာသည် **ပညာရေးဆိုင်ရာရည်ရွယ်ချက်အတွက်သာ** ဖြစ်သည်။

---

## နိဂုံး (Conclusion)

Nmap သည် ကွန်ရက်လုံခြုံရေးအတွက် အခြေခံအကျဆုံးနှင့် အရေးအပါဆုံးသော ကိရိယာတစ်ခုဖြစ်သည်။ ဤသင်ခန်းစာပါ အချက်အလက်များကို ကျွမ်းကျင်စွာ အသုံးချနိုင်ပါက ကွန်ရက်အတွင်းရှိ အားနည်းချက်များကို ရှာဖွေတွေ့ရှိနိုင်ပြီး လုံခြုံရေးစနစ်များကို ပိုမိုအားကောင်းအောင် ဆောင်ရွက်နိုင်မည်ဖြစ်သည်။

---

# Ultimate Nmap Practical Lab Manual (လက်တွေ့စစ်ဆင်ရေးသင်ခန်းစာ)

**ဘာသာရပ်**: ကွန်ရက်ထိုးဖောက်စစ်ဆေးခြင်း (Network Penetration Testing)  
**လိုအပ်သော အရည်အချင်း**: Virtualization (VirtualBox/VMware) အခြေခံသိရှိထားရန်။  
**ရည်ရွယ်ချက်**: Firewall, IDS/IPS များကို ကျော်လွှားကာ အဆင့်မြင့် Nmap အသုံးပြုနည်းကို လက်တွေ့ကျွမ်းကျင်စေရန်။

---

## အပိုင်း ၁: ဓာတ်ခွဲခန်း (Lab) ပြင်ဆင်ခြင်း

ကျွန်ုပ်တို့၏ လေ့ကျင့်ရေးကွန်ရက်တွင် တိုက်ခိုက်သူ (Attacker) နှင့် ပစ်မှတ် (Target) ဟူ၍ နှစ်မျိုးခွဲထားပါမည်။

| Role | Operating System | IP Address (Static) | Software |
| :--- | :--- | :--- | :--- |
| **Attacker (Kali)** | Kali Linux 2025+ | `192.168.56.101` | Nmap, Masscan, Netcat |
| **Target 1 (Vulnerable)** | Metasploitable 2 | `192.168.56.102` | Apache, SMB, FTP, MySQL |
| **Target 2 (Firewall)** | Ubuntu Server 22.04 | `192.168.56.103` | UFW Firewall (Enable) + Nginx |
| **Target 3 (Windows)** | Windows 10 (လေ့ကျင့်ရန်) | `192.168.56.104` | File Sharing, RDP |

### Lab Setup ပြုလုပ်နည်း
1.  VirtualBox တွင် **Host-Only Network** (သို့) **NAT Network** တစ်ခု တည်ဆောက်ပါ။ (အပြင်ဘက် Internet နှင့် သီးခြားဖြစ်စေရန်)
2.  [Metasploitable 2](https://sourceforge.net/projects/metasploitable/) ကို download လုပ်၍ Import လုပ်ပါ။
3.  Ubuntu Server တွင် `sudo ufw enable` နှိပ်၍ Firewall ဖွင့်ပြီး Port 80 ကိုသာ ခွင့်ပြုထားပါ။

---

## အပိုင်း ၂: ကွန်ရက်ရှာဖွေခြင်းနှင့် ပစ်မှတ်သတ်မှတ်ခြင်း (Reconnaissance Phase)

### Lab 1: ARP Spoofing မပါဘဲ Layer-2 ရှာဖွေခြင်း
**အနေအထား**: သင်သည် အတွင်းကွန်ရက် (Internal Network) အတွင်းသို့ ရောက်ရှိနေပြီး **မည်သည့် host များ အသက်ဝင်နေသနည်း** ကို ရှာဖွေရန် လိုအပ်သည်။

*   **Theoretical Fact**: Local Network တွင် Nmap သည် ICMP အစား **ARP Request** ကို ဦးစားပေးအသုံးပြုသည်။ ၎င်းသည် Layer-2 ဖြစ်သောကြောင့် Firewall က ပိတ်ထားသော်လည်း MAC Address ကို ဖော်ထုတ်ပေးနိုင်သည်။
*   **အမိန့် (Command)**:
    ```bash
    sudo nmap -sn -PR 192.168.56.0/24
    ```
    > **လေ့လာစစ်ဆေးချက် (Lab Task)**: output တွင် MAC Address (OUI) ကိုကြည့်ပါ။ `00:0C:29` (VMware) သို့မဟုတ် `08:00:27` (VirtualBox) မဟုတ်သော MAC ရှိပါက ၎င်းသည် ပြင်ပစက်ပစ္စည်း သို့မဟုတ် ဆာဗာ ဖြစ်နိုင်သည်။

### Lab 2: Firewall ရှိသော Host ကို အတင်းရှာဖွေခြင်း (No Ping)
**အနေအထား**: Target 2 (Ubuntu) သည် ICMP (Ping) ကို လုံးဝပယ်ချ (Drop) ထားသည်။ ပုံမှန် scan လုပ်ပါက "Host seems down" ဟုပြမည်။

*   **အမိန့် (Command)**: ပုံမှန် Host Discovery ကို ကျော်ပြီး **Port Scan** ကိုသာ တိုက်ရိုက်စတင်ပါ။
    ```bash
    nmap -Pn -p 80,443,22 192.168.56.103
    ```
    > **ရလဒ်**: `-Pn` ကိုသုံးခြင်းဖြင့် ဆာဗာက port 80 (HTTP) ဖွင့်ထားကြောင်း တွေ့ရပါမည်။

---

## အပိုင်း ၃: Port Scanning Techniques - စစ်ဆင်ရေးအဆင့် (Operational Phase)

### Lab 3: SYN Stealth Scan ဖြင့် Firewall Log ကိုရှောင်ခြင်း
**အနေအထား**: Target 1 (Metasploitable) တွင် open port အားလုံးကို ရှာဖွေရန်။ သို့သော် သမားရိုးကျ Connect Scan (`-sT`) သည် log တွင်ကျန်ခဲ့ပြီး IDS က သိရှိသွားနိုင်သည်။

*   **အမိန့် (Command)**:
    ```bash
    sudo nmap -sS -Pn -p- -T4 192.168.56.102
    ```
    > **Lab Task**: `-p-` သည် port 1 မှ 65535 အားလုံးကို scan လုပ်သည်။ Scan ပြီးဆုံးချိန်တွင် open port များစာရင်းကို ရယူပါ (၂၁, ၂၂, ၂၃, ၂၅, ၅၃, ၈၀, ၁၃၉, ၄၄၅, ၃၃၀၆, ၅၉၀၀, ၆၆၆၇, ၈၀၀၉, ၈၁၈၀...).

### Lab 4: UDP Scan ဖြင့် SNMP/DNS ရှာဖွေခြင်း
**အနေအထား**: TCP port များအပြင် လုံခြုံရေးအရ ပေါက်ကြားလေ့ရှိသော UDP service များ (SNMP - 161) ကို စစ်ဆေးရန်။

*   **အမိန့် (Command)**:
    ```bash
    sudo nmap -sU -p 53,123,161,137,138 --max-retries 1 192.168.56.102
    ```
    > **သတိပေးချက်**: UDP scan သည် အလွန်နှေးကွေးသည်။ `--max-retries 1` ဖြင့် ထပ်မံပို့သည့် packet ကို ကန့်သတ်ပါ။

---

## အပိုင်း ၄: Service Fingerprinting & OS Detection (စစ်ဆေးမှု အဆင့်မြှင့်တင်ခြင်း)

### Lab 5: Aggressive Scan (-A) နှင့် Version Detection
**အနေအထား**: Port 80 (HTTP) ပေါ်တွင် လည်ပတ်နေသော Application ၏ အတိအကျ Version ကို သိရှိရန် လိုအပ်သည်။ ထို့အပြင် Operating System ကိုပါ ခန့်မှန်းရန်။

*   **အမိန့် (Command)**:
    ```bash
    sudo nmap -A -p 21,22,80,443,445 -T4 192.168.56.102
    ```
*   **လက်တွေ့လေ့ကျင့်ခန်း (Output Analysis)**:
    *   Port 80: Apache `2.2.8` (Ubuntu) ဟုပြပါက **CVE-2011-3192** (Range header DoS) ကဲ့သို့သော အားနည်းချက်များ ရှိနိုင်သည်။
    *   Port 445: SMB `Unix (Samba 3.0.20)` ဟုပြပါက **CVE-2007-2447** (Username map script) ကို စမ်းသပ်နိုင်သည်။

### Lab 6: OS Detection ကို လှည့်ဖြားခြင်း (OS Spoofing)
**အနေအထား**: Target က မိမိကို Linux ဟုပြနေသော်လည်း သင်က Windows ဟု ထင်စေချင်သည် (သို့မဟုတ်) ဆန့်ကျင်ဘက်။

*   **အမိန့် (Command)** - Nmap ၏ OS detection ကို ကိုယ်တိုင် TTL ပြောင်းခြင်းဖြင့် လှည့်စားနည်း:
    ```bash
    sudo nmap -O --ttl 128 192.168.56.102  # Windows ပုံစံ TTL
    sudo nmap -O --ttl 64 192.168.56.102   # Linux ပုံစံ TTL
    ```
    (မှတ်ချက်: ဤသည်မှာ ရိုးရှင်းသော လှည့်ကွက်ဖြစ်သော်လည်း Nmap ၏ TCP/IP stack fingerprinting ကို အပြည့်အဝမလှည့်စားနိုင်ပါ။)

---

## အပိုင်း ၅: Nmap Scripting Engine (NSE) - ထိုးဖောက်စစ်ဆင်ရေး

NSE သည် Nmap ကို **Vulnerability Scanner** အဖြစ်သို့ ပြောင်းလဲပေးနိုင်သည်။

### Lab 7: SMB အားနည်းချက်ရှာဖွေခြင်း (EternalBlue စစ်ဆေး)
*   **အမိန့် (Command)**:
    ```bash
    nmap --script smb-vuln-* -p 445 192.168.56.102
    ```
    > **ရလဒ်**: Metasploitable 2 သည် ရှေးကျသော SMB ဗားရှင်းဖြစ်သောကြောင့် `smb-vuln-ms08-067` အားနည်းချက် တွေ့ရှိရမည်။

### Lab 8: HTTP (Web) Directory Brute Force
*   **အမိန့် (Command)** - `http-enum` script ဖြင့် ဝှက်ထားသော လမ်းညွှန်များ (Hidden Directories) ရှာဖွေခြင်း:
    ```bash
    nmap --script http-enum -p 80 --script-args http-enum.fingerprintfile=./nselib/data/http-fingerprints.lua 192.168.56.102
    ```
*   **လက်တွေ့စမ်းသပ်ချက်**: `/dvwa/`, `/phpmyadmin/`, `/webdav/` စသည့် directories များပေါ်လာပါက ၎င်းတို့ကို browser ဖြင့် ဝင်ရောက်ကြည့်ရှုပါ။

### Lab 9: MySQL စကားဝှက် Brute Force (တိုက်ခိုက်မှု)
*   **အမိန့် (Command)**:
    ```bash
    nmap --script mysql-brute -p 3306 192.168.56.102
    ```
    > (ဤ script သည် default user/pass စာရင်းဖြင့် စမ်းသပ်မည်။ ဤသည်မှာ တရားဝင် Pentest တွင် အသုံးပြုသော်လည်း **သတိထားရန်** လိုအပ်သည်။)

---

## အပိုင်း ၆: Firewall & IDS Evasion (ရှောင်ကွင်းနည်းဗျူဟာများ)

ဤအပိုင်းသည် စစ်မှန်သော Red Team ကျွမ်းကျင်သူများ၏ လက်နက်တိုက်ဖြစ်သည်။

### Lab 10: Decoy Scan (အရိပ်အမြွက် IP များ)
**အနေအထား**: Target ရှိ Security Team က သင့် Real IP ကို သိရှိသွားမည်ကို စိုးရိမ်သည်။

*   **အမိန့် (Command)**:
    ```bash
    nmap -D RND:10,192.168.56.200,ME -p 80 192.168.56.103
    ```
    > **ရှင်းလင်းချက်**: ဤ command သည် အတုအယောင် IP ၁၀ ခု (RND:10) နှင့် သင့် Real IP (ME) ကို ရောနှောပို့ဆောင်ပေးသည်။ Target log တွင် IP အများအပြား ပေါ်လာပြီး မည်သည်က စစ်မှန်သည်ကို ခွဲခြားရခက်စေသည်။

### Lab 11: Packet Fragmentation (MTU ချုံ့ခြင်း)
**အနေအထား**: Firewall သည် ပုံမှန် TCP header များကို စစ်ဆေးသည်။

*   **အမိန့် (Command)**:
    ```bash
    sudo nmap -f -p 22,80,443 192.168.56.103
    ```
    > `-f` သည် packet ကို 8 bytes ပိုင်းဖြတ်ပေးသည်။ အချို့ Firewall များသည် fragmented packet များကို စစ်ဆေးရန် မေ့လျော့တတ်သည်။ ပိုမိုထိရောက်ရန် `--mtu 16` ဖြင့် စမ်းသပ်ပါ။

### Lab 12: Source Port Spoofing (အရင်းအမြစ် Port အတုလုပ်)
**အနေအထား**: အချို့ Firewall များသည် Port 53 (DNS) သို့မဟုတ် Port 80 (HTTP) မှ ထွက်သော packet များကို ယုံကြည်ကြသည်။

*   **အမိန့် (Command)**:
    ```bash
    sudo nmap -sS -p 445 --source-port 53 192.168.56.102
    ```
    > Firewall က "Port 53 ဆိုတာ DNS ပဲ၊ အန္တရာယ်မရှိဘူး" ဟု ထင်မှတ်ကာ packet ကို ဖြတ်သန်းခွင့်ပြုနိုင်သည်။

---

## အပိုင်း ၇: Performance Tuning (စွမ်းဆောင်ရည် မြှင့်တင်ခြင်း)

### Lab 13: ကြီးမားသော ကွန်ရက် (/16) ကို အမြန်ဆုံး Scan လုပ်ခြင်း
*   **အမိန့် (Command)**:
    ```bash
    sudo nmap -T5 -sS -p 80 --min-rate 10000 --max-retries 0 192.168.0.0/16
    ```
    > `-T5` (Insane)၊ `--min-rate 10000` (တစ်စက္ကန့်လျှင် packet ၁၀၀၀၀) နှင့် `--max-retries 0` ဖြင့် ပုံမှန် ၁၀ နာရီကြာမည့် scan ကို မိနစ်အနည်းငယ်အတွင်း ပြီးစေနိုင်သည်။

---

## အပိုင်း ၈: Output Management (ရလဒ်သိမ်းဆည်းခြင်းနှင့် ခွဲခြမ်းစိတ်ဖြာခြင်း)

### Lab 14: Grepable နှင့် XML ထုတ်ယူခြင်း
အစီရင်ခံစာ (Report) ပြုလုပ်ရန်အတွက် ရလဒ်များကို စနစ်တကျ သိမ်းဆည်းပါ။

*   **အမိန့် (Command)**:
    ```bash
    nmap -A -p- 192.168.56.102 -oA metaspolit_scan
    ```
    > ၎င်းသည် `metaspolit_scan.nmap`, `metaspolit_scan.gnmap`, `metaspolit_scan.xml` ဟူ၍ သုံးမျိုးထွက်ပေးသည်။

*   **XML to HTML (Report) ပြောင်းခြင်း**:
    ```bash
    xsltproc metaspolit_scan.xml -o report.html
    ```

---

## အပိုင်း ၉: စစ်မှန်သော စုစုပေါင်းတိုက်ခိုက်မှု (Combined Attack Scenario)

**နောက်ဆုံးလက်တွေ့စစ်ဆင်ရေး (Capstone Lab)**:
သင်သည် Target 1 (Metasploitable) ကို ရှာဖွေပြီး အောက်ပါအချက်များကို တစ်ပါတည်းလုပ်ဆောင်ရန် ညွှန်ကြားထားသည်။
1.  ကွန်ရက်အတွင်း အသက်ဝင်သော host များကို ရှာဖွေခြင်း။
2.  Open Port အားလုံးကို ရှာဖွေခြင်း။
3.  ဝန်ဆောင်မှုများ၏ Version ကို ဖော်ထုတ်ခြင်း။
4.  SMB နှင့် HTTP ပေါ်ရှိ အားနည်းချက်များကို NSE ဖြင့် စစ်ဆေးခြင်း။
5.  Firewall (Target 2) ကိုရှောင်ရန် Decoy နှင့် Fragmentation သုံးခြင်း။
6.  ရလဒ်များကို `final_report.xml` အဖြစ် သိမ်းဆည်းခြင်း။

**အမိန့် (The Ultimate One-Liner)**:
```bash
sudo nmap -sS -sC -sV -O -A -f -D RND:5 -p- --min-rate 5000 --max-rtt-timeout 100ms 192.168.56.102 -oA ultimate_pentest
```

---

## နိဂုံး (Final Thoughts)

ဤ Lab များကို အောင်မြင်စွာ လေ့ကျင့်ပြီးပါက သင်သည် Nmap ၏ အခြေခံအသုံးပြုသူမှ **စစ်ဆင်ရေးကျွမ်းကျင်သူ (Operational Expert)** အဆင့်သို့ ရောက်ရှိသွားပါပြီ။
သတိရပါ - **ခွင့်ပြုချက်မရှိဘဲ စစ်ဆင်ရေးများ ပြုလုပ်ခြင်းသည် ဥပဒေအရ ပြစ်မှုဖြစ်သည်။** သင်၏ Lab အတွင်းတွင်သာ ဤကျွမ်းကျင်မှုကို အသုံးပြုပါ။