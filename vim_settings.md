# vim配置修改

vim tab键默认设置为8个空格，修改设置为4个空格,并且设置自动补全
```shell
set tabstop=4
set softtabstop=4
set shiftwidth=4

"set autoindent
set smartindent

inoremap ' ''<ESC>i
inoremap " ""<ESC>i
inoremap ( ()<ESC>i
inoremap [ []<ESC>i
inoremap { {<CR>}<ESC>O

```
之后保存，会出现readonly文件无法修改错误  
>解决办法如下:
+ 在退出时输入如下命令：
```shell
:w !sudo tee %
```
+ 看到如下信息后回车：  
请按ENTER或其他命令继续

+ 看到如下信息后输入字母L：  
w12:警告：文件“Makefile” 已变动，并且在vim中的缓冲区也已变动进一步说明请见“:help w12”
确定([o])，加载文件((L)):

+ 回到编辑界面，输入如下：
```shell
:q
```

# vim 快捷键
>在命令行下，按键说明  
**u**  撤销上一次的操作
