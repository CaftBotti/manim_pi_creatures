# Manim PiCreature

[![Designs collected](https://img.shields.io/badge/Designs%20collected-50-brightgreen)](https://github.com/CaftBotti/manim_pi_creatures)
[![Stars](https://img.shields.io/github/stars/CaftBotti/manim_pi_creatures?style=social)](https://github.com/CaftBotti/manim_pi_creatures)

All pi creatures that appear in 3b1b video that is used for making pi creature scenes with manim. Thank you for your star! 用manim制作像3b1b视频里一样的pi小人动画。请点一个star，谢谢!

> Have you ever seen some lovely pi in 3b1b's videos? Do you want to make those animations as well? You may feel frustrated with that the original manim cairo-backend always makes emotionful pi creatures become "plain" because you only have "PiCreature_plain.svg" but not other designs! 
>
> Don't worry, we have found all of the SVG files of those designs and put them here! Clone this repo and dozens of pi creatures in the `PiCreature` folder, and then put them in `assets\PiCreature` path.

Note, **SVG files of designs of pi creatures have moved to the ["PiCreature" folder](https://github.com/CaftBotti/manim_pi_creatures/blob/main/PiCreature)** so that you can directly replace the "assets\PiCreature" folder in cairo-backend with the new one, and then you can make videos following steps in [usage](https://github.com/CaftBotti/manim_pi_creatures#usage).

This repository is used for manim cairo-backend. We're trying making different versions like manimgl and manimce.

This repository includes all pi creatures that appear in 3b1b's videos, and some pi creatures made by myself that don't appear in 3b1b's videos. You can also upload your own designs by pulling requests. ALL parts of the repository are public, and you can use them anywhere you want. However, we put them here for reference only, do not use them for commercial purposes!

## Usage

**"PiCreature" folder**:

In this folder, there are different emotions of pi creatures. They are from https://www.3blue1brown.com/images/pi-creatures/happy.svg and so on.

You need to put these SVG files in the `assets\PiCreature` folder. Copy the folder directly and replace the "assets\PiCreature" folder.

**"non-3b1b" folder**:

This folder contains some pi creatures' SVG file that made by myself, and they aren't in 3b1b's videos.

**pi_creature.py**:

This python file is from cairo-backend, but we changed it a little (line 53 ~ 56) to see all the pi creatures. Use the modified file instead of the original one to see lovely pi.

## Effect

https://user-images.githubusercontent.com/111475301/209333597-63a97dca-75e8-4f96-9927-fa2bc4b925ff.mp4

The source code is below:

```
from manimlib.imports import *
from manimlib.for_3b1b_videos.pi_creature_animations import *
from manimlib.for_3b1b_videos.pi_creature import *
from manimlib.for_3b1b_videos.pi_class import *
from manimlib.for_3b1b_videos.pi_creature_scene import *
class NowWeHaveEmotions(TeacherStudentsScene):
    def construct(self):
        self.change_student_modes('happy', 'hooray', 'well')
        self.play(self.teacher.change_mode, 'happy')
        self.teacher_says('Now we have emotions!')
        self.wait()
        self.student_says('Hooray!', student_index=1, target_mode='hooray',
                          added_anims=[self.teacher.change, "hooray"])
        self.play(self.teacher.change_mode, 'hooray')
        self.wait(2)
        self.play(RemovePiCreatureBubble(self.students[1]), self.students[1].change_mode, 'hooray')
        self.wait(3)
```

Enjoy your time playing with little cute pi!

# Installation of manim cairo-backend

If you haven't installed cairo-backend yet or don't know how to install it, here is a tutorial:

(cairo-backend is much easier to install than manimgl and manimce, I think)

+ Step 1

Get the source code of cairo-backend: https://github.com/3b1b/manim/tree/cairo-backend

+ Step 2

Use this command in the cairo-backend folder:

```
pip install -r requirements.txt
```

It will install some python site-packages, like pycairo, scipy and numpy.

And please ensure that you installed these requirements and set their path environments:

`FFmpeg`, `dvisvgm` and `MikTeX`.

+ Step 3

Create a python file and copy this code:

```
from manimlib.imports import *
class Test(Scene):
    def construct(self):
        text = TextMobject('If you see this text, \\ you have successfully installed cairo-backend!)
        self.play(Write(text))
        self.wait(3)
```

You can name this file as `start.py` and then use this command:

`python -m manim start.py`

If it exports a video, you have successfully installed cairo-backend.
