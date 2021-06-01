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
```

## Configure to start at boot time
