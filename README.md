# Notes-Embodied-AI
Datawhale开源教程笔记 &amp; Embodied AI体系的建立 &amp; 2025.7.15入门Embodied AI，故有些理解可能不太准确，欢迎issue &amp; 持续更新中

### 资源：
> 主要参考资料：
> 1. 整体框架的理解，简单demo的实现——Datawhale开源组织
> [https://github.com/datawhalechina/ai-hardware-robotics/blob/main/README.md](https://github.com/datawhalechina/ai-hardware-robotics/blob/main/README.md)
> 2. 整体框架的理解，较为完善的知识库——Lumina具身智能社区
> https://github.com/TianxingChen/Embodied-AI-Guide/blob/main/README.md
> 3. 更多是应用落地层面——宇树具身智能社群
> [https://www.unifolm.com](https://www.unifolm.com)


### 说明：
-  [notes_D1](notes_D1) ：我对理论知识的理解
	- 这些是我学习初期的想法，**很可能有误**
	- 我希望在这一部分为可以用极为精简的语言描述清楚功能/原理/实现方式等等
-  [notes_D2](notes_D2) ：理论知识的记录
	- 这一部分可以说是项目相关理论知识的一个库吧
	- 这一部分我只是把相关理论知识过了一遍，旨**尽可能快**得知道**有这么一个东西及其作用**，关键词加粗或高亮
-  [pdf_notes_D1](pdf_notes_D1) ：由于格式转化问题（Obsidian是“双等号“标记高亮但GitHub好像不是...格式问题我先不管了）我把note_D1转成pdf，或许会更清晰些。

---
---

# 1. Embodied AI知识体系(宏观理解)：

### 1.1 Embodied AI整体框架/架构

#### “具身”？

> 这部分或许属于嵌入式-ai机器人领域？——主要解决在一个**资源受限但要求实时性强的环境中**，**完成智能任务并能在物理世界中执行动作**（是具身智能的“具身”？）

> 以下部分旨在对具身实现建立一个大致的概念
> 虽说有部分专业名词以及理解可能不够准确，但不是此时的重点，后续理解更深入时，我会重新修改

<p align="center">
  <img src="images/9c822242d9456be7ed438dcbb208f83.png" alt="Image 1" width="90%" />
</p>
<p align="center">
  <img src="images/fc3db7026f054b3befff15f4292b0d1.png" alt="Image 2" width="90%" />
</p>


#### “智能”——VLA等几个方法范式——对应上述框架中的上位机模块？


---
---

# 2. (细致化)组件-关键词：

- 手眼标定——视觉感知和下位机控制模块——校准高精度标定-“相机看到的坐标系”&“机器人坐标系”的固定转换关系——如果是完全端到端 joint-control（例如 image → joint angle），有时不显式使用；


- RDK X5开发板——控制系统-硬件基础（集成上位机和下位机功能）
- 机器人学习的几个方法范式（VLA，RL，模仿学习，pipline模块化控制等等范式）——控制系统-上位机（高层/决策层）——“决定做什么”
- PID——控制系统-下位机（控制层）——“控制怎么做”；根据传感器反馈的物理量（如位移）来控制效应器（如升力）以使被控制物的（位移）稳定趋于期望值——基于规则；稳定


- 深度估计与3D重建？
- sam？


---
---
# 3. 如何实现简单demo落地：


---
---
# 4. 行业动态和研究前沿

---
---
# 5. PS&疑问：

1. notes_D1文件夹中内容的理解可能有偏差，需要后续实践阶段证明

2. PID是基于规则的而不是基于学习的？PID在后续算法中充当什么作用？
> ChatGPT：
> - 作为低层控制器嵌入高级系统：无人机轨迹跟踪-轨迹由高层路径规划生成，**姿态和高度**由底层 PID 跟踪
> - **Baseline**：在训练自动平衡的智能体时，先用 PID 保证不摔倒，再让 RL 学习超越 PID 性能
> - 混合控制：深度学习辅助 PID-用深度网络预测扰动或系统响应，再由 PID 做**补偿**
> - 在不确定性强的环境中作为“鲁棒 fallback”机制：PID 是最可靠的“安全兜底机制”，始终保持最基本的控制**稳定**性

---
---

# 6. 具身研究可能能用到的工具：
- LLM as General Planner——API编写

<p align="center">
  <img src="images/Pasted%20image%2020250717140829.png" alt="Pasted image 1" width="50%" />
</p>

<p align="center">
  <img src="images/Pasted%20image%2020250717141147.png" alt="Pasted image 2" width="50%" />
</p>




