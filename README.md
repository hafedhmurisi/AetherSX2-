# AetherSX2 FAQ
## What is it?
AetherSX2 is an emulator of the Sony PlayStation 2(TM) / PS2(TM) console for the Android platform. You can play games which you have dumped from disc on your portable device.


## What are the requirements?
The PS2(TM) is an **extremely** complex piece of hardware, with many very powerful components, even for today. You need a high end device to achieve good performance.

We recommend at least a Snapdragon 845-equivalent device. This means 4 large cores (Cortex-A75 level). If you only have two big cores (e.g. Snapdragon 700 series SoCs, you should not enable multi-threaded VU, and performance will suffer as a result). Devices with Mali or PowerVR GPUs will run the app, but performance will be much lower than Adreno GPUs, and the Vulkan renderer will not be available. This is because they are missing a critical feature (dual-source blending).

If you want to use the app on a slower device, you can try it, but games **will** run slow, especially heavier titles. You can try underclocking the CPU by setting the cycle rate to a negative number, and the cycle skip to a positive number in System settings, but this will cause games to lag internally at best, or crash at worst.

### Expectations.
This is a free app, worked on as a hobby in the developer's free time. At the time of writing, it is in very early stages and missing many useful features, however is usable for playing some games.

It is not going to be perfect, far from it. I will continue to improve it when I have time, but please remember this is not my job, and to have realistic expectations, **especially if you do not have a high end device**.

As it is an early preview, you should save your game regularly in case of crashes.

## Disclaimers.
AetherSX2 should only be used to play games you own and have dumped from disc yourself. To dump your games, you can use a tool such as ImgBurn to create a .iso for the disc, and then copy across it to your device over USB.

PlayStation 2 and PS2 are registered trademarks of Sony Interactive Entertainment Europe Limited and in other regions. This app is not affiliated in any way with Sony Interactive Entertainment.

### The app tells me I need a BIOS.

Yes, you do. A BIOS image **is required** to play games and is not optional. This image should be dumped from your own console, using a homebrew application. There are plenty of guides available online on how to dump your console's BIOS.

### My games are running slow/lagging.
Different games have very different hardware requirements, due to how much they utilized the various components of the console. You can try underclocking the CPU by setting the cycle rate to a negative number, and the cycle skip to a positive number in System settings, but this will cause games to lag internally at best, or crash at worst.

### How to improve performance?
- Make sure fastmem is enabled in System settings.
- Enable Multi-Threaded VU1 in System settings. This will cause lower performance if your device does not have at least three "big" CPU cores.
- Use the Vulkan renderer if you have an Adreno GPU. Note that some games will perform better with OpenGL, and may not render correctly with Vulkan. Mali GPUs are not supported by the Vulkan renderer.
- Underclock the emulated CPU by setting the cycle rate to a negative number, and cycle skip to a positive number in System settings.
- For some games, enabling the Preload Textures and GPU Palette conversion options in Graphics settings can improve performance.
- If the game slows down depending on the camera angle, this may be due to GS downloads, which are very slow on mobile GPUs. You can try disabling hardware readbacks in Graphics options, but this may create some glitches in effects.

### How do I customize the touchscreen controller (position/scale)?
Press the pause or back button while ingame, and tap the controls tab in the top-right corner. You can also add additional buttons for hotkeys here, e.g. fast forward, quick load/save, etc.

### The app opens in portrait mode, how do I change it to landscape?
Turn your device around if you have auto rotation enabled. You can also force it to always use landscape in the first page of App Settings.

### My Bluetooth controller isn't working.
Currently we only support a fixed controller mapping, which is determined by your Android vendor. Custom mappings for controllers are planned in the future.

### I want to set different settings for each game.
Currently this is not possible. We plan to add this in the future.

### My games have rendering glitches.
Due to the complexity of the console's hardware, there are still plenty of issues which arise when using the hardware renderer. You can try using the software renderer for these games.

### I want to save more than one state.
This is not currently possible, we are planning to add multiple save slots in the future.

### I want copy my saves from another device.
Currently you can only import an entire memory card at once; it is not possible to import individual saves. Swiping from the left in the game list will show an "Import Memory Card" option which you can use to import a *.ps2 image of a memory card.

### Where are my saves located?
Due to scoped storage on Android 11+, we cannot place your saves in a normal directory on external storage. However, with a file explorer app, you should be able to access the `Android/data/xyz.aethersx2.android` directory, in your primary storage volume, which contains your save states and memory cards. Note that accessing this directory requires granting additional permissions to your file manager on Android 11+.

### How do I add covers to the game grid?
Place cover images in the covers directory, located in the data directory mentioned above, with the file name as the game title or serial in jpg/png format. Alternatively, you can long press in the game list and select "Choose Cover Image" to import an image.

### How do I create launcher shortcuts for games?
Long press the game in the game list, and select "Create Launcher Shortcut".
