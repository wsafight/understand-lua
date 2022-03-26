# 基础类型

Lua 有 8 种基本类型： nil(空)、 boolean(布尔)、 number(数值)、string(字符串)、userdata(用户数据)、function(函数)、thread(线程)以及 table(表)。

我们可以看到对应的类型名称:

```luc
type(nil)            -->  nil
type(true)           -->  boolean
type(10)             -->  number
type("Hello world")  -->  string
type(io.stdin)       -->  userdata
type(print)          -->  function
type(type)           -->  thread
type({})             -->  table
```

我们在 lua.c 中也可以查看对应的定义:

```c
#define LUA_TNONE		(-1)

#define LUA_TNIL		0
#define LUA_TBOOLEAN		1
#define LUA_TLIGHTUSERDATA	2
#define LUA_TNUMBER		3
#define LUA_TSTRING		4
#define LUA_TTABLE		5
#define LUA_TFUNCTION		6
#define LUA_TUSERDATA		7
#define LUA_TTHREAD		8

#define LUA_NUMTYPES		9
```