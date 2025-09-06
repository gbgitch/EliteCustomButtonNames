---
typora-root-url: ./
---

# Custom Button Labels for Elite Dangerous

<img src="docs\images\Settings Compared.png" alt="Settings Compared" style="zoom:50%;" />

What sorcery is this? None really, I just populated a couple of XML files in my Bindings folder according to Frontier's documentation. You can freely name all the buttons and axes, for example to distinguish the throttle from the stick as above, and a variety of icons are available. The best part is that the names are shown not just in the Settings panels, but everywhere in-game:

Pre-flight

<img src="/docs/images/Pre-Flight.png" alt="Pre-Flight" style="zoom:75%;" />

Standard Cam

<img src="/docs/images/Standard Cam.png" alt="Standard Cam" style="zoom:75%;" />

Free Cam

<img src="/docs/images/Free Cam.png" alt="Free Cam" style="zoom:75%;" />

Full Spectrum Scanner

<img src="/docs/images/FSS.png" alt="FSS" style="zoom:75%;" />

FSS Help Screen

<img src="/docs/images/FSS Help.png" alt="FSS Help" style="zoom:75%;" />



## Getting started

First navigate to the game's `ControlSchemes`  folder. By default this is at `%LocalAppData%\Frontier_Developments\Products\elite-dangerous-odyssey-64\ControlSchemes`.

Inside you will find a folder called `DeviceButtonMaps` and in it is a `Readme.txt` file plus a couple of sample button map files. Note however that we don't want to change anything in here because any changes will be clobbered by the next game update. Still the readme is very useful as it lists all the icons that are available.

Instead you want to go to your Bindings folder, which is at `%LocalAppData%\Frontier Developments\Elite Dangerous\Options\Bindings`. If you have been playing for any length of time you probably know the importance of keeping a backup of this folder. In this Git repo, go to `.\files\INTO Bindings` and copy the `DeviceButtonMaps` folder from there to your own Bindings folder. That's it, all done. 

At the time of writing I include:

- `Generic.buttonMap`, to act as a starting point for your own customization - it has every button and axis defined
- `T16000MTHROTTLE.buttonMap` for the Thrustmaster TWCS throttle
- `231D0200.buttonMap`for the VKB Gladiator NXT Premium Right stick

As Frontier's readme notes, you can edit and save these button maps while the game is running to experiment with how different names and icons look. Just go into Options->Controls and the game will re-read them.

## Named devices versus VID and PID

For the uninitiated, every USB device has a Vendor ID (VID) and Product ID (PID) - these are 4 hexadecimal digits each. My VKB Gladiator NXT has VID 231D and PID 0200 which is why the button map for it has that name, and so do all the entries for it in any `*.binds` file.

If however the device's VID and PID are listed in `ControlSchemes\DeviceMappings.xml` then the button map can use that name - hence `T16000MTHROTTLE.buttonMap` for the Thrustmaster TWCS throttle.

In their readme, Frontier advise making sure that your device is so listed, but I found that it had some undesirable effects:

1. Your binds file will start using that name instead of the VID and PID, meaning that sites like [EDRefCard](https://edrefcard.info/) won't know what to do with it.
2. The next game update will clobber your changes (I have confirmed this personally). If you forget to reinstate your edits before  launching the game, it won't recognize the custom name on your binds file, won't be able to load it, and may even clobber it too.

It's up to you but personally I like to leave the game's Products directory well alone and put up with the slightly ugly VID+PID naming convention.

Enjoy!



