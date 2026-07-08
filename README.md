![Header](https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,100:2563eb&height=220&section=header&text=Silas%20%7C%20Go%20Backend&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=High-Concurrency%20Systems%20%7C%20IM%20Architecture%20%7C%20Cloud-Native%20Deployment&descAlignY=58&descSize=16)

<div align="center">

# Hi，我是 Silas 👋

**Go 后端开发者｜高并发系统｜IM 架构｜云原生部署**

> “Happiness is the full use of your powers along lines of excellence.”  
> **幸福，是沿着卓越的方向，充分使用自己的能力。**

</div>

---

## 🧭 关于我

我是一名后端开发者，当前主要方向是 **Go 后端开发、高并发系统、即时通信系统、云原生部署**。

我关注的不只是“功能能不能跑”，而是系统在真实工程环境下是否可靠：

- 高并发下是否会超卖、重复写入、击穿数据库
- MQ 异步链路中消息是否会丢失、重复消费、乱序
- Redis、MySQL、MongoDB 在系统里各自承担什么边界
- 权限、幂等、限流、熔断、重试、补偿是否设计完整
- 服务是否能被部署、观测、排查和持续迭代

我更愿意把后端理解成一套 **处理复杂性、约束风险、保证系统正确性** 的工程能力，而不只是写接口。

---

## 🛠 技术栈

<div align="center">

![Go](https://img.shields.io/badge/Go-后端开发-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-缓存%20%2F%20限流%20%2F%20Lua-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-事务%20%2F%20索引%20%2F%20锁-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-文档数据库-47A248?style=for-the-badge&logo=mongodb&logoColor=white)

![Docker](https://img.shields.io/badge/Docker-容器化部署-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-服务器运维-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Nginx](https://img.shields.io/badge/Nginx-反向代理-009639?style=for-the-badge&logo=nginx&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)

</div>

---

## 🚀 代表项目

### 1. 高并发抽奖 / 秒杀系统

> 一个基于 Go 的高并发后端项目，模拟秒杀、抽奖等瞬时流量冲击场景。

**核心能力：**

- Redis Lua 脚本实现库存原子预扣
- 用户资格记录 + TTL，避免重复抢占
- MQ 异步削峰，降低数据库写入压力
- MySQL 唯一索引兜底幂等，防止重复落库
- Outbox / 重试 / 补偿机制处理消息可靠性
- 限流、熔断保护核心链路
- SSE 实时指标面板观察压测过程
- 区分 Redis 临时资格、MQ pending、MySQL 最终订单状态

**我关注的问题：**

这个项目不是简单的“扣库存接口”，而是围绕高并发场景下的真实风险展开：

- 如何防止超卖？
- Redis 已经防重，为什么 MySQL 还需要唯一索引？
- MQ 消息丢了怎么办？
- 消息重复消费怎么办？
- 数据库被瞬时流量打爆怎么办？
- Redis 成功、DB 失败时如何补偿？
- 最终一致性链路如何观测？

项目地址：

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=Silas-Go&repo=lottery&theme=tokyonight)](https://github.com/Silas-Go/lottery)

---

### 2. 家校沟通 / IM 平台

> 一个偏生产场景的家校沟通与管理系统，包含小程序端、管理后台、后端服务和线上部署链路。

**核心能力：**

- WebSocket + HTTP 实现即时通信
- 消息游标分页，支持历史消息稳定拉取
- 老师、家长、学生、班级之间的权限隔离
- MongoDB 建模：会话、消息、报告、资料、照片、学生、教学单元
- 腾讯云 COS 存储语音、图片、资料文件
- 管理后台维护班级、老师、学生、家长、管理员、人脸档案
- Linux + Docker + Nginx + GitHub Actions 自动化部署
- 线上问题排查：日志、容器、MongoDB、部署链路、权限问题

**我关注的问题：**

这个项目的价值不在于普通 CRUD，而在于真实业务系统中的复杂性：

- 会话权限如何建立和关闭？
- 老师转班、学生转班后历史数据如何保留？
- 家长绑定多个孩子时权限如何隔离？
- 图片、语音、资料文件如何存储和访问？
- 小程序、后台、后端、服务器部署如何联动？
- 线上数据异常如何修复且不影响运行？

项目地址：

[![Readme Card](https://github-readme-stats.vercel.app/api/pin/?username=Silas-Go&repo=parent-connect-backend&theme=tokyonight)](https://github.com/Silas-Go/parent-connect-backend)

---

## 🧠 正在深入学习

### Go 后端

- Go runtime 与 GMP 调度模型
- Goroutine 泄漏、context 取消、并发控制
- channel、mutex、atomic 在工程中的使用边界
- slice、map、interface、defer 等高频基础细节
- Go 项目结构、错误处理、日志、配置管理

### 数据库与缓存

- MySQL 索引、联合索引、回表、覆盖索引
- 事务隔离级别、行锁、间隙锁、死锁
- Redis 数据结构、Lua 脚本、过期策略、持久化
- 缓存穿透、击穿、雪崩、热点 Key 保护
- MongoDB 文档建模与权限数据建模

### 分布式与高并发

- 幂等设计
- MQ 重试、死信队列、重复消费
- Outbox Pattern
- 最终一致性
- 限流、熔断、降级
- 压测、指标、日志与可观测性

---

## 📌 工程观念

- **Redis 很快，但数据库必须是最终事实来源。**
- **幂等不是加分项，是分布式系统的基本盘。**
- **MQ 解决削峰和异步，不自动保证业务正确性。**
- **限流不是为了拒绝用户，而是为了保护系统活下来。**
- **好的后端不是把 CRUD 写完，而是要覆盖失败路径。**
- **架构可以简单，但不能天真。**

---

## 📊 GitHub 数据

<div align="center">

![Silas's GitHub stats](https://github-readme-stats.vercel.app/api?username=Silas-Go&show_icons=true&theme=tokyonight&hide_border=true)

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=Silas-Go&layout=compact&theme=tokyonight&hide_border=true)

![GitHub Streak](https://streak-stats.demolab.com?user=Silas-Go&theme=tokyonight&hide_border=true)

</div>

---

## 🐍 Contribution Graph

<div align="center">

![snake gif](https://github.com/Silas-Go/Silas-Go/blob/output/github-contribution-grid-snake.svg)

</div>

---

## 📫 联系方式

- GitHub: [Silas-Go](https://github.com/Silas-Go)
- 技术方向：Go 后端 / 高并发系统 / IM 架构 / 云原生部署

---

<div align="center">

**沿着卓越的方向，充分使用自己的能力。**

</div>

![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:2563eb,100:0f172a&height=120&section=footer)
