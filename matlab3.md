# matlab 数值计算
- 多项式表示成矩阵，最右边为常数项，向左次数依次加一，没有的项补零表示
- polyval(a,x) 其中a表示多项式矩阵，x为输入变量，当x为范围值时输出图像，为单个值时输出取值
- polyder(a)对a多项式求导
- polyint(a,k)对多项式a进行积分，常数项设为k
- 在做简单的特殊函数微分时，从定义出发，用diff(y)./diff(x)函数解决问题，其中xy为向量
- 注意在作图时要将x输入写为x(1:end-1) 因为diff之后的维度少了一，高阶微分相应减一
- 注意在自己写的函数中如果想要调用另一个函数，需要将另一个函数写成function handle的形式  
	例如积分函数： function [y]=xy_plot(input,x)  
					y=input(x);  
					plot(x,y,'r--');  
					xlabel('x');ylabel('function(x)');  
				end  
				xy_plot(sin,0:0.01:2*pi);%这样使用时会报错  
				y= @(x) sin(x);  
				xy_plot(y,0:0.01:2*pi);%正确方式  
- integral 积分函数 integral(f,x的范围)
