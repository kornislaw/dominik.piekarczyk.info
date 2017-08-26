Title: Playing Minecraft Pi with son
Subtitle: Minecraft Pi is a great entry point for teaching a real programming language.
Slug: playing-minecraft-with-son
Category: Family
Tags: minecraft, python
Date: 2017-08-26


### What is Minecraft Pi


This is a simplified version of Minecraft, which you get preinstalled on Raspberry Pis. The adventage of this version is that for programming purposes you have all set up and ready. You can just run the Python console and start building.

#### Example

```python
from mcpi.minecraft import Minecraft

mc = Minecraft.create()
melon = 103

for j in range(0,10):
	for i in range(0,10):
		mc.setBlock(7,i,7+j, melon)

```

### Accessing Raspberry Pi remotely

You can use SSH to access your Pi and build in Minecraft remotely.

#### How simple it is:

```shell
~ % ssh pi@192.168.1.111
pi@raspberrypi:~ $ python
...
>>> import mcpi.minecraft as minecraft
>>> mc = minecraft.Minecraft.create()
>>> mc.postToChat("Hi Jacek!")
>>> mc.postToChat("What's up? :)")
```

The messages were displayed on the screen wheb Jacek was playing the game, For a while he believed me it is Minecraft talking to him.


### How was my son doing?

To be honest during the first session he didn't learn much. I saw a lot of excitement when I showed to him how easy it is to build a wall of melon blocks using simple nested loops - something that takes a lot of time when building manually.
But the learning curve may be a bit too steep for a 6yo. He was having more fun building manually through the game interface than trying to code. I'm not pushing, it will come with age, I have no doubt.
