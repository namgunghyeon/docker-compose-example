# Redis

haproxy -> redis master(3) -> redis slave(3)

## 네트워크 브릿지 모드
docker-compose -f docker-compose-network-bridge.yaml up --build

클러스터 생성
```
docker exec -it redis-1 redis-cli -p 7000 --cluster create 10.0.0.2:7000 10.0.0.3:7001 \
10.0.0.4:7002 10.0.0.5:7003 10.0.0.6:7004 10.0.0.7:7005 \
--cluster-replicas 1
```

## 네트워크 호스트 모드
docker-compose -f docker-compose-network-host.yaml up --build

클러스터 생성(mac에서 동작하지 않음)
```
docker exec -it redis-1 redis-cli -p 7000 --cluster create <hostIP>:7000 <hostIP>:7001 \
<hostIP>:7002 <hostIP>:7003 <hostIP>:7004 <hostIP>:7005 \
--cluster-replicas 1
```

## 공통
레디스 노드 접속
```
docker exec -it redis-1 redis-cli -c -p 7000

클러스터 정보 확인
127.0.0.1:7000> cluster nodes
```