# ONNX 识别模型（已内置）

本目录已内置 ONNX 两步式棋盘识别引擎的两个模型文件，随 APK 一起打包，
开箱即用，无需再手动放置（服务启动时会自动加载）。

| 文件名 | 大小 | 用途 |
|---|---|---|
| `4_v6-0301.onnx` | 10,704,184 B | RTMPose 棋盘四角关键点检测 |
| `nano_v3-0319.onnx` | 31,101,356 B | Swin 交叉点分类（16 类） |

## 来源

模型与算法来源：[Shirakawa-Kotone/chinese-chess-helper](https://github.com/Shirakawa-Kotone/chinese-chess-helper)
（OnnxRecognizer 原实现）。本工程的移植实现位于 `OnnxBoardRecognizer.kt` / `OnnxGeom.kt`。

## 说明

上游 chess-dike 仓库因体积原因用 `.gitignore` 排除了 `*.onnx`；本构建为了开箱即用，
已将两个模型强制入库并随 APK 分发。若模型缺失或损坏，应用会自动回退到 YOLO 识别
（悬浮窗可切换识别引擎）。
