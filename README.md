# 科了个科

## 起源

2024年百团大战社团招新时开发，增加招新的趣味性。本代码基于
[xlegex](https://github.com/chenxch/xlegex)开源项目进行的二次开发，修改了一些图片、提示信息和游戏难度等。

## 功能

- 和2024年爆火的微信小游戏""羊了个羊"有相同的玩法
- 使用ibeike的图片代替游戏中的图片
- 自定义标题等提示信息
- 具有"移出前三个"和"撤销"等游戏道具

## 二次开发
我保留了所有的修改痕迹，直接看commit的历史记录就好了。不需要搞懂复杂的游戏逻辑，能定制化开发就可以了。

## 运行/部署

运行项目&本地调试
```shell
npm run dev
```
打包项目
```shell
npm run build
```
打包之后会生成 ```dist``` 目录，将 ```dist``` 目录下的所有文件上传到服务器上即可。 
服务器的Nginx配置如下：其中 ```/opt/app/kelegeke/dist``` 是上传到服务器上的目录，需要根据实际情况修改。
```text
# 配置文件路径
# /usr/local/nginx/conf/vhost/apps.conf

# 配置文件内容
server {
    listen 80;
    server_name kelegeke.ibeike.work;

    location / {
        root /opt/app/kelegeke/dist;
        index index.html;
        try_files $uri $uri/ /index.html;
    }
}
```
记得重启nginx
```shell
sudo service nginx reload
```