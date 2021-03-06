# Flutter框架简述  
## 概念

Flutter是一个移动应用框架的软件开发工具包（SDK），具有以下特征：

- 跨平台应用的框架，没有使用Web View或者系统平台自带的控件，使用自身的高性能渲染引擎自绘
- 简化版的浏览器，最大限度在Android和iOS上统一UI，包括业务逻辑和用户体验
- 开发语言使用dart，结合C、C++和Skia构建
- 支持hot reload，包含着完整的控件和工具链
- 一切皆控件，控件是每个Flutter应用程序的基本构建块，与分离视图、控制器、布局和其他属性的框架不同，Flutter具有一致的统一对象模型：控件。一个控件可以定义为：结构元素、风格元素、布局的方面、业务逻辑等
- 组合大于继承，控件本身通常由许多小型、单用途的控件组成，结合起来产生强大的效果，类的层次结构是扁平的，以最大化可能的组合数量
- 强化版的Web View，框架仅提供一个View层，大部分功能依赖原生

## 优势

宏观上：

- 对于用户，Flutter能够提供优美的UI和流畅的使用体验
- 对于开发者，Flutter降低了开发App的门槛，加速移动应用的开发速度，并且能够降低同时开发Android和iOS应用的成本和复杂度
- 对于设计者，Flutter能够轻松做出原型并且能够保持相当高还原度

微观上：

- 高效率，用一套代码库就能开发iOS和Android应用
- 使用新型的、表现力强的语言和声明式的方法，用更少的代码来做更多的事情
- 可以在应用程序运行时更改代码并重新加载查看效果，也就是热重新加载
- 修复崩溃时可以从应用程序停止的位置继续调试
- 创建美观、高度定制的用户体验
- Flutter框架内置了一组丰富的质感设计控件
- 实现定制、美观、品牌驱动的设计，而不受OEM控件集的限制
- 深度优化，移动优先的2D渲染引擎而且对文本支持非常出色
- react风格的框架
- 支持单元和集成测试的API
- 支持与系统平台和第三方SDK交互的插件API
- 支持Windows，Mac和Linux的Headless test runner
- 支持创建，构建，测试和编译应用的命令行工具

## 运行机制

Flutter 应用运行在一个用 C++ 写的引擎中，Flutter 应用可以看做是一个游戏App，代码都是在引擎中运行。

- Android

    引擎的C或C++代码是由Android NDK编译的，而框架的主要代码和应用的代码由Dart compiler编译成native code执行的。
    对于Android应用来说，Flutter框架在引擎中实现了一个继承于SurfaceView的FlutterView。用户所看到的UI都是在这个SurfaceView中显示。如果要和原生平台功能交互，则可以在Activity中使用FlutterView，并通过Flutter提供的消息API和原生平台收发消息。
    
- iOS

    引擎的C或C++代码是由LLVM编译的，而所有Dart的代码会被AOT编译成native code，整个APP运行时使用的是机器指令（并不是拦截器）。

