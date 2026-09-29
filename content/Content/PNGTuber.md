---
description: Information about my PNGTuber and how it works.
comments: "false"
---
---

#### <font style="color:grey"> jan la sitelen tawa soweli e mi kon </font>

 ![[ezgif-3a845aeca74d7183.gif]]

My pngtuber was drawn by [Vinny](https://ko-fi.com/xitzycore) and inspired by (stolen from) [msx](https://msx.horse). 
It is handled entirely by OBS with no external programs and only light community materials. 

The [image reaction plugin](https://obsproject.com/forum/resources/image-reaction.1342/) is used to swap between sprites based on mic input, whilst a [shader-filter](https://obsproject.com/forum/resources/obs-shaderfilter.1736/) is applied to give it that wobbly effect, the shader file is [here](https://msx.horse/files/doodle_linear.effect). [Scale to sound](https://obsproject.com/forum/resources/scale-to-sound.1336/) is then used on the head for some extra animation. 
Below is a step by step process on how to recreate it.

<br>

# Build Process

For every part of your pngtuber that you want to move you will need a sprite. Below is my dismemberment, as I wanted my tail, head and each arm to move independently. 
![[Pasted image 20260928111415.png]]
There are now two ways that you can take this, either:
- Keep them as images and swap between the multiple sprites based on noise level
- Make a slideshow gif of each part that cycles between its variations 

I opted for the latter, and so will explain that methodology. For it, I just used [ezgif](https://ezgif.com/). 

To construct them in obs, create a dedicated scene for it and add two [image reaction](https://obsproject.com/forum/resources/image-reaction.1342/) sources per moving part. 
In one of the sources, set "image when silence" to be an idle sprite, the one you want it to be when you aren't talking, leaving the "image when sound" field blank. 
Do the same for the other [reaction source](https://obsproject.com/forum/resources/image-reaction.1342/), but the inverse, setting your "image when noise" field to your slideshow gif and leaving the "image when silence field" blank.
*The reason I use two different sources for talking and silence as opposed to using one with both fields filled out is because if you use one the wiggly shader filter will apply to the silent sprite too, which I dont want. If youre not using the wiggle effect, feel free to combine it into one source*

| ![[Pasted image 20260928112723.png]] | ![[Pasted image 20260928112809.png]] |
| :----------------------------------: | :----------------------------------: |
|    Silent Sprite Reaction Source     |  Talking Slideshow Reaction Source   |

Play around with the audio thresholds to get the volume levels right so its not swapping to the speaking sprite when you dont mean it to or vice versa. What works for my mic may not work for yours. 
I would recommend creating a new mic source specifically for the pngtuber to pull from that has some filters attached to it like noise gates to prevent it activating from background noise like keyboards or chair creaks.

Then apply the [shaderfilter](https://obsproject.com/forum/resources/obs-shaderfilter.1736/) to the talking source: right click > filters > [user-defined shader](https://obsproject.com/forum/resources/obs-shaderfilter.1736/) > shader text file > [doodle_linear.effect](https://msx.horse/files/doodle_linear.effect). 
Similarly mess around with the scale and snap percentages until you get it to something you like. 
Scale to sound is also applied as a filter, so apply that to whichever body parts you want. I personally use it for the head, and make it only scale vertically. That way, it has this slight squash & grow effect that follows the rise and fall of my voice. 
![[Pasted image 20260928113734.png]]

Repeat this for every body part (remember to add in any static sprites for body parts you dont wish to change or move). 
Another fun touch is making non-talking sprites animated too, for example I have my tails silent sprite set to a slower slideshow that only cycles between two poses to give it a more relaxxed vibe, whilst the speaking one is faster and swaps between all four. 

Finally add this scene as a source in whatever other places you may want it. 
![[Pasted image 20260928114624.png]]

And with that you should have a nice and dynamic pngtuber ready to go! This format is really fun, and can be as simple or as complicated as you want it to be. Whether you only move your head or build a whole animated body that responds dynamically to your voice, its all contained in a single scene, no need for external softwares. 
Thank you again to [msx](https://msx.horse/) for being the one who I took this setup from and to [Vinny](https://ko-fi.com/xitzycore) for drawing my sprites. 

<br>

![[Study.mp4]]
*Showcase video*