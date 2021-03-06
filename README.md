## Collects and parses the logs created by Kafka

When you run this module, it performs a few tasks under the hood:

- Sets the default paths to the log files (but don’t worry, you can override the defaults)
- Makes sure each multiline log event gets sent as a single event
- Uses ingest node to parse and process the log lines, shaping the data into a structure suitable for visualizing in Kibana
- Deploys dashboards for visualizing the log data

### Compatibility

The ```Kafka``` module was tested with logs from versions 0.9, 1.1.0 and 2.0.0.


## Installation

### Linux:

<i>If you haven't already installed filebeat...</i>

1) Enter the following script into the console using elevated privileges

```
curl https://github.com/vizionelkhelp/vizion.ai/blob/master/beat-install-scripts/install-config-kafka.sh > install-config-kafka.sh; chmod a+x  install-config-kafka.sh; ./install-config-kafka.sh _PLACEHOLDER_API_ENDPOINT_
```

2) When prompted, select the proper environment to complete the installation.

**Data should now be shipping to your Vizion Elastic app. Check the ```Discover``` tab in Kibana for the incoming logs**

<br>

<i>If you have already installed filebeat...</i>

1) Enable the module.

```
filebeat modules enable kafka
```

2) Restart Filebeat.

```
service filebeat restart
```

**Data should now be shipping to your Vizion Elastic app. Check the ```Discover``` tab in Kibana for the incoming logs**

<hr>

### Windows:

<i>If you haven't already installed filebeat...</i>

1) As administrator, enter the following command in Powershell or download the zip file [here](https://github.com/vizionelkhelp/Filebeat-Modules/archive/master.zip).

```
Start-BitsTransfer -Source 'https://github.com/vizionelkhelp/Filebeat-Modules/archive/master.zip' -Destination 'C:\Users\Administrator\Downloads\Filebeat-Modules.zip'
```

2) Unzip the package and extract the contents to the `C:/` drive.

3) Back in Powershell, CD into the extracted folder and run the following script:

```
.\installFilebeat.ps1
```

4) When prompted, enter your credentials below and click OK.

```css
Kibana URL: _PLACEHOLDER_KIBANA_URL_
Username: _PLACEHOLDER_USERNAME_
Password: _PLACEHOLDER_PASSWORD_
Elasticsearch API Endpoint: _PLACEHOLDER_API_ENDPOINT_
```

5) Choose the ```Kafka``` module and click OK.

This will install and run Filebeat with the module you enabled set to that particular modules default file path.

**Data should now be shipping to your Vizion Elastic app. Check the ```Discover``` tab in Kibana for the incoming logs**

<br>


<i>If you have already installed filebeat...</i>

1) In Powershell, as administrator, CD into the ```Filebeat``` folder and enter the following command:

```
.\filebeat.exe modules enable kafka
```

2) Restart Filebeat to initate the changes.

```
restart-service filebeat
```

**Data should now be shipping to your Vizion Elastic app. Check the ```Discover``` tab in Kibana for the incoming logs**

<hr>

## Example Dashboard

This module comes with a sample dashboard to see Kafka logs and stack traces.

![Imgur](https://imgur.com/u39MmSK.png)
