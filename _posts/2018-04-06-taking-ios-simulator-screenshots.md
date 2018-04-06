---
layout: post
title: "Taking iOS Simulator Screenshots"
date: 2018-04-06
---

When you are taking screenshots of your app to upload to the App Store, be sure you go into the Simulator and turn off "Debug" -> "Optimize Rendering for Window Size". 

What that does is change the pixel size of the image on the screen to match the pixels of the window in which it is displayed. The upside of that is that the simulator renders faster and looks good on the screen. The downside is that when you take a screenshot, it comes out as the wrong size, because it's a screenshot of the pixels at desktop resolution instead of iOS device resolution. This will cause you to get "Screenshots are the wrong size" errors when you try to upload them to the store. 
