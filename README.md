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

### Audio
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

#### PlayBgm
*This function plays a sound file as background music (BGM).*

Example:
```lua
PlayBgm:{"symbol":"BGM_EVE_SEPARATION_01","fadeInTime":0.0,"isLoop":true,"channel":1,"volume":1.0,"volumeSymbol":"DEFAULT"}
```
Plays the sound file BGM_EVE_SEPERATION_01 with no fade-in with 100% volume, and it is looping.

Syntax matches the syntax of PlaySe.
