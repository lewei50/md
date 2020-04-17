# ioBroker-IamMeter



#### 1.ioBroker settings

 

1. 添加parser。

   ![image-20200416170803091](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416170803091.png) 

   ![image-20200416170901638](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416170901638.png)

   ​		 

2. 添加完成后配置parser:(for example your meter IP is 192.168.15.60)

EMW3080/EMW3162:

	Name				URL or file name					RegEx							Item	Type	Unit	Interval
	emw3080_voltage			http://admin:admin@192.168.15.60/monitorjson	\[(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]	0	number	V	60000
	emw3080_current			http://admin:admin@192.168.15.60/monitorjson	\[\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]	0	number	A	60000
	emw3080_power			http://admin:admin@192.168.15.60/monitorjson	\[\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?\]	0	number	W	60000
	emw3080_ImportEnergy		http://admin:admin@192.168.15.60/monitorjson	\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?\]	0	number	kWh	60000
	emw3080_exportgrid		http://admin:admin@192.168.15.60/monitorjson	\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?)\]	0	number	kWh	60000

EMW3080T:	

	Name:	emw3080t_voltage_a			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	V		
	Interval:	60000
	
	Name:	emw3080t_current_a			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	A		
	Interval:	60000
	
	Name:	emw3080t_power_a			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	W		
	Interval:	60000
	
	Name:	emw3080t_ImportEnergy_a			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000
	
	Name:	emw3080t_exportgrid_a			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000
	
	Name:	emw3080t_voltage_b			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	V		
	Interval:	60000
	
	Name:	emw3080t_current_b			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	A		
	Interval:	60000
	
	Name:	emw3080t_power_b			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	W		
	Interval:	60000
	
	Name:	emw3080t_ImportEnergy_b			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000
	
	Name:	emw3080t_exportgrid_b			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000
	
	Name:	emw3080t_voltage_c			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	V		
	Interval:	60000
	
	Name:	emw3080t_current_c			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	A		
	Interval:	60000
	
	Name:	emw3080t_power_c			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	W		
	Interval:	60000
	
	Name:	emw3080t_ImportEnergy_c			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000
	
	Name:	emw3080t_exportgrid_c			
	URL or file name:	http://admin:admin@192.168.15.60/monitorjson	
	RegEx:	\[\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?\],\[\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,\d+\.?\d+?,(\d+\.?\d+?),\d+\.?\d+?,\d+\.?\d+?\]\]
	Item:	0		
	Type:	number	
	Unit:	kWh		
	Interval:	60000



![image-20200417124300352](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200417124102227.png)![image-20200416172701159](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416172701159.png)

​			 

​		 

3. Instances -- parser.0 -- start :

   ![image-20200416171820252](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokeriobrokerimage-20200416171820252.png)

4. Objects -- parser.0: 

   ​	![image-20200416174124401](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416174124401.png) 

 

#### 2.ioBroker display(Visualisation)

 

1. Adapters -- Visualisation -- +.

   ![image-20200416174410099](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416174410099.png) 

   ![image-20200416174936651](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416174936651.png)

   ![image-20200416175115028](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416175115028.png)

2. http://192.168.12.194:8082/vis/edit.html?main#DemoView.

   ![image-20200416180640613](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416180640613.png) 
   
    ![image-20200416181409670](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416181409670.png)
   
   ![image-20200416182221599](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416182221599.png)
   
   ![image-20200416182338712](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416182338712.png)
   
   ![image-20200416182433346](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416182433346.png)
   
   ![image-20200416182524302](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416182524302.png)
   
   ![image-20200416182743074](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416182743074.png)

 ![image-20200416183427695](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416183427695.png)

 ![image-20200416183503571](https://leweidoc.oss-cn-hangzhou.aliyuncs.com/lewei50/img/iammeter/iobrokerimage-20200416183503571.png)

 

 

 

 

 
