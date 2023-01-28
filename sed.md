## overview

[address]command[command options]

## terminal options
n  no default print out
E   extend regular
i   in-place 
e   expression
f   file



## commands
x Exchange the contents of the hold and pattern spaces.
h 复制pattern space到hold space
H 追加pattern spaced到hold space
g 复制hold space到pattern space
G 追加hold space到pattern space
p 打印当前的pattern space
P 打印当前的pattern space中的第一行
d 清空 pattern space, 重启循环 ，不处理后续命令，不打印 pattern space.
D 删除 pattern space第一行, 重启循环 ，不处理后续命令，不打印 pattern space.
n 打印pattern space; 清空pattern space;读取下一行到pattern space
N 追加下一个输入行到pattern space
:label, 用于跳转
b  无条件跳转
t  s/// 匹配后跳转
T  s/// 不匹配后跳转
q  exit code 
a   append 
i   insert after
c   change
l   pattern space detail print out
s/search/replace/flags  replace
y/src/dst/     translate chars
z   empty pattern space
#  comment
{cmd;cmd;cmd}  group cmd
= print line




## example

```
 seq 6 | sed -n 'N;l;D'
```

```
sed '/./{H;$!d} ; x ; s/REGEXP/REPLACEMENT/'
```
