---
title: Simple LERP with Coroutines
oldlink: https://guidebook.hdyar.com/docs/unity/toolbox/simple-lerp-with-coroutines/
---

# Simple Linear Interpolation with Coroutines

Here is an example script that uses a coroutine to [lerp](https://docs.unity3d.com/ScriptReference/Vector3.Lerp.html) between two provided positions.

There is some extra code to allow the script to ping-pong back and forth between the positions.

In a real-life usage, you probably don't want to enter world-positions manually in the unity inspector. You might use offsets, calculating the real-world start and and position by adding them to the current position. You also could use empty gameObjects that you position in the scene. Use public Transform properties, drop them in, and reference their .position property.

{{< highlight csharp >}}
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class LerpPositionSimple : MonoBehaviour
{
	public Vector3 startPosition;
	public Vector3 endPosition;
	public float timeToMove;
	public bool pingPong;
	void Start()
	{
		Move();
	}
	public void Move()
        {
		StartCoroutine(LerpPos(startPosition,endPosition,timeToMove));
	}
	public void MoveFinished()
	{
		if(pingPong)
		{
			//Swap thestart/end position
			Vector3 temp = startPosition;
			startPosition = endPosition;
			endPosition = temp;
			//restart the move
			Move();
		}
	}
    
	IEnumerator LerpPos(Vector3 start, Vector3 end, float timeToMove)
	{
		float t = 0;
		while(t < 1)
		{
			transform.position = Vector3.Lerp(start,end,t);
			t = t + Time.deltaTime / timeToMove;
			yield return null;//Stops here until right after the next update loop, then continues
		}
		//t won't end up exactly at 1, so let's snap it to be precisely where we want.
		transform.position = end;
		//MoveFinished will start the coroutine again if ping-ponging is turned on
		MoveFinished();
	}
}

{{< /highlight >}}

---
# Using Speed instead of TimeToMove
speed is a more useful property than total time to move, because it allows us to adjust our path and not have to re-adjust the total time afterwards. Given a speed, we can calculate a timeToMove value at the start of the coroutine:
{{< highlight csharp>}}
//'speed' is some float value we need to create.
float timeToMove = Vector3.Distance(startPosition,endPosition)/speed;
{{< /highlight >}}
{{< hint info >}}distance is in 'meters', speed is 'meters per second'.  meters divided by (meters divided by second) is seconds. Nice.
{{< /hint >}}

Here is the coroutine function with speed being passed in, instead of timeToMove. It's otherwise the same.

{{< highlight csharp >}}
IEnumerator LerpPos(Vector3 start, Vector3 end, float speed)
{
	float t = 0;
	float timeToMove = Vector3.Distance(startPosition,endPosition)/speed;
	while(t < 1)
	{
		transform.position = Vector3.Lerp(start,end,t);
		t = t + Time.deltaTime / timeToMove;
		yield return null;
	}
	transform.position = end;
	MoveFinished();
}
{{< /highlight >}}
