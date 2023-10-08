### 自动续签工具

#### 安装

```bash
# 官方安装
wget -O - https://get.acme.sh | sh -s email=[邮箱地址]
# 国内镜像
curl https://gitcode.net/cert/cn-acme.sh/-/raw/master/install.sh?inline=false | sh -s email=my@example.com

# 安装acme-php
git clone https://github.com/cclilshy/acme-php
```

#### 配置文件

```json lines
{
  "acme_path": "/root/.acme.sh",
  // acme.sh路径,一般不用改
  "reload_command": "nginx -s reload",
  // 重载web容器命令,一般不用改
  
  "sites": [
    // 站点1号
    {
      "name": "mix",
      //站点名称
      "path": "/www/wwwroot/dev/public",
      //站点根目录
      "domains": [
        "www.example.com",
        "test.example.com"
      ],
      //域名列表,逗号分隔
      "cert_file": "/www/server/panel/vhost/cert/dev/fullchain.pem",
      //证书文件保存地址
      "key_file": "/www/server/panel/vhost/cert/dev/privkey.pem",
      //密钥文件保存地址
      "ca_file": "/dev/null",
      //ca文件目录,不用修改
      "fullchain_file": "/dev/null"
      //fullchain文件目录,不用修改
    },
    // 站点2号
    {
      "name": "mix",
      //站点名称
      "path": "/www/wwwroot/dev/public",
      //站点根目录
      "domains": [
        "www.example.com",
        "test.example.com"
      ],
      //域名列表,逗号分隔
      "cert_file": "/www/server/panel/vhost/cert/dev/fullchain.pem",
      //证书文件保存地址
      "key_file": "/www/server/panel/vhost/cert/dev/privkey.pem",
      //密钥文件保存地址
      "ca_file": "/dev/null",
      //ca文件目录,不用修改
      "fullchain_file": "/dev/null"
      //fullchain文件目录,不用修改
    }

    // 站点3号...
  ]
}
```

#### 使用方法
```bash
./acme #配置好配置文件后,执行此命令即可
```
