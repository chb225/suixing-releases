# 随行

随行是一款个人使用的 Android 辅助工具，用于日常使用比亚迪蓝牙钥匙和查看车况。

## 主要功能

- **蓝牙钥匙**　手动上锁和解锁，可按需开启走近解锁、离车上锁。
- **车况查看**　查看门锁、门窗、油量、电量和续航等车辆状态。
- **用车提醒**　支持离车锁态提醒、解锁后续航提醒和低油量提醒。
- **蓝牙调试**　校准走近和走远的信号阈值，查看信号波形和控车记录，导出诊断日志。

## 原理讲解

| 方式 | 谁发起，车怎么确认 |
| --- | --- |
| 原厂钥匙＋微动 | 人按门把手，车先收到按键动作，再确认感应区内有有效智能钥匙，最后根据锁态和车门条件执行。传统无钥匙进入常用低频唤醒钥匙，再由钥匙无线应答。驱逐舰 05 的具体射频实现未从厂方资料核实。 [比亚迪车主手册](https://www.byd.com/material/domestic-official/user-manual/other/%E6%B1%89L%20DM%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C260421.pdf) · [Microchip 无钥匙进入参考设计](https://onlinedocs.microchip.com/oxy/GUID-BAA8542B-0F40-4D9C-830C-561D4001CB62-en-US-2/GUID-B911342E-D68F-4E22-BF14-9EF0CFABB035.html) |
| 原厂钥匙按键 | 人按钥匙上的解锁或上锁键，钥匙主动发无线遥控请求，车辆验证后执行。和上一种可以用同一把钥匙，发起动作的位置不同。 [比亚迪车主手册](https://www.byd.com/material/domestic-official/user-manual/other/%E6%B1%89L%20DM%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C260421.pdf) |
| 手机蓝牙钥匙 | 授权后的手机在近距离通过蓝牙向车发送控锁请求。比亚迪部分车型另有 BLE 无感数字钥匙，车可以用手机作为附近的有效钥匙，并响应把手微动。《大汉 EV 用户手册》明确写了按把手解锁和上锁。驱逐舰 05 的手机 WATCH 授权是否具备同一能力，仍需本车证据。 [比亚迪《大汉 EV 用户手册》](https://www.byd.com/material/__CN/domestic-official/user-manual/dynasty/%E5%A4%A7%E6%B1%89EV%E7%94%A8%E6%88%B7%E6%89%8B%E5%86%8C261026.pdf) |
| NFC 钥匙 | 把已开通的手机或支持的卡片贴近车身读卡区，车在本地验证钥匙。开通需要联网，开通后日常刷钥匙可以离线。华为钱包的 NFC 兼容表列有驱逐舰 05、冠军版及荣耀版。 [比亚迪 NFC 使用手册](https://profilesys.bydauto.com.cn/dilinkapp/apps/NFC/pad-help.html) · [华为钱包兼容表](https://h5hosting-drcn.dbankcdn.cn/cch5/huaweipaycdn/aiPass_harmony_support/byd.html) |
| 云端解锁 | 手机经互联网把请求交给比亚迪云服务，云端再联系在线车辆。手机和车可以相距很远，执行和车况回传各有自己的时间。 [比亚迪 App 用户协议](https://profilesys.bydauto.com.cn/ocean/h5/app/agreement/2023-5-23.html) |

## GitHub 参考项目

- 比亚迪近场控车和走近解锁的功能参考。[Qcby/Bydkz](https://github.com/Qcby/Bydkz)
- Android 蓝牙连接、信号校准和远近判断的设计参考。[VitalyArt/BYD-Keyless](https://github.com/VitalyArt/BYD-Keyless)
- 蓝牙自动控锁和云端回退的流程对照。[PoorGrammerA/BydBleAutoLock](https://github.com/PoorGrammerA/BydBleAutoLock)
- 比亚迪中国区车辆状态和云端数据字段的参考。[lejw0925/byd-China](https://github.com/lejw0925/byd-China)
## 下载与更新记录

- [GitHub 发行版](https://github.com/chb225/suixing-releases/releases)
- [Gitee 镜像](https://gitee.com/shu_hua/suixing)
- [V2.2.1 界面预览](preview/suixing-2.2.1-888-preview.html)。将 HTML 保存到本地后用浏览器打开。
- [更新日志](CHANGELOG.md)
