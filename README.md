# 电力安全答题 - Android APK 构建指南

## 方法一：GitHub Actions 自动编译（推荐，无需本地环境）

1. 在 GitHub 新建一个公开仓库（如 `safety-quiz-app`）
2. 将本项目所有文件上传到仓库
3. GitHub 会自动触发 Actions 编译流程
4. 编译完成后，进入 Actions → 最新的 workflow run → Artifacts → 下载 `SafetyQuiz-APK`
5. 解压得到 `SafetyQuiz.apk`，传到手机安装

> 安装前需在手机「设置 → 安全 → 允许安装未知来源应用」

## 方法二：本地编译

### 环境要求
- Node.js 18+
- JDK 11+
- Android SDK（API 33）+ Build Tools

### 编译步骤
```bash
npm install -g cordova@12
npm install
cordova platform add android@12
cordova build android --release
```

APK 位于：`platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk`

## 应用信息
- 包名：com.mingyuan.safetyquiz
- 版本：1.0.0
- 最低 Android 版本：5.0（API 21）
- 目标 Android 版本：13（API 33）
- 权限：INTERNET、ACCESS_NETWORK_STATE（无通讯录权限）
