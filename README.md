<p align="center">
  <img alt="Metabigor" src="https://image.flaticon.com/icons/svg/1774/1774457.svg" height="140" />
  <p align="center">Command line Search Engine without any API key</p>
  <p align="center">
    <a href="https://github.com/j3ssie/Metabigor"><img alt="python" src="https://img.shields.io/badge/python-3.6%2B-blue.svg"></a>
    <a href=""><img alt="Software License" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square"></a>
    <a href=""><img alt="tested" src="https://img.shields.io/badge/tested-Linux%2fOSX-red.svg"></a>
    <a href="https://www.youtube.com/watch?v=O-KKke5fCkc"><img alt="Demo" src="https://img.shields.io/badge/demo-youtube-blue.svg"></a>
  </p>
</p>

## What is Metabigor?
Metabigor allows you to do query from command line to awesome Search Engines (like Shodan, Censys, Fofa, ZoomEye and many others) without any API key.


## How it works?
Metabigor gonna use your cookie or not to simulate search from browser and automatic optimize the query to get more result.

## Main feature
- Regular search like you do from Shodan, Censys, Fofa but on commandline.
- Discovery IP range of target or ASN.
- Get CVE or exploit about app of software.
- Simple github recon to get repo, user and org.


## Installation
```
git clone https://github.com/j3ssie/Metabigor
cd Metabigor
pip3 install -r requirements.txt
```


## Demo
[![asciicast](https://asciinema.org/a/jaARv3sMSOVYQ1yOsjeKZp8Ek.svg)](https://asciinema.org/a/jaARv3sMSOVYQ1yOsjeKZp8Ek)

## How to use

### Basic Usage

```
./metabigor.py -s <source> -q '<your_query>' [options]
```

Check out the [Advanced Usage](https://github.com/j3ssie/Metabigor/wiki/Advanced-Usage) to explore some awesome options

### Example commands
__Note__: Fill your credentials or your sessions on `~/.metabigor/config.conf` if you want to get more results.

```
./metabigor.py -s fofa -q 'title="Dashboard - Confluence" && body=".org"' 
```

```
./metabigor.py -s fofa -q 'title="Dashboard - Confluence" && body=".org"' -b --disable_pages
```

```
./metabigor.py -s shodan -q 'port:"3389" os:"Windows"' --debug
```

### More Options
```
[*] Basic Usage
===============
./metabigor.py -s <source> -q '<your_query>' [options]
./metabigor.py -S <json file of multi source> [options]
./metabigor.py -m <module> -t <target> [options]

[*] More Options
===============
  -o OUTPUT, --output OUTPUT
                        Output file name
  --raw RAW             Directory to store raw content
  --proxy PROXY         Proxy for doing request to search engine e.g:
                        http://127.0.0.1:8080
  -b                    Auto brute force the country code
  --disable_pages       Don't loop though the pages
  --store_content       Store the raw HTML souce or not
  -M                    Print available module and search engine supported
  --hh                  Print this message
  --debug               Print debug output


[*] Example commands
===============
./metabigor.py -s fofa -q 'title="Dashboard - Confluence" && body=".org"'
./metabigor.py -s zoomeye -q 'app:"tomcat"'
./metabigor.py -s shodan -q 'port:"3389" os:"Windows"' --debug
./metabigor.py -s shodan -Q list_of_query.txt --debug -o rdp.txt  -b --disable_pages
./metabigor.py -s censys -q '(scada) AND protocols: "502/modbus"' -o something  --debug --proxy socks4://127.0.0.1:9050

[*] Example commands for other mode
===============
./metabigor.py -m exploit -t 'nginx|1.0'  --debug
./metabigor.py -m exploit -t 'tomcat|7' -d /tmp/ -o tomcat --debug

./metabigor.py -m ip -t example.com -o /tmp/sample
./metabigor.py -m ip -q 'asn|12334' -o /tmp/sample

./metabigor.py -m git -s code -q 'Osmedeus' -o /tmp/sample -store_content
./metabigor.py -m git -s commit -q 'Osmedeus' -o /tmp/sample

```


### Todo
* Auto switch to query using proxy if get blocked.
* Predine query to do specific task like subdomain scan, portscan, ~~ip discovery~~.
* Adding more search engine.
  * Baidu
  * Get free proxy from multiple data sources


## Credits

Logo from [flaticon](https://www.flaticon.com/free-icon/metabolism_1774457) by [Vitaly Gorbachev
](https://www.flaticon.com/authors/vitaly-gorbachev) and ascii logo converted by [picascii](http://picascii.com/)


## But Why Metabigor?\*
* Don't use your API key so you don't have to worry about litmit of API quotation.

* Do query from command line without Premium account.

* Get more result without Premium account. 

* But I have an Premium account why do I need this shit? 
    * Again Metabigor will not lose your API quotation.
    * Your query will optimized so you gonna get more result than using it by hand or API key.
    * Never get duplicate result.


## Disclaimer

> \* Note: Some features above might not works for all Search Engine. <br />
E.g: Some Search Engines allowed use API key without Premium account and and some of them lose your quotation quotation even when you do not use API key.

This tool is for educational purposes only. You are responsible for your own actions. If you mess something up or break any laws while using this software, it's your fault, and your fault only.

## Contact

[@j3ssiejjj](https://twitter.com/j3ssiejjj)
