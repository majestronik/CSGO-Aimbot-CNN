# CSGO-Aimbot-CNN
CS:GO Aimbot based on convolutional neural networks.</br>
![Showcase](https://github.com/ofeksadlo/CSGO-Aimbot-CNN/blob/main/ezgif-5-06587c2150ec.gif)</br>
# How it works
The program will capture 160x160 from the screen then it will</br>
detect whether an opponent in the cropped frame. If there is it will</br>
aim to his head.</br>
The entire process will be displayed at your screen.</br>
At the top left you will see how many frames the model process in a second (The higher the better).
# How to make it work
1) You need to play on fullscreen windowed. For the overlays to show and for the frame capturing.
2) **Mouse raw input needs to be disabled** for the aimbot to work properly.
3) Resolution has to be 1920x1080. Otherwise you'll need to change screenWidth and screenHieght values.</br>
   Notice that fullscreen windowed mode just use native resolution.
4) Install all dependencies from reqiurements.txt file.
5) Open main.py and go to the game. Place an opponent in your FOV and your crosshair will be locked to his head.</br>
   For playing I would pick the aimbotOnly.py because the drawing slows the aimbot a little.</br>
**<ins>Tip:</ins>**</br>
Playing with raw input off may feel like mouse acceleration is on. You'll need to</br>
disable in windows mouse setting the Enhance pointer precision option.</br>
<img src="https://i.redd.it/hxvpfgtu6hcz.png" alt="textDemo" width="200" height="250"></br>


# Keyboard Control
| Key | Action |
| ------ | ------ |
| F5 | Toggle Headshot only (Target heads only) |
| F6 | Toggle Drawing on screen |
| F7 | Toggle Sniper aimbot (Target body only if trigger on it will right click before firing) |
| F8 | Toggle Triggerbot |
| F9 | Change target (ct / t) |

# Compatibility issues
*  The aimbot is good but not perfect it's based on a custom yolo-tiny model.</br>
   This verison of an aimbot is based completely on CPU. Which in CSGO is a big downside.</br>
   Because CSGO is based heavily on CPU the aimbot and CSGO ending up fighting for performance. So</br>
   consider typing in concole fps_max 60. The reason I don't use GPU for inferencing the model.</br>
   Is because I have AMD graphic card. And although there are some ports to use AMD GPU using</br>
   TensorFlow I've decided to simple develop this aimbot CPU only.</br>
   In theory this aimbot can be much more powerful with a decent</br>
   NVIDIA graphic card.</br>
*  In order to get a decent frames the model process in a second. I've only used</br>
   the small fov for detecting opponents.</br>
   You can tweak FOV but both values has to be the same.</br>
   And be a multiple of 32.</br>
   I found the limit to be 128x128. Getting 60 fps on my cpu!</br>
   below that and the detections won't work.</br>
*  The higher the sensetivity the more snappy the aimbot is.</br>
   After some testing I've found the middle ground to be 1.5 on 800dpi.
*  The aimbot only tested on Window 10 with 1920x1080 resolution. But should work</br>
   on other operating systems aswell.
# Bugs
1) When more than one target in the FOV the aimbot locking to both target at same time.</br>
   Even though we do calculate the distance between the target. If the target lost because</br>
   the detection lost him. The aimbot will lock to the new closest target.</br>
   I plan on solving this and improve performance at the same time using tracking method.</br>
   I already gave a try to the existing tracking methods opencv provides. But</br>
   they aren't good enough so I'm gonna implement my own.

# Future plans
- [x] Adding support for aiming on terrorist opponents.
- [x] Adding support for sniper rifles
- [ ] Adding spray control that will target the head
- [x] Adding keyboard shortcut to toggle aimbot On / Off.
- [ ] Adding spray control crosshair.
- [ ] Switching between Sniper aimbot to rifle aimbot to pistol aimbot</br>
   based on which weapon used.</br>
   By detecting weapon text:</br>
   <img src="https://github.com/ofeksadlo/CSGO-Aimbot-CNN/blob/main/textDemo.jpg" alt="textDemo" width="150" height="150">
- [ ] Adding aim key
# Disclaimer
**This project is for educational purposes only.**</br>
Developed in Python 3.7.7
