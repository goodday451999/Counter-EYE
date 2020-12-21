# SurvOnTheGo
A real-time surveillance system enables the detection of people with knives, guns, and other dangerous objects in public places and makes alert to security forces to take necessary steps.

![Demo](https://github.com/goodday451999/SurvOnTheGo/blob/main/DemoVideo/demoVideo.gif)


# Problem Statement: 
In the current global scenario, we are witnessing several terrorist attacks in India such as the 2011 High court bombing, the 2011 Mumbai bombings, the 2008 Mumbai attacks, the 2001 Indian Parliament attack as well as various protests with huge gatherings happening on various issues. Surveillance in such cases is a major challenge for the authorities. It is easy for anti-social elements to masquerade as protestors and create unrest. SurvOnTheGo is a real-time surveillance system enables the detection of people with knives, guns, and other dangerous objects in public places and makes alert to security forces to take necessary steps. 

# Model Architecture: Yolov3 model using Draknet framework
<img src="https://i.imgur.com/MxHMaI9.png" width="900" height="400"/>

# Dataset:
The images and labels are taken from [University of Granada research group](https://sci2s.ugr.es/weapons-detection).
For this project, we are using the region proposals approach. The data contains 3000 images of guns (mostly handguns) in `.jpg` format and their appropriate labels/annotations.

For each image, there is an xml file that contains the class name of the object (like, pistol) and the coordinates of the box surrounding the object.

Here is some of the fields from one of the xml files:
```
<annotation>
  <filename>armas (3)</filename>    <-- file name
  <size>
    <width>1300</width>             <-- image width
    <height>866</height>            <-- image height
    <depth>3</depth>                <-- 3 = a colored image (RGB)
  </size>
  <object>
    <name>pistol</name>             <-- class name

    <bndbox>                        <-- box position around object
      <xmin>471</xmin>              
      <ymin>207</ymin>
      <xmax>613</xmax>
      <ymax>359</ymax>
    </bndbox>
  </object>
</annotation>
```

In this project, we considered the pistol, gun, rifle and knife as a signle class named Weapon.

# Model Performance on Image:
***Input:***

<img src="https://i.imgur.com/A6iB4aE.jpg" width="800" height="800"/>

***Output:*** 

<img src="https://i.imgur.com/bCKj7ba.png" width="800" height="800"/>

# Model Performance on Video:

https://github.com/goodday451999/SurvOnTheGo/blob/main/DemoVideo/OutputVideo.mp4

Youtube Video Link: https://youtu.be/uTCxUHxbJMk

The ***yolov3 model using Draknet framework*** had a detection speed of 36 frames per second (FPS) and a mean average precision (mAP) of 95% on a GPU-1080Ti system.

# Challenges: 
* Making the system work accurately in a large gathering is a major challenge. 
* In such settings a lot of occlusion happens and accurate delineation of the boundaries is difficult.
* Currently used surveillance systems are not yet fully automatic which Requires human effort to properly analyze CCTV footage and other surveillance feeds which make this process time-consuming.
* The proposed method can be used to detect such issues and send alert to nearest police station or security force. This way, we can make CCTV more intelligent and smart.
