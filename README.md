# 随行

随行是一款个人使用的 Android 辅助工具，用于日常使用 BYD 蓝牙钥匙和查看车况。

## 主要功能

- **蓝牙钥匙**　手动上锁和解锁，可按需开启走近解锁、离车上锁。
- **车况查看**　查看门锁、门窗、油量、电量和续航等车辆状态。
- **用车提醒**　支持离车锁态提醒、解锁后续航提醒和低油量提醒。
- **蓝牙调试**　校准走近和走远的信号阈值，查看信号波形和控车记录，导出诊断日志。

## 原理讲解

| 方式 | 谁发起，车怎么确认 |
| --- | --- |
| 原厂钥匙＋微动 | 人按门把手，车先收到按键动作，再确认感应区内有有效智能钥匙，最后根据锁态和车门条件执行。传统无钥匙进入常用低频唤醒钥匙，再由钥匙无线应答。[BYD 车主手册](https://www.byd.com/material/domestic-official/user-manual/other/%E6%B1%89L%20DM%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C260421.pdf) · [Microchip 无钥匙进入参考设计](https://onlinedocs.microchip.com/oxy/GUID-BAA8542B-0F40-4D9C-830C-561D4001CB62-en-US-2/GUID-B911342E-D68F-4E22-BF14-9EF0CFABB035.html) |
| 原厂钥匙按键 | 人按钥匙上的解锁或上锁键，钥匙主动发无线遥控请求，车辆验证后执行。和上一种可以用同一把钥匙，发起动作的位置不同。 [BYD 车主手册](https://www.byd.com/material/domestic-official/user-manual/other/%E6%B1%89L%20DM%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C260421.pdf) |
| 手机蓝牙钥匙 | 授权后的手机在近距离通过蓝牙向车发送控锁请求。BYD 部分车型另有 BLE 无感数字钥匙，车可以用手机作为附近的有效钥匙，并响应把手微动。《大汉 EV 用户手册》明确写了按把手解锁和上锁。[BYD《大汉 EV 用户手册》](https://www.byd.com/material/__CN/domestic-official/user-manual/dynasty/%E5%A4%A7%E6%B1%89EV%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C261026.pdf) |
| NFC 钥匙 | 把已开通的手机或支持的卡片贴近车身读卡区，车在本地验证钥匙。开通需要联网，开通后日常刷钥匙可以离线。[BYD NFC 使用手册](https://profilesys.bydauto.com.cn/dilinkapp/apps/NFC/pad-help.html) |
| 云端解锁 | 手机经互联网把请求交给 BYD 云服务，云端再联系在线车辆。手机和车可以相距很远，执行和车况回传各有自己的时间。 [BYD App 用户协议](https://profilesys.bydauto.com.cn/ocean/h5/app/agreement/2023-5-23.html) |

## GitHub 参考项目

- BYD 近场控车和走近解锁的功能参考。[Qcby/Bydkz](https://github.com/Qcby/Bydkz)
- Android 蓝牙连接、信号校准和远近判断的设计参考。[VitalyArt/BYD-Keyless](https://github.com/VitalyArt/BYD-Keyless)
- 蓝牙自动控锁和云端回退的流程对照。[PoorGrammerA/BydBleAutoLock](https://github.com/PoorGrammerA/BydBleAutoLock)
- BYD 中国区车辆状态和云端数据字段的参考。[lejw0925/byd-China](https://github.com/lejw0925/byd-China)
- BYD 车况在 Home Assistant 中的接入和更新方式参考。[jkaberg/hass-byd-vehicle](https://github.com/jkaberg/hass-byd-vehicle)
- BYD 车机遥测经 MQTT 接入 Home Assistant 的参考。[freddycs/byd_car_mqtt](https://github.com/freddycs/byd_car_mqtt)
- BYD Atto 3 电量、续航和充电状态的车载监测参考。[OVMS 的 Atto 3 文档](https://github.com/openvehicles/Open-Vehicle-Monitoring-System-3/blob/master/vehicle/OVMS.V3/components/vehicle_byd_atto3/docs/index.rst)
- Android 低功耗蓝牙的连接、操作队列、信号强度读取和超时处理参考。[Nordic Android BLE Library](https://github.com/nordicsemi/Android-BLE-Library)

## 下载与更新记录

- [GitHub 发行版](https://github.com/chb225/suixing-releases/releases)
- [Gitee 发行版](https://gitee.com/shu_hua/suixing/releases)
- [更新日志](CHANGELOG.md)
