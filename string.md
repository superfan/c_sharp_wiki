## 字符串



### String

* String 对象是不可改变的。每次使用 System.String 类中的方法之一时，都要在内存中创建一个新的字符串对象，这就需要为该新对象分配新的空间。
* 确保尽量少的装箱。

```
String str1="str1"+9;
String str2="str2"+9.ToString();
```

* 避免分配额外的内存空间。

```
string s1="abc";
s1="123"+s1+"456";    ////以上两行代码创建了3个字符串对象对象，并执行了一次string.Contact方法            
```

* @
* $


* string.Format

```
string a = "t";
string b = "e";
string c = "s";
string d = "t";
string result = string.Format("{0}{1}{2}{3}", a, b, c, d);
```




### StringBuilder

* StringBuilder并不会重新创建一个string对象，它的效率源于预先以非托管的方式分配内存。如果StringBuilder没有先定义长度，则默认分配的长度为16。当StringBuilder字符串长度小于等于16时，StringBuilder不会重新分配内存；当StringBuilder字符长度大于16小于32时，StringBuilder又会重新分配内存，使之成为16的倍数。在上面的代码中，如果预先判断字符串的长度将大于16，则可以为其设定一个更加合适的长度（如32）。StringBuilder重新分配内存时是按照上次容量加倍进行分配的。当然，我们需要注意，StringBuilder指定的长度要合适，太小了，需要频繁分配内存，太大了，浪费空间。



