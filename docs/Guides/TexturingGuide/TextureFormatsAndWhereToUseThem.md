# Texture Formats And Where To Use Them

Kerbal Space Program is able to use different types of texture formats that apply to various applications. The three formats mainly used by the game itself and by mods are .png, .truecolor & .dds

While most mods have documentation on what texture formats to use in which situation in some cases said documentation is either incomplete or outdated, so this guide aims its best to cover all the texture formats and their use cases for Kopernicus, ParallaxContinued, Scatterer, EVE Volumetrics V5 & Singularity.

>  [!TIP]
> For further information on the .dds format check out ballisticfox's guide [here](../DDSFormatGuide/index.md)

---

### Kopernicus Textures

| Useage Case       | Format to use (subformat/compression for .dds is in parentheses)    | Mimaps recommended?   | Notes |
| :-----            | :---              | :---: | ------- |
| Biome Map         | .truecolor        | No    | While some mods use L8 .dds or other formats .truecolor allows for the most colors and is the easist to make. |
| Scaled Color Map  | .dds (BC7)        | Yes   | The alpha value in the texture influences the gloss of the Scaled Color Map, it is recommended on planets with oceans to use very low alpha for the parts of the texture representing land and very high/full alpha for the parts of the texture representing ocean. |
| Scaled Normal Map | .dds (BC3n/DXT5nm) | Yes  | While KSPTextureLoader allows for BC5 normals to be loaded into the game the current Kopernicus shaders are not yet built to use BC5 for normal maps. |
| Scaled Emissive Map | .dds (BC1/DXT1) | Yes   | Needs [VertexColorMapEmissive](https://github.com/jamespglaze/VertexColorMapEmissive), using `blendMode = Additive`. |
| Rim Color Ramp    | .dds (BC7)        | Yes   | Used for the Atmospheric Shader ( `type = Atmospheric` in the ScaledVersion node) for the atmospheric rim effect. |
| Noise Map         | .dds (BC4)        | Yes   | Only used for the Star Shader ( `type = Star` in the ScaledVersion node). |
| Sunspot Map       | .dds (BC4)        | Yes   | Only used for the Star Shader ( `type = Star` in the ScaledVersion node). |
