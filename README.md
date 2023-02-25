# docker-nmp

#### 介绍
基于docker的php运行环境
docker+nginx+mysql+php+...

#### 开箱即用的组件
1.  php 7.x 8.x [支持多php版本]
2.  nginx
3.  mysql
4.  redis
5.  postgres


#### 使用说明

1. 安装[docker](https://www.docker.com)
2. 可选-七牛云镜像：[https://reg-mirror.qiniu.com](https://reg-mirror.qiniu.com)
3. 克隆仓库：

```shell 
git clone https://gitee.com/renxiaotu/docker-nmp.git
```

4. 复制配置文件并重命名

```shell 
cd docker-nmp
copy .env.example .env
copy docker-compose-example.yml docker-compose.yml
```

5. 注释*docker-compose.yml*文件内不需要的服务*在代码前加#号*
6. 按照说明修改配置文件
7. 启动服务
```shell
docker compose up -d
```


####目录结构

```
├── build                       // 编译目录
│   └── php-example             // php编译示例 需编译php7.1则复制本文件夹并重命名（与docker-compose.yml内配置一致）
│       ├── install             // composer.phar和pecl安装包放这里
│       └── Dockerfile          // php编译文件
│
├── conf                        // 配置目录
│   ├── mysql-example           // mysql配置示例 复制文件夹为mysql即可
│   ├── nginx-example           // nginx配置示例 复制文件夹为nginx即可
│   ├── php-example             // php配置示例 复制文件夹为php即可（与docker-compose.yml内配置一致）
│   ├── postgres-example        // postgres配置示例 复制文件夹为postgres即可
│   └── redis-example           // redis配置示例 复制文件夹为redis即可
│
├── log                         // 日志目录 无需调整
│
├── ps                          // 常用PowerShell命令
│   ├── del_none.ps1            // 清理名称为<none>的镜像
│   ├── mysql.ps1               // 登录mysql控制台
│   ├── nginx.ps1               // 登录nginx控制台
│   ├── npmr.ps1                // 初始化并启动nginx+php+mysql+redis服务
│   ├── php.ps1                 // 登录php控制台
│   └── redis.ps1               // 登录redis控制台
│
├── .env.example                // 环境变量配置文件示例 复制文件为.env即可
├── .gitignore                  // git忽略配置
├── docker-compose-example.yml  // docker-compose.yml配置文件示例 复制文件为docker-compose.yml即可
└── README.md                   // help
```
