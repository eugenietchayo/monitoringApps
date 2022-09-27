# monitoringApps

1) Actuator:
   The Actuator is used to monitor our applications. It gives us lots of information regarding projects like, the
   average of memory consumption, etc.
   To use it, head over to: http://localhost:8888/actuator/
   Copy and paste that link to a navigator. On the results, you will see the list of endpoints exposed by the actuator,
   for example:http://localhost:8888/actuator/health

If you hit one of the endpoint, for instance http://localhost:8888/actuator/health, you will see information related to
the memory consumption of the application.

2) Prometheus
   Prometheus is used to monitor applications, just like the Actuation. Unlike the Actuator, Prometheus shows data in a
   separate dashboard and in a specific format.
   When you head over to the actuator endpoint: http://localhost:8888/actuator/, you will be able to see, among the
   results, the prometheus endpoint:
   http://localhost:8888/actuator/prometheus

When you copy and paste that endpoint to a navigator, you see different measurement metrics.
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

When the server is started, head over to http://localhost:9090/ on a navigator.




