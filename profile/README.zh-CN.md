# zlinux-live-util

[English](https://github.com/zlinux-live-util/.github/blob/main/profile/README.md) · 简体中文

面向 Z 世代 Linux 用户的直播周边小工具集，原生优先——都是直播时需要、而 Linux
本来就该做好的东西。

## 为什么有这个组织

Linux 上的直播工具太容易用「塞一个浏览器进来」解决。能用，但不便宜：一个基于
CEF / Electron 的源，为了渲染点东西要吃掉几百 MB 内存和一个 CPU 切片。在 AI
时代，内存已经不便宜了，而「加个浏览器」这笔账是每场直播都要付的。

我们认为这里本来就该有更好的原生解法：一个小进程，用发行版自带的库——PipeWire、
cairo、pango、D-Bus——几 MB 内存干同样的事，启动即用，也不跟编码器抢资源。

长期目标是：普通直播主——而不是发行版维护者——也能把整个直播栈迁到 Linux，
并且就此安定下来。

## 我们坚持什么

- **原生优先，而不是图省事。** 用系统库，不捆绑运行时。
- **资源开销是功能的一部分。** 内存和 CPU 要写明、要实测，并且小到能和游戏、
  编码器同机共存。
- **不做静默失败。** 干不了就明说；这里的项目会把那些花掉真实调试时间的坑写进文档。

## 项目

### [pw-mpris-visualcard](https://github.com/zlinux-live-util/pw-mpris-visualcard)

把本机正在播放的音乐渲染成卡片，以 PipeWire 视频节点直接送进 OBS。

- 单进程、零子进程、不经过浏览器、不经过 HTTP
- 没有消费者连接时完全不渲染（空闲时 CPU 约 0.25%）
- 私有内存 6–25 MB；版面用 cairo + pango 绘制
- 同步歌词走 MPRIS，封面自转，进度环；尺寸任意，帧率上限可调
- 只用发行版系统库——没有语言包管理器，不捆绑运行时
- MIT 许可；OBS 侧配合 [obs-pwvideo](https://github.com/tasokait/obs-pwvideo) 作为视频源

```bash
git clone https://github.com/zlinux-live-util/pw-mpris-visualcard
cd pw-mpris-visualcard && make
```
