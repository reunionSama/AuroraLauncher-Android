# AuroraLauncher Android

AuroraLauncher 安卓启动器，项目维护：reunionSama。

- 可拖动旋转的角色预览，20 种独立程序骨骼动作，默认每 15 秒随机播放。
- 实时极光主页，可调亮度、色彩、速度与高清 / 省电模式。
- 工具中心、实例备忘、收藏、启动检查、网络诊断与日志速览。
- 从本仓库 Releases 读取更新说明，在应用内下载和检查更新包。
- 保留游戏安装、模组、整合包、触控、渲染器、Java 管理与陶瓦联机。

这是基于 Zalith Launcher 2 / PojavLauncher 开源运行核心的 GPL-3.0-or-later 衍生项目。
Aurora 的新增文件标注其作者；修改过的上游文件保留原版权。完整贡献记录及
组件许可保留在对应源码和安装包的开源许可页中。

## Alpha5 改进

- 更新检查加入有限重试、ETag 缓存、后台去重和 API 限流冷却；主接口失败时使用 GitHub 公开发布订阅及附件页。离线缓存明确标记为旧结果，不会冒充已完成检查。
- 极光改用屏幕帧时钟、缓存画笔和渐变，在绘制阶段更新，提供 60 / 30 FPS 模式；设备负载仍影响实际帧率。
- 20 种人物动作加入平滑起止，调整极光选项不再重置动作计时。
- 关于页新增“赞助创作者”：https://ifdian.net/a/AuroraLauncher。

## 下载与更新

安装包显示名称与文件名为 `AuroraLauncher` / `AuroraLauncher.apk`。
未来发布请上传同一私钥签名、具有更高 versionCode 的 ARM64 APK，并填写
GitHub Release 描述；应用会原样读取描述。私钥和密码不应提交到仓库。
CI 生成的是临时测试签名，正式分发需使用之前的持久 Aurora 私钥重新签名。
Android 的未知来源授权和安装确认仍由用户完成。

## 对应源码和复现

此仓库保存全部 Aurora 修改、原生动作、构建脚本与测试。运行核心固定为
`ZalithLauncher/ZalithLauncher2@a6b6fb6a63ce22c4e4fa91cc29a4d64286cd0924`。
递归检出其子模块后运行 `python3 android-port/prepare.py <engine-dir>`。
`.github/workflows/android-apk.yml` 提供可手动运行的完整构建与测试过程；每次成功
构建同时提供包含上游、子模块和全部修改的完整对应源码归档。修改记录也保存在
[Aurora 原构建分支](https://github.com/reunionSama/AuroraLauncher/tree/android-apk-20261029)。

应用启动、界面测试不等于所有手机上的 Minecraft 游戏兼容性保证。
