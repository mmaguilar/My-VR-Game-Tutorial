# My-VR-Game-Tutorial
**Unity VR Basic Hand Presence Tutorial**

Set up and create a Unity VR game with hand presence. This will be an introduction to the setup for our **Virtual Reality PC Builder**, which requires virtual user hands to interact with different elements in the game. 

The VR game needs to: 
* Connect to the Unity scenes/project.
* Connect the controller functions to the user hands. 
* Display player hands for the user to visualize their interactions. 


### Storage Requirements
For the device used to set up VR in Unity, the storage should have more than **40GB available** to required packages and installs. 

### Virtual Reality Requirements
For this tutorial, we will be using the Oculus Quest. Other VR headsets will need to use their corresponding install for their VR setup and the Unity **XR Plug-in Management**.

## Installing Unity 
To install Unity: https://unity.com/download 

After downloading, go to the **Installs** option on the left sidebar. 
- **Click** on `Install Editor`.
- Select **version > 2021.3.6.** Make sure to add the following modules for the install: 
     * Microsoft Visual Studio Community
     * Android Build Support 
        * Open JDK 
        * Android SDK & NDK Tools

## Setting Up a Unity Project
Go to **Projects** on the left sidebar and click on `New Project`.
Name the project and select **3D (URP)** (You may have to download the template) and `Create Project`.

## Setting Up VR in Unity 
Set up your Oculus Quest using the Quest app on your computer. 
Download the app onto the PC:  https://www.oculus.com/Setup/.

Follow the set up instructions in the app to access your device from the VR headset.

### Unity Configurations
Open the **Package Manager** and install `Oculus XR Pugin` and `XR Interaction Toolkit`.
  * To access the **Package Manager**, select the **Windows** option in the navigation bar.
  * In the **Packages** dropdown on the top right, select **Unity Registry** and search for the two installs.
  
Go to `Project Setting` and in the `XR Plug-in Management` tab, install the plugin.
  * Select `Oculus` for both the Destop and Android. 
  
Now, we are ready to begin creating our VR game!

## Creating our VR game 

### Setting up our Environment
**Let's create our main scene.**
In the **Scenes** folder, **right click** to create a new scene 'Main VR Scene'.
To work in this scene, make sure it is selected.
  
**Now, create a new plane on the scene.**
**Right click** on the scene to create a `3D Object` > `Plane` and set its position to (0,0,0).
**Right click** on the scene to create a `Material`object. Name it `Plane Material` and drag it to the plane. 
You can change the color of the plane using the `Plane Material` object.
  
**Next, let's set up our main camera to follow our VR headset movement.**
**Delete** the `Main Camera` in our scene.
**Right click** and select `XR` > `XR Origin` to add an **XR Origin** to the scene. It should contain a main camera along with other tools. 
Set the **XR Origin** position to (0,0,0).
To take the height of the player into account, change the `Tracking Origin Mode` in the **XR Origin** component to `Floor`.
    
Test this by playing your scene on the headset. 

### Creating User Hands 
In the scene, select `XR Origin` > `Camera Offset` and **right click** to select `Create Empty` and name it `Left Hand`.
Add a new component **XR Controller (Action-based)**.
Duplicate this object for the `Right Hand`.

In the `Project` Folder, go to `Samples` > `XR Interaction Tools` > `(version)` > `Starter Assets`.
In this folder, we have presets we can use for the hand XR Controllers. 

Go back to the hand objects and select the settings icon on the **XR Controller (Action-based)** component and select `XR Default Left/Right Controller` for each of the corresponding objects. 

Finally, select `XR Origin` in the scene and add a new **Input Action Manager** component. 
Select the `XRI Default Input Actions` in the `Starter Assets` folder and drag it in the `Action Asset List` of the **XR Origin** controller. 
  
#### Visualizing User Hands 
To visualize the hand presence using a nice hand model, download the hand model from Oculus: https://drive.google.com/file/d/10b39IekUdpBHlcTslZ-BlNRyH5uqPUe1/view?pli=1 

After downloading, drag the package into the Project window and import. 

Go to the `Oculus Folder` and in `Prefabs` you will find a `Left Hand Model` and `Right Hand model`.
Drag each prefab to its corresponding object in the scene. 
  
Now, you should see the hand models following the movement of hand presence.

## Moving Forward to Modifications, Input, Continous Movement, and Interactables.

Having setup VR with Unity, we have the foundations for our project set up. Moving forward, it is important to consider the additional changes we should include in our project set up to allow users to use a wider variety of reality technologies. This may require installing **Open XR** rather than just installing plugins and packages for **Oculus**. 

With our hand presence set up, we can move on to user intput and hand animation. Then, our project should focus on using this updated hand presence to interact with interactables in different ways. Once we have these methods down, we can start working on the detailed design of the hardware interactables and how they interact with our hands and eachother. 

Good luck. 

  
 
 
