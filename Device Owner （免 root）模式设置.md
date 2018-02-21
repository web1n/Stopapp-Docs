##小黑屋使用配置方法

0. 首先确保您的手机 Android 版本大于等于 6.0，并且您知道如何操作 [adb](https://sspai.com/post/23509) 命令。
1. 进入手机「设置 - 帐户」，删除 #所有# 的帐户，包括你的 Google 帐户（之后可以再登录回来）。
2. 如果您之前设置过多用户或手机自带访客模式、应用双开等，也需要一并关闭或删除（之后可以打开）。
3. 在电脑上执行命令： adb shell dpm set-device-owner web1n.stopapp/.receiver.AdminReceiver （这是一行命令）
4. 如果显示 Success 之类的字样，那么表明小黑屋已经配置成功。之后即可打开小黑屋使用，也可以把之前删除的帐号加回来了。

###常见问题：

- 问：提示 “Not allowed to ... already several accounts on the device”
- 答：第 1 步的账户没删干净，请注销您手机上所有的账户，包括 Google 账号和系统自带的如小米账户、三星账户等。注：Xperia 或 ZUK 设置时请拔出 SIM 卡，之后再插入。
- ​


- 问：提示 “Trying to set device owner but device is already provisioned”
- 答：账号没有删干净，请参考第一个问题。
- ​

- 问：提示 “Not allowed to ... already several users on the device”
- 答：使用工具  [本机用户](https://www.coolapk.com/apk/vc.https.adb_removeUser) 来解决。
- ​
- 问：MIUI 用户提示 “Neither user xxx nor current process has android.permission.MANAGE_DEVICE_ADMINS”
- 答：MIUI 用户请手动在系统设置- 开发者设置里，开启「USB 调试（安全设置）」。

