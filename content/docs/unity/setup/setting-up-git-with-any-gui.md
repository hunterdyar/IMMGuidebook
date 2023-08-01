---
title: Git & Unity Quick Setup 
weight: 10
---

# Setting up Git & Unity

## Notes

1. We need .meta files in the git repo.
2. We should ignore auto-generated files: the Library folder in particular will completely bork a Git repo
3. Users could work in different versions of Unity, but it's heavily discouraged, and can lead to unpredictable consequences.
4. If you use Unity's support for proprietary-files-auto-converted-into-assets, such as using ".blend", ".maya", or ".psd" imports (for Blender, Maya, and Photoshop, respectively), then that software needs to be installed on all the machines using the project. See this [manual](https://docs.unity3d.com/Manual/3D-formats.html) for details, but for this reason it's recommended to export to FBX when in production.
5. You should probably configure [Git LFS](https://www.atlassian.com/git/tutorials/git-lfs) for images, models, and other large file types.
6. Unity has a tool (called "UnityYAMLMerge") that can merge scene and prefab files much better than the default git merge behavior. See the [Smart Merge](https://docs.unity3d.com/Manual/SmartMerge.html) manual page for info how to set it up.

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

## Add Collaborators

In GitHub, go to the project page, go to settings, collaborators, and Invite all of your teammates. They will need to accept the invitation, which is easily done through the auto-sent email.

Collaborators need only Clone the repo, like normal. Once cloned, choose the "Open" option from Unity Hub, and select the projects root folder that you just downloaded. 

---

## Git Software

Keep in mind that git is just metadata that lives with your project. It can be deleted, restarted, and moved around no matter what git tool you are using to call the commands. You can [learn ](https://git-scm.com/docs/gittutorial) the command line commands, or use piece of software that is basically just a graphical interface for calling the same commands. You can have and use multiple pieces of git software at the same time.

Some Git GUI software packages will keep their own copy of the *actual* "git" command line software. Others will require you to [install git](https://www.atlassian.com/git/tutorials/install-git?section=windows#windows) separately on your system.

### Git GUI Software

- [Git Fork](https://git-fork.com/) (What I personally use)
- [GitHub Desktop](https://desktop.github.com/) (Works well for GitHub, not very feature-rich)
- [SourceTree](https://www.sourcetreeapp.com/) (Popular, Free, Good)
- [GitKraken](https://www.gitkraken.com/) (One of my students swears by this one)

See here for a [larger list](https://git-scm.com/downloads/guis).
