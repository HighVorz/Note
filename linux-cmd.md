## find

``` bash
# 查找文件
find <path> -name "*.cpp"
```

``` bash
# 查找文件夹
find <path> -type d -name "build"
```

## nm
T：文本段（代码）中的全局符号。
t：文本段（代码）中的静态符号。
D：数据段（已初始化的全局变量）中的全局符号。
d：数据段（已初始化的全局变量）中的静态符号。
B：BSS 段（未初始化的全局变量）中的全局符号。
b：BSS 段（未初始化的全局变量）中的静态符号。
U：未定义的符号（通常表示外部引用）。
C：Common 符号（未初始化的全局变量，通常在多个文件中声明）。
a：绝对符号（不占用存储空间）。
V：弱符号（可以在链接时被覆盖）。
v：弱符号（局部）。
w：弱对象（局部）。


