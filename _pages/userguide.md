---
title: User's Guide
subtitle: Create with first digital tissues in 3D with just a few clicks.
description: ''
featured_image: ''
---

<b>Installation</b>

1. Install the latest edition of Blender from https://www.blender.org/download/
2. Clone the Goo repository or download and unzip
3. In Blender, go to <i>Edit>Preferences</i>, then go to the ‘Add-ons’ tab and enable the checkbox next to <i>Add Mesh: Extra Objects</i>

[Insert screenshots]

4. In <i>Edit>Preferences</i>, go to the File Paths tab and add the <i>/path_to_your_Goo_clone/Goo/scripts/</i> folder to <i>Scripts</i>. 
5. Re-start Blender. 

<b>Your first script</b>

1. Open Blender and its <i>Scripting</i> tab. 
2. Create a cell: <br>
    <blockquote>
    <pre>
        <code>
            from goo import goo
            goo.setup_world()
            cell = goo.Cell(name_string = "my first cell", loc = (0, 0, 0))
            goo.make_cell(cell)
        </code>
    </pre>
    </blockquote>

3. Run your script by clicking the play button in the scripting tab of Blender
4. Yay. You have created your first Goo cell in Blender. Next steps will elaborate on how to add adhesion forces and simulate its shape deformation over time. 

