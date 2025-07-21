#### A1. 坐标系表示：
- **$F_b$：基座坐标系（Base Frame）**  固定在机械臂的底座上，是机械臂运动的全局参考坐标系。
- **$F_e$：末端执行器坐标系（End-Effector Frame）**  固定在机械臂末端执行器（如夹爪或工具）上。
- **$F_c$：相机坐标系（Camera Frame）**  固定在相机光心位置，是视觉感知的参考坐标系。
- **$F_t$：标定目标坐标系（Calibration Target Frame）**  固定在标定目标（如棋盘格、圆点板）上。

<p align="center">
  <img src="../images/Pasted%20image%2020250715135629.png" alt="Pasted image 1" width="66%" />
</p>

#### A2. 坐标系转化——齐次变换矩阵 $T^i_j​$：

> $T^i_j​$表：坐标系 **==j to i==**

> R控制旋转
> t控制平移

<p align="center">
  <img src="../images/Pasted%20image%2020250715135708.png" alt="Pasted image 2" width="66%" />
</p>

<p align="center">
  <img src="../images/Pasted%20image%2020250715135532.png" alt="Pasted image 3" width="66%" />
</p>

#### A3. relationship：

#### 特征/变量属性分析：

**==特征/变量属性分析表：==**

| 特征（变换矩阵）                | 是否为定值 | 是否可获取              |
| ----------------------- | ----- | ------------------ |
| $T^b_e$ （机械手末端夹具到机械手基础） | x     | 机器人系统直接获得          |
| ==$T^e_c$（相机到机械手末端夹具）== | ==v== | ==待标定==Eye In Hand |
| $T^c_t$ （相机到标定板）        | x     | 通过相机获得             |
| ==$T^b_t$ （标定板到机械手基础）== | ==v== | ==待标定==Eye to Hand |
可以发现：

> 4个坐标系对应3个**独立**的坐标转化关系（T）+1个坐标系
> 其中$T^c_t​$可通过拍摄获取
> 其中$T^b_e​$可有机器人系统直接获得
> 
> 因此==只有1个**独立**转化==：$T^e_c​$（Eye In Hand）或$T^b_c​$（Eye to Hand）
> **==只需求其一即可==**


<p align="center">
  <img src="../images/Pasted%20image%2020250715152003.png" alt="Pasted image 3" width="66%" />
</p>

