# Android 开发者的十大 Android 棉花糖新特性

> 原文：<https://thenewstack.io/top-ten-new-android-marshmallow-features-android-developers/>

这是我们将在接下来的几个周末运行的关于 Android 棉花糖系列的第一部分。我们的大部分报道着眼于大规模的应用程序开发和管理，而较少关注特定的操作系统及其在移动设备上的工作方式。但是对我们来说，偶尔提供一个不同的环境是很重要的，所以我们希望这个系列在我们回顾 Android 棉花糖 API 时能够做到这一点。

今年早些时候，谷歌发布了其新版本的 Android——代号为 Android M——和 [Android Lollipop](https://www.android.com/versions/lollipop-5-0/) 一样，我们也获得了开发者预览版。Android M 开发者预览版为开发者提供了一个清晰的时间表来测试他们的应用，并提供了一个探索最新版本 Android 所提供的新功能的机会。我们现在知道这个版本的 Android 是 Android 6.0 [棉花糖](http://www.androidcentral.com/welcome-android-60-marshmallow-era)。谷歌也已经敲定了 Android 版本 23 APIs，开发者可以通过 Android Studio 中的 SDK 管理器下载官方的 [Android 6.0 SDK](https://developer.android.com/preview/index.html) 。

凭借 Android Marshmallow，谷歌对之前版本的操作系统进行了一些改进，并为 Android 平台添加了一些新功能；从新的许可系统到辅助 API，棉花糖被证明是去年棒棒糖的优秀继承者。我们浏览了 Android 23 APIs 和它们的文档，找到了值得注意的特性和它们的 API。以下是我们目前最喜欢的一些:

## 1.用于工作的 Android

有了 Android Marshmallow，开发人员现在有了比以往更多的工具来为公司和企业环境构建应用程序。拥有许多增强功能的`DevicePolicyManager`类现在包含了诸如`setKeyguardDisabled()`和 setStatusBarDisabled()之类的方法，这些方法允许在公司拥有的、一次性(COSU)设备的使用方面进行重大改进。第三方应用程序也可以调用许多 DevicePolicyManager 方法，从而在 COSU 应用程序设计中提供更大的灵活性。通过用`DevicePolicyManager.setSystemUpdatePolicy()`设置系统更新策略，现在可以自动接受或推迟系统更新。开发人员现在还可以禁用/重新启用安全引导，并防止插入设备的屏幕关闭，从而为面向企业的应用程序提供更加独特和专注的体验。

## 2.直接分享

另一个新特性是能够定义[直接分享](https://developer.android.com/preview/api-overview.html#direct-share)目标，在您的应用中启动特定活动。这些 API 有助于用户快速直观地分享信息。使用“共享”菜单，用户可以直接将内容共享给其他应用程序中的目标。要启用直接共享目标，您必须定义一个扩展 Android . service . chooser . choosertargetservice 类的类，并在清单中声明您的`ChooserTargetService`。在该声明中，使用`SERVICE_INTERFACE`操作指定`BIND_CHOOSER_TARGET_SERVICE`权限和意图过滤器。

## 3.辅助 API

在今年的谷歌 I/O 期间宣布的最令人兴奋的功能之一是“Google Now on Tap”，通过长按 home 按钮，你可以从 Google Now 获得一个与当前屏幕上的任何内容相关的上下文弹出卡。默认情况下，上下文由 Android 文本字段和视图层次决定，但是通过使用 [Assist](https://developer.android.com/preview/api-overview.html#assist) API，开发人员可以向默认上下文添加更多信息。您必须实现`Application.OnProvideAssistDataListener`接口。使用`registerOnProvideAssistDataListener()`注册这个监听器。为了提供特定于活动的上下文信息，覆盖`onProvideAssistData()`回调，并可选地覆盖新的`Activity.onProvideAssistContent()`回调。此外，如果您不想让助手共享您的屏幕内容，您可以使用`FLAG_SECURE`创建一个`WindowManager.LayoutParams`，并使用`WindowsManager`系统服务在您感兴趣的视图上设置参数。

## 4.指纹认证

安卓棉花糖为安卓平台带来了[指纹认证](https://developer.android.com/preview/api-overview.html#authentication)的官方支持。要在应用中使用此功能，您首先需要在清单中添加`USE_FINGERPRINT`权限。要通过指纹验证用户，使用带有兼容指纹传感器的设备进行扫描，获取新的`android.hardware.fingerprint.FingerprintManager`类的实例并调用`FingerprintManager.authenticate()`方法。您还必须在您的应用程序上实现指纹认证的用户界面，并在您的 UI 中使用标准的 Android 指纹图标。这是为了在 Android 平台上提供统一的体验。

## 5.通知升级

这次[通知](https://developer.android.com/preview/api-overview.html#notifications) API 没有什么大的变化，但是 Android 通知有一些升级。首先，有一个新的`NotificationListenerService.INTERRUPTION_FILTER_ALARMS`过滤级别，对应于新的仅警报勿扰模式。还有一个新的`Notification.CATEGORY_REMINDER`类别值，用于将用户预定的提醒与其他事件(`CATEGORY_EVENT`)和警报(`CATEGORY_ALARM`)区分开来。Android Marshmallow 还有一个新的`android.graphics.drawable.Icon`类，可以通过`Notification.Builder.setSmallIcon()`和`Notification.Builder.setLargeIcon()`方法附加到你的通知中。最后，有一种新的`NotificationManager.getActiveNotifications()`方法，允许你的应用程序找出哪些通知当前是活动的。

## 6.蓝牙手写笔支持

谷歌已经改进了对蓝牙手写笔的支持。应用程序现在能够监听手写笔按钮的按压，并通过在它们的活动中注册新的`View.onContextClickListener`和`GestureDetector.onContextClickListener`回调来执行辅助动作。`MotionEvent`方法和常量可用于检测手写笔按钮交互:

如果用户用手写笔触摸你的应用程序屏幕上的按钮，`getTooltype()`方法返回`TOOL_TYPE_STYLUS`。

## 7.蓝牙低能量扫描

随着低功耗蓝牙信标越来越受欢迎，Android 将会进化到更好地利用它们提供的位置环境，这是很有意义的。新的`android.bluetooth.le.ScanSettings.Builder.setCallbackType()`确保您的应用程序仅在首次发现与设置`ScanFilter`匹配的广告包时，以及在一段时间内未看到该广告包时才会收到通知。这种扫描方法比以前的平台版本更节能。

## 8.录像

Android Marshmallow 对现有的[视频处理](https://developer.android.com/preview/api-overview.html#video)API 进行了大量升级。新的`android.media.MediaSync`类帮助应用程序同步呈现音频和视频流。音频缓冲区异步提交，并通过回调返回，以避免阻塞主 UI 线程。它还支持动态播放速率。Android Marshmallow 还增加了新的`MediaDrm.EVENT_SESSION_RECLAIMED`事件，表示应用打开的一个会话已经被资源管理器回收。

## 9.声音的

在新的 API 中，对音频处理进行了一些增量增强，特别是通过新的`android.media.midi`类关注对 [MIDI](https://developer.android.com/preview/api-overview.html#audio) 协议的支持。开发人员现在可以使用这些 API 来发送和接收 MIDI 事件。Android 还增加了新的类来创建数字音频捕获和回放对象。`AudioManager.getDevices()`方法允许您检索当前连接到系统的所有音频设备的列表。通过注册一个`android.media.AudioDeviceCallback`对象，你可以在音频设备连接或断开时接收一个回调。

## 10.照相机

[Camera2](https://developer.android.com/reference/android/hardware/camera2/package-summary.html) API 现在支持 YUV 和私有不透明格式图像重新处理。开发人员可以通过调用`CameraManager.getCameraCharacteristics()`方法并检查`REPROCESS_MAX_CAPTURE_STALL`键来决定这些再处理功能是否可用。如果设备支持再处理，您可以通过调用`CameraDevice.createReprocessableCaptureSession()`创建一个可再处理的摄像机捕获会话，并创建输入缓冲区再处理请求。ImageReader 类现在支持`android.graphics.ImageFormat.PRIVATE`格式的图像流，允许应用程序维护一个`ImageReader`输出图像的循环图像队列，选择一个或多个图像，并将它们发送到`ImageWriter`进行相机再处理。

## 摘要

就像它的前身 Lollipop 一样，谷歌为开发人员创造了许多工具，用于使用 Android 棉花糖制作伟大的应用程序。最新版本的 Android 正在为现有用户和新用户提供更好的 Android 体验。Android M 开发者预览版已经让我们很好地了解了我们在不久的将来会看到什么，我已经迫不及待地等待今年晚些时候第一批官方 Android 棉花糖设备系统图像的发布。

在接下来的一系列文章中，我将进一步探索这些 API，并扩展我对这个新操作系统的看法。我将使用示例应用程序和代码片段来介绍这些 API 及其功能。或许我们可以一起做些有趣的事。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>