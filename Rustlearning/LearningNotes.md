# Rust
-----
## cargo
> 包管理工具最重要的意义在于。任何用户拿到你的代码，都能运行起来，而不会因为各种包版本而焦头烂额
### Hello world!
作为一种现代化语言，rust吸收了多个语言的包管理优点，为大家提供了炒鸡大杀器`cargo`,下面是一个示例。 
```bash
$ cargo new hello_world
$ cd world_hello
```
上面的命令使用`cargo new`创建了一个新的项目，该项目的结构和配置文件都是由cargo生成的，意味着我们的项目被cargo所管理。
>ps：Rust项目主要分为两个类型，`bin`和`lib`，前者是可运行的项目，后者是一个依赖库项目
  
来看看这个优雅的项目结构：
```bash
$ tree
.
├── .git
├── .gitignore
├── Cargo.toml
└── src
    └── main.rs
```
连`git`都帮你创建了，实在贴心。  
在上述代码中，`cargo run`首先对项目进行编译，然后再运行，等同于运行了两个指令，下面我们手动试一下编译和运行项目：  
编译
```bash
$ cargo build
    Finished dev [unoptimized + debuginfo] target(s) in 0.01s
```
运行
```bash
$ .\target\debug\hello_world 
Hello, world!
```
在编译的时候，其实有两种编译模式、分别是`debug`和`release`,前者可以非常快地编译出程序来，而损失了一些性能，后者则会进行优化，编译高性能代码
  
当项目大了以后， `cargo run`和`cargo build`不可避免地会变慢，那么有没有更快的方式来验证代码的正确性呢？答案是：有！  
`cargo check`是一个非常快速的命令，仅仅是检查一下代码能否编译通过，而不会真的去编译，能节省非常多的时间。  

### Cargo.toml 和 Cargo.lock  
  
`Cargo.toml` 和 `Cargo.lock`是`cargo`的核心文件，它的所有活动均基于二者
  
- `Cargo.toml` 是 `cargo` 特有的项目数据描述文件，储存了项目所有的元配置信息  
- `Cargo.lock` 则是一个更加详细的项目依赖清单，一般不需要修改它  
  
我们接下来打开`Cargo.toml`
可以看到有两个段落：  
#### [package]
```
name = "hello_world"
version = "0.1.0"
edition = "2021"
```
其中这些配置也一目了然
#### [dependencies]
```
[Nothing yet]
```
那么如果要自定义项目依赖，我应该怎么写呢？
事实上，它可以有三种办法书写
```
[dependencies]
rand = "0.3"
hammer = { version = "0.5.0"}
color = { git = "https://github.com/bjz/color-rs" }
geometry = { path = "crates/geometry" }
```
- 前两者是**基于官方的Rust仓库`crates.io`，通过版本说明来描述依赖**
- 第三个是**基于项目源代码的git仓库地址，通过URL来描述**
- 第四个是**基于本地项目的绝对路径或者相对路径，通过类似于Unix模式的路径来书写**
  
## Var 变量
在 Rust 中，变量都是默认不可变的
