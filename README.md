# OpenSplat Android

这个仓库记录移动端 3D Gaussian Splatting（3DGS）项目从 `mobile3dgs` 桌面原型到 OpenSplat Android 真机采集与端侧训练的迭代。当前关注两个问题：怎样在较短的训练预算内得到可用的新视角画质，以及怎样用少量训练帧补上重建缺口。

## 当前进度

- **安卓版离线训练已验证。** 在 Android 15 模拟器上，现有 APK 可以导入数据、完成 Brush 训练并导出 PLY 和测试报告。质量对照采用相同相机和参考图统一评分。
- **保守换帧是当前的补缺口候选。** 两个 TUM RGB-D 室内序列都观察到局部覆盖改善。训练预算为 2000 步，仅替换少量训练图，并检查已有视角的画质回退。
- **正在准备真机数据复测。** 2026 年 11 月 20 日的实拍测试版已编译并通过安装检查。下一项验收是用目标安卓手机采集室内场景，导出完整 ZIP，并用同一份素材做配对实验。

[迭代路线、实验结果和验收项](docs/iteration-roadmap.md)

## 源码与历史

当前安卓源码以 [OpenSplat Android 上游](https://github.com/SuleMareVientu/opensplat-android) 为基础，迁移起点为 [`1ea9bbb`](https://github.com/SuleMareVientu/opensplat-android/commit/1ea9bbb829d0a4d4a5e4783d3fec1eeb71834d90)，端侧训练使用 [Brush Android](https://github.com/SuleMareVientu/brush-android)。本仓库保留早期 Python 原型源码和 [历史 README](README.legacy.md)。当前测试 APK 从本地 OpenSplat Android 工作树编译。
