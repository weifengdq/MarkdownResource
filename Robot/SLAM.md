常用的SLAM方法:

* 采用状态空间模型加上高斯白噪声--基于扩展卡尔曼滤波\(EKF\)的SLAM方法.   EKF-SLAM
* 非高斯概率分布的样本集合来表示运动模型--基于粒子滤波器\(RBPF\)的SLAM方法.  PF-SLAM, 如Gmapping
* gmapping是一个比较早的算法，核心思想是粒子滤波并且需要里程计，但并不要求很高性能的传感器，初学者一般都是先来玩这个，不过请注意一点，gmapping只是mapping，定位还需要amcl这个蒙特卡洛算法包配合使用，最后才能接入navigation stack。

[SLAM相关资料](http://www.jianshu.com/p/ecc9f489d9b2)

[ORB-SLAM2详解](http://blog.csdn.net/u010128736/article/details/53409199)

https://github.com/raulmur/ORB\_SLAM2

深度相机 RGB-D

[三维重建综述](http://www.jianshu.com/p/7ac4990bd93d)

---

SLAM必然要被深度学习取代

[http://www.rosclub.cn/post-628.html](http://www.rosclub.cn/post-628.html)

---

提供SLAM解决方案的公司:  
思岚

北醒

[乐行天下机器人事业部](https://robot.imscv.com/)

国内从事单目结构光方案开发的有深圳奥比中光科技有限公司、南京华捷艾米软件有限公司等；还有使用双目结构光方案的上海图漾信息科技有限公司；TOF方案的有深圳乐行天下科技有限公司；双目视觉的应用可见于大疆的无人机。

我们的Lidar也相当于 激光器+红外摄像头. EPC610 8\*8就相当于红外摄像头, 最后有64\*64比较好点.

机器人定位和导航、VR/AR手势识别、体感游戏、三维建模、工业智能化检测等等领域这些领域的底层实现算法或者方法实现.

结构光方案优势在于技术成熟，深度图像分辨率可以做得比较高，但容易受光照影响，室外环境基本不能使用；而TOF方案抗干扰性能好，视角更宽，不足是深度图像分辨率较低。

参考: [http://www.rosclub.cn/post-686.html](http://www.rosclub.cn/post-686.html)

嵌入式计算视觉处理器, 都是用的FPGA吧??? 也可以用一棵STM32F4, F7, H7即可. 免去了FPGA的开发复杂性.

CE30加上RGB就是 奥比中光或者Kinect之类的吧? 就是ToF\(单发单收, 单发双收等\) + RGB, 接口是USB, 以太网或者WiFi.

新产品必备的接口: Ethernet / Wi-Fi / Bluetooth 4.1 / USB, 再加上一个迎合旧技术的4针串口.

激光雷达的量产技术...

---

路径规划, ROS使用的是?

（Dijkstra，A\*等）, 思岚的D\*算法

vslam

Roomba 980 是iRobot于2015年12月推出的最新一款采用vslam方案的扫地机，在扫地机顶部一颗斜向上45°的摄像头，摄像头通过vslam算法拾取和记录沙发中的大量特征点\(尤其是物体的边角\)，并在运动过程中不断追踪这些特征点，同时不断检测新的特征点，由此建立一个环境地图。但是，为了定位自己当前的位置，必须要结合其他测距传感器，诸如陀螺仪、惯性导航设备等。

