通过Android Studio 的Sdk Manager安装NDK,安装完之后编译失败,报错信息入下:

    No toolchains found in the NDK toolchains folder for ABI with prefix: mips64el-linux-android
    

网上查了一通,答案大同小异,但都无法解决我的问题,只能自己研究了.

翻一翻NDK的文档,看到这样一段:

![ndk-document.png](https://upload-images.jianshu.io/upload_images/327713-f0f75264413e637f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

    
找到自己本地的android-sdk,如果下载了ndk的相关sdk,会有一个叫“ndk-bundle”的文件夹

![](https://upload-images.jianshu.io/upload_images/327713-39be7ffe6470b4cb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

里边有一个叫“toolchains”的文件夹

![](https://upload-images.jianshu.io/upload_images/327713-e58768023ef0adf1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

我们注意到里边确实没有mips64el相关的文件

![](https://upload-images.jianshu.io/upload_images/327713-545ed516c5164086.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


解决办法如下:

1. [点击这里](https://developer.android.com/ndk/downloads/?hl=zh-cn)通过浏览器单独下载NDK的包.
2. 解压之后打开“toolchains”文件夹,跟android-sdk->ndk-bundle->toolchains文件夹做对比,找到其缺少的文件夹,复制过去

![](https://upload-images.jianshu.io/upload_images/327713-8021840cef437b9e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3.重新编译,问题解决.


 