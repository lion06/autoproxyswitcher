### Auto Proxy Switcher ###
AutoProxySwitcher **automates your internet proxy change when you move** (home / office). It detects network change and sets the internet proxy according to rules you define.

A good use case is when you want to automatically switch to your company proxy when you detect you're connected to its network, and you want to disable the proxy when you're not (at home for example).

Works with **Internet Explorer**, **Chrome**, and **Firefox** when they're configured to use system proxy settings.

### Requirements ###
  * Microsoft DotNet Framework 4.0
  * Windows 8, Windows 7, Windows XP SP3

## Downloads ##
Latest stable: [AutoProxySwitcher\_1.1.6.msi](http://dl.bintray.com/chleitienne/AutoProxySwitcher/AutoProxySwitcher_1.1.6.msi)

For details, older versions or beta, see [Download](Download.md).

### Features ###
  * Detects network change (lan connexion, wifi connexion, disconnection, ...)
  * Baloon alert in system tray when network changes
  * Chooses the proxy based on rules defined in "rules.xml" file. 2 kind of rules are handled:
    * Network mask matching (example: network has mask 10.0.0.0/8)
    * DNS address rule matching (example: DNS is 192.168.0.254)
  * 3 kinds of proxy can be configured:
    * Standard proxy
    * PAC File
    * No proxy (direct connexion)
  * English application
  * Internally uses documented Windows API to switch proxy (no black magic)
  * MSI Setup (Build with WIX)

### Configuration ###
See [ConfigurationFile](ConfigurationFile.md).