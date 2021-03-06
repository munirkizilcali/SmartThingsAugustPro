# SmartThings August Smart Lock Pro Z-Wave Device handler with DoorSense™

```diff
- SEE INSTALL INSTRUCTIONS
```

Z-Wave device handle for August Pro Smart Lock device handler with DoorSense™.

Due to limitations (recognize contact sensor in automation and displaying information using tiles) this device handler creates a child contact sensor (based on new [child contact sensor device]( https://github.com/SmartThingsCommunity/SmartThingsPublic/blob/master/devicetypes/smartthings/child-contact-sensor.src/child-contact-sensor.groovy))

![Devices interfaces - New app vs Old App](images/screenshots/lock_and_child_device_new_vs_old_app.png)
**Devices interfaces - New app vs Old App**


### Why use it?

You should use this device handler if you have a August Lock Pro and you want to use DoorSense™ in automations with no need to have an august connect acting as a bridge (see Validation scenario)

### Validation scenario 
This device handler was tested using Samsung Connect Home Pro (Smartthings V2 Hub) with Firmware version	000.027.00010 in a set up with +10 z-wave devices.

August Smart Lock Pro was connected to both, Smartthings via Z-wave and August Doorbell as a wifi bridge (Wi-Fi bridge is not necessary to use this device handler). No issues were detected when tests were made from different channels (Bluetooth, Wi-Fi bridge or z-wave commands). All three interfaces are able to update status properly.

August Smart Lock Pro firmware was 1.12.2-1.59.0.


![Automation in new app using Lock vs Child contact device](images/screenshots/automation_in_new_app_lock_vs_child_device.png)
**Automation in new app using Lock vs Child contact device**


### Known issues
- Responsiveness to update child device using new app
- Delays to execute commands using new app (1 to 3 seconds)
- Any update to the device handler makes the DoorSense™ unresponsive during the development phase. The reason for it is unknown. When updating the device handler, delete it and create a new one to avoid this issue. This issue somehow affects new installations using github integration

### Install Instructions

Follow [Smartthings Git Hub Integration Guide](https://docs.smartthings.com/en/latest/tools-and-ide/github-integration.html), using user rafaelborja and repository SmartThingsAugustPro.

FIXED: ~~**Due to an unknown issue installation using GitHub is making the device handler unresponsive to events. Please create the [august-lock-pro-zwave-lock-with-doorsense device handler]( devicetypes/rafaelborja/august-lock-pro-zwave-lock-with-doorsense.src/august-lock-pro-zwave-lock-with-doorsense.groovy) source code by following the instructions bellow**~~

**Developer note: Please feel free to try Smartthings Git Hub Integration and validite if this issue is specific to my installation.**

You can also create create a new decive handler from code copying and pasting [child-contact-sensor device handler](devicetypes/rafaelborja/child-contact-sensor.src/child-contact-sensor.groovy) and [child-contact-sensor device handler]( devicetypes/rafaelborja/august-lock-pro-zwave-lock-with-doorsense.src/august-lock-pro-zwave-lock-with-doorsense.groovy) source code
### FAQ
#### Why a child door sensor?
Due to a bug in Smartthings, only a child device can be used on standard automation app.

### Contributions
Please feel free to contribute with suggestions forks, and **pull requests** at https://github.com/rafaelborja/SmartThingsAugustPro
