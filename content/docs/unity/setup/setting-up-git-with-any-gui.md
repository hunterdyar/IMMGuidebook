---
title: Git & Unity Quick Setup 
---

# Setting up Git & Unity



## Setup The Local Repository

1. Create an empty Unity Project, or use an existing project.
2. Initiate a New Repository in the root directory.
3. Add a .gitignore file for Unity.
   1. You can use [this one](https://raw.githubusercontent.com/github/gitignore/main/Unity.gitignore), which is worth reading through. The most important things to tell git to ignore are the Library, Temp, and Logs folders, and the .sln solution file.
   2. Save that above link to a file, and change it's name to ".gitignore". Where the file has no name, and the file extension "gitignore".
4. (Optional) Setup Git LFS. 
   1. This is not a guide on git LFS, but I will note that you *don't* want to use Git LFS for scene files, which some git LFS guides tell you to do. Instead, a better solution is to use Unity's [YAMLMergeTool](https://docs.unity3d.com/Manual/SmartMerge.html) to deal with the complexities of scene files.
5. Stage and Commit the initial project.
   1. We want to commit our Assets (and SampleScene), the packages folder, the ProjectSettings folder.

## Setup the Remote Repository

1. In GitHub, select 'Create a New Repository'.
   1. Give it a name and description.
   2. Do **not** add a readme or a .gitignore. We want this to be a *completely* empty repository.
2. After creating the repository, it should be *empty*. The project page should say something like "Quick Setup...", with some advice on how to add code.
3. Copy the URL (the one that ends in .git) from that Quick Setup box on the empty repository page.
4. In our Git client, add the repository url as a remote.
5. Push our initial changes, double checking we are not committing anything in the Library folder or auto-generated IDE-config folders (like .idea or .vscode).