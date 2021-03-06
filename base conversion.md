
## 二进制和八进制的互相转换

### 二进制转换为八进制

8等于2的三次方，1位八进制的数可以认为是3位二进制的数组合而成，所以在将二进制数转换为八进制数时，可以采用“取三合一法”，具体方法是从右至左依次将二进制的每3位组合起来，如果到最左边时发现不足3位则在前面加‘0’

如：11010100011 -> 
(11) (010) (100) (011) -> 
(011) (010) (100) (011) ->
3 2 4 3 =3243

### 八进制转换为二进制

方法同上，将每一位八进制数拆成3位二进制数，最后去掉前面的‘0’

Ps：十六进制与二进制的转换与八进制同理，只是方法变成“取四合一法”

## 二进制和十进制的互相转换

### 二进制转换为十进制
用位权相加法，将任何一个二进制数的值都用它的按位权展开式表示。例如：将二进制数10101.11(2)转换成十进制数。

10101.11(2)＝1\*2^4＋0\*2^3＋1\*2^2＋0\*2^1＋1\*2^0＋1\*2^(-1)＋1\*2^(-2)
＝2^4＋2^2＋2^0＋2^(-1)+2^(-2)=16+4+1+0.5+0.25=21.75(10)

### 十进制转换为二进制

#### (1)整数部分的转换

将十进制整数转换成二进制整数采用“除2取倒余法”。

![](https://github.com/hjm1027/ph/blob/master/t01619d1a26fbe7f23a.jpg?raw=true)

原理：举个十进制整数转换为二进制整数的例子，假设十进制整数A化得的二进制数为edcba的形式，那么用上面的方法按权展开，得:

A=a(2^0)+b(2^1)+c(2^2)+d(2^3)+e(2^4) (后面的和不正是化十进制的过程吗)

假设该数未转化为二进制,除以基数2得

A/2=a(2^0)/2+b(2^1)/2+c(2^2)/2+d(2^3)/2+e(2^4)/2

注意:a除不开二，余下了,其他的绝对能除开，因为他们都包含2，而a乘的是1，他本身绝对不包含因数2，只能余下。

商得:

b(2^0)+c(2^1)+d(2^2)+e(2^3)，再除以基数2余下了b，以此类推。

当这个数不能再被2除时，先余掉的a位数在原数低，而后来的余数数位高，所以要把所有的余数反过来写。正好是edcba

#### (2)小数部分的转换
十进制小数转二进制

十进制小数转换成二进制小数采用"乘2取整，顺序排列"法。具体做法是:用2乘十进制小数，可以得到积，将积的整数部分取出，再用2乘余下的小数部分，又得到一个积，再将积的整数部分取出，如此进行，直到积中的小数部分为零，此时0或1为二进制的最后一位。或者达到所要求的精度为止。

然后把取出的整数部分按顺序排列起来，先取的整数作为二进制小数的高位有效位，后取的整数作为低位有效位。

如:0.625=(0.101)B

0.625*2=1.25======取出整数部分1

0.25*2=0.5========取出整数部分0

0.5*2=1==========取出整数部分1

再如:0.7=(0.1 0110 0110...)B

0.7*2=1.4========取出整数部分1

0.4*2=0.8========取出整数部分0

0.8*2=1.6========取出整数部分1

0.6*2=1.2========取出整数部分1

0.2*2=0.4========取出整数部分0

0.4*2=0.8========取出整数部分0

0.8*2=1.6========取出整数部分1

0.6*2=1.2========取出整数部分1

0.2*2=0.4========取出整数部分0

原理：关于十进制小数转换为二进制小数
假设一十进制小数B化为了二进制小数0.ab的形式，同样按权展开，得
B=a(2^-1)+b(2^-2)
因为小数部分的位权是负次幂，所以我们只能乘2，得
2B=a+b(2^-1)
注意a变成了整数部分，我们取整数正好是取到了a，剩下的小数部分也如此。
值得一提的是，小数部分的按权展开的数位顺数正好和整数部分相反，所以不必反向取余数了。

## 八进制和十进制的互相转换

### 八进制转换为十进制

与二进制转换为十进制的方法一样，任何一个八进制数的值都用它的按位权展开式表示。如将92.65(8)转换成十进制数。

92.65(8)=9\*8^2+2\*8^1+6\*8^(-1)+5\*8^(-2)=74.828125(10)

### 十进制转换为八进制

#### 方法1 直接转换法

此方法与十进制转换为二进制的方法一样，整数部分转换，除8取余法，每次将整数部分除以8，余数为该位权上的数，商继续除以8，余数又为上一个位权上的数，然后以此类推一直下去，直到商为零为止，最后从最后一个余数向前排列就可以了。如图

![](https://github.com/hjm1027/ph/blob/master/t0175fd166aec3b492a.png?raw=true)

小数部分转换，这里是乘8取整法，也就是说小数部分乘以8，然后取整数部分，再让剩下的小数部分再乘以8，再取整数部分，然后以此类推一直下去，一直乘到小数部分为零为止或者到达所需的精度为止。如图

![](https://github.com/hjm1027/ph/blob/master/t01e5e22d325bf844fa.png?raw=true)

#### 方法2 间接转换法

先将十进制数转换为二进制数，再将二进制数转换为八进制数
