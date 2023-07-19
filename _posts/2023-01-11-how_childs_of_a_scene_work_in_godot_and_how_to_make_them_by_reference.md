---
title: how childs of a scene work in godot and how to make them by reference.md
date: 2023-01-11 14:01 -500
categories: [Tutorial,Workflow]
tags: [Godot]
---

- The t in .tres and .tscn is "**text**" (_if u leave the **t** off, it becomes a binary_)

### MAKING A CHILD IN A SCENE BY LOCAL VALUES 
-when creating a new resource as a child of a scene(tscn), its values are store in the **tscn** file:
![1](https://user-images.githubusercontent.com/78625020/211858345-3ce7312a-a202-41ef-b98e-2840395a50a7.png)

all the values are store inside the scene(tscn), this way all changes to the child remains local

### MAKING A CHILD IN A SCENE BY REFERENCING A RESOURCE FILE
-in this way, the scene checks the resource file(tres) for values
![2](https://user-images.githubusercontent.com/78625020/211860545-8722bc61-1917-4158-9efd-39a611bc1fa2.png)

all the values are store in the resource file(tres), this way changes affects all the scenes this resource is instantiated  
**UNLESS**
-u make your resource "local to scene"  
![3](https://user-images.githubusercontent.com/78625020/211864470-76920fa7-8fe5-4075-b69b-22e4731891ac.png)

in this way:
- **all changes made on the resource file affect all instances of it, the local ones only affect how it behaves inside that scene** 

![4](https://user-images.githubusercontent.com/78625020/211868202-a3bbf1e4-c04a-451e-8c98-72133a5a4660.png)

-u can use this if u want to make a preset of something that will have a lot of variations or if u want to embed new parameters/variables or outright make costume resource of your own:

![5](https://user-images.githubusercontent.com/78625020/211869292-50e0f55e-2738-46b0-8d60-a3d3dabb4bce.png)


source:
https://www.youtube.com/watch?v=mRaz4KlTh-c
