									LiteOs搭建

步骤一：拷贝sdk包到linux系统上，解压，进入root模式下进行编译

步骤二：先拷贝.config文件：cp configs/hi3518ev_debug_fast_deconfig .config文件

步骤三：先编译osdrv 发现一堆错误 找到osdrv中的readme.xx文件把需要的安装包放进去，编译过去

步骤四：进入Liteos ，解压liteos.tgz并进入，然后拷贝.config ，然后make

步骤五：在外围执行 make mini boot 编译生成uboot镜像 ，即 opensource/uboot/u-boot-2016.11下生成的u-boot-hi3516ev200.bin即为可用的u-boot镜像。

步骤六：编译drv 可能会缺少文件 正常能跑过的

步骤七：编译ndk,在最外面编译ndk就行

步骤八：编译middleware,现执行make prepare保证所需要版本的补丁拷贝到改目录，make 发现缺少几个压缩包，自己下载放进去就OK。

步骤九：reference编译最后编译 ，make reference  发现有错误   ，make clean make reference_distclean

需要拷贝提示错误的几个文件进去simsunb_16*32.dat 还在wife下的文件包两个错误拷贝进去就能通过了。

![](C:\Users\12798064\Desktop\Home\MY\bug\LiteOs.png)

需要的安装包大概有这些（可能不全）：

![](C:\Users\12798064\Desktop\Home\MY\bug\安装包.png)