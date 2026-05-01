# AppStore软件源管理系统-GO版

基于 Go + Vue3 开发的 iOS 软件源管理后台
## 项目截图
   <img width="2560" height="1279" alt="image" src="https://github.com/user-attachments/assets/c43b4988-8780-4c2b-8a25-439115dac2da" />
   <img width="2560" height="1279" alt="image" src="https://github.com/user-attachments/assets/4c8f0d87-4206-44c2-b2d0-154d33d0cef1" />
   <img width="2560" height="1279" alt="image" src="https://github.com/user-attachments/assets/19df3512-daf7-444c-bf5a-69738a29ae3c" />
   <img width="2560" height="1279" alt="image" src="https://github.com/user-attachments/assets/ccf793c3-e502-47fa-882a-76c8039da20b" />
   <img width="2560" height="1279" alt="image" src="https://github.com/user-attachments/assets/9ce85a92-f88d-4a8b-8dea-cc56d637ee13" />
   <img width="2560" height="1279" alt="image" src="https://github.com/user-attachments/assets/db4e145f-5a85-4bfa-899a-3e3a7e1fcc81" />

## 客服QQ 778610 可联系客服付费搭建 备注来源
   ```
   自助授权：http://auth.pkq7.cn 永久50米
   ```

## 技术栈

- 后端：Go 1.21+ / Gin / GORM / MySQL
- 前端：Vue3 / TypeScript / Element Plus / Vite
- 部署：宝塔面板 / Linux

## 功能

- App 管理（支持 IPA 上传自动解析、云存储）
- 卡密管理（生成/激活/批量删除）
- UDID 黑名单（含公开对接接口）
- UDID 监控
- 系统配置（软件源/网站/云存储）
- 工作台数据统计
- 软件源搬运 支持加密源
- 自动化搬运 支持加密源
- 下载地址检查
- 安装引导系统

2.0预计更新 几个首页预览 应用签名功能 预计五月底更新

## 安装部署

### 环境要求

- Linux 服务器（推荐宝塔面板）
- Go 1.21+
- MySQL 5.7+

### 宝塔面板部署

1. 宝塔 → 软件商店 → 安装 **Go 项目管理器**

2. 新建 Go 项目：
   - 项目路径：上传的程序目录
   - 启动文件：`go-source-linux`
   - 端口：`1117`（或自定义）
   - 环境变量：指定变量
   ```
   PORT=1117（端口）
   ```

3. 添加网站，开启反向代理：
   ```
   代理目标：http://127.0.0.1:1117
   ```

4. 访问域名 `/install` 完成安装引导

---

### 安装引导说明

访问 `/install` 路径，按步骤填写：

| 配置项 | 说明 |
|--------|------|
| 数据库主机 | 通常为 `127.0.0.1` |
| 数据库端口 | 默认 `3306` |
| 数据库用户名 | MySQL 用户名 |
| 数据库密码 | MySQL 密码 |
| 数据库名 | 提前创建好的数据库名 |
| 服务端口 | Go 程序监听端口，默认 `1117` |
| 后台路径 | 自定义后台入口，如 `admin` |
| GO项目名称 | 宝塔中的项目名，用于自动重启 |
| 网站名称 | 显示在后台的站点名称 |
| 管理员账号 | 登录后台的用户名 |
| 管理员密码 | 登录后台的密码 |

---

## 软件源接口

公开接口，无需认证：

```
GET /appstore        # 获取软件源数据
GET /Blacklist       # 获取黑名单列表
GET /Blacklist/check?udid=xxx  # 检查单个 UDID
```

## 目录结构

```
├── go-source/       
│   └── dist/           # 前端构建产物（运行时需要）
│   └── go-source-linux/           # 运行文件
```


