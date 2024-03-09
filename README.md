<h2 align="center">ABLSpineLevelCheck: Localization of Vertebral Levels on Fluoroscopy via Semi-supervised Abductive Learning</h2>
<p align="center">
    <a href="https://github.com/ThreeStones1029/ABLSpineLevelCheck/blob/main/LICENSE">
        <img alt="license" src="https://img.shields.io/badge/LICENSE-GPL%203.0-blue">
    </a>
</p>
<details>
<summary>Fig</summary>

![albspinelevelcheck_overview](https://github.com/xxx)
</details>
<p align="left">
This is the official implementation of the paper "ABLSpineLevelCheck: Localization of Vertebral Levels on Fluoroscopy via Semi-supervised Abductive Learning".
The workflow of the proposed ABLSpineLevelCheck. (a) The function f contains two neural networks that work in an ensemble strategy. (b) The outputs O from the two neural networks contain the object detection results, respectively. (c) The ensemble module leverages the knowledge base to abduce the pseudo labels. (d) The knowledge base KB includes a set of first-order logical clauses suggested by orthopedic surgeons. (e)(f) The abduced results are sent back to retrain the neural networks.
</p>

## Abstract
<p align="center">居中对齐</p>
<p align="left">左对齐</p>
<p align="right">右对齐</p>
Deep learning has shown promising results in localizing ver-
tebrae in X-ray images. However, in deep learning, data labeling is time-
consuming and resource-intensive. To address this problem, a semi-supervised
abductive learning technique called ABLSpineLevelCheck is proposed.
First, the spine fluoroscopic images without annotation are fed into the
networks to estimate their pseudo-labeles of vertebra localization. Then,
these pseudo-labels are abduced by logical reasoning through knowledge
base composed of a set of first-order logical clauses. Finally, the networks
are retrained by the abduced results. We also propose to incorporate an
ensemble method that effectively combines semantic detection of verte-
bral levels and instance detection. Moreover, simulated dataset and the
BUU dataset are utilized to boot the robustness of the networks. Exhaus-
tive experiments demonstrate the effectiveness of pretraining, ensemble,
and logical reasoning modules. Furthermore, ABLSpineLevelCheck out-
performs traditional deep learning methods and can handle the training


## Performance
| No | DRR | BUU | Real Label Dataset | Fake Label Dataset | Study | mAP | AP50 | AP75
|:---:|:---:|:---:| :---:|:---:|:---:|:---:|:---:|:---:|
| (1) | × | × | 80% | 0% | RT-DETR50 | 0.621 | 0.770 | 0.766 |
| (2) | √ | × | 80% | 0% | RT-DETR50 | 0.674 | 0.861 | 0.827 |
| (3) | √ | √ | 80% | 0% | RT-DETR50 | 0.697 | 0.854 | 0.854 |
| (4) | √ |  √ | 80% | 0% | RT-DETR50+LR | 0.705 | 0.864 | 0.864 |
| (5) | √ | × | 20% | 0% | RT-DETR50 | 0.455 | 0.598 | 0.551 |
| (6) | √ | √ | 20% | 0% | RT-DETR50 | 0.662 | 0.849 | 0.809 |
| (7) | √ | √ | 20% | 60% | RT-DETR50+LR | 0.671 | 0.862 | 0.827 |
| (8) | √ | √ | 20% | 60% | only instance+LR+retrain | 0.714 | 0.908 | 0.868 |
| (9) | √ | √ | 20% | 60% | **Ours(YOLOv5+LR+retrain)**  | **0.737** | 0.919 | 0.896 |
| (10) | √ | √ | 20% | 60% |**Ours(RT-DETR101+LR+retrain)**  | 0.724 | 0.920 | 0.869 |
| (11) | √ | √ | 20% | 60% | **Ours(RT-DETR50+LR+retrain)**  | 0.724 | **0.933** | **0.898** |
