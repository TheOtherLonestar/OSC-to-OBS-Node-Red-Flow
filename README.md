# OSC-to-OBS-Node-Red-Flow
A Node-Red Flow that enables the use of OSC commands to control OBS. 

Set the IP address and port you use in the Websocket Node. Set the port you want to use to receive OSC commands (Default 4555).
Any spaces in scene names, filter names, source names, etc can be replaced with an \*. For example if you want to switch to 
a scene named "Scene 1" the command would be /Scene/Scene\*1

## Supported commands:

**Set Current Scene** /Scene/SceneName *example* /Scene/Intro  
**Set Filter Visibility** (enable/disable filters) /FilterVisibility/SourceName/FilterName/(true,false)\n *example* /FilterVisibility/Camera/Blur/true  
**Opacity** (add a color correction filter to the source you want to control) /Opacity/SourceName (Value as int 0-100)  
**Set Source Visibility** /SourceVisibility/SceneName/Source/(true,false)  
**Volume** /Volume/SourceName (Value as float 0-1)  
**Set Source Position X axis** /SetSourcePositionX/SceneName/Source/Name/ (X postion as int)   
**Set Source Position Y axis** /SetSourcePositionY/SceneName/Source/Name/ (Y postion as int)   
**Set Source Scale** /SetSourceScale/SceneName/SourceName (Value as float 1=100 percent scale)  
**Set Preview Scene** /ScenePreview/SceneName  
**Set Source Rotation** /SourceRotate/SceneName/SourceName (value as float in degrees)  
**Enable Studio Mode** /EnableStudioMode  
**Disable Studio Mode** /DisableStudioMode  
**Transition from preview** /TransitionTake  

