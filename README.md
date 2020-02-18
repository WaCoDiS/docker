# WaCoDiS Docker

Docker files for containerization of WaCoDiS modules.

# Startup

1. `cd wacodis_services`
1. `docker-compose up -d`
1. `cd ..`
1. `docker-compose up`

This will boot up the backing services (elasticsearch and rabbitmq) in their own network.
The WaCoDiS services should be started separately (and a few seconds later) as they depend
on the backing services. 

The message dashboard is provided via a nginx reverse proxy and should be available at:

http://localhost/message-dashboard/index.html

The Job Definition API (as the central component for submitting new job tasks) is available at:

http://localhost:8081/swagger-ui.html

# License

Apache 2.0
