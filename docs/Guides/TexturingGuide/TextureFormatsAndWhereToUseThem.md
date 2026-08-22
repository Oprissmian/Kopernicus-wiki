# Texture Formats And Where To Use Them

Kerbal Space Program is able to use different types of texture formats that apply to various applications. The three formats mainly used by the game itself and by mods are .png, .truecolor & .dds

While most mods have documentation on what texture formats to use in which situation in some cases said documentation is either incomplete or outdated, so this guide aims its best to cover all the texture formats and their use cases for Kopernicus, ParallaxContinued, Scatterer, EVE Volumetrics V5 & Singularity.

>  [!TIP]
> For further information on the .dds format check out ballisticfox's guide [here](../DDSFormatGuide/index.md)

**Note: For the "Mipmaps recommended?" collum a "Yes" means that mipmaps are strongly recommended/required as they help with various things that make the texture look better and gives better performance. A "No" means that mipmaps aren't needed/recommended, but in most cases still having them shouldn't add too much of a performance cost.**

---

### Kopernicus Textures

| Useage Case       | Format to use (subformat/compression for .dds is in parentheses)    | Mipmaps recommended?   | Notes |
| :-----            | :---              | :---: | ------- |
| Biome Map         | .truecolor        | No    | While some mods use L8 .dds or other formats .truecolor allows for the most colors and is the easist to make. |
| Ring Texture      | .dds (BC7)        | Depends | Use mipmaps if the ring uses a tiled texture, otherwise if the texture isn't tiled don't use mipmaps. |
| Backlit Ring Texture | .dds (BC7)     | Depends | Use mipmaps if the ring uses a tiled texture, otherwise if the texture isn't tiled don't use mipmaps. |
| Scaled Color Map  | .dds (BC7)        | Yes   | The alpha value in the texture influences the gloss of the Scaled Color Map, it is recommended on planets with oceans to use very low alpha for the parts of the texture representing land and very high/full alpha for the parts of the texture representing ocean. |
| Scaled Normal Map | .dds (BC3n/DXT5nm) | Yes  | While KSPTextureLoader allows for BC5 normals to be loaded into the game the current Kopernicus shaders are not yet built to use BC5 for normal maps. |
| Scaled Emissive Map | .dds (BC1/DXT1) | Yes   | Needs [VertexColorMapEmissive](https://github.com/jamespglaze/VertexColorMapEmissive), using `blendMode = Additive`. |
| Rim Color Ramp    | .dds (BC7)        | Yes   | Used for the Atmospheric Shader ( `type = Atmospheric` in the ScaledVersion node) for the atmospheric rim effect. |
| Noise Map         | .dds (BC4)        | Yes   | Only used for the Star Shader ( `type = Star` in the ScaledVersion node). |
| Sunspot Map       | .dds (BC4)        | Yes   | Only used for the Star Shader ( `type = Star` in the ScaledVersion node). |
| Terrain Texture(s) | .dds (BC7)       | Yes   | This should by a greyscaled texture of e.g. soil with the alpha value influencing the gloss. |
| Terrain Normal Map(s) | .dds (BC3n/DXT5nm) | Yes | See the explanation given in the Scaled Normal Map row. |
| PQS Heightmap      | .dds (R8 for 8 bit; R16 for 16 bit)     | No    | For use in the PQS Mods `VertexHeightMap`, `VertexMitchellNetravaliHeightMap` or `VertexHeightMapBicubic` (VertexHeightMapBicubic is provided by [AdvancedPQSTools](https://github.com/CharonSSS/AdvancedPQSTools), VertexMitchellNetravaliHeightMap is provided by the [mod of the same name](https://github.com/pkmniako/Kopernicus_VertexMitchellNetravaliHeightMap)). |
| PQS Colormap      | .dds (BC7)        | No    | For use in the PQS Mods `VertexColorMap` or `VertexColorMapBlend`. For celestial bodies with oceans it is highly recommended to use a separate Colormap for PQS, otherwise for non-oceanic/vaccum worlds you can use the same Colormap used by `ScaledVersion`. |

