# 🐾 拒绝非酋！自定义你的claude宠物！

<p align="center">
  <img src="https://img.shields.io/badge/Environment-Pure%20Browser-success?style=flat-square" alt="Environment">
  <img src="https://img.shields.io/badge/Claude%20Code-v2.1.89-blue?style=flat-square" alt="Version">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License">
</p>

这是一个专为 **Claude Code** 打造的宠物 (Buddy) 初始号生成器。完全基于纯前端（HTML + JS）编写，**无需安装 Node.js 或 Bun 环境**，双击网页即可开刷！

本项目完美复刻了 Claude Code 原生的 `Mulberry32 PRNG` 与 `FNV-1a` 哈希算法，能精准碰撞出你想要的极品宠物（支持筛选：物种、稀有度、是否闪光、帽子、眼睛），并直接生成原汁原味的 64 位 Hex 秘钥。

## ✨ 核心特性

- 🚀 **零门槛即开即用**：纯浏览器运行，双击 `buddy_finder.html` 即可开始爆破。
- 🎯 **全方位精准狙击**：支持传说级 (Legendary)、闪光 (Shiny) 以及各种外观挂件的强制筛选。
- ⚙️ **算力保护机制**：采用异步分批运算，即使挑战“百万分之一”的极品概率，浏览器也不会卡死。

## 🛠️ 使用教程

### 第一步：爆破你的极品天选 ID
1. 下载本项目中的 `buddy_finder.html` 文件，或者直接访问在线演示页面（如果有）。
2. 在浏览器中打开它。
3. 根据你的喜好选择条件（例如：`传说 Legendary` + `龙 dragon` + `仅闪光 ✨`）。
4. 点击 **“▶ 开始搜索”**。
5. 等待程序碰撞出结果，点击 **“复制 ID”**（你将得到一串 64 位代码）。

### 第二步：写入本地配置 (极简版)

拿到 ID 后，我们需要欺骗 Claude Code 让它以为这就是你的账号：

1. **彻底关闭**正在运行的 Claude Code 终端。
2. 找到你电脑上的 Claude Code 配置文件 `~/.claude.json`：
   - **Windows**: `C:\Users\你的用户名\.claude.json`
   - **Mac/Linux**: `/Users/你的用户名/.claude.json`
3. 用任何文本编辑器（记事本、VS Code）打开它。
4. **⚠️ 关键步骤：**
   - 寻找文件中是否有一行叫 `"companion": {...}` 的配置。**如果有，请将 `"companion"` 及其大括号内的内容全部删除！**（如果不删，系统会读取旧宠物，你的新 ID 不会生效）。
   - 找到 `"userId"` 字段，将它的值替换为你刚刚复制的 64 位新 ID。
   
   修改后的文件结构大致如下：
   ```json
   {
     "userId": "这里粘贴你的64位新ID",
     "autoUpdaterStatus": "dismissed",
     "theme": "dark"
     // 确保这里没有 "companion" 字段！
   }
