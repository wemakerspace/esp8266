# SSD1306 oled屏幕驱动显示图片
我们需要提前准备的材料:  
1、0.96寸SPI接口的OLED屏幕 * 1 块  
2、esp8266开发板 *1块  
3、母到母杜邦线 * 4条  
4、micropython开发环境(包含IDE，以及程序上传相关耗材)  

二、屏幕介绍 

从左向右依次为  
GND  3.3v输入负极  
VCC   3.3v输入正极  
SCL   时钟  (部分屏幕上是D0)  
SDA  MOSI数据    (部分屏幕上是D1)  
RST  硬件复位  
D/C  数据命令  
CS  (7针屏幕上多的一针)


三、屏幕和开发板连线方式 
 
屏幕| 开发板|GPIO
--| -- | --
GND| GND|
VCC|3.3V|
SCL	|D5	|14
SDA	|D6	|12
RST	|D7	|13
D/C	|D8	|15

关于framebuffer说明
https://mpython.readthedocs.io/zh/master/library/micropython/framebuf.html#framebuffer

	• framebuf.line(x1,y1,x2,y2,c)，画直线
	• framebuf.hline(x,y,w,c)，画水平直线
	• framebuf.vline(x,y,w,c)，画垂直直线
	• framebuf.fill_rect(x,y,w,h,c)，画填充矩形
	• framebuf.rect(x,y,w,h,c)，画空心矩形

学习使用  
oled.fill(0)  #首现进行清除屏幕  
oled.line(4,4,100,32,1)   # 画一个三角形的斜边
oled.hline(4,32,96,1)   # 画三角形的底边
oled.vline(4,4,28,1)  画三角形的侧边
oled.rect(2,3,101,33,1)  在三角形外面画一个长方形
oled.fill_rect(10,10,5,5,1)


四、图片准备
1、百度上找到一张需要显示的图片
2、将图片进行处理，转换成我们屏幕大小
3、处理好的图片转换成PBM格式，上传到开发板(https://convertio.co/)

编写代码。上传到开发板


    


