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
