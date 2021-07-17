# CSC207 2018Fall Project Phase1
### Custom Tile developing log
##### Kewei Qiu of __Group 0557__
---
### Purpose of this file
  As a member of group 0557, one of my assigned task is try to implement one of the several bonuses of phase 1: allow player of _SlidingTiles_ to custom their tile by uploading a picture from their device.
  Due to limited time and some un-studied knowledge, I did not finish the whole tile customizer. However, there are some important developing processes and useful information during the developing progress.
  As a result, I think that it is necessary to record these processes and information, in purpose of reviewing and later learning.
---
### My understanding about tile customizer
  There are 4 steps to custom tile image, according to my design
 - Pick one image from user's device either gallery or camera.
 - Crop the image, to let it have the same size as the grid board of _SlidingTiles_ game.
 - Split the cropped image into several smaller blocks, according to the chosen difficulty.
 - Pass split blocks to tiles, to construct customized board.
---
### Till now progress
In my implementation I used SoundCloud API Library developed by jdamcd.
##### Pick image
 - Since getting an image by device camera might be a little complex, I decided to let user pick already-existed image from gallery of their devices.
 - In one youtube tutorial I found that define a method with using class Crop's (in SoundCloud API Library) method pickImage can meet our needs easily.
 - I tried this and found that it works on me.
##### Crop chosen image
 - The previous tutorial also mentioned this progress.
 - I cropped the image by using Crop.of() in crop class and passed the result into an ImageView which is shown on the screen.
##### Split cropped image
 - I followed another tutorial and implemented this part using Bitmap API.
 - The method took 2 arguments: the ImageView result from previous part, and the chosen game difficulty, which is used to determine the number of smaller chunks to be created.
 - After finished the result chunkedImages has all the small image chunks in the form of Bitmap class, and It was stored in an Arraylist
##### Pass split image
 - This is where major problems arose.
 - I have not figured out how to implement this prat yet.
---
#### Major problems I met
 1. Rebulid project issue
 Since image cropper used a third-party library, I have to rebulid the project to make the implementation working properly. (This is what I found from google, and it does worked on me)
 However, when I pushed my changes to repository, one of my teammate pulled it, but he cannot get rid of 'unresolved' error even after rebuliding the project.
 2. Passing Drawable issue
 After getting an ArrayList of result chunks as Bitmaps, I was able to convert them into Drawable.
 However, I did not figure out how to pass these Drawables into constructor of Tile, since I learned form piazza that Drawable object should not be passed around activities and is not serializable.
 This is the problem which preventing me have any progress in part 4 mentioned above.
