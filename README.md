[toc]

# demo_0519_basicmessagechannel

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)

For help getting started with Flutter, view our
[online documentation](https://flutter.dev/docs), which offers tutorials,
samples, guidance on mobile development, and a full API reference.



# BasicMessageChannel

## flutter 调 native

### Dart实现

1. 定义特定的MessageChannel，标识为“com.sicilyliu”
2. 定义点击触发的Future方法，里面调用的MessageChannel.send(XXX)

### swift实现

1. 初始化FlutterViewController，FlutterMethodChannel
2. 定义messageChannel.setMessageHandler，里面根据调过来的数据（一般是字典，分别以方法名，参数等作为key）做相应处理

## native 调 flutter

### swift实现

1. 初始化FlutterViewController，FlutterBasicMessageChannel
2. 调用messageChannel.sendMessage(XXX)，里面一般传字典

### Dart代码

1. 唤醒监听receiveMessage()，放在initState()里面，类似于一种声明
2. 定义监听处理receiveMessage()方法，里面调用messageChannel.setMessageHandler，里面根据调过来的数据（一般是字典，分别以方法名，参数等作为key）做相应处理。

