---
layout: post
title: "My favourite geometric proof for a 10 year old."
categories: ml
---


## Angles, Rotating Pens and Polygons 
Imagine a pen lying parallel to the base of the triangle, with the lead pointing to the right.

1. Rotate the pen clockwise so that it is parallel to the right side of the triangle. You've successfully spun the pen $A$ degrees.

2. Continue the clockwise rotation, and rotate it until it is parallel to the left side of the triangle. You've now spun it $B$ more degrees.

3. Finally, rotate the pen until it is parallel to the base again. You've spun it an additional 
$C$ degrees.

In these three steps, you’ve rotated the pen by 
$A+B+C$ degrees. If you keep track, you’ll notice that the pen is pointing in the opposite direction, meaning it has completed half a revolution, or 180 degrees.

No matter the angles of the triangle, the pen will always end up pointing in the opposite direction when it reaches the base again. Therefore, the combined sum of the interior angles is always 180 degrees.

<svg viewBox="50 0 400 400" xmlns="http://www.w3.org/2000/svg">
  <polygon points="250,50 400,300 100,300" 
           fill="none" 
           stroke="#333" 
           stroke-width="3" />
  
  <g>
    <g id="pen">
      <rect x="0" y="-10" width="60" height="20" rx="2" fill="#3498db" />
      <polygon points="70,0 60,-10 60,10" fill="#2c3e50" />
    </g>
    
    <animateMotion id="initialPos"
      path="M 0,0 L 200,200"
      begin="0s; reset.end"
      dur="0.01s"
      fill="freeze" />
    
    <animate id="wait1"
      attributeName="opacity"
      from="1"
      to="1"
      begin="initialPos.end"
      dur="0.5s"
      fill="freeze" />
    
    <animateTransform id="rotate1"
      attributeName="transform"
      type="rotate"
      from="0 70 0"
      to="60 70 0"
      begin="wait1.end"
      dur="1s"
      fill="freeze" />
    
    <animate id="wait2"
      attributeName="opacity"
      from="1"
      to="1"
      begin="rotate1.end"
      dur="1s"
      fill="freeze" />
    
    <animateTransform id="rotate2"
      attributeName="transform"
      type="rotate"
      from="60 10 0"
      to="120 10 0"
      begin="wait2.end"
      dur="1s"
      fill="freeze" />
    
    <animate id="wait3"
      attributeName="opacity"
      from="1"
      to="1"
      begin="rotate2.end"
      dur="1s"
      fill="freeze" />
    
    <animateTransform id="rotate3"
      attributeName="transform"
      type="rotate"
      from="120 50 40"
      to="180 50 40"
      begin="wait3.end"
      dur="1s"
      fill="freeze" />
    
    <animate id="finalWait"
      attributeName="opacity"
      from="1"
      to="1"
      begin="rotate3.end"
      dur="1s"
      fill="freeze" />
    
    <animateTransform id="reset"
      attributeName="transform"
      type="rotate"
      from="180 0 0"
      to="0 0 0"
      begin="finalWait.end"
      dur="0.01s"
      fill="freeze" />
  </g>
</svg>

#### Generalization

The nice thing with this perspective, is that you can apply it to any kind of polygon, irregular or not. Furthermore, exterior angles are covered by rotating the pen anti-clockwise.

TODO: add picture 
