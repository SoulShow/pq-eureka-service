
#profiles 指定不通的配置文件来执行，实现注册中心高可用
nohup java -jar eureka-service-0.0.1-SNAPSHOT.jar --spring.profiles.active=peer1 &
nohup java -jar eureka-service-0.0.1-SNAPSHOT.jar --spring.profiles.active=peer2 &
nohup java -jar eureka-service-0.0.1-SNAPSHOT.jar --spring.profiles.active=peer3 &

java -jar pq-eureka-service-1.0.0-SNAPSHOT.jar  > /export/data/logs/log.file  2>&1 &