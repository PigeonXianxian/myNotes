# 第三章 数据和C

## 3.1 实例程序-程序中的新元素
1）错误与警告  
- 错误-程序中有错，不能进行编译
- 警告-不终止编译，编写的代码有效，但结果可能不是程序员想要的(exm:从`double`类型转换为`float`类型可能会丢失数据)  
 
2）  
```c
float value;
printf("Your weight in platinum is worth $&.2f.\n",value);
```
我们在`printf()`中使用`%f`来处理浮点值，`%.2f`中的`.2`用于精确控制输出，指定输出的浮点数只显示小数点后面两位  
  
3）
```c
float weight;
scanf("%f",&weight);
```
`scanf()`用于读取键盘的输入  
`%f`说明`scanf()`要读取用户从键盘输入的浮点数  
`&weight`告诉`scanf()`把输入的值赋给名为weight的变量

## 3.2 变量与常量数据
- 有些数据类型在程序使用之前已经预先设定好了，在整个程序的运行过程中没有变化，这些称为**常量**
- 其他数据类型在程序运行期间可能会被改变或被复制，这些称为**变量**  

## 3.3 数据：数据类型和关键字
按计算机的存储方式可分为两大类型：**整数类型**和**浮点数类型**  
`int`：基本的整数类型  
`long`、`short`、`unsigned`、`signed`：提供基本整数类型的变式(exm:`unsigned short int`或`long long int`)  
`char`：指定字母和其他字符(exm:#、$、%、*)，也可以表示较小的整数  
`float`、`double`、`long double`：表示带小数点的数  
`_Complex`：表示复数  
`_Imaginary`：表示虚数  
#### | 位、字节和字
**位(bit)** 最小的存储单位，可以存储0或1  
**字节(byte)** 常用的计算机储存单位，为8位  
**字(word)** 设计计算机时给定的自然存储单位。计算机字长越大，其数据转移越快，允许的内存访问也越多  
### 3.3.2 整数
**整数**是没有小数部分的数。计算机以二进制数字存储整数  
exm：数字7以二进制写是111。因此，要在8位字节中存储该数字，需要把前五位都设置成0，后3位设置成1  
|0|0|0|0|0|1|1|1|
|-|-|-|-|-|:-:|:-:|:-:|
| | | | | |2<sup>2</sup>|2<sup>1</sup>|2<sup>0</sup>|
### 3.3.3 浮点数
计算机把浮点数分成小数部分和指数部分来表示，而且分开存储这两部分  
|+|.314159|1|
|:-:|:-------:|:-:|
|符号|小数|指数|

+0.314159*10<sup>1</sup> =3.14159

## 3.4 C语言基本数据类型
### 3.4.1 int类型
`int`的取值范围因计算机系统而异，一般需要占用一个机器字长。目前个人计算机为64位处理器，因此用64位存储一个int值。  
一般而言，系统用一个特殊位的值来表示有符号整数的正负号。