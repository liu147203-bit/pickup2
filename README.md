# Pickup Windows 便携版

这是 `PickupWindows` 的可直接运行 Windows 便携包。

## 下载与运行

1. 下载仓库中的 **`PickupWindows-portable.zip`**。
2. 右键压缩包并选择“全部解压”，不要直接在压缩包预览窗口中运行。
3. 打开解压后的 `PickupWindows-portable` 文件夹。
4. 双击 `run.bat`，也可以直接双击 `PickupWindows.exe`。

程序不需要安装，也没有写死原电脑路径。整个文件夹复制到其他 Windows 电脑后仍可使用。

## 系统要求

- Windows 10 / Windows 11（推荐）
- .NET Framework 4.x
- 无需管理员权限

## 压缩包内容

```text
PickupWindows.exe      已编译的 Windows 主程序
PickupWindows.cs       完整 C# 源码
run.bat                一键启动；缺少 exe 时自动尝试编译
build-csharp.bat       从源码重新编译
README.md              完整使用说明
SHA256SUMS.txt         包内文件完整性校验值
```

## 数据与隐私

程序数据保存在每个使用者自己的 Windows 用户目录：

```text
%USERPROFILE%\.sessiontracker\pickup-windows.xml
```

便携包中不包含上传者电脑上的个人 session 数据。因此，别人下载后会得到相同程序，但会在自己的电脑上生成独立数据。

## 兼容性说明

程序使用 Windows WinForms 和 UI Automation。不同 AI 桌面应用是否能读取到完整会话标题，取决于该应用是否向 Windows 暴露辅助功能控件；不能读取时会退化为记录前台窗口标题与活动时间。

## 文件校验

仓库根目录的 `SHA256SUMS.txt` 可用于验证下载的便携包是否完整。

> 当前可执行文件没有商业代码签名，Windows 可能显示“未知发布者”。可先验证 SHA-256，或使用压缩包中的源码自行编译。

## 上游说明

本项目是根据 GitHub 项目 `RaylinWang/pickup` 制作的 Windows 适配版本。
