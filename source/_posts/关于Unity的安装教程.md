---
title: 关于Unity的安装教程
date: 2025-08-03 00:36:35
tags: [Unity]
---
# Unity 安装完整指南 (Windows版)

## 前言
本教程将详细指导您在 Windows 系统上完成 Unity 编辑器的安装过程，包含 Unity Hub 安装、编辑器版本选择、许可证激活等关键步骤。

---

## 目录
1. [系统要求](#系统要求)
2. [下载 Unity Hub](#下载-unity-hub)
3. [安装 Unity Hub](#安装-unity-hub)
4. [安装 Unity 编辑器](#安装-unity-编辑器)
5. [激活许可证](#激活许可证)
6. [创建第一个项目](#创建第一个项目)
7. [常见问题](#常见问题)

---

## 系统要求
在安装前，请确保您的 Windows 计算机满足以下要求：

| 组件 | 最低要求 | 推荐配置 |
|------|----------|----------|
| **操作系统** | Windows 10 (64位) | Windows 11 (64位) |
| **CPU** | Intel Core i5-4代 或 AMD 同等 | Intel Core i7-10代 或 AMD Ryzen 7 |
| **内存** | 8GB RAM | 16GB RAM |
| **显卡** | DX10/DX11/DX12 兼容显卡<br>支持 Shader Model 5.0 | NVIDIA GTX 1660 / AMD RX 580 |
| **存储空间** | 30GB 可用空间 | SSD 固态硬盘 (500GB+) |
| **其他** | DirectX 11 兼容显卡 | 支持 Vulkan API |

> 💡 重要提示：
> - Unity 2022 LTS 及以上版本不再支持 32 位系统
> - 需要安装 Visual C++ Redistributable 2019
> - 建议关闭杀毒软件避免安装中断

---

## 下载 Unity Hub
Unity Hub 是管理 Unity 安装的核心工具：

1. 访问官方下载页面：[https://unity.com/download](https://unity.com/download)
2. 点击 **"Download Unity Hub"** 按钮
3. 选择 Windows 版本下载：
   - 文件名称：`UnityHubSetup.exe`
   - 大小：约 100MB

> ⚠️ 安全提示：务必从官方渠道下载，避免第三方修改版本

---

## 安装 Unity Hub

### 安装步骤
1. 双击下载的 `UnityHubSetup.exe`
2. 接受许可协议
3. 选择安装位置（默认推荐）:C:\Program Files\Unity Hub\
4. 点击 "Install" 开始安装
5. 安装完成后启动 Unity Hub

### 首次启动配置
1. 创建 Unity ID 或登录现有账号
2. 选择界面语言（推荐英文）
3. 设置默认项目存储位置：D:\UnityProjects\ # 推荐非系统盘
4. 启用自动更新功能

---

## 安装 Unity 编辑器
通过 Unity Hub 安装编辑器：

1. 在 Unity Hub 左侧菜单选择 **"Installs"**
2. 点击右上角 **"Install Editor"** 按钮
3. 选择长期支持版 (LTS)：
- 推荐版本：**Unity 2022.3 LTS**
- 避免使用技术预览版 (Tech Stream)

4. 添加所需模块（根据开发需求选择）：
| 模块 | 必选 | 说明 |
|------|------|------|
| **Microsoft Visual Studio** | ✓ | 代码编辑器（C#开发必备） |
| **Android Build Support** | ✓ | 安卓应用开发 |
| **Windows Build Support** | ✓ | PC 游戏开发 |
| **WebGL Build Support** | ✓ | 网页游戏开发 |
| **Documentation** | ✓ | 离线文档 |
| **Unity Test Framework** | △ | 单元测试工具 |

5. 选择安装位置（至少 20GB 空间）：D:\Unity\Editor\2022.3.20f1\ # 示例路径
6. 点击 **"Install"** 开始下载安装

> ⏱ 安装时间参考：
> - 基础编辑器：约 15-30 分钟
> - 包含所有模块：约 60-90 分钟

---

## 激活许可证
首次使用需激活免费许可证：

1. 在 Unity Hub 左侧菜单选择 **"Licenses"**
2. 点击右上角 **"Add License"**
3. 选择 **"Unity Personal"**
4. 阅读并同意条款：
- 年收入 < $100,000 可使用免费版
- 禁止使用于敏感行业（赌博等）
5. 点击 **"Done"** 完成激活

> 💼 专业版说明：年收入 > $100,000 需购买 $399/月的 Unity Pro

---

## 创建第一个项目
1. 在 Unity Hub 中点击 **"New project"**
2. 选择模板：
| 模板 | 用途 |
|------|------|
| **3D Core** | 标准3D项目（推荐新手） |
| **2D** | 2D游戏开发 |
| **URP** | 通用渲染管线（平衡画质/性能） |
| **HDRP** | 高清渲染管线（影视级画质） |

3. 设置项目：

项目名称: MyFirstUnityProject
位置: D:\UnityProjects\  # 推荐非系统盘
版本: 2022.3.20f1 LTS   # 选择已安装的版本
4. 点击 "Create project"
5. 等待 Unity 编辑器初始化（首次启动较慢)

### ❌ 问题：Unity Hub/编辑器启动崩溃

**错误现象**：
- 启动时闪退
- 显示"Unity has stopped working"错误窗口
- 提示显卡驱动相关错误
- 长时间卡在初始化界面无响应
- 启动后立即自动关闭

**可能原因**：
1. 显卡驱动不兼容
2. 图形API配置冲突
3. 配置文件损坏
4. 系统组件缺失（如VC++运行库）
5. 硬件加速冲突

---

#### 解决方案1：更新显卡驱动

# NVIDIA显卡
winget install -e --id NVIDIA.GeForceExperience
# 或手动下载：https://www.nvidia.com/Download/index.aspx

# AMD显卡
winget install -e --id AMD.Catalyst
# 或手动下载：https://www.amd.com/support

# Intel集成显卡
winget install -e --id Intel.IntelDriverAndSupportAssistant
# 或手动下载：https://www.intel.com/content/www/us/en/download-center/home.html

#### 解决方案2：添加启动参数

通过创建特殊快捷方式强制使用特定图形API：


# 创建Unity Hub安全模式快捷方式
$hubPath = "C:\Program Files\Unity Hub\Unity Hub.exe"
$hubShortcut = "C:\Users\Public\Desktop\Unity Hub (Safe Mode).lnk"
$WshShell = New-Object -ComObject WScript.Shell
$Shortcut = $WshShell.CreateShortcut($hubShortcut)
$Shortcut.TargetPath = $hubPath
$Shortcut.Arguments = "--disable-gpu"
$Shortcut.Save()

# 创建Unity编辑器OpenGL模式快捷方式
$editorPath = "C:\Program Files\Unity\Hub\Editor\2022.3.20f1\Editor\Unity.exe"
$editorShortcut = "C:\Users\Public\Desktop\Unity Editor (OpenGL).lnk"
$Shortcut = $WshShell.CreateShortcut($editorShortcut)
$Shortcut.TargetPath = $editorPath
$Shortcut.Arguments = "-force-opengl"
$Shortcut.Save()

#### 解决方案3：安装必要运行库
# 安装最新VC++运行库
winget install Microsoft.VCRedist.2015+.x64

# 安装.NET Framework 4.8
winget install Microsoft.DotNet.DesktopRuntime.6

# 安装DirectX最终用户运行时
choco install directx -y

### ❌ 问题：许可证激活失败

**错误现象**：
- 提示"License activation failed"错误
- 无法选择Unity Personal免费许可证
- 显示"License is not valid"
- 反复要求重新激活
- 激活窗口卡在加载状态

**可能原因**：
1. 网络连接问题
2. 防火墙/安全软件阻止
3. 本地许可证文件损坏
4. 系统时间/时区设置错误
5. Unity账号问题

---

#### 解决方案1：命令行激活


# 步骤1：切换到Unity安装目录
cd "C:\Program Files\Unity\Hub\Editor\2022.3.20f1\Editor"

# 步骤2：释放当前许可证
.\Unity.exe -returnlicense -batchmode -quit

# 步骤3：手动激活（会打开浏览器）
.\Unity.exe -manualactivate

# 步骤4：强制关闭Unity进程
Get-Process Unity | Stop-Process -Force

# 步骤5：验证激活状态
.\Unity.exe -batchmode -nographics -quit -logFile | Select-String "License type:"

解决方案2：离线激活

#1. **访问手动激活页面**  
   打开浏览器访问：  
   [https://license.unity3d.com/manual](https://license.unity3d.com/manual)

#2. **登录Unity账号**  
   ![登录页面](https://i.imgur.com/LzKJ9cP.png)  
   使用与Unity Hub相同的账号登录

#3. **生成许可证文件**  
   
   graph LR
     A[选择许可证类型] --> B[Unity Personal]
     B --> C[确认系统信息]
     C --> D[生成.ulf文件]

#4. **下载许可证文件** 
   - 文件名格式：`Unity_v2022.x.ulf`
   - 保存位置：默认在`下载`文件夹
   - 文件内容示例：
     ```xml
     <LICENSE>
       <UNITY>2022.3.20f1</UNITY>
       <SERIAL>US-XXXX-XXXX-XXXX-XXXX-XXXX</SERIAL>
       <EMAIL>your@email.com</EMAIL>
       <MACHINE>XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX</MACHINE>
     </LICENSE>
     ```
	 
#5. **放置许可证文件**

 创建Unity许可证目录（如果不存在）
New-Item -Path "C:\ProgramData\Unity" -ItemType Directory -Force

 移动许可证文件
Move-Item -Path "$env:USERPROFILE\Downloads\Unity_v2022.x.ulf" `
          -Destination "C:\ProgramData\Unity\Unity_lic.ulf" `
          -Force

 验证文件位置
Test-Path "C:\ProgramData\Unity\Unity_lic.ulf"
#6. **打开Unity验证激活状态**