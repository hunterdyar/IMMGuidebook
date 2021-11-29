---
title: Clicking On Objects in 3D

---
# Clicking On Objects in 3D
Clicking on objects is a non-trivial task, despite how often we implement this behavior. Luckily, it's not terribly difficult.

There are two challenges: 

1. The mouse is in screen-space, calculated in pixel-distance away from the top-left of the screen. Objects, on the other hand, are in world-space: they have a position in the scene. 
2. Objects in 3D can overlap each other visually. How do we know which one is "under" the mouse, and only select it?

To solve the first challenge, we need some kind of system to go from screen space to world space. Well, that's the **camera.** Camera's are basically devices to convert from world space to screen space, it's trivial for them to go the other way too! We will get a reference to the camera so we can use functions that the camera provides.

{{< highlight csharp >}}

private Camera cam;

void Awake(){
	cam = Camera.main;
}
{{< /highlight >}}

Now that we have that, we need to figure out when we click, and get the mouse coordinates in screen-space:
{{< highlight csharp >}}
void Update(){
	if(Input.GetMouseButtonDown(0))
	{
		Vector3 mouseScreenPos = Input.mousePosition;
	}
}
{{< /highlight >}}

{{< hint warning >}}
It's considered good practice to store (aka [cache](https://en.wiktionary.org/wiki/cache)) the 'Camera.main' property in a local variable, because behind-the-scenes, it uses a very slow access method: FindGameObjectWithTag("MainCamera"). However, in Unity 2020.2, this was [fixed](https://blog.unity.com/technology/new-performance-improvements-in-unity-2020-2). So  it's okay to use now. I'll still use a cached variable here so this example code remains valid for older unity versions.
{{< /hint >}}

In order to solve the second part of our challenge, we are going to use the physics system. With this solution, it means that objects we want to click on **need colliders**. We will create a ray that extends along the cameras point-of-view, from the mouse position, "back" into the scene. Using a raycast means that first thing it hits will be the closest thing to the camera.

We will use the cameras [ScreenPointToRay](https://docs.unity3d.com/ScriptReference/Camera.ScreenPointToRay.html) function. 

We also don't really need to store the mousePosition as a temporary Vector3 variable, lets just skip that and plug in the "Input.mousePosition" directly to this camera function.

{{< highlight csharp >}}
Ray ray = cam.ScreenPointToRay(Input.mousePosition);
{{< /highlight >}}

Now we need to do a [Raycast](https://docs.unity3d.com/ScriptReference/Physics.Raycast.html). I advise you to research Raycasts more, starting with that above documentation page. It uses a C# feature called an ["out" parameter modifier](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/out-parameter-modifier). "Out" (and "ref") allow a function to modify variables that it takes as parameters. That means we have the return type from the function (in this case, a boolean: did we hit anything at all), it has *another* "returned" value - if we did hit something, the data about it is now available in this variable. The 'out' keyword is how we know that this function is allowed to repalce the data in this variable.

The RaycastHit datatype is a simple data structure used to get information from the hit. Check out the information it holds in the [RaycastHit scriptingAPI documentation](https://docs.unity3d.com/ScriptReference/RaycastHit.html).

Let's put it all together.
   
{{< highlight csharp >}}
private Camera cam;

void Awake(){
	cam = Camera.main;
}

void Update(){
	if(Input.GetMouseButtonDown(0))
	{
		Ray ray = cam.ScreenPointToRay(Input.mousePosition);
		RaycastHit hit;
		if(Physics.Raycast(ray, out hit, 100))
		{
        		Debug.Log("clicked on "+hit.collider.gameObject.name);
   		}
	}
}
{{< /highlight >}}

## Going Further: Only Clicking Certain Things
You can use a layer mask to dertermine what you can and cannot click on. LayerMasks are [bitmasks](https://en.wikipedia.org/wiki/Mask_(computing)), which are annoying to create by hand. If we make one that is serializable, however, it becomes trivially easy to edit in the unity inspector. The Physics.Raycast function takes a layer mask as an argument.

Creating a layer mask:
{{< highlight csharp >}}
[SerializeField] private clickableLayerMask;
{{< /highlight >}}

Allows us to use the Inspector to select our layer(s):
![Layer Mask Property Inspector](/images/unity/toolbox/clickableLayerMask.png)

We need to be sure to put the objects we want to select on the layers here, and objects we don't want to select on a different layer.

We can then pass this in as an argument in the Raycast funtion. The entire example code now looks like this:

{{< highlight csharp >}}
using UnityEngine;

public class ClickingThings : MonoBehaviour
{
	private Camera cam;
	[SerializeField] private LayerMask clickableLayerMask;
	void Awake()
	{
		cam = Camera.main;
	}
	void Update()
	{
		if (Input.GetMouseButtonDown(0))
		{
			Ray ray = cam.ScreenPointToRay(Input.mousePosition);
			RaycastHit hit;
			if (Physics.Raycast(ray, out hit, Mathf.Infinity, clickableLayerMask))
			{
				Debug.Log("clicked on " + hit.collider.gameObject.name);
			}
		}
	}
}
{{< /highlight >}}

{{< hint info >}}
The only other change is for the raycast distance, I replaced "100" with "Mathf.Infinity". You probably want to limit the distance of your raycasts to something appropriate as a small optimization.
{{< /hint >}}