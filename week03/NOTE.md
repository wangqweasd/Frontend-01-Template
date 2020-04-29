# 每周总结可以写在这里
学习总结
一.javaScript中有7中数据类型
1.undefined;
2.null;
3.String;
4.Boolean;
5.Number;
6.Object;
7.Symbol
凡是属性名属于Symbol类型，都是独一无二的，可以保证不会与其他属性名产生冲突
Symbol函数前不能使用new,这个是因为生产的Symbol是一个原始类型的值，不是对象，基本上，它是一种类似字符串的数据类型
二.var 最好写在函数内最前面或变量第一次出现的地方
三.0.1+0.2为什么不等于0.3
这是因为浮点数运算的精确问题，计算机只认识二进制，在进行运算时，需要将其他进制数值转成二进制，然后再进行计算，
由于浮点数用二进制表达时是穷的所以0.1+0.2是不等于0.3的
正确的比较方法：Math.abs(0.1 + 0.2 - 0.3) <= Number.EPSILON;
四.let,const,var
区别：let,const都是块级作用域，在函数内使用let定义后，对函数外部无影响，
const定义的变量是不可改变的，而且必须初始化，
var定义的变量可以修改，但是不初始化会变量提升输出undefined
五.定义函数一般有三种方式
1.function关键字
function x(){}
2.函数字面量
var x = function(){}
3.Function()构造函数
var x = new Function()