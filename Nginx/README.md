#Nginx VS
为方便查看和调试nginx源码,所以将ngx的代码搞成可直接用VS编译的版本,需要用Visual Studio2015编译.  
调试前需要将env中的文件解压到nginx.exe所在目录  
基于Mainline的[Nginx 1.11.0](https://github.com/nginx/nginx/tree/release-1.11.0)修改.


问题:
1. nginx是多进程模型,直接调试只能调试主进程,要调试子进程需要手动附加到指定进程,此时子进程的一部分初始化代码已经运行过了.一种比较Hack的方式是在main函数开头加assert(false)等出错然后附加