# Network-Automation
#Add DHCP Pool to 2 Switches. Python 2.7.0

from netmiko import ConnectHandler,redispatch

SW01 = {
'device_type' : 'cisco_ios',
'ip' : '192.168.238.42',
'username' : 'cisco',
'password' : 'cisco123',
}

switches = [SW01]
for routerslist in routers :
   net_connect = ConnectHandler(**routerslist)
   config_commands = ['ip dhcp pool DATA01', 'network 80.80.80.0 255.255.255.0', 'default-route 80.80.80.1']
   output = net_connect.send_config_set(config_commands)
   print output

SW2 = {
'device_type' : 'cisco_ios',
'ip' : '192.168.238.44',
'username' : 'dhari',
'password' : 'cisco123',
}

switches = [SW02]
for routerslist in routers :
   net_connect = ConnectHandler(**routerslist)
   config_commands = ['ip dhcp pool DATA02', 'network 90.90.90.0 255.255.255.0', 'default-route 90.90.90.1']
   output = net_connect.send_config_set(config_commands)
   print output
