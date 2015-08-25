## Latest version ##

### 1.1.6 ###
[AutoProxySwitcher\_1.1.6.msi](http://dl.bintray.com/chleitienne/AutoProxySwitcher/AutoProxySwitcher_1.1.6.msi)
  * Automatically reload configuration file on change
  * Ability to start a shell command when a network is detected (via cmd.exe /C)
  * New configuration shortcuts in systray menu
  * Avoid crash when pinging unresolved DNS names

## Previous versions ##
### 1.1.5 Beta version ###
[AutoProxySwitcher\_1.1.5-beta.msi](https://drive.google.com/file/d/0By8ulHaDubfrTDFQN2pTTndpOFE/edit?usp=sharing)
  * Bug fix: when bypassing proxy for local addresses, correctly write the bypass string sent to wininet.

### 1.1.4 Beta version ###
[AutoProxySwitcher\_1.1.4-beta.msi](https://drive.google.com/file/d/0By8ulHaDubfrcktFRUZpcG5iOUk/edit?usp=sharing)
  * Bug fix: use the right API to notify IE when proxy changes

### 1.1.3 Beta version ###
[AutoProxySwitcher\_1.1.3-beta.msi](https://drive.google.com/file/d/0By8ulHaDubfrZnlEYkNqNC1YQXc/edit?usp=sharing)
  * Bug fix: notify Internet Explorer of each proxy change

### 1.1.2 Beta version ###
[AutoProxySwitcher\_1.1.2-beta.msi](https://drive.google.com/file/d/0By8ulHaDubfrcF9nT0ktNnBvam8/edit?usp=sharing)
  * New feature: added "bypasslocal" attribute to standard Proxy node to bypass proxy for local addresses (ex: `<Proxy url="..." bypasslocal="true" />`
  * Better handle errors when loading configuration. Error is displayed on status window

### 1.1.1 Beta version ###
[AutoProxySwitcher\_1.1.1-beta.msi](https://drive.google.com/file/d/0By8ulHaDubfrYXhoWnJqMXJyb0U/edit?usp=sharing)
  * New feature: ability to test if a machine is available (ex: `<Ping ip="127.0.0.1" />`)
  * New feature: ability to nest and combine tests in rules (ex: `<And></And>, <Or></Or>, <Not></Not>`)
  * New feature: ability to set or clear proxy exceptions (ex: `<Proxy url="..." exceptions="..." />`)
  * New feature: ability to test an interface name with regular expressions (ex: `<Interface name="Wi.?Fi" />`)
  * Updated interface
  * Only take "active" interfaces into account
  * Do not remove config folder when installing newer version or uninstalling
  * Moved log file to folder `%APPDATA%\AutoProxySwitcher`

### 1.0.15 ###
[AutoProxySwitcher\_1.0.15.0.msi](https://docs.google.com/file/d/0By8ulHaDubfrY0dQTDlsVTBBZW8/edit?usp=sharing)
  * Fixed network range computing
  * Slight interface update

### 1.0.14 ###
[AutoProxySwitcher\_1.0.14.0\_beta.msi](https://docs.google.com/file/d/0By8ulHaDubfrTDNGYkIzbGVWdzQ/edit?usp=sharing)
  * Added logging (logfile.txt)
  * Better rules and network matching algorithm
  * Updated sample rules with comments