# monitoringApps

https://www.youtube.com/watch?v=gJZhdEJvZmc

1) Actuator:
   The Actuator is used to monitor our applications. It gives us lots of information regarding projects like, the
   average of memory consumption, etc.
   To use it, head over to: http://localhost:8888/actuator/
   Copy and paste that link to a browser. On the results, you will see the list of endpoints exposed by the actuator,
   for example:http://localhost:8888/actuator/health

If you hit one of the endpoint, for instance http://localhost:8888/actuator/health, you will see information related to
the memory consumption of the application.

2) Prometheus
   Prometheus is used to monitor applications, just like the Actuation. Unlike the Actuator, Prometheus shows data in a
   separate dashboard and in a specific format.
   When you head over to the actuator endpoint: http://localhost:8888/actuator/, you will be able to see, among the
   results, the prometheus endpoint:
   http://localhost:8888/actuator/prometheus

When you copy and paste that endpoint to a browser, you see different measurement metrics.
http://localhost:8888/actuator/prometheus

Next step:

- Download prometheus server at: prometheus.io/download

Extract the zip file: C:\Dev\Projects\Monitoring\prometheus_server
In the file: prometheus.yml, add these configurations under scrape_configs:

- job_name: 'spring-actuator'
  metrics_path: '/actuator/prometheus'
  scrape_interval: 5s
  static_configs:
    - targets: ['localhost:8888']

Close the file: prometheus.yml and
Start the server by double-clicking on prometheus.exe, or by entering this command on a powershell terminal :
.\prometheus.exe.

When the server is started, head over to http://localhost:9090/ on a browser.

3) Grafana
   The Grafana dashboard is more customizable than the prometheus dashboard
   Download grafana for windows : https://grafana.com/grafana/download?platform=windows
   Choose the zip option.
   Extract the zip : C:\Dev\Projects\Monitoring\grafana\grafana-9.1.6\bin
   In the folder obtained, go to the bin.
   Start the Grafana server by clicking on grafana-server.exe or by entering this on a powershell command:
   .\grafana-server.exe

Head unto a browser and enter: http://localhost:3000/
enter admin and admin for username and password







