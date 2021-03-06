# OSC-to-OBS-Node-Red-Flow
A Node-Red Flow that enables the use of OSC commands to control OBS. 

Set the IP address and port you use in the Websocket Node. Set the port you want to use to receive OSC commands in the udp node (Default 4555).  
Spaces are not used in OSC addresses. This is especially a problem if you plan on using Qlab to send your OSC commands. Some of these OSC commands  
make use of scene names and source names in OBS which do allow spaces. To get around this replace spaces in scene names with an \*. 
Any spaces in scene names, filter names, source names, etc can be replaced with an \*. For example if you want to switch to 
a scene named "Scene 1" the command would be /Scene/Scene\*1.  It's probably easier to just avoid spaces in your scene and source names. If you want to use a /* in  
your source or scene name then I can't help you.

## Supported commands:

**Set Current Scene** /Scene SceneName (string)  
*example* /Scene Intro  
  
**Set Filter Visibility** (enable/disable filters) /FilterVisibility/SourceName/FilterName/ 0,1 (int 0=disable 1=enable)  
*example* /FilterVisibility/Camera/Blur 0
  
**Opacity** (add a color correction filter to the source you want to control.) /Opacity/SourceName (int 0-100)  
*example* /Opacity/Camera 50   
  
**Set Source Visibility** /SourceVisibility/SceneName/Source 0,1 (int 0=disable 1=enable)  
*example* /SourceVisibility/Intro/Graphic 1
  
**Volume** /Volume/SourceName (float in dB -100-20 NOTE:OBS mixer only has a range of -60-0dB however OBS supports larger values. Anything below -100 will be -inf)  
*example* /Volume/mic -10  

**Set Source Position of both X and Y axis** /SetSourcePosition/SceneName/SourceName/ (X postion as int) (Y position as int)   
*example* /SetSourcePositon/MainCamera  640 540

**Set Source Position X axis** /SetSourcePositionX/SceneName/SourceName/ (X postion as int)   
*example* /SetSourcePositonX/MainCamera  640

**Set Source Position Y axis** /SetSourcePositionY/SceneName/SourceName/ (Y postion as int)   
*example* /SetSourcePostionY/Maincamera 520  

**Set Source Scale** /SetSourceScale/SceneName/SourceName (Value as float 1=100 percent scale)  
*example* /SetSourceScale/Scene_2/cam 1.5  

**Set Preview Scene** /ScenePreview/SceneName  
*example* /ScenePreview/Scene_2  

**Set Source Rotation** /SourceRotate/SceneName/SourceName (value as float in degrees)  
*example* /SourceRotate/Scene_2/Camera 180  

**Enable Studio Mode** /EnableStudioMode  
*example* /EnableStudioMode  

**Disable Studio Mode** /DisableStudioMode  
*example* /DisableStudioMode  
  
**Transition from preview** /TransitionTake  
*example* /TransitionTake  

