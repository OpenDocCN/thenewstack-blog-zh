# 现成的黑客:用处理代码定制您的仪表

> 原文：<https://thenewstack.io/off-the-shelf-hacker-customize-your-gauges-with-processing-code/>

/*

*蒸汽朋克规

*

*读取串行输入流并在模拟仪表上显示数值

*在开始时加速指针，并使仪表变红。使用图形文件

*用于表盘和指针。改为平移/旋转图形

*使用代码手动构造指针。

*/

PFontf；

PImageG1 photo、  g2photo 、  p1photo 、p2 photo；

浮动 g1x ，  g1y ，  g2x ，g2y；

弦 角=【0】；  //角度度数

StringI value=【0】；  //输入行

浮动 测量角度=275.0；  //量规附加角度到最大值

浮动gaugestartangle=135.0；  //仪表角度从 3:00 零点位置

floatmaxinputvalue=157.5；  //最大测量极限

浮动 角度 1f=0.0；  //量规 1 的指针角度

浮动 角度 2f=0.0；  //仪表 2 的指针角度

floatsegLength=95；  //从中心到最大点的指针长度

intrevup=0；  //针针时的初始转速值

浮动 危险值=130；  //如果输入高于该数值，仪表变红

buffered readerdata file 1；  //从 Arduino 输入文件

buffered readerstartup file；  //启动时插针的 rev-up 文件

作废 设置 () {



(600、300)；  //仪表窗口尺寸

G1 photo=loadImage("/home/pi/gauge 10-b . png ")；  //规#1 面图形文件

G2 photo=loadImage("/home/pi/gauge 10-c . png ")；  //规#2 面图形文件

P1 photo=loadImage("/home/pi/clock-pointer . gif ")；  //仪表#1 指针图形文件

p2photo=loadImage("/home/pi/s-pointer . gif ")；  //仪表#2 指针图形文件

f=create font(《潘赫斯特》、  16 、true)；



stroke weight(2)；  //线条粗细

行程 ( 0 ， 0 ，0)；  //线条颜色(RGB)

g1x=150；  //仪表#1 指针 x 原点

g1y=身高*0.5；  //仪表#1 指针 y 原点

g2x=373；  //仪表#2 指针 x 原点

g2y=73；  //仪表#2 指针 y 原点



data file 1=create reader("/dev/TT yama 0 ")；

//连接到串行输入数据文件

//如果仪表不可见，首先在命令行执行 stty

startup file=create reader("/home/pi/processing-3.3/gauge-test 2 . txt ")；

//连接到加速文件

}

作废 绘制 () {



背景(255)；  //使背景变白(255)

图片(G1 照片， 0 ，0)；  //规#1 面图形

图像 ( g2photo ， 300 ，0)；  //规#2 面图形

text font(f，16)；  //仪表#1 数字文本读出设置

textAlign(居中)；

(0)；

{

if(revup=0){//在脚本启动时显示 revup 代码

ivalue=startup file。readLine()；

如果(ivalue=null){

=1；

ivalue=“20，20”；

}

}

目不斜视

ivalue=data file 1。readLine()；  //启动后拉入串行数据

}

}

(io exception){

e 。printStackTrace()；

ivalue=null；

}

如果(ivalue=null){

//因错误或文件为空而停止读取

no loop()；

}



如果(ivalue)！=null){



println(ivalue)；  // ivalue 结帐

串件=拆分 ( ivalue 、’、)；  //将串行输入行分成几段

弦G1 值 = 棋子0；

字符串G2 值 = 棋子1；

打印(G1 值)；

打印("+")；

println(G2 value)；

// anglef =弧度(135) +弧度(270)；

//输入值到量规角度的转换

角度 1f=(弧度 ( 高斯角度)+(浮动(G1 值)*

angle 2f=(弧度(gaugestartangle))+(浮动(g2value)*弧度(

正文(int(G1 value)，  150 ，275)；  //打印 1 号标尺上的数字值



如果(int(G1 value)&gt； 危险值 ){ //超过设定值时仪表变红

0 0 】

(A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A) (A

noTint ();

}

// push and pop to display pointer values on gauge

pushMatrix

segment1 (g1x g1y angle1f】

popMatrix();

pushMatrix

g2xg2yangle2f】

popMatrix();

(T76)(T77)

}

)(我)(们)(都)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(。

xy】

rotate (a )//旋转指针(T129)

)(那)(就)(是)(我)(们)(的)(一)(个)(情)(况)(,)(我)(们)(都)(不)(知)(道)(,)(我)(们)(还)(是)(不)(知)(道)(,)(我)(们)(还)(是)(不)(知)(道)(,)(我)(们)(还)(是)(不)(知)(道)(,)(我)(们)(还)(是)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(。//指针图形图像

}

)(我)(们)(都)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(。

translate xy 】

rotate (a )//旋转指针(T51)

( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( )( ) // 指针图形图像

}