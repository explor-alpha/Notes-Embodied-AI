# Notes-Embodied-AI
Datawhale开源教程笔记 &amp; 我对Embodied AI体系的建立

### 参考
> [!NOTE] 参考
> 1. Datawhale项目链接
> [https://github.com/datawhalechina/ai-hardware-robotics/blob/main/README.md](https://github.com/datawhalechina/ai-hardware-robotics/blob/main/README.md)

### 说明：
-  [notes_D1](notes_D1) ：我对理论知识的理解
	- 这些是我学习初期的想法，**很可能有误**
	- 我希望在这一部分为可以用极为精简的语言描述清楚功能/原理/实现方式等等
-  [notes_D2](notes_D2) ：理论知识的记录
	- 这一部分可以说是项目相关理论知识的一个库吧
	- 这一部分我只是把相关理论知识过了一遍，旨**尽可能快**得知道**有这么一个东西及其作用**，关键词加粗或高亮
-  [pdf_notes_D1](pdf_notes_D1) ：由于格式转化问题（Obsidian是“双等号“标记高亮但GitHub好像不是...格式问题我先不管了）我把note_D1转成pdf，或许会更清晰些。

### 整体项目框架/基础技术路线：

**梳理成图：**

**关键词：**
- PID——根据传感器反馈的物理量（如位移）来控制效应器（如升力）以使被控制物的（位移）稳定趋于期望值。——（基于规则；稳定）
- 手眼标定；
- vla；
- ros；
- sam
- 仿真环境

**串联：**

### PS&疑问：

1. notes_D1文件夹中内容的理解可能有偏差，需要后续实践阶段证明

2. PID是基于规则的而不是基于学习的？PID在后续算法中充当什么作用？
> ChatGPT：
> - 作为低层控制器嵌入高级系统：无人机轨迹跟踪-轨迹由高层路径规划生成，**姿态和高度**由底层 PID 跟踪
> - **Baseline**：在训练自动平衡的智能体时，先用 PID 保证不摔倒，再让 RL 学习超越 PID 性能
> - 混合控制：深度学习辅助 PID-用深度网络预测扰动或系统响应，再由 PID 做**补偿**
> - 在不确定性强的环境中作为“鲁棒 fallback”机制：PID 是最可靠的“安全兜底机制”，始终保持最基本的控制**稳定**性


### 具身研究可能能用到的工具：
- LLM as General Planner——API编写
![Pasted image 20250717140829](../images/Pasted%20image%2020250717140829.png)
![Pasted image 20250717141147](../images/Pasted%20image%2020250717141147.png)

