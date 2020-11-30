开机自启动脚本
=======

系统会在 `/flash` 或者 `/sd`(优先) 目录创建 `boot.py` 文件和`main.py`， 开机会自动先执行`boot.py`，然后执行`main.py`（如果检测到SD卡则执行SD卡里的）， 编辑这两个脚本的内容即可实现开机自启，请不要在`boot.py`里面写死循环（While True）程序，如果写了就擦除固件吧。

- boot.py 主要用于配置硬件，只配置一次即可。
- main.py 可以用于主要的运行的程序。

对应的具体执行的[代码在此](https://github.com/sipeed/MaixPy/blob/972059491227ece63fbfc2cd0e78fe13ee78427d/components/micropython/port/src/maixpy_main.c#L586-L595)，有疑问就直接看源码。

注意:
    * Micro SD 卡应该被格式化为 FAT(FAT32) 文件系统
    * FAT 格式的储存卡会被挂载到 `/sd`, 内部 Flash 中的 SPIFFS 会被挂载到`/flash`

