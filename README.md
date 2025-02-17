# Airscape NodeServer

This is a Polyglot V2 Nodeserver for the ISY 994i to control [Airscape Whole House Fans](https://airscapefans.com/) using the [Gen 2 Controls API](https://blog.airscapefans.com/archives/gen-2-controls-api).  If you don't already own one of these awesome fans, you can not purchase the Gen 2 controller online, you have to call them.

## Information

When you Fan is off and you turn it on by increasing the speed then the nodeserver will watch the status by polling the fan every second to see when the door is done moving and the fan actually turns on.  This way you get immediate feedback because the 'Door Moving' will immediately be set to True, then when the fan actually turns on it will set the speed.

When you use 'Set Speed', it will call speed up or speed down once every second to increase/decrease the speed until it sees the speed you requeste.

For all other status changes for Speed Down, Speed Up, or Off, you will see the ISY status change right away since the Fan API returns the proper status on each command.

By default the 'Debug Level' on the Controller is set to Debug.  Please leave it this way until you feel the Nodeserver is stable, then change it to Warning which will log much less data to your machine.

## Installation

- Download from the Nodeservers -> Nodeserver Store
- Install from the Nodeservers -> AddNode Server
- Add the info for your fan in the NodeServer configuration page
- Restart the Nodeserver

## Requirements

- ISY Firmware running the latest 5.x Firmware
- A machine running the [Polyglot V2](https://github.com/UniversalDevicesInc/polyglot-v2/blob/master/README.md)

## Issues

[Git Hub Issue Tracker](https://github.com/jimboca/udi-poly-airscape/issues)

## Release Notes

- 2.0.8: 10/24/2019
  - Send heartbeat on startup
- 2.0.7: 10/22/2019
  - Modify speed range from 0-9 to 0-10, Thanks @BillB66
- 2.0.6: 04/23/2019
  - Set Controller default ST=1 as it should be.
- 2.0.5: 04/22/2019
  - Add timeout in watch_door for 60 seconds
  - [Don't upload profile on every restart, add version checking](https://github.com/jimboca/udi-poly-airscape/issues/2)
- 2.0.4: 04/21/2019
  - Added interlock 1 & 2, although I don't have the equipment yet, so can't completely test
  - Fixed Timer to show correctly
  - Cleaned up code.
- 2.0.3: 04/18/2019
  - Add missing requests to requirements.txt
  - Make sure node address is lowercase and <= 14 characters
  - Change default polling to 5 seconds
- 2.0.2: 04/17/2019
  - Set Speed works
  - Can reference everything in Programs
- 2.0.1:
  - When doorinprocess it watches the status in a tight loop.
- 2.0.0: 04/16/2019
  - Initial Release
