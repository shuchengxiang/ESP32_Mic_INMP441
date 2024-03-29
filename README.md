# ESP32_Mic_INMP441
ESP32+INMP441模块实现远程获取声音
此项目主要参考https://github.com/lixy123/ESP32_Remote_MIC ,进行了一些调试、引脚修改和版本固定，感谢大神的贡献，如需参看原项目请点击上方链接

## 功能：
esp32 网页麦克风终端，可在网页端听取终端接收的声音

## 硬件:
ESP32 + INMP441(I2S麦克风模块)  
INMP441 <---> ESP32 , 接线定义见I2S.h  
SCK <---> IO26  
WS <---> IO22  
SD <---> IO21  
L/R <---> GND  

## 使用方法：
1. 将data目录中的内容传入spiffs 
2. 修改src/main.cpp中的wifi名称、密码，编译程序、烧录至ESP32
3. 打开网页浏览器, 输入访问地址 http://192.168.137.100（这个地址可根据自己的局域网ip,进行设置，在src/main.cpp中修改）
4. 网页打开后有一个切换声音是否播放按钮（按钮listen on时为接收状态，应能听到声音）, 点击后浏览器开始接收并播放声音.

注:
1.暂不支付多并发，同一时间只允许一个客户端
2.必须用支持html5的浏览器, IE不支持html,所以不可以用. pc上可以用chrome浏览器, 手机上内置的浏览器基本上都支持html5
3.如果电脑播放声音为杂音, 电脑控制面板找到声音设置,将声音播放格式改成48000hz

## 未来的用法
未来想要接入语音识别api进行更多的应用，从此项目中可找到网络传输相关的代码

## 其他参考项目
https://github.com/atomic14/esp32-i2s-mic-test

## 许可证
* GPL-3.0 license

