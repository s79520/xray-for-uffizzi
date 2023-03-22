# xray for Uffizzi

TIPS: 可点击仓库的“Use this template”在仓库的原基础上创建私库

![image](https://user-images.githubusercontent.com/122191366/212063458-2def0e1a-805a-4451-ae62-324b67abee47.png)

## 项目特点

* 本项目用于在Uffizzi云服务商部署xray ，采用的方案为 Nginx + WebSocket + VMess/Vless/Trojan/Shadowsocks + TLS
* xray 核心文件和配置文件作了“特殊处理”，每个项目都不同，大大降低被封和连坐风险
* vmess 和 vless 的 uuid 或 trojan 和 shadowsocks 的密码，路径既可以自定义，又或者使用默认值
* 集成哪吒探针，可以自由选择是否安装
* 部署完成如发现不能上网，请检查域名是否被墙，可使用 Cloudflare CDN 或者 worker 解决。

## 客户端配置       添加节点如图

![image](https://user-images.githubusercontent.com/127391868/227061338-c4a75463-9b78-462c-9b9b-d69e1518637d.png)


## 部署

* 注册 [Uffizzi](https://www.uffizzi.com/)
* 在 `entryport.sh` 的 4-11 行修改项目变量
* 项目用到的变量
  | 变量名 | 是否必须 | 默认值 | 备注 |
  | ------------ | ------ | ------ | ------ |
  | UUID         | 否 | de04add9-5c68-8bab-950c-08cd5320df18 | 可在线生成 https://www.uuidgenerator.net/ |
  | VMESS_WSPATH | 否 | /vmess | 以 / 开头 |
  | VLESS_WSPATH | 否 | /vless | 以 / 开头 |
  | TROJAN_WSPATH | 否 | /trojan | 以 / 开头 |
  | SS_WSPATH | 否 | /shadowsocks | 以 / 开头 |
  | NEZHA_SERVER | 否 |        | 哪吒探针服务端的 IP 或域名 |
  | NEZHA_PORT   | 否 |        | 哪吒探针服务端的端口 |
  | NEZHA_KEY    | 否 |        | 哪吒探针客户端专用 Key |
