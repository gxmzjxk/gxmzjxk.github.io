---
    layout: post
    title: 在 Git bash 中使用 Windows系统命令 乱码
    category: windows
    tags: ['Git', 'Windows']
---
## 缘起
需要在 `Windows10` 上安装`Ruby`，需要知道系统版本是32位还是64位的，查看的方式有很多种
1. 点击操作系统最下角的[开始]田字标识，然后点[设置]齿轮标识 > [系统] > [ 关于 ]
2. 命令行：`systeminfo`，**在Git Bash 中执行出现了乱码**

## Why
1. Git Bash 中可以运行 Windows cmd 可以使用的命令，默认的 cmd 的活动代码页（active codepage）是 936 代表的`GBK`编码，而 git bash 默认的编码是 `utf8` 所以在 git bash 中执行cmd 中的命令，例如 `systeminfo`，就会出现乱码问题
> Git Bash 本质上是只一个壳(Shell)，Core 依然是Windows系统自带的指令

## How
> 因为 cmd 是操作系统的基础工具，如果贸然改动其编码会遇到不可知问题，所以正确的做法是修改 Git Bash 展示中文时的编码

在 Git Bash 中右键选中 `options`，在左侧栏目中点击`Text`，在右侧最下方，点击 `Locale` 选中 `zh_CN`， Charactor set 选中 `GBK (chinese)` ， 点击 `Apply`

## 总结
由于网上大部分答案基本都是关于Git使用相关的问题，无法解决我的问题，所以在这里记录一下，Git 使用(提交中文文件名，提交中文注释)等乱码问题，请参看扩展阅读

## 扩展阅读
[解决 Git 在Windows上的中文乱码问题](https://devopshub.cn/2018/01/07/g4e-faq-4-git-encoding-error/)

## 参考

[windows git-bash 设置](https://www.cnblogs.com/a-ray-of-sunshine/p/4973836.html)