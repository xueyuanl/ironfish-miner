# 用Docker部署Iron Fish 铁鱼挖矿

首先我们需要安装好依赖，把`docker`和 `docker-compose`都装好

### 部署环境

设置你的 Set your graffiti 口令，替换成你自己的。
```
docker run --rm -it --network host --volume $HOME/.ironfish:/root/.ironfish ghcr.io/iron-fish/ironfish:latest config:set blockGraffiti "graffiti"
```

然后我们一条命令把环境拉起来，这样就开始挖矿拉。
程序每次会自动拉取最新代码并部署，并在后台运行。
```
# always pull new version and run background
docker-compose pull && docker-compose up -d
```
用这个来检查你的挖矿状态
```
docker exec -it ironfish ./bin/run status -f
```

停止挖矿也是一条命令结束。想再次开始挖矿的话，直接运行上一条即可。
```
docker-compose down
```

# 其他参考命令

Check logs
```
docker-compose logs -f
# or
docker logs miner -f
docker logs ironfish -f
```
Check status
```
docker exec -it ironfish ./bin/run status -f
docker exec -it ironfish ./bin/run config:show
```
