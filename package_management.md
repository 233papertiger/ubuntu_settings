




# 包的安装、卸载和解压相关操作命令如下：

## 软件包安装：
```shell
sudo apt-get install <package>
```

```shell
sudo dpkg -i xxx.deb
```
使用 “dpkg” 时可能出现类似下面的报错

dpkg: 依赖关系问题使得 mendeleydesktop 的配置工作不能继续：
 mendeleydesktop 依赖于 python；然而：
  未安装软件包 python。
 mendeleydesktop 依赖于 gconf2；然而：
  未安装软件包 gconf2

可以使用如下命令解决：
```shell
sudo apt-get install -f
```
然后再使用dpkg命令进行安装

## 软件包卸载：
```shell
# 删除软件及其配置文件
apt-get --purge remove <package>
# 删除没用的依赖包
apt-get autoremove <package>
```

## 软件包解压：
.7z文件解压

```shell
sudo apt-get install p7zip-full
7z x 文件名.7z
```

ubuntu的软件包格式是deb，如果要安装rpm的包，则要先用alien把rpm转换成deb

```shell
sudo apt-get install alien # alien 默认未安装，所以首先要安装它
sudo alien xxx.rpm # 将rpm转换为deb，完成后会生成一个同名的xxx.deb
sudo dpkg -i xxx.deb # 安装deb包
```

TIP：
注意，用alien转换的deb包并不能保证100%顺利安装，所以可以找到deb最好直接用deb
有时候，我们想要使用的软件并没有被包含到 Ubuntu 的仓库中，而程序本身也没有提供让 Ubuntu 可以使用的 deb 包，你又不愿从源代码编译。但假如软件提供有 rpm 包的话，我们也是可以在 Ubuntu 中安装的。