煤矿井下开采要素检测数据集，9900张，提供yolo，voc，coco三种标注方式
图像尺寸:640*640
类别数量:5类![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/3537a7f70ba84cfda57a8d16b96395c2.png)

训练集图像数量:6933; 验证集图像数量:1976； 测试集图像数量:991
类别名称: 每一类图像数 ，每一类标注数![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/e7bc8562f11947c2bf047b9d6f63d94f.png)

gripper - 夹持器：9793,9800
chuck - 卡盘：7611,7611
drill_pipe - 钻杆：9090,9340![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/c0905bbb97764124b2408fed1556be0f.png)

mine_safety_helmet - 矿用安全帽：3949,4401
coal_miner - 矿工：4431,5649
image num: 9900![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/58ae3a36428c4706ad50f99c28008ea7.png)
# 煤矿井下开采要素检测数据集

| 项目 | 详情 |
| --- | --- |
| 数据集名称 | 煤矿井下开采要素检测数据集 |
| 总图像数量 | 9900张 |
| 图像尺寸 | 640*640 |
| 标注格式 | YOLO + VOC + COCO |
| 类别数量 | 5类 |
| 数据集划分 | 训练集：6933张   验证集：1976张   测试集：991张 |

### 类别明细

| 类别 | 中文名称 | 含该类图像数 | 标注总数 |
| --- | --- | --- | --- |
| gripper | 夹持器 | 9793 | 9800 |
| chuck | 卡盘 | 7611 | 7611 |
| drill_pipe | 钻杆 | 9090 | 9340 |
| mine_safety_helmet | 矿用安全帽 | 3949 | 4401 |
| coal_miner | 矿工 | 4431 | 5649 |

### 应用价值

井下暗光、粉尘复杂场景，用于井下设备状态识别、矿工人员检测、安全帽佩戴合规检查、井下采掘工作面智能监测，适用于煤矿安全生产AI监控、井下机器人视觉检测项目。

```
# YOLOv11n 训练脚本
from ultralytics import YOLO

if __name__ == '__main__':
    model = YOLO("yolov11n.pt")
    model.train(
        data="mine_element.yaml",
        epochs=80,
        imgsz=640,
        batch=8,
        device=0
    )
```

```
# PyQt5 推理启动代码
import sys
from PyQt5.QtWidgets import QApplication
from detect_ui import MainWindow

if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = MainWindow()
    window.show()
    sys.exit(app.exec_())
```


