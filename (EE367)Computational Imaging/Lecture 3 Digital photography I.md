## 第一部分 摄影发展的历史
pinhole camera/camera obscura(针孔摄像，暗箱)
Daguerreotype(银版摄像法) 使用透镜聚焦光线并使用化学物质固定影像
SLR camera(single-lens reflex camera,单反摄像机)![[Pasted image 20260703221203.png]]


## 第二部分 几何光学和镜头
透镜成像公式
$$\frac{1}{f}=\frac{1}{S_1}+\frac{1}{S_2}$$
镜头像差（Aberrations）：理想透镜并不存在，现实中会产生各种模糊或畸变：

	球差（Spherical aberration）：通过透镜边缘的光线与通过中心的光线无法聚焦在同一点
	彗差（Coma）：轴外光束聚焦后形成的像点带有彗星尾巴一样的拖尾。
	色差（Chromatic aberration）：不同颜色的光（波长不同）折射率不同，导致焦点错开。通常使消色差双合透镜（Achromatic doublet）（结合冕牌玻璃 Crown 和火石玻璃 Flint）来矫正。

衍射极限(Diffraction Limit)就是在分辨率上面的天花板
$$d=\frac{\lambda}{2n\sin \theta}$$
没看懂这个公式，怎么这个公式写法一堆的？

FoV
## 第三部分 光圈、曝光和景深
光圈（Aperture）：控制光线通过孔径的大小。其单位用 f值（f-number, N） 表示（$N = f/D$，焦距除以孔径）。f值越小（如 $f/1.4$），光圈开得越大，进光量越多。

弥散圆（Circle of Confusion, CoC）：当焦点不准时，一个物点在传感器上成像为一个模糊的圆点。

景深（Depth of Field, DoF）：画面中成像清晰的前后距离范围。大光圈（小f值）会产生浅景深（Shallow DoF），常用于拍摄背景模糊的焦外虚化（Bokeh）艺术效果。

快门速度 / 曝光时间（Shutter speed / Exposure time）：控制传感器接收光线的时间。时间长会产生运动模糊（Motion blur）。

衍射极限（Diffraction Limit）：当光圈缩得太小（f值很大）时，光波会发生衍射，形成艾里斑（Airy pattern，这个玩意物理里面好像学过吗？）。根据恩斯特·阿贝（Ernst Abbe）定律，这会限制相机的最高几何分辨率。

编码孔径(Coded Aperture)传统相机的光圈一般就是一个圆，但是如果使用特定的mask，让特定的光透过孔，然后通过算法将原先的信息都还原出来。这么做并不是没有意义的，传统相机想要进光量大就要放大光圈，想要深景深就需要缩小光圈，而使用编码孔径就可以解决这个问题。

## 第四部分 传感器与像素结构
色彩空间阵列（Pixel Anatomy）最常见的就是bayer pattern了

## 第五部分 图像噪声和信噪比

光子转换成raw图像
![[Pasted image 20260704152012.png]]


这个部分里面会引入多种噪声，其主要分布包括
高斯噪声（Gaussian Noise），来源可能是热噪声，读取噪声和放大噪声，它具有加性，是独立于信号的
光子噪声/散粒噪声（Photon noise/ Shot noise）由于光子的随机到达引起的，服从泊松分布，是依赖于信号的。

信噪比（Signal-to-Noise Ratio，SNR）这个之前在捣鼓VAR的时候用过，
$$SNR=\frac{mean\ pixel\ value}{stardard\ deviation\ of\ pixel\ vlaue}$$

