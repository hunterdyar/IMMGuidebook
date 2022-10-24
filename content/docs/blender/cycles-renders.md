---
title: Faster Renders in blender
draft: true
---

## Cycles

### Bounces
- Move lights objects further from geometry.
- Use emmisive materials for on-object lights instead of lights that are close.
- Prevent lights from intersecting geometry (note 'light radius')
- Every bounce needs more samples. If we are primarily lighting our scene by shining a light at a surface, and letting that surface be the "light source", we are going to need a lot more samples.
- Try not to light too much of the scene using bounced lighting. The more bounced lighting, the more samples we need for smooth renders.
