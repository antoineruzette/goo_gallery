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
2. Create a cell collection and add your first cell to it: <br>
<pre>
    <code class="language-python">             
                    from goo import goo <br>
                    goo.setup_world() <br>

                    cell_collection = bpy.data.collections.new("my_first_collection")
                    bpy.context.scene.collection.children.link(cell_collection)
                    cell = goo.Cell(name_string = &#x22;my first cell&#x22;, loc = (0, 0, 0)) <br>
                    goo.make_cell(cell) <br>
    </code> 
</pre>




3. Run your script by clicking the play button in the scripting tab of Blender
4. Add a material that will be used to render your simulation. 
<pre class="line-numbers">
    <code class="language-python">             
                    matg = bpy.data.materials.new("Green")
                    matg.diffuse_color = (0,0.1,0,0.8)
                    
                    obj = bpy.context.active_object
                    obj.active_material = matg
                    bpy.ops.collection.objects_remove_all()
                    bpy.data.collections['my_first_collection'].objects.link(obj)
    </code> 
</pre>
4. Yay. You have created your first Goo cell in Blender. Next steps will elaborate on how to add adhesion forces and simulate its shape deformation over time. 

<b>Add cell adhesion and </b>

1. Once your Blender scene


<b>Biological features supported by Goo</b>

1. Biological cells
2. Cell deformability
3. Cell adhesion
4. Cell growth 
5. Cell random motility
6. Cell division
