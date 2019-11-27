# wildfirechat-server-docker

```
docker run -d \
    --name chat-server \
    --hostname chat-server \
    -v /data/chat-server/config:/opt/wildfirechat/config \
    -p 80:80 -p 1883:1883 -p 8083:8083 -p 18080:18080 \
    --restart on-failure \
    --log-opt max-size=100mb \
    chenyu1990/chat-server:1.0.0
```
