# \[Win]wmic



# Windows系统中CMD wmic查看硬盘、内存、CPU、BIOS、网卡等信息

<https://www.cnblogs.com/fusheng11711/p/11959106.html#查看磁盘剩余空间>







示例：查看磁盘空间：wmic LogicalDisk where "Caption='D:'" get FreeSpace,Size /value
