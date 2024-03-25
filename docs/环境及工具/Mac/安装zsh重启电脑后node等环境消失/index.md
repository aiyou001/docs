### 项目场景：
今天 Mac 安装 iTerm2，附带主题、oh my zsh 插件，一切正常。今天运行项目，发现不能用 npm、node、nvm 等命令。

上网找了很多方案，最终受 stackoverflow 一篇帖子启发，成功得到解决。

废话不多说，解决方案如下：

```bash
## 只需要按照以下步骤，打开zsh的配置文件,放开宏命令即可

##第一步 打开配置文件
open ~/.zshrc

##第二步 找到下面这行，你会发现plugin右边的配置默认只有git  这时候你可以自由添加你想要用的,用空格隔开。（node nvm yarn npm ）等等  然后保存
'plugins=(git)' -> 'plugins=(git node nvm yarn npm)'

## 第三步  更新配置文件，启用修改
source ~/.zshrc

## 最后一步
重启终端，再尝试一切是否正常
```


### 参考
- [Mac终端 安装 iTerm2、oh my zsh美化插件后，node/npm/yarn等指令不能使用的解决办法](https://blog.csdn.net/qq_38774001/article/details/123510628?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-123510628-blog-129349346.235%5Ev39%5Epc_relevant_anti_vip_base&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-123510628-blog-129349346.235%5Ev39%5Epc_relevant_anti_vip_base&utm_relevant_index=2)