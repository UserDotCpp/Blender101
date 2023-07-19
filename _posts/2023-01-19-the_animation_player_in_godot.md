---
title: the animation player in godot.md
date: 2023-01-19 12:23 -500
categories: [Tutorial,Workflow]
tags: [Godot]
---

### animation player anatomy
>shift anchor your movement to the axes

![guide](https://user-images.githubusercontent.com/78625020/213387092-26cb094a-756f-4e70-a9dc-d267a13c0a87.png)


![rec](https://user-images.githubusercontent.com/78625020/213343130-bf26e361-820a-4e8b-8fde-86275ff34bf0.PNG) 

this records all the changes on existing tracks

![key](https://user-images.githubusercontent.com/78625020/213343049-dadc63e2-423b-4c23-8d90-19608fe4652e.PNG) 

insert key records all changes and makes new tracks if needed 

![reset](https://user-images.githubusercontent.com/78625020/213345886-7db73a6e-ef5b-4a9f-b5db-74a7b81d9034.PNG) 

this will enable the reset track

the reset track runs when the node is loaded

![reset track](https://user-images.githubusercontent.com/78625020/213344338-47755eed-7fd6-4e9d-af97-f8888e620244.PNG)

![interpolation modifiers](https://user-images.githubusercontent.com/78625020/213390582-e66785e4-1584-4e22-9689-8d952feae14d.PNG)

the interpolation modifiers manage the frames between your key frames, like so:

![1](https://user-images.githubusercontent.com/78625020/213391382-800642e3-8a36-4c6c-92e8-a361a189f81a.PNG)

**the track settings**, tells godot how to update the values 
- Continuous: Update the property on each frame
- Discrete: Only update the property on keyframes
- Trigger: Only update the property on keyframes or triggers. Triggers are a type of keyframe used by the current_animation 
        
![2](https://user-images.githubusercontent.com/78625020/213392187-8c74ec99-9936-460b-a365-ddf0ab5dad3f.PNG)

**the track interpolation**,tells how fast the inbetween frames go
- Nearest: no inbetweens
- Linear: calculates the speed in base of the distance of the 2 keyframes de manera exponencial
- Cubic: calculates the speed in base of the distance of the 2 keyframes but rough than linear 
        
![3](https://user-images.githubusercontent.com/78625020/213393653-f6b585bc-ccf1-45f9-a6e5-160def7021c6.PNG)

**the Loop modes**
- Clamp loop interpolation: when the track ends it starts from the first frame
- Wrap loop interpolation:  when the track ends the frames regress until they reach the first one 

>**bezier curve** its not in the **"the track settings"** but it behaves like one,it lets u edit the function of the interpolation

### texture regions for sprite sheets
texture regions let us divide the sprite in different areas to work with. There are 3 "**snap modes**" for this purpose:

1. pixel snap: ...
2. **grid snap: requires that all frames share the same dimensions to separate them in grids(insert workflow addendum for asesprite)** 
3. auto snap: godot detect which are the frames by spacing because of this , u cant use 2 separated objects in one sprite and this needs more position and rotation adjustment cos the sprites don't have an opset with each other

![regions](https://user-images.githubusercontent.com/78625020/213356743-49d06c58-19fb-48d7-8aa6-b20c613e0005.png)
regarles of whitch snap mode u use (grid snap in the example)_
![grid](https://user-images.githubusercontent.com/78625020/213358799-44032b18-d4cd-4c09-9ec2-4d0236e79b5f.png)
_the animation workflow is still the same:
![last](https://user-images.githubusercontent.com/78625020/213364874-2ffc430b-a01d-4b66-aeb6-009175845a53.png)


resources:
[place holder sprite](https://www.spriters-resource.com/game_boy_advance/sfalpha3/sheet/5516/)
[script structure](https://www.youtube.com/watch?v=WSKCRPnNrSg&t=272s)
