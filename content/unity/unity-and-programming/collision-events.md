---
title: Collision Events
---
# Unity Collision Events

## Overview Video
A (slow) video walking through setup and common mistakes for using collision events.

{{< youtube zZne0_Ic3tM >}}

## Example

A really common pattern when using collision events is to check if the thing we hit has a certain tag, or has a certain component.

GetComponent is slower than using CompareTag, so we prefer that - however, it can quickly become impractical.

{{< highlight csharp >}}
void OnCollisionEnter(Collision other)
{
    if (other.gameObject.CompareTag("Player"))
    {
        //code for if I hit the player
    }
    //
    Enemy hitEnemy = other.gameObject.GetComponent<Enemy>();
    if (hitEnemy != null)
    {
        //code for if I hit a gameObject with an Enemy component.
        //We should basically always check for null. 
    }
}
{{< /highlight >}}

## Split Up The Logic
A common mistake is to try and put all of the logic for a collision on the same script. In fact, all scripts on both gameObjects involved with a collision will have the collision event functions called. This lets us split our logic up into appropriate places.

Lets say we move around and dodge asteroids. We can have:
- an OnCollisionEnter function on a PlayerMovement script that plays sounds when we bonk into walls
- an OnCollisionEnter function on a Player script that checks if we got hit by an asteroid and lose health, flash a color, and play a hurt sound.
- an OnCollisionEnter function on the asteroid script that destroys itself when it hits various thing, and plays a sound.

That's taking three separate pieces of logic: asteroid handling, player-wall handling, and player-asteroid handling, and moving them to locations that are appropriate. It's certainly possible to do all of this in one code, but we discover quickly - as we add different enemy types, for example - that it gets really unwieldy and is prone to bugs. Keeping things compartmentalized makes our life easier. 