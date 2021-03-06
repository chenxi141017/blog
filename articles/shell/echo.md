echo 通常用于 shell 脚本中以显示消息或输出其他命令的结果。

显示带颜色的输出内容，需要使用参数 `-e` ， 格式如下:

```shell
echo -e "\003[背景颜色;文字颜色;显示方式m字符串\003[0m"
```

示例:  

```shell
echo -e "\033[40;31;5mSomething string\033[0m"
```

上述代码将会输出字符串 `Something string` , 其中背景颜色是黑色，文字颜色是红色，文字闪烁；

注：

- 背景颜色， 文字颜色， 显示方式，可以随意搭配，如果缺失某一项将使用默认选项；
- `-e` 是命令 `echo` 的一个可选项，它用于激活特殊字符的解析器，可以转义反斜杠字符;
- `\033` 引导非常规字符序列;
- `m` 意味着设置属性然后结束非常规字符序列，显示的字符串之前有一个 `m` ；



显示方式具体内容：

| 显示方式 | 含义         |
| :------- | ------------ |
| 0        | 关闭所有属性 |
| 1        | 设置高亮     |
| 4        | 下划线       |
| 5        | 闪烁         |
| 7        | 反显         |
| 8        | 消隐         |



[颜色](<https://en.wikipedia.org/wiki/ANSI_escape_code#Colors>)具体内容：

| 文字颜色 | 背景颜色 | 颜色   |
| -------- | -------- | ------ |
| 30       | 40       | 黑色   |
| 31       | 41       | 红色   |
| 32       | 42       | 绿色   |
| 33       | 43       | 黄色   |
| 34       | 44       | 蓝色   |
| 35       | 45       | 紫红色 |
| 36       | 46       | 青蓝色 |
| 37       | 47       | 白色   |

