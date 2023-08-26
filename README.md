# AwaCxx

**AwaCxx** is a special C++ runtime which provide a sandbox, a script-like mode and variable enviroments. Just for happy.

**AwaCxx** 是一个特殊的C++运行时，它提供sandbo、类似脚本的模式，以及一个可变的环境。它只是为了瞬息欢愉。

<br/>

Go to the [developing notes](doc/notes/en-us/index.md).

前往[开发记录](doc/notes/zh-cn/index.md)。

<br/>

It is being developed now. Here are *preview*.

开发中，*前瞻*如下。


## Feature / 特点

Here are my goals:
- Easy to use
- Expandable
- Light-weight enough
- Cross-platform
- Using standard library everywhere
- Written in modern C++ language (>=20)
- Few dependence

以下是我的目标：
- 易用
- 可拓展
- 轻量级
- 跨平台
- 大量使用标准库
- 使用现代C++语言（至少是20）
- 几乎无依赖项

<br/>

## Examples / 示例

Here are some examples I imagined:

我想象中的它是这样的：

<br/>

```cpp
#include <iostream>
#include <AwaCxx/AwaCxx.h>

int main(int argc,char** argv,char** envp)
{
    using namespace std;
    using namespace AwaCxx;
    
    Enviroments::Context ctx;
    ctx.doImport("std");
    ctx.doUsingNamesp("std");
    auto [out,end]=ctx["cout","endl"];
    out<<"Hello world!"<<end;
    ctx.define("num",Types::Int,0);
    ctx.function("f");
    f.overload(Type::Void,{},
        [](Enviroments::Context& ctx,ObjectList args){
            auto [out,num,end]=ctx["cout","num","endl"];
            out<<++num<<end;
        }
    );
    f();
    f();
    f();
}
```

<br/>

Output:

输出：

<br/>

```
Hello world!
1
2
3
```

<br/>

## Other to say / 其他

I am a high school grade 12 student and preparing for the coming Gaokao. So there are little time to program.

没时间，摆了。爱咋咋地。

<br/>

This project was inspired by *Herta* from *Honkai: Star Rail* in some degree. Thank you Herta.

项目受到*黑塔*女士的启发。

<br/>

***She's really beautiful.***

***她真好看。***
