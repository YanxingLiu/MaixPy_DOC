---
title: SP_WEATHER 的使用
keywords: maixpy, k210, AIOT, 边缘计算
desc: maixpy doc: SP_WEATHER 的使用
---


<img src="../../../assets/hardware/module_spmod/sp_weather.png"/>

SP_Weather 气象模块拥有两颗传感器, 磁性传感器 QMC7983, 这是一个内置灵敏度补偿与 NTC 的三轴磁性传感器, 具有出色的动态范围和精度以及超低的功耗. 温湿度气压传感器 BME280, 能够同时测量温湿度以及气压.

## 参数

### 磁性传感器 QMC7983

* 磁感应量程: ±30 高斯
* 精度: 每 LSB 1mG
* RMS 噪声: 2mG
* 对外接口: I2C, 默认地址 0x2C,可通过选择电阻调节
* 工作电压: 2.6V~3.6V
* 工作温度: -30°C ~ 85°C

### 温湿度气压传感器 BME280

* 温度传感器的关键参数
  * 测量范围: -40°C~85
  * 精度:
  
|范围(°C)|误差值(°C)|
|:----:|:----:|
|25|±0.5|
|0~65|±1.0|
|-20~0|±1.25|
|-40~-20|±1.5|

* 湿度传感器的关键参数
  * 响应时间(τ63%): 1 s
  * 精度公差: ±3% 相对湿度
  * 磁滞: ±1% 相对湿度
* 气压传感器的关键参数
  * RMS 噪声: 0.2Pa(相当于 1.7cm)
  * 偏移温度系数: ±1.5 Pa/K(相当于 1℃ 温度变化时为 ±12.6cm)
* 对外接口: I2C,默认地址 0x76,可通过选择电阻调节
* 工作电压: 1.71V~3.6V
* 工作温度: -30°C ~ 85°C

模块详细信息请参考[气象模块规格书与数据手册](http://api.dl.sipeed.com/shareURL/MAIX/HDK/sp_mod/sp_weather)

## 使用方法

1. 准备: 已烧录最新固件的开发板, sp_weather 模块.

2. 运行: 连接模块, 修改[示例代码](https://github.com/sipeed/MaixPy_scripts/tree/master/modules/spmod/sp_weather)中 config 包围的配置, 运行后可看到终端打印的磁性传感器和气压温湿度传感器数据

程序如下:

```python
weather=SPWEATHER(i2c=i2c_bus) # create sp_weather
while 1:
    time.sleep_ms(500)
    print(weather.qmc_read_xyz) # QMC7983 read data
    print(weather.bme_values) # BME280 read data

'''output
>>> I2C devices:[44, 118]
0x32
6
(228, 123, 156)
('31.0C', '1017.75hPa', '34.32%')
(235, 130, 185)
('30.75C', '1017.74hPa', '34.31%')
(235, 130, 161)
('30.7C', '1017.82hPa', '34.32%')
'''
```

主要步骤为:

* 创建 SPWEATHE(参数为: I2C 对象).

* 读取磁力传感器数据和温湿度数据.(读取到的数据均为元组)
