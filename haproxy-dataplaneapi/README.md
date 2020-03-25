# HAProxy Data Plane API
Rest API로 HAProxy Configuration 정보를 Runtime에 변경

```
curl -X GET --user dataplaneapi:mypassword http://localhost:5000/v2/services/haproxy/configuration/frontends

{"_version":1,"data":[{"default_backend":"backendnodes","mode":"http","name":"haproxynode"}]}
```
