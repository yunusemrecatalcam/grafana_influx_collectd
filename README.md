#Grafana-InfluxDB-Collectd Monitoring System
Docker compose makes us enable to easily manage the monitoring stack.
 
####External files
- collectd.conf to collectd container
- influxdb.conf and types.db to influxdb container

To run all the system, run
```
docker-compose up -d
```
after running these command, you will be able to reach the Grafana over browser.

The default address is: http://server_ip:3000

#####Firstly, you should add InfluxDB to Grafana as a Data Source;

- Click to settings button placed on the left.
- Click to blue "Add data source" button and select InfluxDB and 
apply following configurations
```
  Query Language: InfluxQL
  URL: http://localhost:8086
  Access: Browser
  No auth
  Database: collectd
```
Click save and test, it'll come a green pop-up if everything is ok.
 
You should now import the dashboard that I prepared for collectd metrics.
For doing that;
- Click the + button on the left 
- Click to import 
- Copy the text of grafana_dashboard.json and paste it to the text box
 "Import via panel json" placed on the page.
 
 After the import, you can see your metrics and that all!


