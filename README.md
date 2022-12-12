# manim_pi_creatures
All pi creatures appear in 3b1b video

This repository is used for manim cairo-backend.
We're trying making different versions like manimgl and manimce.

## Usage
**PiCreatures_happy.svg and so on**:

These are different emotions of pi creatures. They are from https://www.3blue1brown.com/images/pi-creatures/happy.svg and so on.

You need to put them in the `assets\PiCreature` folder.

We just put them in the repository for reference only, do not use them for commercial purposes!

**pi_creature.py**:

This python file is from cairo-backend, but we changed it a little (line 53 ~ 56) to see all the pi creatures. Use the modified file instead of the original one
to see cute pi.

## Effect


https://user-images.githubusercontent.com/111475301/206908960-0b212863-a691-4b41-8b21-d0a8d1ec2d98.mp4

The source code is below:

```
from manimlib.imports import *
from manimlib.for_3b1b_videos.pi_creature_animations import *
from manimlib.for_3b1b_videos.pi_creature import *
from manimlib.for_3b1b_videos.pi_class import *
from manimlib.for_3b1b_videos.pi_creature_scene import *


class NowWeHaveExpressions(TeacherStudentsScene):
    def construct(self):
        self.change_student_modes('happy', 'hooray', 'well')
        self.teacher_says('Now we have emotions!')
        self.wait()
        self.student_says('Hooray!', student_index=1)
        self.wait(2)
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

Ensure that you installed these requirements and set their path environments:

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

If it's exporting a video, you have successfully installed cairo-backend.
