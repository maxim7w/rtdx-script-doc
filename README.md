# PMD: RTDX - Scripting Documentation

Internal scripts are stored as .lua source code and can be opened with any text editor. They are stored in:
```javascript
romfs/Data/StreamingAssets/native_data/scripts
```

They consist of 4 different content types:
- -- <<★ScenePartitionBlob  
 This marks a section at the beginning of a .lua setting scene properties.
- -- <<★LuaBlob  
 This marks a section of raw LUA code.
- -- <<★ActCommandBlob  
 This marks a section of scripting in the game engine.
- -- <<★ActAssetBlob  
 This marks a section in which asset properties are set.
- -- <<★CutsceneBlob  
 This marks a section in which a scripted cutscene is played.

Most scripts have japanese comments or backup text explaining the content.
## Audio
#### PlaySe
*This function plays a sound file as a sound effect.*

Example:
```lua
PlaySe:{"isWait":false,"symbol":"SE_ENV_BREEZE_LP","fadeInTime":0.5,"volume":1.0,"volumeSymbol":"DEFAULT"}
```
Plays the sound effect SE_ENV_BREEZE_LP with a fade-in of 0.5s with 100% volume.

Syntax:
- isWait: bool (true/false)
- isLoop: bool (true/false)
- symbol: string (internal sound name)
- fadeInTime: float (time in seconds)
- volume: float (0%-100% => 0-1.0)
- volumeSymbol: string (?)

#### StopSe
*This function stops a currently playing sound effect.*

Example:
```lua
StopSe:{"symbol":"SE_EVT_PERIPPAA_FLY_03_LP","fadeInTime":1.5}
```
Syntax:
- symbol: string (internal sound name)
- fadeInTime: float (time in seconds)

#### PlayBgm
*This function plays a sound file as background music (BGM).*

Example:
```lua
PlayBgm:{"symbol":"BGM_EVE_SEPARATION_01","fadeInTime":0.0,"isLoop":true,"channel":1,"volume":1.0,"volumeSymbol":"DEFAULT"}
```

Plays the sound file BGM_EVE_SEPERATION_01 with no fade-in with 100% volume, and it is looping.

Syntax matches the syntax of PlaySe.

## Graphics and Rendering

#### SetVisible
*Makes a character visible or invisible.*

Example:

```lua
  CH:HERO:{
    0::SetVisible:{"visible":false}
  }
```

Syntax:
- char index, for example CH:HERO, indicating the affected hero character
- visible: bool (true/false)

#### ScreenFade
*Makes the screen fade to a specific position.*

Example:

```lua
ScreenFade:{"moveCameraParam":{"distanceMode":0,"toCamParam":{"refSymbol":"","directData":{"fovType":105,"fieldOfView":60.0,"near":0.10000000149011612,"far":1000.0,"rotateType":100,"pos":{"x":0.0,"y":0.0,"z":0.0},"rotateQ":{"x":0.0,"y":0.0,"z":0.0,"w":0.0},"rotateAtPos":{"x":0.0,"y":0.0,"z":1.0},"rotateAtRollDeg":0.0}}},"isWait":true,"fadeMode":100,"fadeLayer":0,"fadeTime":0.5,"fadeTimeSymbol":"","fadeColorStart":{"r":0.0,"g":0.0,"b":0.0,"a":0.0},"fadeColorEnd":{"r":0.0,"g":0.0,"b":0.0,"a":0.0}}
```

Syntax: WIP

#### SetCam
*Sets camera parameters.*

Example:

```lua
CAMERA::{
    0::SetCam:{"cameraParam":{"refSymbol":"","directData":{"fovType":0,"fieldOfView":40.0,"near":0.10000000149011612,"far":1000.0,"rotateType":100,"pos":{"x":-36.47456359863281,"y":1.4158525466918946,"z":0.30426549911499026},"rotateQ":{"x":-0.014602495357394219,"y":0.9118948578834534,"z":-0.032567769289016727,"w":-0.40886905789375307},"rotateAtPos":{"x":0.0,"y":0.0,"z":1.0},"rotateAtRollDeg":0.0}}}
  }
```
Syntax:
- cameraParam: string
 - refSymbol: string
 - directData: string
   - fovType: number
   - fieldOfView: number (FOV)
   - near: float
   - far: float
   - rotateType: number
   - pos: string
     - x: float
	  - y: float
	  - z: float
	- rotateQ: string
	    - x: float
	    - y: float
	    - z: float
	    - w: float
	- rotateAtRollDeg: float

