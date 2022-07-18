# Apple Input Device Drivers for Windows 10 & 11
Re-packaged official driver support software enabling the native usage of various Apple accessories and peripherals—including keyboards, mice, and trackpads.

## Version
Built with Windows Support version 6.1.7071 (latest version).

## Information
Apple has released drivers enabling the native usage of their proprietary interface and peripheral devices on Microsoft Windows operating systems. 

To protect its users, Apple began requiring their driver downloads to occur through a controlled utility—known as Boot Camp Assistant—available only on macOS to automate the process and prevent the user from accidental misconfiguration of critical system drivers, but this also restricted the accessibility to non-critical and necessary device drivers such as human interface devices. This repository aims to provide access to device drivers in the event that they cannot be acquired via Boot Camp Assistant.

## Compatibility
The drivers listed here are compatible with Windows 10 and 11. Though Apple has not made an official comment on Windows 11 compatibility, testing demonstrates they still function as intended.

Compatible devices include all versions of Apple Magic Mouse, Apple Magic Keyboard, Apple Magic Trackpad, and all Apple proprietary wired keyboards and mice.

## Usage
To install the desired device driver, open the folder name corresponding to the device type, right-click the `.inf` file and choose `Install`. Upon completion you will need to disconnect and reconnect your device.

The Apple Magic Keyboard will require you to install the `.inf` files in both the `AppleKeyboard` and `AppleMagicKeyboard2` folders.

## Settings
### Function Key Reversal
To reverse the function of the `Fn` key, change the following `DWORD (32-bit) Value`s in the Registry Editor from `0` to `1`:

`HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\KeyMagic\OSXFnBehavior`
`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\KeyMagic\OSXFnBehavior`

### Inverted Scrolling
To reverse the direction of the scroll wheel the same way macOS does, change the following `DWORD (32-bit) Value` in the Registry Editor from `0` to `1` and restart your PC:

`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\HID\xxxxx\yyyyy\Device Parameters\FlipFlopWheel`

Let `xxxxx` respresent the device instance ID (this can be found through Device Manager) and `yyyyy` the next (only) available registry key.

### Remapping the `⌘` Key
To make the command key `⌘` function as a control `CTRL` the same way macOS does, you will need to use a utility like [Sharpkeys](https://github.com/randyrants/sharpkeys) or [Microsoft PowerToys](https://github.com/microsoft/PowerToys).

## License
Apple has not provided any software license agreement for the use of its Windows Support Software—only Boot Camp Utility, which provides no specifications on proprietary driver usage. Since no usage license has been explicitly declared, the content here is intended only for those running Windows on a genuine macOS product via Boot Camp but have issues downloading the drivers via Boot Camp Assistant. 

## Resources
[brigadier](https://github.com/timsutton/brigadier) - Utility for downloading Windows Support Software on Windows natively.

[Sharpkeys](https://github.com/randyrants/sharpkeys) and [Microsoft PowerToys](https://github.com/randyrants/sharpkeys) - GitHub utilities that can assist in remapping the `⌘` key to emulate macOS.

Boot Camp Support Software - Versions [5.1.5621](https://support.apple.com/kb/DL1720?locale=en_US) and [4.0.4033](https://support.apple.com/kb/DL1636?locale=en_US) for Windows 7 installs (use [this](https://support.apple.com/en-us/HT205016#tables) table to find out which version you need).

Boot Camp Utility - [Software License Agreement](https://www.apple.com/legal/sla/docs/Boot_Camp_Utility.pdf) (PDF)
