---
layout: default
title: Modeling Optimizations
nav_order: 4
---

# Modeling Optimizations

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

This section describes different optimizations whould can / should be done when exporting a mesh for use in Morrowind.

## Remove Extra Nodes

When modelling in Blender, Blender will often insert extra shapes when can clutter a NIF. This can be fixed by deleting extra shapes before exporting.

1. Select all of the shapes of your model.
2. `CTRL` + `j` to join the shapes together.
3. Select the newly joined shape.
4. `CTRL` + `i` to select inverse.
5. `x` to delete the extra shapes.

## Remove Object Transformations

Before exporting, make sure your object is at 0,0,0. Open the Item -> Transform window and set Location and Rotation transforms to 0. You can also select the object and use `ALT`+`P` and clear + keep parent transforms.

## Combine Shapes of Same Material

1. Go into Edit mode and select all vertices (`A`).
2. `P` and separate by materials.
3. For each separated object which uses the same material, rejoin the objects with `CTRL`+`J`.
4. In the materials window, delete the duplicate material for the joined object.

## Add Collision Mesh

Collision meshes help Morrowind handle pathfinding and AI more efficiently. You should have a collision mesh for any static objects.

1. Add a new Axis / Empty object adjacent to your object.
2. Rename the empty object `Collision`.
3. Duplicate your normal object and move the duplicate into the `Collision` object.
4. Hide the original object for ease of work.
5. Merge the objects of the duplicate objects, then simpify the mesh as much as possible with dissolve or other tools.
6. Remove material proeprties from the duplicate objects.
7. Disable hiding on the original objects.
