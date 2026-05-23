# 🌍 Global Timezone Tool

<div align="center">

  ![Kotlin Multiplatform](https://img.shields.io/badge/Kotlin-Multiplatform-blue.svg)
  ![Compose Multiplatform](https://img.shields.io/badge/Compose-Multiplatform-FF6AB3C.svg)
  ![License](https://img.shields.io/badge/License-MIT-green.svg)
  ![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20iOS%20%7C%20Web-lightgrey.svg)

  **一款功能强大的全球时区追踪工具**

  [English](#english-documentation) • [中文文档](#中文文档)

</div>

---

## 中文文档

### 📱 应用介绍

Global Timezone Tool 是一款基于 Kotlin Multiplatform 技术开发的跨平台应用，支持 Android、iOS 和 Web 平台。该应用专为频繁需要与世界各地进行时间协调的用户设计，提供实时时区转换、时间差计算、多城市管理等功能。

#### ✨ 核心功能

- **🕐 实时时间显示** - 同时查看多个城市的当前时间
- **⏰ 智能时差计算** - 自动计算任意城市与基准城市的时间差
- **🌍 城市管理** - 添加、删除、排序世界各地的城市
- **🎨 个性化设置** - 12/24小时制、秒显示、多语言支持
- **💾 数据持久化** - 城市列表和设置自动保存
- **🔔 崩溃上报** - 集成 Firebase Crashlytics 确保应用稳定性
- **🌙 深色主题** - 现代化的 Material Design 3 界面

### 🚀 快速开始

#### 环境要求

- **开发工具**: IntelliJ IDEA / Android Studio
- **Kotlin 版本**: 2.3.20+
- **Gradle 版本**: 8.11.2+
- **Android SDK**: API 24+ (Android 7.0+)
- **iOS 版本**: iOS 14.0+
- **浏览器**: Chrome/Firefox/Safari (支持现代 Web 标准)

#### 克隆项目

```bash
git clone https://github.com/YingZiGeGe/Globaltimezonetool.git
cd Globaltimezonetool
```

#### 编译和运行

**Android 应用:**
```bash
# macOS/Linux
./gradlew :composeApp:assembleDebug

# Windows
.\gradlew.bat :composeApp:assembleDebug
```

**iOS 应用:**
```bash
# 在 Xcode 中打开 iosApp/iosApp.xcworkspace 并运行
# 或使用以下命令
./gradlew :composeApp:iosSimulatorArm64Test
```

**Web 应用:**
```bash
# 使用 Wasm 目标（推荐，性能更好）
./gradlew :composeApp:wasmJsBrowserDevelopmentRun

# 或使用 JS 目标
./gradlew :composeApp:jsBrowserDevelopmentRun
```

### 📖 使用指南

#### 1. 添加城市

1. 点击右下角的 `+` 按钮
2. 在城市选择器中搜索您想添加的城市
3. 点击城市名称将其添加到您的城市列表

#### 2. 设置基准城市

- 基准城市用于计算时差
- 在任意城市卡片上点击 "⭐ 设为基准" 按钮
- 基准城市会有特殊标识显示

#### 3. 排序城市

- 长按任意城市卡片上的拖拽手柄（≡）
- 拖动到您想要的位置
- 松开即可完成排序

#### 4. 移除城市

- 点击城市卡片右上角的 `×` 按钮
- 确认移除该城市

#### 5. 设置选项

**进入设置页面:**
- 点击右上角的 `⚙️` 设置图标

**可用设置:**
- **时间格式**: 切换 12/24 小时制
- **秒显示**: 显示/隐藏秒数
- **语言**: 选择界面语言（中文、英文等）
- **隐私政策**: 查看隐私政策和条款

#### 6. 时间计算器

点击右上角的 `🧮` 图标进入时间计算器：
- 选择源城市和目标城市
- 输入时间和日期
- 即时查看转换后的时间
- 支持夏令时自动调整

### 🏗️ 项目结构

```
Globaltimezonetool/
├── composeApp/                    # Kotlin Multiplatform 应用代码
│   ├── src/
│   │   ├── commonMain/            # 跨平台共享代码
│   │   │   ├── kotlin/           # Kotlin 代码
│   │   │   └── resources/        # 共享资源
│   │   ├── androidMain/          # Android 特定代码
│   │   ├── iosMain/              # iOS 特定代码
│   │   └── jsMain/               # Web 特定代码
│   └── build.gradle.kts          # 应用构建配置
├── iosApp/                       # iOS 应用入口点
├── gradle/                       # Gradle 配置
│   ├── libs.versions.toml        # 版本管理
│   └── wrapper/                  # Gradle Wrapper
├── build.gradle.kts              # 项目构建配置
└── README.md                     # 项目说明
```

### 🛠️ 技术栈

- **框架**: Kotlin Multiplatform + Compose Multiplatform
- **UI**: Material Design 3
- **导航**: Voyager
- **数据持久化**: Multiplatform Settings
- **时间处理**: Kotlinx DateTime
- **崩溃报告**: Firebase Crashlytics
- **构建工具**: Gradle 8.x

### 📋 功能特性

#### 核心功能实现

**时区数据处理:**
- 使用 IANA 时区数据库
- 支持全球 500+ 个城市
- 自动处理夏令时变更
- 实时时间同步

**用户界面:**
- Material Design 3 设计规范
- 流畅的动画效果
- 响应式布局
- 深色主题优化

**数据持久化:**
- 城市列表自动保存
- 用户设置持久化
- 基准城市记忆
- 多语言支持

#### 平台特定功能

**Android:**
- Firebase Crashlytics 集成
- 全局异常处理
- 应用状态保存
- 通知支持

**iOS:**
- 原生 Swift 集成
- Crashlytics 框架
- 本地存储降级方案
- Xcode 项目配置

**Web:**
- 浏览器兼容性优化
- 错误捕获机制
- 本地存储支持
- 响应式设计

### 🐛 故障排除

#### 常见问题

**Q: Android 应用无法编译**
```bash
# 清理并重新构建
./gradlew clean
./gradlew :composeApp:assembleDebug
```

**Q: iOS 应用运行时崩溃**
- 确保 Xcode 版本为 14.0 或更高
- 清理 Xcode 缓存: `Product → Clean Build Folder`
- 重新安装 CocoaPods 依赖: `pod install`

**Q: Web 应用无法加载**
- 确保浏览器支持现代 Web 标准
- 尝试使用不同浏览器（Chrome 推荐）
- 清除浏览器缓存后重试

**Q: 城市时间不准确**
- 检查设备时区设置
- 确保网络连接正常
- 尝试重新添加城市

### 📄 许可证

本项目采用 MIT 许可证。详情请查看 [LICENSE](LICENSE) 文件。

### 👨‍💻 贡献

欢迎贡献代码！请遵循以下步骤：

1. Fork 本项目
2. 创建您的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交您的更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

### 📞 联系方式

- **GitHub**: [YingZiGeGe/Globaltimezonetool](https://github.com/YingZiGeGe/Globaltimezonetool)
- **问题反馈**: [Issues](https://github.com/YingZiGeGe/Globaltimezonetool/issues)

---

## English Documentation

### 📱 App Introduction

Global Timezone Tool is a cross-platform application built with Kotlin Multiplatform technology, supporting Android, iOS, and Web platforms. Designed for users who frequently need to coordinate time with different parts of the world, it provides real-time timezone conversion, time difference calculation, and multi-city management features.

#### ✨ Core Features

- **🕐 Real-time Time Display** - View current time for multiple cities simultaneously
- **⏰ Smart Time Difference** - Automatically calculate time differences between cities
- **🌍 City Management** - Add, remove, and reorder cities from around the world
- **🎨 Personalization** - 12/24-hour format, seconds display, multi-language support
- **💾 Data Persistence** - City list and settings are automatically saved
- **🔔 Crash Reporting** - Integrated Firebase Crashlytics for app stability
- **🌙 Dark Theme** - Modern Material Design 3 interface

### 🚀 Getting Started

#### Requirements

- **Development Tool**: IntelliJ IDEA / Android Studio
- **Kotlin Version**: 2.3.20+
- **Gradle Version**: 8.11.2+
- **Android SDK**: API 24+ (Android 7.0+)
- **iOS Version**: iOS 14.0+
- **Browser**: Chrome/Firefox/Safari (modern web standards support)

#### Clone the Project

```bash
git clone https://github.com/YingZiGeGe/Globaltimezonetool.git
cd Globaltimezonetool
```

#### Build and Run

**Android Application:**
```bash
# macOS/Linux
./gradlew :composeApp:assembleDebug

# Windows
.\gradlew.bat :composeApp:assembleDebug
```

**iOS Application:**
```bash
# Open iosApp/iosApp.xcworkspace in Xcode and run
# Or use the command
./gradlew :composeApp:iosSimulatorArm64Test
```

**Web Application:**
```bash
# Using Wasm target (recommended, better performance)
./gradlew :composeApp:wasmJsBrowserDevelopmentRun

# Or using JS target
./gradlew :composeApp:jsBrowserDevelopmentRun
```

### 📖 User Guide

#### 1. Add Cities

1. Click the `+` button in the bottom right corner
2. Search for the city you want to add in the city picker
3. Click the city name to add it to your city list

#### 2. Set Base City

- The base city is used for calculating time differences
- Click the "⭐ Set as Base" button on any city card
- The base city will be highlighted with a special indicator

#### 3. Reorder Cities

- Long press the drag handle (≡) on any city card
- Drag to your desired position
- Release to complete the reorder

#### 4. Remove Cities

- Click the `×` button in the top right corner of a city card
- Confirm to remove the city

#### 5. Settings

**Access Settings Page:**
- Click the `⚙️` settings icon in the top right corner

**Available Settings:**
- **Time Format**: Toggle between 12/24-hour format
- **Seconds Display**: Show/hide seconds
- **Language**: Choose interface language (Chinese, English, etc.)
- **Privacy Policy**: View privacy policy and terms

#### 6. Time Calculator

Click the `🧮` icon in the top right corner to access the time calculator:
- Select source and target cities
- Input time and date
- Instantly view converted time
- Automatic daylight saving time adjustment

### 🏗️ Project Structure

```
Globaltimezonetool/
├── composeApp/                    # Kotlin Multiplatform application code
│   ├── src/
│   │   ├── commonMain/            # Cross-platform shared code
│   │   ├── androidMain/          # Android specific code
│   │   ├── iosMain/              # iOS specific code
│   │   └── jsMain/               # Web specific code
│   └── build.gradle.kts          # App build configuration
├── iosApp/                       # iOS application entry point
├── gradle/                       # Gradle configuration
│   ├── libs.versions.toml        # Version management
│   └── wrapper/                  # Gradle Wrapper
├── build.gradle.kts              # Project build configuration
└── README.md                     # Project documentation
```

### 🛠️ Tech Stack

- **Framework**: Kotlin Multiplatform + Compose Multiplatform
- **UI**: Material Design 3
- **Navigation**: Voyager
- **Data Persistence**: Multiplatform Settings
- **Time Processing**: Kotlinx DateTime
- **Crash Reporting**: Firebase Crashlytics
- **Build Tool**: Gradle 8.x

### 📋 Feature Implementation

#### Core Features

**Timezone Data Processing:**
- Uses IANA timezone database
- Supports 500+ cities worldwide
- Automatic daylight saving time handling
- Real-time time synchronization

**User Interface:**
- Material Design 3 guidelines
- Smooth animations
- Responsive layout
- Dark theme optimization

**Data Persistence:**
- Automatic city list saving
- User settings persistence
- Base city memory
- Multi-language support

#### Platform-Specific Features

**Android:**
- Firebase Crashlytics integration
- Global exception handling
- App state preservation
- Notification support

**iOS:**
- Native Swift integration
- Crashlytics framework
- Local storage fallback
- Xcode project configuration

**Web:**
- Browser compatibility optimization
- Error capture mechanism
- Local storage support
- Responsive design

### 🐛 Troubleshooting

#### Common Issues

**Q: Android app fails to compile**
```bash
# Clean and rebuild
./gradlew clean
./gradlew :composeApp:assembleDebug
```

**Q: iOS app crashes on startup**
- Ensure Xcode version is 14.0 or higher
- Clean Xcode cache: `Product → Clean Build Folder`
- Reinstall CocoaPods dependencies: `pod install`

**Q: Web app fails to load**
- Ensure browser supports modern web standards
- Try a different browser (Chrome recommended)
- Clear browser cache and retry

**Q: City times are inaccurate**
- Check device timezone settings
- Ensure network connection is working
- Try re-adding the city

### 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

### 👨‍💻 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### 📞 Contact

- **GitHub**: [YingZiGeGe/Globaltimezonetool](https://github.com/YingZiGeGe/Globaltimezonetool)
- **Issue Tracker**: [Issues](https://github.com/YingZiGeGe/Globaltimezonetool/issues)

---

<div align="center">

**Made with ❤️ using Kotlin Multiplatform**

**⭐ Star us on GitHub!** [YingZiGeGe/Globaltimezonetool](https://github.com/YingZiGeGe/Globaltimezonetool)

</div>
