# 카프카 명령어

## Windows
### 주키퍼 실행
zookeeper-server-start.bat ../../config/zookeeper.properties
### 카프카 서버 실행 - 반드시 주키퍼 먼저 실행
kafka-server-start.bat ..\..\config\server.properties

## Mac
### 주키퍼 실행
bin/zookeeper-server-start.sh config/zookeeper.properties
### 카프카 서버 실행 - 반드시 주키퍼 먼저 실행
bin/kafka-server-start.sh config/server.properties
### 띄어진 브로커 정보 확인
bin/kafka-broker-api-versions.sh --bootstrap-server
### 토픽 리스트 확인
bin/kafka-topics.sh --bootstrap-server localhost:9092 --list

### 필기노트
## 신뢰도 높게 데이터 전송 환경 설정
acks=all(-1) \
min.insync.replicas=3 \
rf=3

## 파티션 개수 = 컨슈머 개수 맞추기
## 적재할 곳에 따라 그룹 나눠서 장애에 유연하게 대응리

