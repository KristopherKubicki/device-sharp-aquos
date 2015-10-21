# Sharp Aquos Device Type
This is a device type for the Sharp Aquos integration to SmartThings.  I believe it actually works with almost all Sharp TV models manufacturered since 2010. 

<img src='http://ecx.images-amazon.com/images/I/81NwfXtTSyL._SX522_.jpg'>

I loosely based this on <a href='https://github.com/halkeye/sharp.aquos.devicetype.groovy'>Gavin Mogan's Sharp Remote</a>.  Most of the commands I found from a <a href='http://snpi.dell.com/sna/manuals/A1534250.pdf'>Sharp manual</a>.

If you wish to programmatically access this device, it should accept most of the standard capabilities.  However,  I also added a capability and command that I am trying to get SmartThings to accept: inputSelect().  If you would like to switch inputs to input 1, for example, you would send inputSelect(1)

##Potential Bugs
SmartThings does not have the ability to parse return values from the Sharp console.  Thus, the state of the device is kept internal to the SmartThings device, and may drift from reality. 

In addition, you can only send one command every 8 seconds.  I wrote some blocking code to prevent the device from drifting quickly, but if you send more than 3 commands in a 20 second window you will definitely drift. 

I had to hardcode the inputs you'd like to select on line 92.  I only use input "1" and "2".  You'll have to update this for your own taste, as SmartThings will not let us pick an array from device preference()

As a last note, if you want to increase the reliability of the device, remove the login and password from your Sharp Network TV settings.

##License 
Copyright (c) 2015, Kristopher Kubicki
All rights reserved.
