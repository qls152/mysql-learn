# 利用gdb调试mysql

可参考[利用gdb调试mysql](https://cloud.tencent.com/developer/article/1693422)

在调试mysql时，gdb会出现如下错误

> 通过gdb 调试mysql出现无法attach相应进程

具体解法可参考：[How to solve "ptrace operation not permitted" when trying to attach GDB to a process?](https://stackoverflow.com/questions/19215177/how-to-solve-ptrace-operation-not-permitted-when-trying-to-attach-gdb-to-a-pro)

gdb attach成功后，会出现

![](https://img-blog.csdnimg.cn/96239a3459874447bdbe072c5fb9c9b6.png)

 解决方案可参考: [gdb: Cannot find new threads: generic error after system update](https://stackoverflow.com/questions/10840621/gdb-cannot-find-new-threads-generic-error-after-system-update)

 也即设置

 ```c++
 set debug libthread-db 1
 ```