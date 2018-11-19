
#profiles 指定不通的配置文件来执行，实现注册中心高可用
nohup java -jar eureka-service-0.0.1-SNAPSHOT.jar --spring.profiles.active=peer1 &
nohup java -jar eureka-service-0.0.1-SNAPSHOT.jar --spring.profiles.active=peer2 &
nohup java -jar eureka-service-0.0.1-SNAPSHOT.jar --spring.profiles.active=peer3 &

nohup java -jar -Xms64m -Xmx128m pq-eureka-service.jar  > /export/data/logs/pq-eureka-service.file  2>&1 &

nohup java -jar -Xms64m -Xmx128m pq-user-service-1.0.0-SNAPSHOT.jar  > /export/data/logs/pq-user-service.file  2>&1 &

nohup java -jar -Xms64m -Xmx128m pq-api-1.0.0-SNAPSHOT.jar  > /export/data/logs/pq-api.file  2>&1 &

nohup java -jar -Xms64m -Xmx128m pq-agency-service-1.0.0-SNAPSHOT.jar  > /export/data/logs/pq-api.file  2>&1 &