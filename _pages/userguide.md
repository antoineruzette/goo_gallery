---
title: User's Guide
subtitle: Goo allows you to create your first 3D digital tissues in just a few clicks.
description: ''
featured_image: ''
---

<b>Installation</b>

1. Install the latest edition of Blender from <a href="https://www.blender.org/download/">https://www.blender.org/download/</a>
2. Clone the Goo repository (or download and unzip)
3. In Blender, go to <i>Edit>Preferences</i>. Then, check <i>Add Mesh: Extra Objects</i> in the ‘Add-ons’ tab. 
4. In <i>Edit>Preferences</i>, go to the File Paths tab and add the <i>/path_to_your_Goo_clone/Goo/scripts/</i> folder to <i>Scripts</i>. 
5. Re-start Blender. 

[Insert screenshots]

<b>Your first script</b>

1. Open Blender and its <i>Scripting</i> tab. 
2. Declare your first cell collection and colors for cell material:
<pre>
    <code class="language-python">             
                    from goo import goo 
                    goo.setup_world() <br>
                    # create first collection
                    goo.make_collection("my_first collection")

                    # colors 
                    goo.add_material("green", 0, 0.1, 0)
                    goo.add_material("red", 0.1, 0, 0)
    </code> 
</pre>

2. Declare your first cells: <br>
<pre>
    <code class="language-python">             
                    # create first cell
                    goo.make_cell("my_first_cell", loc = (0,0,0), material = "green", collection = "my_first_collection")
                    # create second cell
                    goo.make_cell("my_second_cell", loc = (0,2,0), material = "red", collection = "my_first_collection")
    </code> 
</pre>


3. Create your first scene by clicking the play button in the scripting tab of Blender. 
4. Yay. You have created your first cells in Blender using Goo. Next steps elaborate on how to add adhesion forces and how to animate the scene using Blender's physics engine. 

<b>Add cell adhesion</b>

The current scene is static as no interactions between cells have been declared. 
1. 

<b>Biological features supported by Goo</b>

1. Biological cells
Goo's cells models biological cells as polygon mesh deformable upon collision with other cells. Cells' physical behavior such as stiffness, pressure and adhesion are tunable for biologists to investigate their impact on cell and tissue shapes. Homotypic adhesion is supported in Goo. 
2. Cell adhesion
Adhesion forces are mimmicked by Blender's built-in force fields. In Goo, they emanate from the cell's surface, are local and centered on the cell's center of mass. 
3. Cell growth 
Goo cells grow at a user-specified rate so that they volume isotropically increase. 
4. Cell random motility
Goo implements cell undirected motility as a uniform random walk. 
5. Cell division
Goo's model for cell division follows Hertwig's rule, stating that cells divide along their long axis. Therefore, the division plane is described as the plane orthogonal to the long axis and that passes by the cell's center of mass. 