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

[Insert screenshots]

<b>Your first script</b>

1. Open Blender and its <i>Scripting</i> tab. 
2. Declare your first cell collection and colors for cell material:
<blockquote-medium>           
    from goo import goo 
    goo.setup_world() <br>
    # create first collection
    goo.collection("my_cell_collection")

    # colors 
    goo.material("green", 0, 0.1, 0)
    goo.material("red", 0.1, 0, 0)
</blockquote-medium>
2. Declare your first cells: <br>
    <pre>
        <code class="language-python">             
            # create first cell
            goo.cell("my_first_cell", loc = (0,0,0), material = "green", collection = "my_cell_collection")
            # create second cell
            goo.cell("my_second_cell", loc = (0,2,0), material = "red", collection = "my_cell_collection")
        </code> 
    </pre>
3. Create your first scene by clicking the play button in the scripting tab of Blender. 
4. Yay. You have created your first cells in Blender using Goo. Next steps elaborate on how to add adhesion forces and how to animate the scene using Blender's physics engine. 

<b>Add cell adhesion</b>

The current scene is static as no interactions between cells have been declared. 
1. Declare your first adhesion forces. 
    <pre>
        <code class="language-python">  
            # create first force collection
            goo.collection("my_force_collection")           
            # declare first force
            goo.adhesion("my_first_force", "my_first_cell", strength = -1000, falloff = 1, collection = "my_force_collection")
            # declare second force
            goo.adhesion("my_second_force", "my_second_cell", strength = -1000, falloff = 1, collection = "my_force_collection")
        </code> 
    </pre>
2. Execute the script in Blender's scripting tab then start the simulation in the <i>Layout</i> tab. 

<b>Biological features supported in Goo</b>

1. Biological cells <br>
Goo's cells models biological cells as polygon mesh deformable upon collision with other cells. Cells' physical behavior such as stiffness, pressure and adhesion are tunable for biologists to investigate their impact on cell and tissue shapes. Homotypic adhesion is supported in Goo. 
2. Cell adhesion <br>
Adhesion forces are mimmicked by Blender's built-in force fields. In Goo, they emanate from the cell's surface, are local and centered on the cell's center of mass. 
3. Cell growth <br>
Goo cells grow at a user-specified rate so that they volume isotropically increase. 
4. Cell random motility <br>
Goo implements cell undirected motility as a uniform random walk. 
5. Cell division <br>
Goo's model for cell division follows Hertwig's rule, stating that cells divide along their long axis. Therefore, the division plane is described as the plane orthogonal to the long axis and that passes by the cell's center of mass. 