# nginx-loadbalancer
Load balancer on nginx that will have 1 server for UK, 2 servers for US, and 1 server for the rest. In case of failure, it should send all traffic to backup server. Health check should happen every 5 seconds

### Setup ngrok
```shell
./ngrok http http://localhost:8091
```

### Example request from Ukraine
```shell
curl --location --request GET 'http://6267-213-110-131-241.ngrok.io'
```

Response:
```
Response from OTHERS server
```

### Example request from US location
```shell
curl --location --request GET 'http://6267-213-110-131-241.ngrok.io'
```

Response:
```
Response from US-1 server
```
or
```
Response from US-2 server
```