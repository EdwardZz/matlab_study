# matlab日常笔记
- who 显示变量
- whos查看工作区变量
- 尽量避免使用matlab中的内建名称作为自己变量的名称，否则会发生混乱，例如cos 
- clear + 变量名，删除工作空间变量（后面不加为全删）
- 程式后面加分号不显示变数结果
- clc清命令界面
- close all 关闭所有图形
- 换行时可以在上一行末尾加...
- ctrl+C可以退出程序
- [函数大全](http://cn.mathworks.com/help/matlab/functionlist.html)
## **矩阵知识**
- 中括号中加;表示换行
- x:y 表示等差为1的数列
- x:i:y表示等差为i的数列
- A(3,:)表示第三列 =[]表示置空
- *为矩阵乘法，.*为各元素相乘
- 矩阵加'为转置
## 判断符号
- ~=为不等于
- &&为与
- ||为或
## 函数注意事项
- 写function时要注意到输入可能为矩阵形式的存在
- 变量输入少于默认值时，要在程序里写一个默认值，函数输入变量个数为nargin(内建变量)
- function handle 类似于指针的存在
## 文件的读取与加载
- save例子：save mydata1.mat 保存工作区变量
  save mydata2.mat -ascii 保存为记事本可读文件
- load例子：load('mydata.mat') load('mydata.mat','-ascii')
## matlab基础绘图
- plot(x,y,'str')表示画出x,y坐标图，后面str为图中线的模式选择 [模式链接](http://cn.mathworks.com/help/matlab/ref/linespec.html;jsessionid=c7c31e941cf0370837d8ae2d6939)
- legend（‘标记1’,'',''）可以在图上做标记
- 注意如果要在同一张图中显示多个结果，需要在显示函数两边加 hold on 和 hold off
- 坐标注释：xlabel() ylabel() zlabel()（当图形为三维的时候才会使用zlabel）
- 图名：title()
- 修改图的特征方式：例如 h= plot(x,y)  
	1、首先get(h)会返回线的特征  
	2、其次根据想改变的东西设置set(h,'特征符号'，相应变化)  
	3、gca边界 gcf图整体  
- subplot(m,n,x)子图绘制，里面有m*n个图，当前绘制的图的序号为x
- 保存图片 ：saveas(gcf,'<filename>','<格式>') 格式有：jpeg png tiff bmp/ pdf meta等
## matlab彩图绘制
- imagesc(z) 在将z与xy的关系定下来后，使用该命令可以将其变为彩色平面图
- colorbar显示彩色对应的值
- colormap(模式)修改对应的色系
## matlab3D图形
- meshgrid产生网格坐标 例：[x,y]=meshgrid(x,y)
- contour(x,y,z)做3图的投影 contour(z,[-3.5:0.5:3.5])以0.5为等差序列画线 contourf(Z)填充颜色  
		clabel标记线的值
