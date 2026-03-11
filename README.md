# Fake Bluetooth Connect

LSPosed module that makes scoped apps always think a Bluetooth A2DP device is connected.

## Hook coverage

- `AudioManager.isBluetoothA2dpOn()`
- `BluetoothAdapter.getProfileConnectionState(BluetoothProfile.A2DP)`

The goal is to let some music apps enable external lyric display features even when no Bluetooth device is actually connected.

## Usage

1. Install the APK
2. Enable this module in LSPosed
3. Add the target app to the module scope in LSPosed
4. Force stop the target app
5. Reopen the target app
6. Turn on the External Device Bluetooth Lyrics / Car Bluetooth Lyrics feature inside the target app

## Notes

- This module is designed to be minimally invasive
- It only changes app-side query results
- It does not fake global Bluetooth connection state for the whole system
- Compatibility may vary across apps if they rely on additional audio device callbacks or their own cached state

## Tested

- NetEase Cloud Music: V9.4.70 working
- QQ Music: V20.1.5.8 working

## Build

This project uses:

- Android Studio / Gradle
- LSPosed modern API (`libxposed`)
- Kotlin

## License

MIT

---

# 伪蓝牙连接

一个 LSPosed 模块，让被加入作用域的应用始终认为当前已连接蓝牙 A2DP 设备。

## Hook 范围

- `AudioManager.isBluetoothA2dpOn()`
- `BluetoothAdapter.getProfileConnectionState(BluetoothProfile.A2DP)`

目的是让部分音乐应用在没有真正连接蓝牙设备时，仍然启用外显歌词功能。

## 使用方法

1. 安装 APK
2. 在 LSPosed 中启用本模块
3. 在 LSPosed 中给本模块勾选目标应用作用域
4. 强制停止目标应用
5. 重新打开目标应用
6. 在目标应用内部开启 外接设备蓝牙歌词 / 车载蓝牙歌词 功能

## 说明

- 本模块尽量保持最小侵入
- 只修改应用侧查询结果
- 不会伪造整个系统的全局蓝牙状态
- 如果某些应用依赖额外的音频设备回调或自身缓存状态，兼容性可能存在差异

## 已测试

- 网易云音乐: V9.4.70 可用
- QQ音乐: V20.1.5.8 可用

## 构建

项目使用：

- Android Studio / Gradle
- LSPosed modern API（`libxposed`）
- Kotlin

## 协议

MIT
