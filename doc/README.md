# 文档

## API设计

Flutter项目增加Taro支持。i.e.

```shell
flutter taro create .
```

Flutter项目入口增加Taro配置。i.e. 

```dart
import 'package:flutter_taro/flutter_taro.dart';

void main(){
  support_taro();
  return runApp(MyApp());
}
```

## 架构

计划整体参考Flutter for Web的实现方式做。

- 关于API。Flutter for Web对接浏览器API实现等效语法。替换成Taro API即可。
  考虑到浏览器API和小程序API具有相似性，可以部分参考并重构。
  不过总体来说仍然是工程的主体，需要大量堆人堆时间堆测试，适配数量和质量决定项目可用性。
- 关于引擎。Flutter框架和代码整体被编译成JavaScript代码。理论上大体可以复用给小程序。
  开发阶段是用`dartdevc`，生产阶段是用`dart2js`。
  是Flutter for Taro的基础，初期只有解决此问题才有继续下去的可能性。
  
基本可以按照上述分类划分项目模块。

## 社区

Flutter官方不计划支持custom engine，包括其相关工具链的代码提交。
理由是项目活不长。

## 参考资料

- [把Flutter扩展到微信小程序端的探索](https://github.com/areslabs/flutter_mp/blob/master/doc/把Flutter扩展到微信小程序端的探索.md)
- [Flutter 架构概览](https://flutter.cn/docs/resources/architectural-overview#flutter-web-support)
- [让 Flutter 在鸿蒙系统上跑起来](https://tech.meituan.com/2021/01/22/flutter-in-harmonyos.html)
- [Custom Flutter Engine Embedders](https://github.com/flutter/flutter/wiki/Custom-Flutter-Engine-Embedders)
