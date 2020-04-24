## 1. Introduction

**Domoticz**是一个轻量级的智能家居系统 ，通过它你可以监测和控制各种设备，包括灯和开关以及各种传感器、仪表比如：温度、雨滴、风速、紫外线(UV)辐射、用电发电、燃气流量、用水量等等。 还可以向任一移动设备发送通知或警告。
Our Wi-Fi energy meter (WEM3080/WEM3080T) can be integrated with Domoticz system.


## 2. Domoticz settings

 

Step 1, open /domoticz/scripts/lua_parsers, then add the flowing code to iammeter.lua flow(WEM3080):

```lua
-- Retrieve the request content
s = request['content'];

-- Update some devices (index are here for this example)

local voltage = domoticz_applyJsonPath(s, '.Data[0]')
local current = domoticz_applyJsonPath(s, '.Data[1]')
local power = domoticz_applyJsonPath(s, '.Data[2]')
local importenergy = domoticz_applyJsonPath(s, '.Data[3]')
local exportgrid = domoticz_applyJsonPath(s, '.Data[4]')

domoticz_updateDevice(1, 0, voltage)
domoticz_updateDevice(2, 0, current)
domoticz_updateDevice(3, 0, power)
domoticz_updateDevice(4, 0, importenergy)
domoticz_updateDevice(5, 0, exportgrid)
```

add the flowing code to iammetert.lua  flow (WEM3080T):

```lua
-- Retrieve the request content
s = request['content'];

-- Update some devices (index are here for this example)

local voltage_a = domoticz_applyJsonPath(s, '.Datas[0][0]')
local current_a = domoticz_applyJsonPath(s, '.Datas[0][1]')
local power_a = domoticz_applyJsonPath(s, '.Datas[0][2]')
local importenergy_a = domoticz_applyJsonPath(s, '.Datas[0][3]')
local exportgrid_a = domoticz_applyJsonPath(s, '.Datas[0][4]')

local voltage_b = domoticz_applyJsonPath(s, '.Datas[1][0]')
local current_b = domoticz_applyJsonPath(s, '.Datas[1][1]')
local power_b = domoticz_applyJsonPath(s, '.Datas[1][2]')
local importenergy_b = domoticz_applyJsonPath(s, '.Datas[1][3]')
local exportgrid_b = domoticz_applyJsonPath(s, '.Datas[1][4]')

local voltage_c = domoticz_applyJsonPath(s, '.Datas[2][0]')
local current_c = domoticz_applyJsonPath(s, '.Datas[2][1]')
local power_c = domoticz_applyJsonPath(s, '.Datas[2][2]')
local importenergy_c = domoticz_applyJsonPath(s, '.Datas[2][3]')
local exportgrid_c = domoticz_applyJsonPath(s, '.Datas[2][4]')

domoticz_updateDevice(6, 0, voltage_a)
domoticz_updateDevice(7, 0, current_a)
domoticz_updateDevice(8, 0, power_a)
domoticz_updateDevice(9, 0, importenergy_a)
domoticz_updateDevice(10, 0, exportgrid_a)

domoticz_updateDevice(11, 0, voltage_b)
domoticz_updateDevice(12, 0, current_b)
domoticz_updateDevice(13, 0, power_b)
domoticz_updateDevice(14, 0, importenergy_b)
domoticz_updateDevice(15, 0, exportgrid_b)

domoticz_updateDevice(16, 0, voltage_c)
domoticz_updateDevice(17, 0, current_c)
domoticz_updateDevice(18, 0, power_c)
domoticz_updateDevice(19, 0, importenergy_c)
domoticz_updateDevice(20, 0, exportgrid_c)
```

Step 2, open domoticz -- Setup -- Hardware:

![image-20200424102101934](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424102101934.png)

Set by the flow picture ,then Click Add (WEM3080):

![image-20200424103235543](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424103235543.png)

if your meter is  WEM3080T:

![image-20200424105359154](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424105359154.png)

Click  Create Virtual Sensors (WEM3080)

![image-20200424103526313](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424103526313.png)

![image-20200424104058751](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424104058751.png)

![image-20200424104453746](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424104453746.png)

![image-20200424104522508](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424104522508.png)

![image-20200424104612626](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424104612626.png)

![image-20200424104643129](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424104643129.png)

Click  Create Virtual Sensors (WEM3080T):

![image-20200424105533376](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424105533376.png)

 ![image-20200424105615469](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424105615469.png)

![image-20200424105902645](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424105902645.png)

![image-20200424105945460](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424105945460.png)

![image-20200424110023555](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110023555.png)

![image-20200424110051725](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110051725.png)

![image-20200424110226115](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110226115.png)

![image-20200424110257635](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110257635.png)

![image-20200424110359531](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110359531.png)

![image-20200424110424953](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110424953.png)

![image-20200424110450768](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110450768.png)

![image-20200424110535751](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110535751.png)

![image-20200424110608628](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110608628.png)

![image-20200424110630817](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110630817.png)

![image-20200424110655065](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110655065.png)

![image-20200424110720184](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424110720184.png)



Step 3,then click Setup -- Devices , you can see the datas  (WEM3080):

![image-20200424111105971](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424111105971.png)

Step 4, notes, iammeter.lua/iammetert.lua domoticz_updateDevice first number must Corresponding to Idx:

![image-20200424111710312](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424111710312.png)

![image-20200424111847692](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424111847692.png)



## 3.Domoticz  display

Open the Utility:

![image-20200424112325345](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/openhabimage-20200424112325345.png)




## 4.Reference

1. [API reference](https://www.iammeter.com/doc/iammeter/integrate-with-PVOutput.html)

2. [integrated in third-party server](https://www.iammeter.com/doc/iammeter/integrate-with-thirdparty-server.html)

3. [FAQ](https://www.iammeter.com/doc/iammeter/FAQ.html)












