# 여러 서비스 띄우기

## 설정
- 다른 서비스에서 postgres를 사용하려면 `url: jdbc:postgresql://postgres/rec_db?currentSchema=testdb` 주소를 사용해 접속 가능

## 빌드
```shell
$ docker-compose up --build
```
