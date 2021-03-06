vim编辑器是所有Unix及Linux系统下标准的编辑器，vi是Linux中最基本的文本编辑器，vim是vi的升级版。
### 1. vim基本概念
1. 命令行模式(command mode)

控制屏幕光标的移动、字符、字或行的删除，移动复制某区段及进入Insert mode(或last line mode)下。
2. 插入模式(Insert mode)

只有在Insert mode下，才可以做文字输入，按**ESC**键可回到命令行模式
3. 底行模式(last line mode)
 
将文件保存或退出vim，也可以设置编辑环境，如寻找字符串、列出行号等  
对于前端来说，可将vim简化为两个模式，即：将底行模式并入命令行模式
### 2. vim基本操作
1. 进入vim

在系统提示符号输入vim及文件名称后，就进入vim全屏编辑画面 如：vim filename  
vim之后处于命令行模式，要切换到插入模式才能输入文字。
2. 切换到插入模式(Insert mode)编辑文件

在命令行模式下按一下字母i就可以进入插入模式，输入文字了。
3. Insert切换

处于插入模式，您只能一直输入文字，如果发现输错了字，想用光标键往回移动，将该字删除，就要先按一下ESC键转到命令行模式再删除文字。
4. 退出vim及保存文件

在命令行模式下，按一下```:```冒号键进入底行模式，如：  
:w filename (输入w filename将文章以指定文件名filename保存)  
:wq (输入wq，存盘并退出vim)  
:q!(输入q!,不存盘并强制退出)

### 3. 命令行模式功能键
1. 插入模式

按```[i]```切换进入插入模式，按"i"进入插入模式后是从光标当前位置开始输入文件；  
按```[a]```进入插入模式后，是从目前光标所在位置的下一个位置开始输入文字；  
按```[o]```进入插入模式后，是插入新的一行，从行首开始输入文字；
2. 插入模式-->命令行模式

**ESC键**
3. 移动光标

vim可以直接用键盘上的光标来上下左右移动，但正规的vim是用小写英文字母```[h]、[j]、[k]、[l]```，分别控制光标左、下、上、右移一格。

按```[ctrl] + [b]```：屏幕往“后”移动一页。  
按```[ctrl] + [f]```：屏幕往“前”移动一页。  
按```[ctrl] + [u]```：屏幕往“后”移动半页。  
按```[ctrl] + [d]```：屏幕往“前”移动半页。  
按数字```[0]```：移到文章的开头。  
按```[G]```：移动到文章的最后。  
按```[$]```：移动到光标所在行的“行尾”。  
按```[^]```：移动到光标所在行的“行首”。  
按```[w]```：光标跳到下个字的开头。  
按```[e]```：光标跳到下个字的字尾。  
按```[b]```：光标回到上个字的开头。  
按```[#l]```：光标移动到该行的第#个位置，如：5l
4. 删除文字

```[x]```：每按一次，删除光标所在位置的“后面”一个字符。  
```[#x]```：如：[6x]表示删除光标所在位置的“后面”6个字符。  
```[X]```：大写的X，每按一次，删除光标所在位置的“前面”一个字符。  
```[#X]```：例，[20X]，表示删除光标所在位置的“前面”20个字符。  
```[dd]```：删除光标所在行。  
```[#dd]```：从光标所在行开始删除#行
5. 复制

```[yw]```：将光标所在之处到字尾的字符复制到缓冲区中。  
```[#yw]```：复制#个字到缓冲区  
```[yy]```：复制光标所在行到缓冲区  
```[#yy]```：例，[6yy]表示拷贝从光标所在行**往下数**6行文字。  
```[p]```：将缓冲区内的字符贴到光标所在位置。  
**注意**：所有与 **y** 有关的复制命令都必须与 **p** 配合才能完成复制与粘贴功能。
6. 替换

```[r]```：替换光标所在处的字符。  
```[R]```：替换光标所到之处字符，直到按下 **[ESC]** 键为止。  
7. 回复上一次操作

```[u]```：如果您误执行一个命令，可以马上按下[u]，回到上一个操作。按多次 **[u]** 可以执行多次回复
8. 更改

```[cw]```：更改光标所在处的字到字尾处  
```[c#w]```：例，[c3w]表示更改三个字
9. 跳至指定行

```[Ctrl] + [g]```：列出光标所在行的行号。  
```[#G]```：例，[15G]，表示移动光标至文章第15行行首。

### 4. Last line mode下命令汇总
在使用[last line mode]之前，请记住先按住 **[ESC]** 键确定已处于[command mode]下后，再按 **[：]** 冒号即可进入[last line mode]。
1. 列出行号

```[set nu]```：输入[set nu]后，会在文件中的每一行前面列出行号。
2. 跳到文件中的某一行

```[#]```：[#]号表示一个数字，在冒号后输入一个数字，再按回车键就会跳到该行，如：输入数字15，再回车，就会跳到文章的第15行。
3. 查找字符

```[/关键字]```：先按[/]键，再输入您想寻找的字符，如果第一次找的关键字不是您想要的，可以一直按[n]会往后寻找到您要的关键字为止。  
```[?关键字]```：先按[?]键，再输入您想寻找的字符，如果第一次找的关键字不是您想要的，可以一直按[n]会往前寻找到您要的关键字为止。
4. 保存文件

```[w]```：在冒号输入字母[w]就可将文件保存起来。
5. 离开vim

```[q]```：按 **[q]** 就是退出，如果无法离开vim，可以在[q]后跟一个 **[!]** 强制离开vim 俗称的：**[q!]**。  
```[qw]```：一般建议离开时，搭配[w]一起使用，在退出时还可保存文件。