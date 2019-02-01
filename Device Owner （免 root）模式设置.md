## 小黑屋免 Root（设备管理员）模式使用配置方法

免 Root 模式不需要反复连接电脑设置，一次配置，一直有效，只要不卸载小黑屋或是刷机，小黑屋都可正常使用。
 
 
#### 国产手机及三星系统请注意：

国产手机系统时常修改 Android 底层，做出一些不符合 Google 规定的修改。这些修改可能会对免 Root 模式的兼容性造成一些影响，常见如下：

- 无法静默安装，提示缺少权限（MIUI）
- 每次冻结 App 弹出卸载提示，解冻弹出权限请求（华为、锤子等）
- 通知栏闪烁「设备管理员已开启，点击关闭」（OPPO、VIVO 等）
- 自带的双开无法使用（华为、MIUI 等）
- 与三星 KNOX 安全文件夹冲突，可能导致无法开机（三星）
- 偶尔刚解冻的 App 无法联网（一加等）
- 状态栏和锁屏显示「设备由小黑屋管理」

如不能接受上述问题，请考虑使用也是 无需 Root 的 [麦克斯韦妖模式](https://70.wf/archives/2019/01/16/185.html)或放弃使用小黑屋。

### 设备管理员设置步骤

#### 如果您不知道如何执行 adb 指令,请使用 [一键激活工具](https://https.vc/archives/220/) 。

0. 首先确保您已安装小黑屋，并且您知道如何操作 [adb](https://sspai.com/post/23509) 命令。
1. 进入手机「设置 - 帐户」，删除 所有 的帐户，包括你的 Google 帐户（之后可以再登录回来）。
2. 如果您之前设置过多用户或手机自带访客模式、应用双开等，也需要一并关闭或删除（之后可以打开）。
3. 在电脑上执行命令： `adb shell dpm set-device-owner web1n.stopapp/.receiver.AdminReceiver` （请复制，勿手输）
4. 如果显示 Success 之类的字样，那么表明小黑屋已经配置成功。之后即可打开小黑屋使用，也可以把之前删除的帐号加回来了。

### 常见问题：

#### 未设置成功？

- 问：提示 “Not allowed to ... already several accounts on the device”
- 答：第 1 步的账户没删干净，请注销您手机上所有的账户，包括 Google 账号和系统自带的如小米账户、三星账户等。注：Xperia 或 ZUK 手机在设置时请拔出 SIM 卡，之后再插入。

- 问：提示 “Trying to set the device owner, but device owner is already set.”
- 答：DPM权限已经激活。如果小黑屋仍然无法启动，请确认是否使用了同类软件。

- 问：提示 “Not allowed to ... already several users on the device”
- 答：第 2 步的用户没有删除干净。

- 问：提示 “android.os.DeadObjectException ...”
- 答：尝试更换数据线或重启手机。

- 问：MIUI 用户提示 “Neither user xxx nor current process has android.permission.MANAGE_DEVICE_ADMINS”
- 答：MIUI 用户请手动在系统设置- 开发者设置里，开启「USB 调试（安全设置）」。

- 问：我尝试在安卓设置-设备管理器设置中启用小黑屋以代替以上设置步骤，但是发现无法使用，怎么办？
- 答：设备管理员不等于设备管理器，启用设备管理器也无法激活小黑屋。

#### 已设置成功，但是？

- 问：手机通知栏和锁屏界面出现「手机被小黑屋管理」提示，这是正常的吗？
- 答：这是小黑屋的无 Root 工作原理，是正常的。

- 问：我不想用了，然后发现卸载不了？
- 答：请先解冻所有的应用，然后到小黑屋设置里点击「卸载」。
