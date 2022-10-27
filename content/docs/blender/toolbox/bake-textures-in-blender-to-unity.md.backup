---
title: How to Bake Procedural Materials into PBR Maps

draft: True

---

## How to Bake Procedural Materials into PBR Maps

### Setup

1. Apply your material to a square plane; adjust settings to your liking.  
![Material Display](/images/blender/toolbox/material-display.png)
2. UV Unwrap your plane. (**Important!**)
3. Add an Image Texture to the Shading Node Workspace for each texture type you want to bake (diffuse, AO, normal, etc.)

### Diffuse Map Example (Base Color)

1. Use cycles (can only bake materials in cycles), set **Bake Type** to **Diffuse**  
![Bake Type to Defuse](/images/blender/toolbox/bake-type-diffuse.png)
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

### Importing into Unity


