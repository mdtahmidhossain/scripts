### Cisco IOS Device: Basic Operations Guide

#### Introduction

This guide outlines detailed command sequences for basic operations on Cisco IOS devices, essential for networking professionals.

#### Accessing and Configuring the Device

**Initial Access:**
- **Console Access:** Connect using a console cable.
- **Remote Access:** Access remotely via Telnet or SSH.

**Entering Privileged Mode:**
- Access privileged EXEC mode: 
  ```
  enable
  ```

**Global Configuration Mode:**
- Enter global configuration mode: 
  ```
  configure terminal
  ```

**Basic Configuration Commands:**
- Show current configuration: `show running-config`
- Display IOS version/system info: `show version`
- Interface details: `show interfaces`

#### IP Manipulation

**Assigning IP Addresses:**
- Assign an IP to an interface:
  ```
  enable
  configure terminal
  interface GigabitEthernet0/0
  ip address 192.168.1.1 255.255.255.0
  no shutdown
  end
  ```

**Configuring Static Routing:**
- Set a static route:
  ```
  enable
  configure terminal
  ip route 192.168.2.0 255.255.255.0 192.168.1.2
  end
  ```

#### Managing Network Device Status

**Bringing Interfaces Up or Down:**
- Disable an interface:
  ```
  enable
  configure terminal
  interface GigabitEthernet0/0
  shutdown
  end
  ```
- Enable an interface:
  ```
  enable
  configure terminal
  interface GigabitEthernet0/0
  no shutdown
  end
  ```

#### Device Management and Maintenance

**Rebooting the Device:**
- Reboot the device: 
  ```
  enable
  reload
  ```

**Saving Configurations:**
- Save changes:
  ```
  end
  write memory
  ```

**Setting Passwords:**
- Set console password:
  ```
  enable
  configure terminal
  line console 0
  password [PASSWORD]
  login
  end
  ```
- Set VTY password for Telnet/SSH:
  ```
  enable
  configure terminal
  line vty 0 4
  password [PASSWORD]
  login
  end
  ```

#### Basic Troubleshooting Tools

- Check connectivity: `ping 192.168.1.1`
- Trace route: `traceroute 192.168.1.1`
- Show routing table: `show ip route`
- Interface status summary: `show interfaces status`

