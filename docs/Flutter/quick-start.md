?> 笔者用的windows系统

## 安装
我是通过git安装的，没有安装git得先安装git。

```
$ cd C:\src
$ git clone https://github.com/flutter/flutter.git
```

让Flutter在安装过程中使用国内的镜像，配置两个环境变量。

```
export PUB_HOSTED_URL=https://pub.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
```

安装Flutter

```
flutter doctor

// 下面是我的安装成功后打印的信息

```