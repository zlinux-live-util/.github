# zlinux-live-util

面向 Linux 直播的原生优先工具集。

做直播周边那些小而必要的件，方法是用发行版自带的库自己实现。为了让控件显示点
东西而塞进一个浏览器，代价是每场直播都要付出几百 MB 内存和一个 CPU 切片；而一个
原生小进程用几 MB 就能干同样的事。目标是：普通直播主——而不是发行版维护者——
也能把整个直播栈迁到 Linux 并安定下来。

[English](https://github.com/zlinux-live-util/.github/blob/main/profile/README.md)

## 项目

| 项目 | 说明 | 许可 |
| --- | --- | --- |
| [pw-mpris-visualcard](https://github.com/zlinux-live-util/pw-mpris-visualcard) | 把正在播放的音乐渲染成卡片，以 PipeWire 视频节点送进 OBS。单进程、不经过浏览器、零子进程、不经过 HTTP。 | MIT |

欢迎贡献；每个项目的 README 写明了 patch 需要附带什么。
