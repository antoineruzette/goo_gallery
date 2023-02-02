---
title: User's Guide
subtitle: Create with first digital tissues in 3D with just a few clicks.
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
2. Create a cell: <br>
<pre><code>
from goo import goo
goo.setup_world()
cell = goo.Cell(name_string = &#x22;my first cell&#x22;, loc = (0, 0, 0))
goo.make_cell(cell)
</code></pre>
3. Run your script by clicking the play button in the scripting tab of Blender
4. Yay. You have created your first Goo cell in Blender. Next steps will elaborate on how to add adhesion forces and simulate its shape deformation over time. 

