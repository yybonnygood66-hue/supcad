# SupCAD 技能安装包

SupCAD 是面向 Codex 的 CAD 与工程绘图技能集合。本仓库提供 Windows 迁移安装包、安装说明和完整性校验文件，方便在另一台电脑安装使用。

## 下载

请进入 **[最新发布版本（Releases）](https://github.com/yybonnygood66-hue/supcad/releases/latest)**，下载 Assets 中的安装 ZIP、安装说明和 SHA-256 校验文件。

当前安装包导出日期：**2026-11-10**；ZIP 大小：126,105,136 字节（约 120.3 MiB），完整解压约 961 MiB。请下载 Release 附件中的安装包；GitHub 自动生成的 Source code 压缩包仅包含本仓库说明文件。

## 安装

1. 下载并完整解压安装 ZIP。
2. 在解压后的 `SupCAD-Portable` 文件夹打开 PowerShell，执行：

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\Install-SupCAD.ps1
```

该参数仅作用于本次 PowerShell 进程。脚本会验证包内 SHA-256，备份已有同名技能，复制并核对安装结果。

3. 默认安装到 `$CODEX_HOME/skills`；未设置 `CODEX_HOME` 时为当前用户的 `~/.codex/skills`。可用 `-SkillsDirectory` 指定目录。
4. 重新打开 Codex，创建新聊天并请求使用 `$supcad`。

若不能运行脚本，可手动将包内 `skills` 下的全部 14 个文件夹复制到 Codex 用户技能目录，保持同级，并提前备份已有文件。

详细步骤与启动提示词见 [安装说明](docs/INSTALL.zh-CN.md)。

## 包含的技能

SupCAD、CAD、DXF、Implicit CAD、DfAM、G-code、Bambu、标准件、SendCutSend、URDF、SRDF、SDF、CAD Viewer、Structure Mechanics，共 14 个技能，并包含随附知识库和检索数据库。

## 使用条件和范围

这是技能及随附资源安装包。建模和查看仍需按目标电脑配置 Python、Node 等依赖；DWG 操作需要原生引擎。AutoCAD 等第三方程序及其授权需另行准备。

外部结构工作台源码、第三方程序、虚拟环境、视频/PDF/DWG 原件、项目规范台账、账号密钥、设备密码、Codex 配置与聊天记录不在包内。安装后请先阅读 `supcad/references/portable-installation.md` 并检查实际依赖。结构计算能力以目标环境的实际检查结果为准，项目参数与旧规范记录不能直接作为新项目的确定设计依据。

## 文件校验

安装 ZIP 的 SHA-256：

```text
cde82fd274fe0c1d3618813c3150bd9ad79e379ec68c34356a85b4ec88f37c9a
```

可在 PowerShell 中执行 `Get-FileHash -Algorithm SHA256 -LiteralPath '安装包的完整路径'`，与上述值及 Release 校验文件核对。包内 `manifest.json` 另提供逐文件清单和散列。

## 许可说明

安装包中各组件保留其原有 LICENSE 和许可说明；本仓库未对第三方组件重新授权。
