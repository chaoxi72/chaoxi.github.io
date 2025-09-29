## 刷机方式

#### 线刷
- 下载对应版本的安卓镜像，[Android镜像地址](https://developers.google.com/android/images?hl=zh-cn)
- 线刷包 工厂镜像包
  - bootloader(fastboot),radio,image
    - vender.img 驱动
    - system_other.img, system.img 系统分区
    - boot.img linux内核
- [官方刷机教程](https://source.android.com/docs/setup/test/running?hl=zh-cn)
- [小肩膀教程](https://mp.weixin.qq.com/s/1EySfXSucGdiuEBTfLsymA)
#### 卡刷
- 刷完之后需要双清、三清、四清等
- 卡刷包 OTA全量包/OTA增量包
## Pixel 6遇到的网络连接问题
- 手动修改手机时间
- 参考文档
  - [重述：如何修复 Android 手机上的 SSL 连接错误](https://www.thesslstore.com/blog/fix-ssl-connection-errors-android-phones/)
- 自动设置
```bash
adb shell "settings put global ntp_server pool.ntp.org"
```

## WIFI信号问题
- adb shell settings put global captive_portal_mode 0
  - 把 Android 的“网络检测模式”设置为 禁用，这样系统就不会去探测网络可用性，也不会弹出 WiFi 登录认证提示。

