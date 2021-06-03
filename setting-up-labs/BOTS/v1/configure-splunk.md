# Boss of the SOC : V1

## Install Splunk Enterprise
1. Go to [Splunk]()
```
wget -O splunk-8.2.0-e053ef3c985f-linux-2.6-x86_64.rpm 'https://www.splunk.com/bin/splunk/DownloadActivityServlet?architecture=x86_64&platform=linux&version=8.2.0&product=splunk&filename=splunk-8.2.0-e053ef3c985f-linux-2.6-x86_64.rpm&wget=true'

sudo apt-get install rpm

rpm -ivh splunk-8.2.0-e053ef3c985f-linux-2.6-x86_64.rpm
```

```
wget -O splunk-8.2.0-e053ef3c985f-linux-2.6-x86_64.tgz 'https://www.splunk.com/bin/splunk/DownloadActivityServlet?architecture=x86_64&platform=linux&version=8.2.0&product=splunk&filename=splunk-8.2.0-e053ef3c985f-linux-2.6-x86_64.rpm&wget=true'

tar xvzf splunk_package_name.tgz -C /opt
```
## Get Splunk to start
```
sudo cd /opt/splunk/bin

sudo cp /opt/splunk/etc/splunk-launch.conf.default /opt/splunk/etc/splunk-launch.conf

sudo vim /opt/splunk/etc/splunk-launch.conf
# set value of SPLUNK_HOME & enable it

sudo /opt/splunk/bin/splunk start --accept-license

#Create a Username
#Create a Password
#Navigate to the Splunk Web Interface, specified at the bottom

sudo vim $SPLUNK_HOME/etc/system/local/user-seed.conf
# Add the following to the file (Minus the "#"'s)
# [user_info]
# USERNAME = admin
# PASSWORD = <your new password>
```

## Configure to start at boot time

## Add Required Apps
|                                         App / Add-on                                         | Version |                 Download                |
|:--------------------------------------------------------------------------------------------:|:-------:|:---------------------------------------:|
| Splunk Enterprise                                                                            | 6.5.2   | http://www.splunk.com                   |
| Fortinet Fortigate Add-on for Splunk                                                         | 1.3     | https://splunkbase.splunk.com/app/2846  |
| Splunk Add-on for Tenable                                                                    | 5.0.0   | https://splunkbase.splunk.com/app/1710/ |
| Splunk Stream Add-on (Note Stream 6.6.1 is no longer available. Use Version 7.1.1 instead.)  | 6.6.1   | https://splunkbase.splunk.com/app/1809/ |
| Splunk App for Stream (Note Stream 6.6.1 is no longer available. Use Version 7.1.1 instead.) | 6.6.1   | https://splunkbase.splunk.com/app/1809/ |
| Splunk Add-on for Microsoft Windows                                                          | 4.8.3   | https://splunkbase.splunk.com/app/742/  |
| TA-Suricata                                                                                  | 2.3     | https://splunkbase.splunk.com/app/2760/ |
| Microsoft Sysmon Add-on                                                                      | 3.2.3   | https://splunkbase.splunk.com/app/1914/ |
| URL Toolbox                                                                                  | 1.6     | https://splunkbase.splunk.com/app/2734/ |

## Upload BOTS Data Set
[Download](https://s3.amazonaws.com/botsdataset/botsv1/botsv1.json.gz) the BOTS v1 data set (11.3 GB)

```
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.WinEventLog-Application.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.WinEventLog-Security.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.WinEventLog-System.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.XmlWinEventLog-Microsoft-Windows-Sysmon-Operational.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.fgt_event.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.fgt_traffic.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.fgt_utm.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.iis.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.nessus-scan.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-dhcp.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-dns.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-http.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-icmp.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-ip.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-ldap.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-mapi.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-sip.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-smb.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-snmp.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-tcp.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.suricata.json.gz
https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.winregistry.json.gz

wget -v --input-file=./bots_urls 

split -b 500m botsv1*
```

|                  Splunk Sourcetype                  |                                                        Compressed JSON file                                                       |
|:---------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------:|
| WinEventLog:Application                             | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.WinEventLog-Application.json.gz                             |
| WinEventLog:Security                                | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.WinEventLog-Security.json.gz                                |
| WinEventLog:System                                  | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.WinEventLog-System.json.gz                                  |
| XmlWinEventLog:Microsoft-Windows-Sysmon/Operational | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.XmlWinEventLog-Microsoft-Windows-Sysmon-Operational.json.gz |
| fgt_event                                           | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.fgt_event.json.gz                                           |
| fgt_traffic                                         | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.fgt_traffic.json.gz                                         |
| fgt_utm                                             | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.fgt_utm.json.gz                                             |
| iis                                                 | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.iis.json.gz                                                 |
| nessus:scan                                         | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.nessus-scan.json.gz                                         |
| stream:dhcp                                         | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-dhcp.json.gz                                         |
| stream:dns                                          | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-dns.json.gz                                          |
| stream:http                                         | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-http.json.gz                                         |
| stream:icmp                                         | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-icmp.json.gz                                         |
| stream:ip                                           | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-ip.json.gz                                           |
| stream:ldap                                         | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-ldap.json.gz                                         |
| stream:mapi                                         | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-mapi.json.gz                                         |
| stream:sip                                          | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-sip.json.gz                                          |
| stream:smb                                          | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-smb.json.gz                                          |
| stream:snmp                                         | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-snmp.json.gz                                         |
| stream:tcp                                          | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.stream-tcp.json.gz                                          |
| suricata                                            | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.suricata.json.gz                                            |
| winregistry                                         | https://s3.amazonaws.com/botsdataset/botsv1/json-by-sourcetype/botsv1.winregistry.json.gz                                         |
