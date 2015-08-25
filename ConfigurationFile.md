# Introduction #

The configuration file is `AutoProxySwitcher\rules.xml`, stored in `<CommonApplicationData>` folder.

Depending on your system, `<CommonApplicationData>` is located at different places:
  * XP : %ALLUSERSPROFILE%\Application Data
  * Win7 & 8: %SYSTEMDRIVE%\ProgramData

It contains a list of configurations : network detection rules, and a proxy configuration.

Whenever a change in your computer configuration is detected, the proxy is changed based on the rules you gave.

# Sample file #

This sample file contains 3 configurations.

The first, "At work", tels the system to use the given proxy.pac file when network address is "10.0.0.0/8" or when DNS ip is "10.1.0.254".

The second configuration, "At client site", tels the system to use the proxy "proxy.local.lan" on port 3128, when network ip address "192.168.1.0/24".

The third configuration, "Default config", is used when none of the previous configurations match (for example, at home). In this case, the proxy is disabled.

```
<?xml version="1.0" encoding="utf-8" ?>
<Networks>
  <!-- First configuration -->
  <Network name="At work">
    <Proxy type="PacFile" url="http://proxy.local.lan/proxy.pac" />
    <Rules>
      <Subnet ip="10.0.0.0/8" />
      <DNS ip="10.1.0.254"/>
    </Rules>
  </Network>
  
  <!-- Second configuration -->
  <Network name="At client site">
    <Proxy type="Standard" url="http://proxy.local.lan:3128" />
    <Command>program.exe</Command>
    <Rules>
      <Subnet ip="192.168.1.0/24" />
    </Rules>
  </Network>

  <!-- Default -->
  <Network name="Default Config">
    <Proxy type="None" />
  </Network>
</Networks>
```

# Proxy configurations available #

## Standard proxy ##
```
  <Proxy url="http://proxy.local.lan:3128" exceptions="127.0.0.1;192.168.0.2" bypasslocal="false" />
```
**Exceptions are available since 1.1.1-beta**.

When the "exceptions" attribute is not present, exceptions are left untouched.

When the "exceptions" attribute is set to "" (blank), exceptions are cleared.

**Bypass local addresses is optional and is available since 1.1.2-beta**.

## Proxy PAC file ##
```
  <Proxy type="PacFile" url="[pacfile url]" />
```

## No proxy (= disabling proxy) ##
```
  <Proxy type="None" />
```
This disables the proxy.

# Command action #
The command action allows you to run a shell command when the network is detected. The command is run through (CMD.EXE /C).

# Available rules #

## Subnet address ##
```
  <Subnet ip="192.168.1.0/24" />
```
The subnet address (or network address) should exactly match the given value.

## DNS address ##
```
  <DNS ip="10.1.0.254" />
```
One of the DNS of the network should exactly match the given address.

## Ping machine ##
**Available since 1.1 beta**
```
  <Ping ip="[machine name or ip]" />
```
The given machine is pingable.

The ping test is only done at application startup or when the network configuration change

## Interface name ##
**Available since 1.1 beta**
```
  <Interface name="Wi-fi" />
```
The interface name matches the given value.

## Logic rules (And, Or, Not) ##
**Available since 1.1.6**

By default, an OR logic is applied to the rules you write.
But you can tell the engine to apply an And logic when needed, and also use the Not expression.

For example, if you want to match a subnet of "10.0.1.0/24" or "192.168.1.0/24" AND a DNS address of "10.0.1.235", you can write the rule this way:
```
  <Rules>
     <And>
       <Or>
         <Subnet ip="10.0.1.0/24" />
         <Subnet ip="192.168.1.0/24" />
       </Or>
       <DNS ip="10.0.1.235" />
     </And>
   </Rules>
```

# Log File #
Since 1.1 beta, the log file is located in %APPDATA%\AutoProxySwitcher folder.