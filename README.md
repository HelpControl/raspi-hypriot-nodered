# これはなに？

Node-RED on Docker on Hypriot on Raspberry Pi

# 起動方法

```bash
$ git clone https://github.com/taturou/raspi-hypriot-nodered.git
$ cd raspi-hypriot-nodered
$ docker-compose build
$ docker-compose up -d
```

# アクセス方法

Webブラウザで `http://{raspi-ip-address}:1880` にアクセス。

# インストール済みのノード

* node-red-contrib-azure-blob-storage
* node-red-node-sensortag
* node-red-contrib-azure-iot-hub
