# Texture Formats And Where To Use Them

Kerbal Space Program is able to use different types of texture formats that apply to various applications. The three formats mainly used by the game itself and by mods are .png, .truecolor & .dds

While most mods have documentation on what texture formats to use in which situation in some cases said documentation is either incomplete or outdated, so this guide aims its best to cover all the texture formats and their use cases for Kopernicus, ParallaxContinued, Scatterer, EVE Volumetrics V5 & Singularity.

>  [!TIP]
> For further information on the .dds format check out ballisticfox's guide [here](../DDSFormatGuide/index.md)

---

### Kopernicus Textures

| Useage Case       | Format to use (subformat/compression for .dds is in parentheses)    | Mimaps recommended?   | Notes |
| :-----            | :---              | :---: | ------- |
| Biome Map         | .truecolor        | No    | While some mods use L8 .dds or other formats .truecolor allows for the most colors and is the easist to make |
| Scaled Color Map  | .dds (BC7)        | Yes   |