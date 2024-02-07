# 로컬 테스트 Redis Cluster

- 실행
    - `docker-compose up`
    - `docker exec -it redis-master-1 bash`
    - container 콘솔에서 명령어 실행  
  `redis-cli --cluster create 127.0.0.1:7000 127.0.0.1:7001 127.0.0.1:7002 127.0.0.1:7003 127.0.0.1:7004 127.0.0.1:7005 --cluster-replicas 1`
    - 확인
      ```
      redis-cli -c -p 7000
      > set foo bar
      > set hello world
      > get foo
      > get bar
      ```