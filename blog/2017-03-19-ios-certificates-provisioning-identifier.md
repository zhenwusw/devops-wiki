一切起源于苹果臭名昭着的安全策略 。。。

首先，苹果的安全方案能够实现以下几种需求：

-  apps deployed from the App Store are trusted because they are cryptographically signed by Apple

- enterprise organizations can deploy applications to their employees without publishing to the app store (so called "Line of Business apps" that have no business being published to the general public)

- app developers can deploy development binaries to (up to 100 of) their own devices for testing

- app developers can run a beta program by directly deploying correctly-signed apps to customers


苹果的 scheme 包含以下几个部分:

**Identifiers -** 应用唯一标识符， 如 `com.zhenwusw.myapp`。也称作："Application Identifiers" 或 "Bundle Identifiers"。

**Certificates -** 这是苹果授权给你的加密证书。就像 SSL 那样从授权商那里拿到的签名证书。苹果用你提供的私钥来标识你应用程序中不同的部分。
不同的证书创建不同类型的授权。有些证书允许你将应用提交到 Apple Store，有些证书允许苹果的推送服务器通过 APNS 推送消息到应用程序，如果不这么做，
很容易被第三方欺骗并发送垃圾信息。最最常用的证书一般会在你将应用安装到手机或是提交到 App Store，证书里面包含了你使用的私钥。

**Provisioning Profiles -** 这可能是最难理解的部分，一个 provision profile 表明这个设备已经签名正确。开发者可以创建两种不同
的 provision profiles: Development 和 Distribution; 一个比较合理的解释是：Provisioning profiles say "application
with this **Identifier** signed with this **Certificate's** privvate key are okay to run on these device."
也就是说一个 Provisioning profile 关联一个证书。Development profiles 有 100 个设备的限制。Distribution profiles 
则有 Ad-Hoc 和 App Store 两种。

**Entillements -** 在 iOS 的 bundle 里面，往往可以发现 Entilements.plish 文件，该文件表明这个应用需要拥有哪些功能。假设
当你想签名一个应用用于发布到 App Store, 则类似 `get-task-allow` 这类 entilement 则不可以被声明。


## 如何创建将应用安装到本地设备

**首先创建 Certificate Signing Request (CSR)**
In the Applications folder on your Mac, open the Utilities folder and launch Keychain Access.

Within the Keychain Access drop down menu, select Keychain Access > Certificate Assistant > Request a Certificate from a Certificate Authority.


- In the Certificate Information window, enter the following information:

  + In the User Email Address field, enter your email address.
  
  + In the Common Name field, create a name for your private key (e.g., John Doe Dev Key).
  
  + The CA Email Address field should be left empty.
  
  + In the "Request is" group, select the "Saved to disk" option.
  
- Click Continue within Keychain Access to complete the CSR generating process.


经过上面操作后, 一份 CSR 文件被成功创建。非对称加密中必须有一对公钥和私钥。私钥储存在本地 login keychain 中，而公钥
则存放在 CSR 文件中。


**接下来将 CSR 上传到**

成功后你会看到一份可供下载的证书

![download certificate](https://cloud.githubusercontent.com/assets/349215/24081819/c34dcbe2-0cf5-11e7-9dbc-e11373ee4a82.png)


双击下载后的证书即可安装到本地，可以通过 login keychina 查看。

接下来，对于每一个 App, 创建一个 App ID
在根据证书和 APP ID 创建一份 p12 文件，不详叙了 ...



## 扩展阅读

http://blog.cnbang.net/tech/3386/
