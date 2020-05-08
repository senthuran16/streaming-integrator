# How to Use Grafana Dashboards

In order to use these dashboards with grafana you have to follow these instructions.

## 1. Configuring Prometheus Reporter.  
To enable statistics for the Prometheus Reporter, add the following configuration to deployment.yaml
1. Navigate to `<WSO2_SI_HOME>/conf/runner/deployment.yaml`.
2. Add following Configurations,
````
wso2.metrics:
  # Enable Metrics
  enabled: true
  reporting:
    console:
      - # The name for the Console Reporter
        name: Console

        # Enable Console Reporter
        enabled: false

        # Polling Period in seconds.
        # This is the period for polling metrics from the metric registry and printing in the console
        pollingPeriod: 2

metrics.prometheus:
 reporting:
   prometheus:
     - name: prometheus
       enabled: true
       serverURL: "http://localhost:9005"
````

## 2. Start the Streaming Integrator.
1. Navigate to <WSO2_SI_HOME> and issue following command in the terminal,
    1. `bin/server.sh` (if you are on a Linux/Mac OS) .
    2. `server.bat` (if you are on a Windows OS).

## 3. Start the grafana server.
1. Download grafana from the following URL  https://grafana.com/grafana/download  
2. Extract the downloaded file and Navigate to grafana directory.  
3. Issue following command in the console `bin/grafana-server`.  
4. Navigate to grafana home with following URL `localhost:3000`.

## 4. Load dashboards into grafana.
Once you have login to the grafana follow these steps to import dashboards into grafana

1. Navigate to +(plus) icon at the left upper corner.  
![](./image-1.png)

2. Select `import`.  
3. Then select `upload .json file` and select relevant json file from this directory.
