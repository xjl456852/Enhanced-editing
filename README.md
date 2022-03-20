ZH增强编辑

## 版本更新
### 0.4.5版本（更新于2022-3-17）
- 调整「转换文字颜色或背景颜色」功能，允许指定5种颜色值

### 0.4.4版本（更新于2022-3-10）
- 增加「选择当前语法」功能：选择光标所在的当前MrakDown语法（如加粗、高亮、删除、链接等效果）文本。
- 增加「键控游标跳转 Alt+Shift+J 或+L」功能： 控制游标在同类文本行或选区间跳转

### 0.4.3版本（更新于2022-3-3）
- 尝试解决实时阅览模中无序列表使用中文标点的部分BUG。
- 深度优化 js 文件代码，解决出错的调试信息，条理更加清晰。
- 增加「将内部链接语法转为超链接」功能

### 0.42版本（更新于2022-2-24）
- 修正「设置标题语法」功能中光标定位问题
- 增加「键控切换文件列表「Alt+Shift+I 或 +K」功能， 利用键盘控制切换文件列表中的文件显示
- 增加「折叠当前同级标题Ctrl+Shift+Alt+D」功能，判断当前行的标题层级，将正文中同级标题一次性折叠起来。
- 增加「列表转为图示」功能：选中列表文本，转换为相应层级的MerMaid语法图示，支持修改列表后更新图示。
- 修正精简代码时带出的「转换路径」问题
- 恢复「简繁转换」功能

### 0.4.1版本（更新于2022-2-14）
- 增加「键控游标 Alt+ I J K L U O」功能， 利用主键盘区控制编辑区的游标位置。
- 增强「MD语法格式刷」功能：当未选任何文本时，按下Alt+C +G +S +U +N 等快捷键即 开启或关闭 此功能。

### 0.4.0版本（更新于2022-2-13）
- 继续精简优化 js 文件代码，请全面测试，如有问题，敬请反馈！
- 增强「智能换行」功能
- 支持在正文情况下按下回车补加一次换行功能
- 支持在列表行中按下回车保持普通换行
- 实现在```代码块```中按下回车后的缩进效果

- 增强「转换无语法文本」功能，支持鼠标点击文本的语法部分后，去除相应的语法字符

### 0.3.9版本（更新于2022-2-12）
- 精简优化 js 文件代码
- 增强「删除当前段落Ctrl+D」功能：若在[[]]内会先删除链接内容、当遇有序列表项时会正常调小后面序号。

### 0.3.8版本（更新于2022-1-23）
- 完善「智能符号 Alt+;」功能，将 Dataview (dv)、Query (qy)、Mermaid (mm)、js、ja、py、css等单词转为```代码块```语法。
- 完善「修复意外断行」功能，去除行末多余空格
- 修正「上方插入空行、下方插入空行」功能

### 0.3.7版本（更新于2022-1-18，点此下载）
- 支持选择光标所在段落文本
- 支持选择光标所在整句文本
- 支持将划选文本转换为Anki挖空效果
- 完善嵌入当前网址页面功能，支持腾讯、B站、油管视频网址的自动处理

### 0.3.6 版本（更新于2022-1-13）
- 不再指定低频操作功能的快捷键
- 划选文字后可一键指定为当前笔记的文件名。
- 注意：暂不能自动全局修改。仅建议新建文档时使用。

- 划选网址后可一键嵌入当前网址页面到笔记中。

