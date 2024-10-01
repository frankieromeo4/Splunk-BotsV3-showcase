# Splunk-BotsV3-showcase
index="botsv3" sourcetype="stream:ip"
I wanted to start this search off with taking a look at some src_ip
![Screenshot](https://i.imgur.com/4I1HBLt.jpg)

index="botsv3" sourcetype="stream:ip" (src_mac=* AND dest_mac=*)
|table _time src_ip src_mac dest_ip dest_mac

With the table function as you can see in the picture list out some of the keys things i want to see and leaves the rest out.  (src_mac=* AND dest_mac=*) just makes sure it only shows those with values in it.
![Description](https://i.imgur.com/5mBrMNY.png)

index="botsv3" sourcetype="stream:ip" (src_mac=* AND dest_mac=*)
|table _time src_ip src_mac dest_ip dest_mac
|stats count by src_ip src_mac 
|sort - count 
|head 10

Here instead of seeing multiple duplicate ip addressses it puts each them in a counter and lists them from greatest to least. The head feature allows you to list a certain amount, with my search i listed the top 10.
![Description](https://i.imgur.com/z3UiB20.png)


Now when looking at whos communicating over your network Splunk has a useful tool in the search query called Iplocation, as you can see from the screenshot, Region as well as the Country as been added to our search table.
![Desktop Screenshot](https://i.imgur.com/pyTvog1.png)

index="botsv3" sourcetype="stream:ip" (src_mac=* AND dest_mac=*) 
|stats latest(_time) as _time count by src_ip src_mac 
|sort - count 
|iplocation src_ip 
|search Country=* 
|head 10 
|table _time src_ip src_mac count Country

Now by cleaning up the search a little I moved the Table function to the bottom, by doing this, it got rid of some of the collums we didnt need that the iplocation provided such as the lon. and lat.

![Desktop Shot with GeForce](https://i.imgur.com/xY6UbIv.png)


Now the we got our search exactly where we want it, we can save our search as a macro, which allows us to not have to waste time on that extensive search in the future. For this example all we have to type next time is 'top_10_source_ip'. If used for another data saet you will have to change some of the field names but at least you have the outline.
![Desktop Shot with GeForce](https://i.imgur.com/NTVBGTv.png)

Setting up alerts for specfic events youd like to be notified on.
![Desktop Shot with GeForce](https://i.imgur.com/O4E7Zhv.png)

Now that we created our search we can use that to create us a dashbord that we can come back to check on.
![Desktop Shot with GeForce](https://i.imgur.com/zT287rQ.png)

With the dashboard we can create tokens for our collums in the table
![Desktop Shot with GeForce](https://i.imgur.com/D4Gsaa3.png)

index="botsv3" sourcetype="stream:ip" (src_mac=* AND dest_mac=*) 
|stats latest(_time) as _time count by src_ip src_mac 
|sort - count 
|iplocation src_ip 
|search Country=* 
|head 10 
|table _time src_ip src_mac count Country




