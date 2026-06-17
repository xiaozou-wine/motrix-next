<div align="center">
  <img src="src/assets/logo.png" alt="Motrix Next" width="128" height="128" style="border-radius: 24px;" />
  <h1>Motrix Next (Multi-source Edition)</h1>
  <p>基于 <a href="https://github.com/AnInsomniacy/motrix-next">Motrix Next</a> 修改，支持多源下载。</p>

[![GitHub release](https://img.shields.io/github/v/release/xiaozou-wine/motrix-next.svg)](https://github.com/xiaozou-wine/motrix-next/releases)
![Platform](https://img.shields.io/badge/platform-Windows-blue.svg)

</div>

---

## 新增功能

### 多源下载

同一文件有多条直链时，可以在新建任务中粘贴多条链接（每行一个），开启「多源下载」开关，让 aria2 同时从多个源拉取分片，合并为一个文件。

### 任务计时器

下载开始后自动计时，暂停时暂停，完成后显示总耗时。

### 实际源数

任务详情 Sources 标签新增独立 URL 数量显示。

## 直链获取

本项目配合 [xiaozou-wine/goodlink](https://github.com/xiaozou-wine/goodlink) 使用，可导入百度网盘账号获取多条直链。

脚本修改自 [LinkSwift](https://github.com/LinkSwift)。

## 使用方法

1. 从 [goodlink](https://github.com/xiaozou-wine/goodlink) 获取直链脚本，导入百度网盘账号
2. 在分享页面获取多条直链
3. 打开 Motrix Next → 新建任务 → 粘贴直链（每行一条）
4. 开启「多源下载」→ 提交

### UA 配置

百度网盘需要设置 User-Agent：

1. 设置 → User-Agent → 新建 Profile，UA 值填 `pan.baidu.com`
2. 新建规则，Host Pattern 填 `*.baidu.com`，选择刚创建的 Profile

## 安装

从 [GitHub Releases](https://github.com/xiaozou-wine/motrix-next/releases) 下载安装包。

## 致谢

- [Motrix Next](https://github.com/AnInsomniacy/motrix-next) by AnInsomniacy
- [LinkSwift](https://github.com/LinkSwift)

## License

[MIT](https://opensource.org/licenses/MIT)
