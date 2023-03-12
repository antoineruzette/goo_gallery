---
title: User's Guide
subtitle: Goo allows you to create your first 3D digital tissues in just a few clicks.
description: ''
featured_image: ''
---

<h2>Installation</h2>

1. Install one of the Blender 3 releases from <a href="https://www.blender.org/download/">https://www.blender.org/download/</a>. We recommend using Blender 3.3. Remember the folder location of Blender's executable file. 
2. Clone the <a href="https://github.com/smegason/Goo">Goo repository</a> (or download and unzip). 
3. In Blender, go to <i>Edit>Preferences</i>. Then, check <i>Add Mesh: Extra Objects</i> in the ‘Add-ons’ tab. 
4. In <i>Edit>Preferences</i>, go to the File Paths tab and add the <i>/path_to_your_Goo_clone/Goo/scripts/</i> folder to <i>Scripts</i>. 
5. Re-start Blender. 

<div>
  <img src="images\demo\blender_edit_preferences.jpg" height="200"> 
  <img src="images\demo\blender_add_mesh.jpg" height="200">

  Left: nagivate to the preferences. Right: enable <i> Add Mesh: Extra Objects</i> add-on
</div>

<h2>Your first script</h2>

<b>Create cells</b>

<ol>
  <li>Open Blender and its <i>Scripting</i> tab.</li>
  <li>Import goo and Blender's Python API, and set up Blender's scene:</li> 
</ol>

```python
from goo import goo
import bpy
goo.setup_world() 
```

<ol start="3">
  <li>Declare your first cell collection, link your first two cells to it. The first cell is displayed in purple, which is the default material and the other in red. Colors are encoded following <a href="https://www.tug.org/pracjourn/2007-4/walden/color.pdf">RGB</a> color model:</li>
</ol>

```python    
# create first collection
goo.make_collection(name = "my_cell_collection")

# create first cell
goo.make_cell(name = "my_first_cell", 
                loc = (0,0,0), 
                collection = "my_cell_collection")
# create second cell
goo.make_cell(name = "my_second_cell", 
                loc = (0,2,0), 
                material = ("red", 0.1, 0, 0), # optional, default = ("purple", 0.007, 0.021, 0.3)
                stiffness = 2, # optional, default = 1
                collection = "my_cell_collection")  
```
<ol start="4">
  <li>Create your first scene by clicking the play button in the scripting tab of Blender.</li>
  <li>Yay. You have created your first cells in Blender using Goo. Next steps elaborate on how to add adhesion forces and how to animate the scene using Blender's physics engine.</li>
</ol>

<b>Add cell adhesion</b>

Cells do not interact yet thus declare the corresponding adhesion forces: 

```python
# create first force collection
goo.make_collection(name = "my_force_collection")           
# declare first force
goo.make_force(force_name = "my_first_force", 
                cell_name = "my_first_cell", 
                strength = -1000, 
                collection = "my_force_collection")
# declare second force
goo.make_force(force_name = "my_second_force", 
                cell_name = "my_second_cell",
                strength = -1000, 
                falloff = 1, # optional, default = 1
                collection = "my_force_collection")
```

<b>Add simulation details and launch</b>

Handlers wrap up functions from Blender and Goo to update Blender's scene when certain critera are met e.g. triggers cell division. 

```python
# launch simulation
goo.launch_simulation(start = 1, # optional, default = 1
                      end = 250, # optional, default = 250
                      filepath = "path_to_data_file//file.json", # if data = True
                      adhesion = True; # optional, default = True
                      growth = False, # optional, default = False
                      division = False, # optional, default = False
                      motility = False, # optional, default = False
                      data = False # optional, default = False
                      )
```

<b>Execute your script</b>

1. Execute your script from Blender's <i>Scripting</i> tab then run the simulation in Blender's <i>Layout</i> tab (shortcut: `spacebar`). 
2. Execute and run your Python/Goo script from a VSCode terminal with the following command: 

```python
python simulations/blender_background.py
```

`blender_background.py` specifies your Blender executable path and the path to your newly created Goo script. 

```python
subprocess.run(
["<your_blender_folder>\\blender.exe",
"--python",
"<your_path>\\my_fist_script.py"])
```

<h2>Biological features supported in Goo</h2>

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