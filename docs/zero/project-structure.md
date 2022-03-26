# 项目结构

Lua 整个源代码结构如下所示:

- manual
    - 2html
    - manual.of
- tests
- .gitignore
- all


- lapi                     c语言接口
- lauxlib                  构建 Lua 标准库的辅助库
- lbaselib                 基础库函数
- lcode                    源码生成
- lcorolib                 协程库
- lctype                   类型相关数据
- ldblic                   Lua 调用调试相关接口  
- ldebug                   调试库
- ldo                      Lua 栈和调用结构
- ldump                    序列化预编译的 Lua 字节码
- lfunc                    操作函数原型和闭包的辅助函数
- lgc                      垃圾回收
- linit                    内嵌库的初始化
- liolib                   标准 I/O 库
- ljumptab                 解释器的跳转表 
- llex                     词法分析
- llimits                  限制等一些基本类型定义
- lmathlib                 标准数学库
- lmem                     内存管理 
- loadlib                  Lua 的动态库加载器   
- lobject                  对象管理  
- lopcodes                 字节码操作
- lopnamse                 对应的字节码名称
- loslib                   系统标准库 
- lparser                  解析器  
- lprefix                  预先 Lua 定义代码
- lstate                   全局状态机
- lstring                  字符串表(Lua 所有字符串) 
- lstrlib                  字符串和模式匹配的标准库
- ltable                   Lua hashtable
- ltablib                  table 标准库
- ltests                   Lua 实现调试的内部模块
- ltm                      标记方法(运行时的特定关键点调用，程序员可以更改标准行为)
- lua                      解释器
- luaconf                  Lua 配置文件
- lualib                   Lua 标准库  
- lundump                  加载预编译 Lua 代码
- lutf8lib                 UTF-8 标准库
- lvm                      Lua 虚拟机
- lzio                     缓冲流

- makefile
- onelua
- README.md

通过以上的所有文件，我们就可以执行 lua 代码了。
 
- 词法、语法分析 -> OpCode
  这里通过 llex(词法分析) 和 lparse(语法分析) 生成了 OpCode

- OpCode -> Lua 虚拟机
  然后将 OpCode 输入到虚拟机 lvm 中，虚拟机包含了 ldo、lgc、lapi 以及标准库。

我们可以看到  