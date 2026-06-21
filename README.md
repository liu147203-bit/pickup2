# Pickup Windows

Pickup Windows 是根据 GitHub 项目 `RaylinWang/pickup` 制作的 Windows 便携版复刻。

## 下载后直接使用

1. 在 GitHub 仓库页面点击 **Code → Download ZIP**，或下载 `dist/PickupWindows-portable.zip`。
2. **先完整解压**，不要直接在压缩包预览窗口里运行。
3. 双击 `run.bat`；也可以直接双击 `PickupWindows.exe`。

程序不需要安装，也不依赖仓库所在的固定路径。把整个文件夹复制到另一台 Windows 电脑后仍可运行。

## 系统要求

- Windows 10 / Windows 11（推荐）
- .NET Framework 4.x
- 普通用户权限即可；无需管理员权限

仓库已经包含编译好的 `PickupWindows.exe`。只有在可执行文件被删除、或你修改了源码时，才需要运行 `build-csharp.bat` 重新编译。

> 说明：当前可执行文件没有商业代码签名，Windows 可能显示未知发布者提示。可先对照 `SHA256SUMS.txt` 验证文件，或使用源码自行编译。

## 文件说明

```text
PickupWindows.exe      已编译的 Windows 主程序
PickupWindows.cs       完整 C# 源码
run.bat                一键启动；缺少 exe 时自动尝试编译
build-csharp.bat       使用系统自带 .NET Framework 编译器构建
SHA256SUMS.txt         文件完整性校验值
```

## 已实现

- Windows 桌面常驻，关闭窗口后隐藏到托盘。
- 自动扫描 Codex session。
- 自动扫描 Claude Code session。
- 自动扫描常见 AI 工具本地缓存目录。
- 每 30 秒自动刷新 session。
- 每 2.5 秒检测当前前台 AI / Agent 窗口。
- 支持豆包、ChatGPT、Claude、DeepSeek、Kimi、通义、元宝、Cursor、Windsurf、Trae、Copilot 等窗口活动记录。
- 尝试通过 Windows UI Automation 读取桌面端侧边栏标题。
- 支持新建项目、分配 session、归档项目、隐藏 session。
- 支持给 session 添加网站、链接、路径和备注。

## 数据位置

每台电脑的数据独立保存在当前 Windows 用户目录：

```text
%USERPROFILE%\.sessiontracker\pickup-windows.xml
```

因此，把程序文件夹分享给别人不会携带你电脑上的个人 session 数据。

## 重新编译

双击：

```bat
build-csharp.bat
```

脚本会自动识别 32 位或 64 位 .NET Framework 目录，并生成新的 `PickupWindows.exe`。

## Windows 平台限制

macOS 原项目可以依赖 Accessibility 读取桌面端侧边栏。Windows 版使用 UI Automation 尝试读取，但能否获得完整会话标题取决于对应 AI 应用是否向系统暴露控件文本。

如果某个桌面端不暴露侧边栏和聊天标题，程序会退化为记录前台窗口活动片段，包括 AI 名称、窗口标题和使用时间。

## 上游项目

- 原项目：`RaylinWang/pickup`
- 本仓库为 Windows 适配版本，保留上游项目说明与归属。
