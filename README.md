# wildfirechat-server-docker

```
mkdir -p /var/chat-server
docker run -d --name chat-server chenyu1990/wildfirechat-server:1.0.0 \
docker cp chat-server:/opt/wildfirechat/config /var/chat-server
docker rm -f chat-server
docker run -d \
    --name chat-server \
    --hostname chat-server \
    -v /var/chat-server/config:/opt/wildfirechat/config \
    -p 8000:80 -p 1883:1883 -p 8083:8083 -p 18080:18080 \
    --restart on-failure \
    --log-opt max-size=100mb \
    --network chat-network \
    chenyu1990/wildfirechat-server:1.0.0
```
