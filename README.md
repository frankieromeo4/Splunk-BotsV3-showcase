# Splunk-BotsV3-showcase
https://imgur.com/desktop-shot-with-geforce-EKcEaoM

https://imgur.com/desktop-shot-with-geforce-fjDK3lM

List out the IAM users that accessed an AWS service (successfully or unsuccessfully) in Frothly’s AWS environment?
index="botsv3" sourcetype=aws:cloudtrail userIdentity.type="IAMUser"
| table userIdentity.userName
| top userIdentity.userName

https://imgur.com/desktop-shot-with-geforce-4nw03FG

https://imgur.com/desktop-shot-with-geforce-FexdaTw

