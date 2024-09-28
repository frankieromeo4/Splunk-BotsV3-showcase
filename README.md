# Splunk-BotsV3-showcase
index="botsv3" sourcetype="stream:ip"
![Screenshot](https://i.imgur.com/4I1HBLt.jpg)

index="botsv3" sourcetype="stream:ip" (src_mac=* AND dest_mac=*)
|table _time src_ip src_mac dest_ip dest_mac
![Description](https://i.imgur.com/5mBrMNY.png)

index="botsv3" sourcetype="stream:ip" (src_mac=* AND dest_mac=*)
|table _time src_ip src_mac dest_ip dest_mac
|stats count by src_ip src_mac 
|sort - count 
|head 10
![Description](https://i.imgur.com/z3UiB20.png)

![Desktop Screenshot](https://i.imgur.com/pyTvog1.png)

index="botsv3" sourcetype="stream:ip" (src_mac=* AND dest_mac=*) 
|stats latest(_time) as _time count by src_ip src_mac 
|sort - count 
|iplocation src_ip 
|search Country=* 
|head 10 
|table _time src_ip src_mac count Country

![Desktop Shot with GeForce](https://i.imgur.com/xY6UbIv.png)

![Desktop Shot with GeForce](https://i.imgur.com/NTVBGTv.png)

![Desktop Shot with GeForce](https://i.imgur.com/O4E7Zhv.png)

![Desktop Shot with GeForce](https://i.imgur.com/zT287rQ.png)

![Desktop Shot with GeForce](https://i.imgur.com/D4Gsaa3.png)

index="botsv3" sourcetype="stream:ip" (src_mac=* AND dest_mac=*) 
|stats latest(_time) as _time count by src_ip src_mac 
|sort - count 
|iplocation src_ip 
|search Country=* 
|head 10 
|table _time src_ip src_mac count Country




