# 로컬 테스트 Redis Cluster

- 버전 : **Redis 7.2.4**

- 실행
    - `docker-compose up`
    - `docker exec -it redis-master-1 bash`
    - container 콘솔에서 명령어 실행  
	  `redis-cli --cluster create redis-master-1:7000 redis-master-2:7001 redis-master-3:7002 redis-slave-1:7003 redis-slave-2:7004 redis-slave-3:7005 --cluster-replicas 1`
    - 확인
      ```
      redis-cli -c -p 7000
      > set foo bar
      > set hello world
      > get foo
      > get bar
      ```
- 설정 추가  
  ```
  // 도커 내부통신만 하면 상관없는데, 도커 외부에서 접근하기 위해 추가
  cluster-announce-ip {publicIP}
  cluster-announce-port port
  cluster-announce-bus-port 내부-bus-port
 ```