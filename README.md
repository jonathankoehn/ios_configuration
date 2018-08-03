# ios_configuration

Configuration file to connect and disconnect a VPN depending on the wifi SSID or interface type (WiFi/cellular).

iOS automatically connects and if necessary reconnects to the VPN, but there is no guarantee all traffic is tunneled.
If the VPN setup fails (some wifis may intentionally block it), the device will use the network without VPN connection.

##### Creation of the configuration
The basic file can and should be created using [Apple Configurator 2](https://support.apple.com/de-de/apple-configurator). The lines can be pastet inside the following XML-element:

```xml
<plist version="1.0">
<dict>
  <key>PayloadContent</key>
  <array>
    <dict>
      <key>IPSec</key>
      <dict>
      <!-- some lines -->
      <!-- paste here -->
      </dict>
    <!-- some more lines (and closing tags, hopefully) -->
```

##### Install
You can move copy the configuration to your device (e.g. by sending it via AirDrop) and once the profile opens, click `Install`.

##### Uninstall
To remove the configuration, you navigate to `Settings / General / Profiles / <your profile name>`  and press `Remove Profile`.

##### Disable temporary
If installed, the connection on demand can be deactivated in menu: `Settings / VPN / <your VPN name>` (press the information-symbol on the right) and switch off `Connect on demand`.

##### Note
The configuration as created by Apple Configurator 2 also works in macOS. If you add the lines to apply the on-demand-connection, macOS will not accept the profile.
