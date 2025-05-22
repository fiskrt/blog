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

<svg viewBox="0 0 400 400" width="400" height="400" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>
  
  <path d="M 200 100 L 300 250 L 100 250 Z" 
        fill="none" 
        stroke="#2d3748" 
        stroke-width="3"/>
  
  <g font-family="Arial" font-size="16" font-weight="bold">
    <text x="85" y="255" text-anchor="middle" fill="#2d3748">
      C
      <animate attributeName="font-size" values="16;24;24;16" dur="1.5s" begin="rotate3.begin-0.2s" fill="freeze"/>
    </text>
    <text x="200" y="90" text-anchor="middle" fill="#2d3748">
      B
      <animate attributeName="font-size" values="16;24;24;16" dur="1.5s" begin="rotate2.begin-0.2s" fill="freeze"/>
    </text>
    <text x="315" y="255" text-anchor="middle" fill="#2d3748">
      A
      <animate attributeName="font-size" values="16;24;24;16" dur="1.5s" begin="rotate1.begin-0.2s" fill="freeze"/>
    </text>
  </g>
  <defs>
    <g id="pen">
      <rect x="-30" y="-10" width="60" height="20" fill="#4a5568"/>
      <path d="M 30 -10 L 50 0 L 30 10 Z" fill="#1a202c"/>
      <rect x="-37" y="-9" width="7" height="18" fill="#f56565" rx="1"/>
    </g>
  </defs>
        
  <g>
    <animateTransform
      id="move1"
      attributeName="transform"
      type="translate"
      from="200 200"
      to="260 250"
      dur="1s"
      begin="0s;move4.end+1s"
      fill="freeze"/>
    
    <animateTransform
      id="move2"
      attributeName="transform"
      type="translate"
      from="260 250"
      to="200 100"
      dur="1s"
      begin="rotate1.end+0.5s"
      fill="freeze"/>
    
    <animateTransform
      id="move3"
      attributeName="transform"
      type="translate"
      from="200 100"
      to="140 250"
      dur="1s"
      begin="rotate2.end+0.5s"
      fill="freeze"/>
    
    <animateTransform
      id="move4"
      attributeName="transform"
      type="translate"
      from="140 250"
      to="200 200"
      dur="1s"
      begin="rotate3.end+0.5s"
      fill="freeze"/>
    
    <g>
      <animateTransform
        id="rotate1"
        attributeName="transform"
        type="rotate"
        from="0"
        to="60"
        dur="1s"
        begin="move1.end+0.5s"
        fill="freeze"/>
        
      <animateTransform
        id="rotate2"
        attributeName="transform"
        type="rotate"
        from="60"
        to="120"
        dur="1s"
        begin="move2.end+0.5s"
        fill="freeze"/>
      
      <animateTransform
        id="rotate3"
        attributeName="transform"
        type="rotate"
        from="120"
        to="180"
        dur="1s"
        begin="move3.end+0.5s"
        fill="freeze"/>
      
      <animateTransform
        id="reset"
        attributeName="transform"
        type="rotate"
        from="180"
        to="360"
        dur="0.01s"
        begin="move4.end+0.99s"
        fill="freeze"/>
      
      <use href="#pen"/>
    </g>
  </g>
</svg>

#### Generalization

The nice thing with this perspective, is that you can apply it to any kind of polygon, irregular or not. Furthermore, exterior angles are covered by rotating the pen anti-clockwise.

TODO: add picture 
