# L8 CPU管理的直观想法
> 多进程图像是操作系统的核心图像

## CPU工作原理
CPU是自动取址并执行的计算机硬件
设置`PC`的初值为程序的起始地址
存在IO慢，CPU快的矛盾，CPU不应该长时间闲置
### 并发
- 一个CPU上交替执行多个程序
- 修改`PC`寄存器，保存现场：PCB数据结构(process control block)
### 进程
- 进程：运行中的、动态的程序
- 特点：进程有始终、有走停、要通过保存寄存器来保护现场

!!! tip 考点
    进程（相对于程序而言）的几个特点
