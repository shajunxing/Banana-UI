[Watch video](https://user-images.githubusercontent.com/1294264/227157679-5ae997e0-90c9-47d7-beae-6c2432c939d8.webm)

![test_luabanana_1](https://user-images.githubusercontent.com/1294264/227215277-10d72a0a-f65a-4d91-9745-f9e3f7e013ea.png)

![test_luabanana_2](https://user-images.githubusercontent.com/1294264/227215377-2ebc9a45-13ac-45bb-b34c-09c4b883461c.png)

![test_luabanana_3](https://user-images.githubusercontent.com/1294264/227215394-4d8ea91e-0760-4954-a35c-b85bdf7e4a69.png)

![test_luabanana_4](https://user-images.githubusercontent.com/1294264/227215420-dd02f425-8f55-4354-a08e-876cefff36b7.png)

![test_luabanana_6](https://user-images.githubusercontent.com/1294264/227215493-6852e626-a138-4d86-9d98-275e58641fbc.png)

![test_luabanana_7](https://user-images.githubusercontent.com/1294264/227215518-a2a3425f-9385-4899-b7ff-77c2175aae28.png)

# Banana UI: A minimalist ISO C compatible cross -platform graphical user interface infrastructure

The realization of computer engineering should be simple. For example, the graphic interface of many people talked about, the more deeper research. The more you feel, is it necessary to be so complicated? The main graphics interface is not the screen, mouse, and keyboard three ax? I like to come from scratch. If my energy allows me to even want to bite my CPU, my own programming language, my own compiler, and the next, use C language to define a set of minimum operations, including reading and writing pixels, including reading and writing pixels, including reading and writing pixels, including reading and writing pixels. The mouse keyboard event, corresponding to different software and hardware platforms, the minimum requirement is to implement these functions and compile them. Advanced, such as reading and writing pixels is too slow, so can I read and write wholeheartedly? No problem, these are called optional operations. The implementation is OK. It is not realized. I also have the default version of reading and writing pixels, and even if the mouse keyboard event is not needed, it can not be implemented. The pictures, fonts, windows, controls, input methods, etc. on the bottom layer are all written in C, or exported to the script language such as Lua.

Of course, the goal is very large. An extremely streamlined screen display/mouse/keyboard core, theoretically few code can be expanded to any platform. In order to improve performance and make most of the functional platforms, the mixed operations of the layer are all the layers of mixed operations are all. Use pure C code to operate in memory, and finally Flush to the device. Well, the graphics interface, software graphics interface, game, etc. of the operating system can all, such as implementing a set of common functions under Framebuffer, which can completely replace the Linux text interface, just like the previous dosshell.

At present, basic functions have been implemented in Windows GDI, Linux Framebuffer, and Xorg environment, including: pixels read and write on the screen; mouse events; custom rectangular areas (I call it "block"); pixel read and write; The alpha hybrid operation between the blocks; the block read and write of the screen; the wide -point formation such as the unifont is used, and the scope can be customized. If it contains the complete Plane 1 and 2 Image files; and export all the above functions to the LUA 5.1 environment. The following functions are to be realized: Chinese input method; UI architecture similar to World of Warcraft in LUA 5.1; realize some Dosshell semi -graphical programs.

The source code is temporarily disclosed to prevent malicious FORK and random modification. When the function is stable in the future, there are any suggestions for suggestions to talk privately. The example program includes C language and LUA. The command line is generally like this: "./ xx <platform name> [[platform parameter] ...]", or "./minLua xx.Lua <platform name> [Platform Parameter] ...] ", Minlua is the LUA interpreter that removes the interactive function, without additional dependencies such as Readline, Curse. If the platform name under Linux is "linux_xorg", then there is no platform parameter, if it is "linux_framebuffer", then the specified parameters need to be Framebuffer and mouse device file names, such as: "./ minlua test_luabanana_1.lua linux_framebuffer /dev/fb0 /dev/input/event2 ", note that Framebuffer runs under the console rather than X Windows, and users need to have corresponding permissions. The easiest way is to add users to the Video and Input group.
