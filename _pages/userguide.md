---
title: User's Guide
subtitle: Goo allows you to create your first 3D digital tissues in just a few clicks.
description: ''
featured_image: ''
---

<b>Installation</b>

1. Install one of the Blender 3 releases from <a href="https://www.blender.org/download/">https://www.blender.org/download/</a>. We recommend using Blender 3.3.
2. Clone the <a href="https://github.com/smegason/Goo">Goo repository</a> (or download and unzip). 
3. In Blender, go to <i>Edit>Preferences</i>. Then, check <i>Add Mesh: Extra Objects</i> in the ‘Add-ons’ tab. 
4. In <i>Edit>Preferences</i>, go to the File Paths tab and add the <i>/path_to_your_Goo_clone/Goo/scripts/</i> folder to <i>Scripts</i>. 
5. Re-start Blender. 

<figure>
  <img src="images\demo\blender_edit_preferences.jpg" alt="" style="width:25%"> <img src="images\demo\blender_add_mesh.jpg" alt="" style="width:45%">
  <figcaption>Left: nagivate to the preferences. Right: enable <i> Add Mesh: Extra Objects</i> add-on </figcaption>
</figure>

<b>Your first script</b>

1. Open Blender and its <i>Scripting</i> tab. 
2. Declare your first cell collection and colors for cell material:

```python
from goo import goo
import bpy
goo.setup_world() 

# colors 
goo.add_material(name = "green", r = 0, g = 0.1, b = 0)
goo.add_material(name = "red", r = 0.1, g = 0, b = 0)
# create first collection
goo.make_collection(name = "my_cell_collection")
```

3. Declare your first two cells, one in green and the other in red: <br>

```python    
# create first cell
goo.make_cell(name = "my_first_cell", loc = (0,0,0), \
                material = "green", collection = "my_cell_collection")
# create second cell
goo.make_cell(name = "my_second_cell", loc = (0,2,0), \
                material = "red", collection = "my_cell_collection")
```

4. Create your first scene by clicking the play button in the scripting tab of Blender. 
5. Yay. You have created your first cells in Blender using Goo. Next steps elaborate on how to add adhesion forces and how to animate the scene using Blender's physics engine. 

<b>Add cell adhesion</b>

The current scene is static as no interactions between cells have been declared. 
1. Declare the corresponding adhesion forces: 

```python
# create first force collection
goo.make_collection(name = "my_force_collection")           
# declare first force
goo.make_force(force_name = "my_first_force", cell_name = "my_first_cell", \ 
                strength = -1000, falloff = 1, collection = "my_force_collection")
# declare second force
goo.make_force(force_name = "my_second_force", cell_name = "my_second_cell", \
                strength = -1000, falloff = 1, collection = "my_force_collection")
```

<b>Add simulation details</b>

```python
# set simulation parameters for cell stiffness
goo.simulation_stifness(tension = 1, compression = 1, shearing = 1, bending = 1)

# instantiate handlers
handlers = goo.handler_class()
# add forces to simulate
handlers.forces = [fA1, fA2]
# clear the frame
bpy.app.handlers.frame_change_post.clear()
# add adhesion handlers to the simulation
bpy.app.handlers.frame_change_post.append(handlers.adhesion_handler)
```

2. Execute the script in Blender's scripting tab then start the simulation in the <i>Layout</i> tab. 

<b>Biological features supported in Goo</b>

<h4>1. Biological cells </h4>
Goo's cells models biological cells as polygon mesh deformable upon collision with other cells. Cells' physical behavior such as stiffness, pressure and adhesion are tunable for biologists to investigate their impact on cell and tissue shapes. Homotypic adhesion is supported in Goo. 
<h4>2. Cell adhesion </h4>
Adhesion forces are mimmicked by Blender's built-in force fields. In Goo, they emanate from the cell's surface, are local and centered on the cell's center of mass. 
<h4>3. Cell growth </h4>
Goo cells grow at a user-specified rate so that they volume isotropically increase. 
<h4>4. Cell random motility</h4> 
Goo implements cell undirected motility as a uniform random walk. 
<h4>5. Cell division</h4> 
Goo's model for cell division follows Hertwig's rule, stating that cells divide along their long axis. Therefore, the division plane is described as the plane orthogonal to the long axis and that passes by the cell's center of mass. 