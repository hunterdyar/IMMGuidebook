---
title: A Basic Level Manager
oldlink: https://guidebook.hdyar.com/docs/unity/toolbox/basic-level-manager/
---
# A Basic Level Manager
For an explanation of this code, see [this video]({{< ref "scene-switching.md" >}}) on scene switching, where the code is written and explained.

## LevelManager.cs
{{< highlight csharp >}}
using UnityEngine;
using UnityEngine.SceneManagement;

public class LevelManager : MonoBehaviour
{
    public void RestartLevel()
    {
        SceneManager.LoadScene(SceneManager.GetActiveScene().name);
    }

    public void GoToNextScene()
    {
        //Get the current level build Index
        int current = SceneManager.GetActiveScene().buildIndex;
        
        //increase it by one
        int next = current + 1;
        int total = SceneManager.sceneCountInBuildSettings;
        
        //If we are at the end of our list, just go back to the first level in the list.
        if (next >= total)
        {
            next = 0;
        }

        //go to build index
        SceneManager.LoadScene(next);
    }
    void Update()
    {

        if (Input.GetKeyDown(KeyCode.R))
        {
            RestartLevel();
        }

        //Cheat codes! Maybe delete this part?
        if (Input.GetKeyDown(KeyCode.N))
        {
            GoToNextScene();
        }
    }
}

{{< /highlight >}}