### 0.3.5 版本（更新于2022-1-2）
- 智能符号：自动转换、匹配或跳过括号符号，快捷键 Alt+;
- 输入【（或[(再按下快捷键可转换为〖
- 在 〖输入文字 后按下快捷键可匹配出 〗
- 在 《输入文字|》光标处按下快捷键可跳过》符号



## 功能说明
### 转换内部链接
- 「Alt+Z」 在选文两端添加或去除 [[ ]] 符号
- 支持批量转换用换行符分隔的多行文本或顿号分隔的多句文本。
- 禁用 "|[]?\*<>/: 等符号

### 智能符号
- 「Alt+;」 自动转换、匹配或跳过各种类型的括号符号「0.3.5版本」
- 判断前后字符，要么跳过后半部分引号，要么自动补全相关括号。
- 行首特殊字符的转换，参考Easy Typing插件
	-  》  → >
	-  、 → /

- 原来是〖文字|-  按 Alt+; 后在光标|处上屏〗
- 判断前两字符并替换为 → 后的符号
	-  【（ 或   [(   →〖
	-  （< 或   (<   →〈
	-  （【 或   ([   →〔
	-  “ 【 或 "[  →『
	-  ‘ 【 或   '[  →「
	-  ……  → ^

- 判断光标以前最近的前括号并匹配对应后括号
	-  《***》〈***〉［***］｛***｝【***】〖***〗〔***〕『***』「***」
	-  [[链接]]  ==高亮==   **加粗** ~~删除~~ %%注释%%

- 原来是 [[文字|]]###   在光标|处按 Alt+; 则跳到]] 后面
- 判断后面为以下字符组时 自动跳过
	-  |)>}]）》〉｝】〗〕』」
	-  |]]
	-  |**
	-  |==
	-  |~~


- 判断当前行内容，如为 Dataview、Query、Mermaid等单词，则转为代码块语法「0.3.8版本」
- dv → ```dataview```
- qy  → ```query```
- mm → ```mermaid```
- 也支持 js css ph等缩写


### 转换 MarkDown 语法
- 转换同义链接「Alt+Q」：将选文转换为 [[|选文]] 样式后再选择文档
- 转换粗体语法「Alt+C」∶将选文转为或去除 **粗体** 效果
- 转换斜体语法「Alt+X」∶将选文转为或去除 _斜体_ 效果
- 转换行内代码「Alt+D」∶将选文转为或去除 `行内代码` 效果
- 转换删除线「Alt+S」∶将选文转为或去除 ~~删除线~~ 效果
- 转换下划线「Alt+H」∶将选文转为或去除 下划线 效果
- 转换代码块「未设置」∶将选文转为或去除 ```代码块``` 效果
- 转换上标语法「Alt+U」∶将选文转为或去除 上标 效果
- 转换下标语法「Alt+N」∶将选文转为或去除 下标 效果
- 转换待办状态「未设置」：转换选文行首的待办状态，顺序为 -[ x-!?><+] 效果
- 转换挖空「未设置」：将选文转为或去除 {{c1::选文}} 效果 「0.3.7版本」
- 转换标题语法「Ctrl+1-6」∶指定或取消当前行文本为N级标题
- 转换文字颜色「Ctrl+Shift+1-7」∶将选文转为或去除 赤橙黄绿青蓝紫 颜色
- 转换背景颜色「Ctrl+Alt+1-7」∶将选文背景转为或去除 赤橙黄绿青蓝紫 颜色
- 转换无语法文本「Ctrl+Alt+Z」∶去除选文中所有markdown语法字符
- 获取无语法文本「Ctrl+Alt+C」∶去除选文中的所有markdown语法字符，并写入剪贴板

### 增减常见括号
- 【选文】「未设置」：在选文两端添加或去除 【】符号
- （选文）「未设置」：在选文两端添加或去除 （）符号
- 「选文」「未设置」：在选文两端添加或去除 「」符号
- 《选文》「未设置」：在选文两端添加或去除 《》符号

### 全局转换操作
- 英转中文标点「未设置」∶将笔记中的英文标点转换为中文标点，如,.?!"等
- 中转英文标点「未设置」∶将笔记中的中文标点转换为英文标点，如，。？！“等
- 转换路径语法「未设置」∶将 c:\\windows 与 [](file:///c:\/windows) 路径语法相互转换
- 简体转为繁体「未设置」：将笔记中的简体汉字转换为繁体汉字
- 繁体转为简体「未设置」：将笔记中的繁体汉字转换为简体汉字

### 个性增强功能
- 粘贴MD表格「Ctrl+Alt+V」∶将复制的Office表格直接粘贴为MarkDown语法表格「0.4.2版本已提升为智能粘贴」
- 修复错误语法「未设置」∶修复错误的MD语法，如1。列表、【】（）链接、[[]]()回链等
- 修复意外断行「未设置」∶修复笔记中的意外断行（删除结尾不是句式标点的换行符）
- 搜索当前文本「未设置」：通过搜索面板在当前文档中搜索划选内容。
- 获取时间信息「未设置」∶获取当前行中的时间信息，并控制链接笔记中的视频进行跳转播放
- 获取标注文本「未设置」∶获取标题、高亮、注释及前缀(#标注\批注\反思)等文本内容
- 选择当前整段「未设置」：选择光标所在的当前整段文本。「0.3.7版本」
- 选择当前整句「未设置」：选择光标所在的当前整句（中文）文本。「0.3.7版本」
- 自动设置标题「未设置」∶将选文中的单行文本（末尾非标点或数字）转为标题
- 指定当前文件名「未设置」：划选文字后指定为当前笔记的文件名。「0.3.6版本」
- 嵌入当前网址页面「未设置」∶在行末插入Html代码来嵌入所选网址页面。「0.3.7版本」
- 获取相对路径「未设置」：获取当前笔记在库目录内的相对路径。

### 插入或去除空行（空格）
- 编辑区内按下回车补加一次换行（有开关）
- 批量插入空行「Ctrl+Shift+L」∶在划选的文本行或全文中间批量插入空白行
- 批量去除空行「Ctrl+Alt+L」∶批量去除划选文本或全文中的空白行
- 上方插入空行「未设置」∶在当前文本行的上行插入空白行
- 下方插入空行「未设置」∶在当前文本行的下行插入空白行
- 末尾追加空格「未设置」∶在每行文本的末尾追加两个空格
- 去除末尾空格「未设置」∶批量去除每个文本行末尾的空格字符
- 添加中英间隔「未设置」：在正文的汉字与字母之间批量添加空格，如 china 中国。
- 去除所有空格「未设置」：去除正文中所有的全、半角空格


>欢迎向蚕子(QQ:312815311) 提出操作需求和建议，我们为增强编辑功能来共同努力！
