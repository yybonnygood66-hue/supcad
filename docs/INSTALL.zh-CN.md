# SupCAD 跨电脑安装包

导出日期：2026-11-10。适用于将 Windows 电脑的 SupCAD 技能迁移到另一台 Codex。

## 安装

1. 从本仓库 Releases 下载 ZIP，先完整解压；不要在压缩包内直接运行。
2. 在解压后的 `SupCAD-Portable` 文件夹打开 PowerShell，执行：

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\Install-SupCAD.ps1
```

此参数仅作用于本次进程，不修改系统执行策略。若组织策略禁止运行脚本，使用手动安装方式。

3. 脚本安装到 `$CODEX_HOME/skills`；未设 `CODEX_HOME` 时为当前用户的 `~/.codex/skills`。也可通过 `-SkillsDirectory` 指定另一安装路径。安装前校验文件散列；已有同名技能会备份到目标 skills 的相邻目录，再安装新副本。
4. 重新打开 Codex 并创建新聊天，让它检查是否发现 `$supcad`。

手动安装：把本包 `skills` 内的全部 14 个技能文件夹放入目标 Codex 的用户技能目录，保持它们互为同级；保留已有文件备份。可根据目标版本的技能设置选择实际目录。

## 给另一台 Codex 的启动提示词

```text
已安装本包 SupCAD 技能。请使用 $supcad，先读取 references/portable-installation.md，检查配套技能及目标电脑依赖。把来源电脑的绝对路径重新定位；按我接下来要做的工作配置用户级隔离环境，先做一个小型 CAD/DXF 生成、打开和检查。报告实际检查结果。外部结构工作台、规范台账及项目原件没有迁移时，明确标记相应功能不可用。
```

## 包含与范围

包含 SupCAD、CAD、DXF、Implicit CAD、DfAM、G-code、Bambu、标准件、SendCutSend、URDF、SRDF、SDF、CAD Viewer、Structure Mechanics，共 14 个技能；保留内置知识库和检索数据库。文件清单及 SHA-256 见 `manifest.json`。

这是技能及随附资源安装包，不是整机软件镜像或全离线依赖包。可安装技能并读取内置知识；实际建模/查看需目标机 Python/Node 等依赖，DWG 操作需原生引擎。外部结构工作台源码、第三方程序、虚拟环境、视频/PDF/DWG 原件、规范台账、账号密钥、设备密码、Codex `config.toml`/`auth.json` 及聊天记录未打包。完整迁移条件见 `supcad/references/portable-installation.md`。

安装脚本在备份后合并复制技能文件，不会删除目标技能中已有的额外文件。保留原项目参数作为来源记录，不据此推定新项目尺寸或规范有效性。

## 校验

安装包 SHA-256：`cde82fd274fe0c1d3618813c3150bd9ad79e379ec68c34356a85b4ec88f37c9a`。

桌面原始安装说明亦作为 Release 附件提供。
