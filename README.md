# Kiwi

Kiwi is an Android application for managing patient health encounters. It uses the [SecugenPlugin] (https://github.com/chrisekelley/SecugenPlugin)
to enable fingerprint scanning for identification. This plugin works with the Secugen Hamster Plus fingerprint scanner.

# Development

This application was built using Cordova. 

To deploy to tablet:

    cordova run android
    
## Updating the Secugen Plugin

Use platforms/android/bakeapp.sh to refresh the plugin when you change it.

## Fingerprint Scanning Service Codes:

- Status Code 0 = Invalid form sent
- Status Code 1 = Success 
- Status Code 2 = Invalid key
- Status Code 3 = Invalid ISO template

## Configuration
    
Change the url and paths in res/values/strings.xml

    <string name="app_name">Kiwi</string>
    <string name="templatePath">/sdcard/Download/fprints/</string>
    <string name="serverUrl">http://somewhere.com/</string>
    <string name="serverUrlFilepath">api/Person/Enroll</string>
    <string name="serverKey">authorizationKey</string>
    <string name="templateFormat">TEMPLATE_FORMAT_ISO19794</string>
    
## Debugging
    
Since the fingerprint scanner uses the device's USB port, you must use wifi debugging. Here are some useful commands:

    adb kill-server      
    adb start-server   
    adb tcpip 5555
    adb shell ip -f inet addr show wlan0  
    adb connect 192.168.0.101
    
    ./installapp.sh
    
The platforms/android/bakeapp.sh script is also useful during development when removing/installing the plugin.

    
    
    
