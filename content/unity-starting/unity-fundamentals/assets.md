---
title: Assets
type: docs
oldlink: guidebook.hdyar.com/docs/unity/unity-fundamentals/assets/
---
# What are Assets?
An asset is an actual file on your computer. We store Assets in the &#8220;Assets&#8221; folder inside of our unity project folder. Assets are any item in Unity that we may want to use.

When we select an asset in the project window, the Inspector will show us it&#8217;s import properties. These are often very important, they tell Unity how to handle the file. For example: fixing scale issues with 3D models.

It's easier to explain assets if we consider their uses.

## Common Asset Types

#### Image Files

Images, like BMP or Jpeg&#8217;s, and even Photoshop documents directly (I haven&#8217;t utilized this new feature and still export all my sprites as PNG&#8217;s with transparency).

#### 3D Models

Unity supports FBX files for your 3D models. It also supports saving your native file format into the asset folder (ie: .max, .blend, .mb, .ma), and Unity turns them into .fbx&#8217;s when it runs and builds the game. This is useful if you are going back and forth a lot, but it&#8217;s still generally wise to export as FBX, especially if you are sharing/collaborating with others. Keep things from getting too messy.

See the unity manual for information on [importing models](https://docs.unity3d.com/Manual/ImportingModelFiles.html), [Model File Formats.](https://docs.unity3d.com/Manual/3D-formats.html) Getting textures and animations to import with a model correctly (or to associate these things with models that have already been imported) can be tricky, and I won&#8217;t get into the details of this here.

#### Audio Files

Unity supports a wide variety of audio, and will (by default) compress it to when it builds the game. Unity supports mp3, .ogg, .wac, .aif audio files, and  
.mod, .it, .s3m, and .xm tracker modules files.

If you don&#8217;t know what tracker modules are, don&#8217;t worry. Think midi, they are sequence data and short audio samples to build out tracks. This helps create long songs without large file sizes.

#### Scripts

As we work in Unity, we will create lots of Scripts. These are C# or JavaScript files. You can make the files from within unity.

{{< hint info >}}

If you click the **Add Component **in the Inspector and create a **New Script **from here, it will put that script in the base assets folder. Before we open it up in our text editor, we should remember to move it to a Scripts folder, or wherever we want to move it. Unity will keep track of objects that we move around (from within Unity&#8217;s project window), but our IDE/text editors may not.
{{< /hint >}}

## File Structure

Unity technically doesn&#8217;t care where in your project you store your assets. Technically you can have them all just sitting in your assets folder. Don&#8217;t do this. Create folders that categorize your asset. Generally based on type. Almost all of my projects have the following folders: &#8220;Scripts&#8221;, &#8220;Materials&#8221;, &#8220;Models&#8221;, &#8220;Images&#8221;, &#8220;Scenes&#8221;. Your&#8217;s probably should soon.

This organization isn&#8217;t just to keep things pretty. Unity projects can get complicated quickly, and finding assets is going to be important.

You should adopt a standard naming convention for your files, as well. But i won&#8217;t yell at you about that. At the very least, keep things descriptive.
