---
title: "Another application for Blender"
date: 2023-01-07T16:28:39+01:00
draft: false
image: banner.png
categories:
    - Software
tags:
    - Gases
    - Application
---

# Motivation
I bought a second-hand compressor, quite old but very cheap, and now I'm already filling tanks with it very satisfactorily. I'm very happy even though it's something I should have done a long time ago; I was tired of having to plan where and when to fill bottles and spending gasoline to get there. Besides, I'm overcoming the fear of handling the compressor and the bottles. I used to feel apprehensive about the high pressure involved, but as always happens, after about twenty fills, the body gets used to the valve's blowing of overpressure and purging.

The compressor runs on gasoline, and I use it to fill air, but sometimes I refill bottles that previously had nitrox, and I'd like to know in advance the resulting mixture. For this, there are many blending apps for all systems, but by programming it from scratch, I can revisit the notes from the Blender course and also continue gaining proficiency in creating GUI in Python.

# Ideas and Development
I'm going to create a program that takes the mixture with which the bottle is provided and the mixture you desire for the bottle. The system will then return the bars of O2, He, and air that you need to apply to achieve it, which is typical in this kind of applications.

Additionally, it has another option that I'll likely use the most, which is to tell you the resulting mixture when filling any bottle with air. Also, I'll include the prices of the gases sold in Spain, including the price of compressed air, which always has a fixed cost in the industry. I don't understand why, so if someone comes by someday and I want to charge them for the fill, I'll charge them a fair amount, never more or less.

# Where to Find It
I've uploaded it to a [GitHub project](https://github.com/avances123/gasblender). It's a Python script, and in the same repository, there's a file with the dependencies it needs to run.

# Future
I hope to implement a small database to keep track of my fills and thus monitor the maintenance needed for the compressor. This change might even lead to transitioning directly from Python to a web-based application.

