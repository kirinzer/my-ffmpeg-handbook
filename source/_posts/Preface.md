---
title: Preface
---
# 序章

### 好的设计总是心有灵犀？

早年准备重构音视频渲染框架时做技术选型，曾选到了 Filament，当时应该是考虑到跨平台的优良支持，还有轻量，以及 3D 渲染效果。虽然它已经不再是 Google 官方维护的工程，但是社区依然活跃至今。

它给我印象最深刻的，就是丰富的文档细节，以及见名知意的定义和概念。你很容易理解这个类是做什么用途的。

甚至和 Top 音视频产品 SDK 都大差不大的。可以说"**好的设计总是心有灵犀**"。

下面初始化部分的代码片段：

1.创建一个Engine、一个Renderer和一个SwapChain, SwapChain是从本机窗口指针（例如NSViewmacOS 上的一个或 Windows 上的一个）创建的：**HWND**(窗口句柄)

```
Engine* engine = Engine::create();
SwapChain* swapChain = engine->createSwapChain(nativeWindow);
Renderer* renderer = engine->createRenderer();
```
2.要渲染一帧，必须创建一个View、一个Scene和一个Camera：

```
Camera* camera = engine->createCamera(EntityManager::get().create());
View* view = engine->createView();
Scene* scene = engine->createScene();

view->setCamera(camera);
view->setScene(scene);
```
Filament 的开发文档提到，有依赖 SDL2 管理窗口和输入事件(iOS)，渲染上下文(Android)。

同时 Filament 提供了更高级、更加抽象的 API 接口,而 SDL 更偏向于底层的多媒体功能支持。

在后面也会提到 **SDL** 这个库，作为了解学习 FFmpeg 的辅助。

学习这些在不同抽象层级的代码库，可以让你深刻了解到不同层级的功能应该怎么划分。提高代码设计能力。



### 为什么我要写这个手册？

作者自身做音视频开发工作有比较长一段时间了，平时业务工程代码接触的多了，难免接触底层代码的时间会少，因此写这本手册是结合业务工程再来回顾。同时也做一个梳理总结。

另外，作者自身一向注重开源。很多好的设计和细节就藏在开源的代码里。这本手册仅仅是抛砖引玉，希望能提供到帮助给大家。



### 这本手册的作用？

1）对于音视频行业从业人员，是你必要的知识储备，关于这部分的知识一般来说都比较零散，不够体系化。

这本书可以完善你的知识体系，更好的解决在工作中可能涉及的问题。

2）对于还未毕业，有考虑从事这个方向的在校同学，这本书可以帮你入门音视频行业。

3）对于非音视频行业从业人员，如有兴趣可以只看概念部分，对一个视频或者音频是如何被播放起来有一个了解即可。



### 勘误

因时间精力有限，如文章有所疏漏，欢迎在文章下评论，或者通过邮箱，公众号联系作者本人。





