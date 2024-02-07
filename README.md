# M5Cardupter-UserDemo-Plus for Platform.io

The UserDemo-Plus firmware with the default platform.io project structure.

I kind of stumbled through this so I had to omit some of the apps to get it to compile.

- Uses the arduino esp32 package.
- Project structure is laid out like a typical platform.io project.
- Removed apps:
  - Keyboard
  - Chat: I found that it needed the esp8266's espnow.h and adding that library would have led to a dependency rabbit hole I wouldn't know how to deal with effectively.
  - REPL: I think the implementation of pikapython or at least the app doesn't work well enough to be useful outside of using print(). Also pikapython gave me trouble compiling so I just removed it instead.

I would like to make this use M5Unified and M5GFX at some point.

## A bit of setup:

- Download the project and open it in Platform.io.
- Create a git repo in the project directory if you don't have one yet.
- Install the git submodules: Run the commands "git submodule init" and then "git submodule update".
- If it the Arduino and ESP8266Audio folders are still empty, you may need to open the .gitmodules folder and copy the github links and run "git submodule paste-link-here" for each - submodule.
  - Note: We may not need the Arduino submodule. I think Platform.io installs a usable arduino esp32 core but I haven't tested it yet.

# M5Cardputer-UserDemo-Plus

Official firmware enhanced

- add arduino-esp32 as a ESP-IDF component for easier development
  - porting some native but messy code to Arduino lib to avoid crash
- porting @cyberwisk's cardputer WebRadio as an App
  - using a modded version of ESP8266Audio to support https and chunked stream (like qtfm.cn)
  - ability to play radio in background when pressing HOME (G0), press ESC to fully exit
  - more radios (you can modify the radio list at (main/apps/app_radio/M5Cardputer_WebRadio.cpp)
- enhance SCAN, TIMER (renamed to CLOCK), SetWiFi App
- add SCALES and ENV IV App for the mini-scales and ENV IV m5stack sensors
- system enhance
  - WiFi will remain connected in background in default, open SetWiFi App again to turn off
  - use ESP-IDF's automatic sntp
  - enhance system bar
    - show battery voltage and current free heep size
    - add real feature to WiFi icon

# M5Cardputer-UserDemo

M5Cardputer user demo for hardware evaluation.
