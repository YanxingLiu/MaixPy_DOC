SPI 的使用
=========

关于 SPI 详细介绍请参考[SPI-API 文档](../../api_reference/machine/spi.md).

## 使用方法

* 从 machine 导入 SPI 模块

```python
from machine import SPI
```

* 配置使用到的 pin 脚为片选 GPIO 功能和 SPI 功能.

```python
fm.register(25,fm.fpioa.GPIOHS10, force=True)#cs
cs = GPIO(GPIO.GPIOHS10, GPIO.OUT)

fm.register(28,fm.fpioa.SPI1_D0, force=True)#mosi
fm.register(26,fm.fpioa.SPI1_D1, force=True)#miso
fm.register(27,fm.fpioa.SPI1_SCLK, force=True)#sclk
```

* 创建 SPI 对象

```python
spi1 = SPI(SPI.SPI1, mode=SPI.MODE_MASTER, baudrate=10000000, polarity=0, phase=0, bits=8, firstbit=SPI.MSB)
```

* 使用片选 GPIO 选中从机, 通过 SPI 读写数据

```python
cs.value(0)
spi1.write_readinto(w, r)
cs.value(1)
```

## 示例

选中片选 GPIO 对应从机并收发数据

```python
from machine import SPI
from fpioa_manager import fm
from Maix import GPIO

m.register(25,fm.fpioa.GPIOHS10, force=True)#cs
cs = GPIO(GPIO.GPIOHS10, GPIO.OUT)

fm.register(28,fm.fpioa.SPI1_D0, force=True)#mosi
fm.register(26,fm.fpioa.SPI1_D1, force=True)#miso
fm.register(27,fm.fpioa.SPI1_SCLK, force=True)#sclk

spi1 = SPI(SPI.SPI1, mode=SPI.MODE_MASTER, baudrate=10000000, polarity=0, phase=0, bits=8, firstbit=SPI.MSB)

w = b'\xFF'
r = bytearray(1)

cs.value(0)
print(spi1.write_readinto(w, r))
cs.value(1)
```
