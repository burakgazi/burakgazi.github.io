### How to setup openVPN client config for specific ip 1
If you want to use OpenVPN just for specific ips here is how :

in .ovpn file add the following :
    
     #don't route all traaffic
     route-nopull
     # redirect the Intranet network via the VPN
     route 172.1.0.0 255.255.0.0

Here is the breakdown:

     route-nopull
This line ensures that you do not pull route config from vpn

    route 172.1.0.0 255.255.0.0
    
    
This line you tell to route all traffic for any ip starting with 172.1. to go through VPN.

if you were to set subnet to 255.255.255.0, that will route all traffic for any ip starting with 172.1.0. to go through VPN.


### Forever with --debug option in config
To use forever config file and enable debug mode for node app here is a sample forever.json file 

     [{
        "uid": "app1",
        "append": true,
        "watch": false,
        "script": "server.js",
        "sourceDir": "/home/user/app1",
        "command": "node --debug=5800"
    }, {
        "uid": "app2",
        "append": true,
        "watch": false,
        "script": "bin/www",
        "sourceDir": "/home/user/app2",
        "command": "node --debug=5801"
       }

in breakdown:
when you give "command", it uses that command to execute your script that you give in "script".
After setting up we can execute the command
   
     forever forever.json

our both apps will be started by forever, and app1 will be listening on port:5800 for debug and app2 in port : 5802

### About me 
 Self-thought programmer since 2010. Started with c++, used .NET C# for several years. For the past year(2016) fall in love with node.js .

You can contact me
 
[burak@gazi.co] (mailto:burak@gazi.co)

[github.com/burakgazi](https://github.com/burakgazi) 

[twitter.com/_burakgazi](http://www.twitter.com/_burakgazi)
 
[gazi.co](https://www.gazi.co)
