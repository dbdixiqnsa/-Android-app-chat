# Android 即时通讯应用 🚀

![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)

基于安卓原生开发与Spring Boot后端的即时通讯解决方案，支持跨网络实时消息传输。

## 🌟 核心特性
- 基于TCP/IP协议的实时消息传输
- Spring Boot服务端提供RESTful API
- MySQL数据库存储结构化数据
- 花生壳内网穿透实现公网访问
- 用户头像与多媒体文件云端存储

---

## 🛠️ 部署指南

### 环境要求
| 工具                | 用途                     | 官方链接                          |
|---------------------|--------------------------|-----------------------------------|
| IntelliJ IDEA       | 服务端开发               | [官网下载](https://www.jetbrains.com/idea/) |
| Android Studio      | 客户端开发               | [官网下载](https://developer.android.com/studio) |
| 花生壳              | 内网穿透                 | [下载地址](https://hsk.oray.com) |
| MySQL 8.0+          | 数据库服务               | [下载地址](https://dev.mysql.com/downloads/mysql) |

---

### 🚦 部署流程

#### 1. 数据库配置
1. 安装MySQL并配置环境变量  
   📖 [环境变量配置教程](https://blog.csdn.net/qq_52853542/article/details/124669072)
2. 执行数据库脚本初始化表结构
-- 在IDEA Database工具中执行仓库中的SQL脚本
   
2. 内网穿透配置
花生壳客户端安装与注册

创建HTTP映射规则：

内网主机：本地IP地址

内网端口：8080

外网域名：花生壳分配的公网域名

📌 花生壳配置教程

3. 服务端配置
修改 Serve/src/main/resources/application.properties：<br>spring.datasource.username=您的数据库账号<br>spring.datasource.password=您的数据库密码<br>
spring.web.resources.static-locations为用户上传的头像等图片的保存位置，该项目已经将该文件夹放入仓库，在自己电脑上运行时请修改为自己的路径，类似于file:///E:/Chat_informations/post_images/  文件夹结构请勿改变<br>
5. 客户端配置
修改 Client/java/com/example/chat/utils/Constants.java：<br>public class Constants {<br>
&nbsp;&nbsp;&nbsp;&nbsp;// 使用花生壳分配的公网域名<br>
&nbsp;&nbsp;&nbsp;&nbsp;public static final String BASE_URL = "http://你得到的域名/api";<br>
&nbsp;&nbsp;&nbsp;&nbsp;public static final String VERSION_BASE_URL = "http://你得到的域名";<br>
}<br>
⚠️ 注意事项
确保服务端端口8080未被占用

防火墙需放行8080端口流量

📬 技术支持
遇到问题？欢迎随时联系：

联系方式	账号
📧 QQ	1652855974&nbsp;&nbsp;&nbsp;&nbsp;
💬 微信	Lgy2873551074
