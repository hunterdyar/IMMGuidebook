---
title: How to Bake Procedural Materials (Blender to Unity)
oldlink: https://guidebook.hdyar.com/docs/blender/toolbox/bake-textures-in-blender-to-unity/
---

## How to Bake Procedural Materials into PBR Maps

### Setup

1. Apply your material to a square plane; adjust settings to your liking.  
![Material Display](/images/blender/toolbox/material-display.png)
2. UV Unwrap your plane. (**Important!**)
3. Add an Image Texture to the Shading Node Workspace for each texture type you want to bake (diffuse, AO, normal, etc.)

### Diffuse Map Example (Base Color)

1. Use cycles (can only bake materials in cycles), set **Bake Type** to **Diffuse**  
![Bake Type to Diffuse](/images/blender/toolbox/bake-type-diffuse.png)
2. Disable **Direct** and **Indirect** contributions under **Influence**  
![Disable Direct and Indirect Contributions](/images/blender/toolbox/disable-direct-indirect-contr.png)
3. Set **Margin --> Size** to zero pixels  
![Margin Size](/images/blender/toolbox/margin-size.png)
4. While selecting your **Diffuse Image Texture** node, click the **Bake** button.  
![Diffuse Image Texture Node](/images/blender/toolbox/diffuse-image-texture-node.png)
5. Save your Diffuse Image Texture wherever you want.  
![Diffuse Image Texture Display](/images/blender/toolbox/diffuse-image-texture-display.png)

- Other textures can be baked in the same way by just changing the Bake Type.  
![Bake Type Drop Down](/images/blender/toolbox/bake-type-dropdown.png) ![Normal Map Texture](normal-map-texture.png)

### Baking Metallic Maps
Metallic Maps are a bit harder to bake in Blender (3.3.0 as of writing this) because there is no Metallic option. You must bake it to a placeholder Bake Type and simply rename the file.  

A good way to do this is to take advantage of the Node-Wrangler Addon’s Node Preview feature. With the addon enabled, you can CTRL + SHIFT + CLICK on any node to preview its data. Behind the scenes, it’s setting the value coming off the node as an emission value. Here’s how we can exploit this:  

1.	Preview the final node in your tree of metallic value nodes.  
![Final Node Preview](/images/blender/toolbox/final-node-preview.png)  
Alternatively, if your material has a flat metallic value, you can preview a value node set to the metallic value.  
![Flat Metallic Value](/images/blender/toolbox/flat-metallic-value.png)  
2. Set the **Bake Type** to **Emit**.  
![Emit Bake Type](/images/blender/toolbox/emit-bake-type.png)  
3. Bake as usual. (Remember to have your desired image texture node selected!)  

## Importing into Unity
![Import to Unity](/images/blender/toolbox/import-to-unity.png)

### How to Set up Textures in Unity Materials

1. Unity and Blender have slightly different names for each map.

| Blender      | Unity     | Definition |
|--------------|-----------|------------|
| Diffuse      | Albedo    | RGB Base Color of Material|
| Glossy       | Metallic***| BW/A How much Material looks like metal (kinda)|
|Roughness     | Smoothness***| BW/A How light scatters across a surface|
|Normal        | Normal| RGB values that determine how light bounces per pixel|
|Height        | Height | BW how much each pixel displaces the mesh|
|Ambient Occlusion| Occlusion| BW contains lighting data for soft/ambient shadows|  
2. You can simply import your baked textures and drag and drop them into the corresponding texture slots. Some texture maps, like Normal maps, require their type to be set to the correct value.  
![Normal Map in Task Bar](/images/blender/toolbox/normal-inspector.png)

- **Important Note:** Unity combines the Metallic and Roughness maps from Blender into one map. The alpha channel of the Metallic Map determines *Smoothness*. Generally, it is okay to use Blender’s Roughness for Unity’s Metallic Map but **INVERT THE VALUES OF BLENDER’S BAKED ROUGHNESS MAP** or the Metallic/Smoothness will be inverted.  

### Combined Roughness and Metallic

This compositing setup can be used to prepare a Roughness + Metallic Map for Unity:  
![Compositing Node Setup](/images/blender/toolbox/compositing-node-setup.png)  

After compositing, set your render size to the preferred texture size and complete your render.  
![Setting Texture Size](/images/blender/toolbox/setting-texture-size.png)
