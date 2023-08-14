# Ubuntu无法安装rpm包(ubuntu RPM should not be used directly install RPM packages, use Alien instead!
简单来说，ubuntu的软件包格式是deb，如果要安装rpm的包，则要先用alien把rpm转换成deb

```shell
sudo apt-get install alien # alien 默认未安装，所以首先要安装它
sudo alien xxx.rpm # 将rpm转换为deb，完成后会生成一个同名的xxx.deb
sudo dpkg -i xxx.deb # 安装deb包
```

Tip：
注意，用alien转换的deb包并不能保证100%顺利安装，所以可以找到deb最好直接用deb
有时候，我们想要使用的软件并没有被包含到 Ubuntu 的仓库中，而程序本身也没有提供让 Ubuntu 可以使用的 deb 包，你又不愿从源代码编译。但假如软件提供有 rpm 包的话，我们也是可以在 Ubuntu 中安装的。