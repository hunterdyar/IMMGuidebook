---
title: Coroutines
oldlink: https://guidebook.hdyar.com/docs/programming/advanced/coroutines/
---
## Coroutines Overview Video
{{< youtube 8fIF5F3AvJo >}}

## Implementing Coroutines for grid movement in a project.
{{< youtube Rg2SsZ8yy8c>}}

## Coroutine Syntax

{{< highlight csharp >}}
void Start()
{
    //whenever we want to start a coroutine, we call 'StartCoroutine'
    StartCoroutine(CoroutineName());    
}

//a normal function of return type "IEnumerator". Can take arguments.
IEnumerator CoroutineName()
{
    //do something
    yield return null;//wait for right after next update loop
    yield return new WaitForSeconds(0.5f);//wait for half a second
}

{{< /highlight >}}

## Movement With Coroutines Example
{{< highlight csharp >}}

public IEnumerator MoveTo(Vector3 destination, float timeToMove)
{
    Vector3 start = transform.position;
    float t = 0;
    while (t < 1)
    {
        t = t + Time.deltaTime/timeToMove;//it will take t timeToMove seconds to get from 0 to 1.
        transform.position = Vector3.Lerp(start, destination,t);
        yield return null;
    }
    //Snap to exactly the destination position
    transform.position = destination;
}
{{< /highlight >}}
