未 root 手机无线连接电脑

- 将 Android 设备与要运行 adb 的电脑连接到同一个局域网，比如连到同一个 WiFi
- 将设备与电脑通过 USB 线连接。应确保连接成功（可运行 adb devices 看是否能列出该设备）。
- 让设备在 5555 端口监听 TCP/IP 连接：

``` 
adb tcpip 5555

``` 


- 查看 手机 IP 地址：
```
adb shell ip -f inet addr show wlan0
```

- adb connect ip:5555
- 断开 USB 连接。
- adb devices




