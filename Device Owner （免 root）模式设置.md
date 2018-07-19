## 小黑屋免 Root（设备管理员）模式使用配置方法

如果您的手机已经 Root 请直接打开小黑屋使用，无需折腾。如果手机无法 Root，请务必仔细阅读下文：

#### 国产手机及三星系统请注意：

国产手机系统时常修改 Android 底层，做出一些不符合规定的修改，因此其与设备管理员模式的兼容性或多或少存在一些问题，常见如下：

- 每次冻结 App 弹出卸载提示，解冻弹出权限请求（华为、锤子）
- 通知栏闪烁「设备管理员已开启，点击关闭」（OPPO、VIVO）
- 自带的双开无法使用（华为、MIUI）
- 安全文件夹被系统禁用（三星）
- 虹膜识别等功能被禁用（三星）
- 偶尔刚解冻的 App 无法联网（一加等）

如不能接受上述问题，请考虑使用其他模式或放弃使用小黑屋。

设备管理员模式不需要反复连接电脑设置，一次配置，终身有效，重启或升级系统都没有影响。

### 设备管理员设置步骤

0. 首先确保您的手机 Android 版本大于等于 6.0，并且您知道如何操作 [adb](https://sspai.com/post/23509) 命令。
1. 进入手机「设置 - 帐户」，删除 所有 的帐户，包括你的 Google 帐户（之后可以再登录回来）。
2. 如果您之前设置过多用户或手机自带访客模式、应用双开等，也需要一并关闭或删除（之后可以打开）。
3. 在电脑上执行命令： `adb shell dpm set-device-owner web1n.stopapp/.receiver.AdminReceiver` （请复制，勿手输）
4. 如果显示 Success 之类的字样，那么表明小黑屋已经配置成功。之后即可打开小黑屋使用，也可以把之前删除的帐号加回来了。

tip：您不能尝试在安卓设备管理器设置中启用小黑屋以代替以上步骤，设备管理员不等于设备管理器，启用设备管理器也无法激活小黑屋。

### 常见问题：

- 问：提示 “Not allowed to ... already several accounts on the device”
- 答：第 1 步的账户没删干净，请注销您手机上所有的账户，包括 Google 账号和系统自带的如小米账户、三星账户等。注：Xperia 或 ZUK 手机在设置时请拔出 SIM 卡，之后再插入。

- 问：提示 “Trying to set the device owner, but device owner is already set.”
- 答：DPM权限已经激活。如果小黑屋仍然无法启动，请确认是否使用了同类软件。

- 问：提示 “Not allowed to ... already several users on the device”
- 答：使用  [本机用户](https://www.coolapk.com/apk/vc.https.adb_removeUser) 工具来解决。

- 问：提示 “android.os.DeadObjectException ...”
- 答：尝试更换数据线或重启手机。

- 问：小米手机出现薛定谔的猫问题
- 答：小米手机如果需要开启 USB 调试就得登陆账号,登陆账号就无法激活设备管理员权限。这是小米的问题，请自行解决。

- 问：MIUI 用户提示 “Neither user xxx nor current process has android.permission.MANAGE_DEVICE_ADMINS”
- 答：MIUI 用户请手动在系统设置- 开发者设置里，开启「USB 调试（安全设置）」。
