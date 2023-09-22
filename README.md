# core-keeper-server

Server 架設流程

```
// 啟動 steamcmd docker
>docker run -p 27015:27015/tcp -p 27036:27036/tcp -p 27015:27015/udp -p 27036:27036/udp  -v F:\core_keeper_server:/home/core_keeper_server  --entrypoint /bin/sh -it --name=core_keeper_server -d steamcmd/steamcmd:ubuntu-20

// 更新 contaner 內的工具
>apt-get update && apt-get upgrade

// 創建新使用者
>useradd -mrU -s /usr/sbin/nologin core_keeper_server

// 下載遊戲 server 檔案
>su - core_keeper_server -s /bin/bash -c "steamcmd +force_install_dir /home/core_keeper_server/server_data +login anonymous +app_update 1007 validate +app_update 1963720 validate +quit"

// 安裝缺少的工具
>apt-get install xvfb

後續設定...
```
