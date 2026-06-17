<div align="center">
  <img src="src/assets/logo.png" alt="Motrix Next" width="128" height="128" style="border-radius: 24px;" />
  <h1>Motrix Next (Multi-source Edition)</h1>
  <p>基于原版 Motrix Next 修改，支持多源下载 — 多条直链同时下载同一文件以提升速度。</p>

[![GitHub release](https://img.shields.io/github/v/release/xiaozou-wine/motrix-next.svg)](https://github.com/xiaozou-wine/motrix-next/releases)
![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)

</div>

---

## 这是什么？

本项目基于 [AnInsomniacy/motrix-next](https://github.com/AnInsomniacy/motrix-next)（一个用 Tauri 2 + Vue 3 重写的 Motrix 下载器），在此基础上增加了**多源下载**功能。

直链获取脚本修改自 [LinkSwift](https://github.com/LinkSwift)，能够导入百度网盘登录账号，在分享页面上获取多条直链并复制到 Motrix 进行多源下载。

直链获取工具仓库：[xiaozou-wine/goodlink](https://github.com/xiaozou-wine/goodlink)

## 新增功能

### 多源下载

在新建任务时，将同一文件的多条直链粘贴到 URL 文本框（每行一个），打开**多源下载**开关，即可让 aria2 从多个源同时拉取不同分片，合并为一个文件。

**实测效果**（百度网盘直链）：

| 模式 | 时间 | 提升 |
|------|------|------|
| 单源 | 4 分 53 秒 | - |
| 双源 | 2 分 22 秒 | **2.05 倍** |

### 任务计时器

下载开始后自动计时，暂停时计时暂停，完成后显示总耗时。在任务卡片和任务详情中均可查看。

### Sources 显示

任务详情的 Sources 标签新增「实际源数」，显示去重后的独立 URL 数量。

## 使用方法

### 1. 获取百度网盘直链

1. 前往 [xiaozou-wine/goodlink](https://github.com/xiaozou-wine/goodlink) 获取直链获取脚本
2. 导入你的百度网盘账号
3. 在分享页面获取多条直链并复制

### 2. 配置 UA（重要）

百度网盘下载需要设置特定的 User-Agent：

1. 打开 Motrix Next → 设置 → User-Agent
2. 创建新 Profile：
   - **名称**：`百度网盘`
   - **UA 值**：`pan.baidu.com`
3. 创建匹配规则：
   - **Host Pattern**：`*.baidu.com`
   - 选择刚才创建的 Profile

这样遇到百度链接时会自动使用正确的 UA，其他链接不受影响。

### 3. 多源下载

1. 点击**新建任务**
2. 将获取到的多条直链粘贴到 URL 文本框（每行一个）
3. 打开**多源下载**开关
4. 点击提交

### 4. 验证多源是否生效

点击任务 → 切到 **Sources** 标签 → 查看「实际源数」是否大于 1。

## 安装

从 [GitHub Releases](https://github.com/xiaozou-wine/motrix-next/releases) 下载最新安装包。

**Windows**：下载 `MotrixNext_x.x.x_x64-setup.exe`，运行安装即可。

## 开发

```bash
# 前置要求：Rust (stable)、Node.js >= 22、pnpm 11.x

git clone https://github.com/xiaozou-wine/motrix-next.git
cd motrix-next
pnpm install
pnpm tauri dev      # 启动开发环境
pnpm tauri build    # 构建生产版本
```

## 致谢

- [Motrix Next](https://github.com/AnInsomniacy/motrix-next) by AnInsomniacy — 原版项目
- [Motrix](https://github.com/agalwood/Motrix) by agalwood — 初始项目
- [Aria2 Next](https://github.com/AnInsomniacy/aria2-next) — 下载引擎
- [LinkSwift](https://github.com/LinkSwift) — 直链获取脚本原作者

## License

[MIT](https://opensource.org/licenses/MIT)
