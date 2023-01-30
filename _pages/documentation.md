---
title: Documentation
subtitle: ''
description: ''
featured_image: ''
---

<!DOCTYPE html>

<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" /><meta name="generator" content="Docutils 0.19: https://docutils.sourceforge.io/" />

    <title>Functions and Classes &#8212; Goo 0.0.1 documentation</title>
    <link rel="stylesheet" type="text/css" href="_static/pygments.css" />
    <link rel="stylesheet" type="text/css" href="_static/pyramid.css" />
    <script data-url_root="./" id="documentation_options" src="_static/documentation_options.js"></script>
    <script src="_static/jquery.js"></script>
    <script src="_static/underscore.js"></script>
    <script src="_static/_sphinx_javascript_frameworks_compat.js"></script>
    <script src="_static/doctools.js"></script>
    <script src="_static/sphinx_highlight.js"></script>
    <link rel="index" title="Index" href="genindex.html" />
    <link rel="search" title="Search" href="search.html" />
    <link rel="next" title="User’s Guide" href="userguide.html" />
    <link rel="prev" title="Goo Overview" href="summary.html" />
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Neuton&amp;subset=latin" type="text/css" media="screen" charset="utf-8" />
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Nobile:regular,italic,bold,bolditalic&amp;subset=latin" type="text/css" media="screen" charset="utf-8" />
<!--[if lte IE 6]>
<link rel="stylesheet" href="_static/ie6.css" type="text/css" media="screen" charset="utf-8" />
<![endif]-->

  </head><body>

    <div class="related" role="navigation" aria-label="related navigation">
      <h3>Navigation</h3>
      <ul>
        <li class="right" style="margin-right: 10px">
          <a href="genindex.html" title="General Index"
             accesskey="I">index</a></li>
        <li class="right" >
          <a href="py-modindex.html" title="Python Module Index"
             >modules</a> |</li>
        <li class="right" >
          <a href="userguide.html" title="User’s Guide"
             accesskey="N">next</a> |</li>
        <li class="right" >
          <a href="summary.html" title="Goo Overview"
             accesskey="P">previous</a> |</li>
        <li class="nav-item nav-item-0"><a href="index.html">Goo 0.0.1 documentation</a> &#187;</li>
        <li class="nav-item nav-item-this"><a href="">Functions and Classes</a></li> 
      </ul>
    </div>  

    <div class="document">
      <div class="documentwrapper">
        <div class="bodywrapper">
          <div class="body" role="main">
            
  <section id="module-goo">
<span id="functions-and-classes"></span><h1>Functions and Classes<a class="headerlink" href="#module-goo" title="Permalink to this heading">¶</a></h1>
<p>import bpy
import bmesh
import mathutils
import numpy as np
import sys</p>
<dl class="py class">
<dt class="sig sig-object py" id="goo.Cell">
<em class="property"><span class="pre">class</span><span class="w"> </span></em><span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">Cell</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">name_string</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">loc</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">material</span></span><span class="o"><span class="pre">=</span></span><span class="default_value"><span class="pre">''</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">flavor</span></span><span class="o"><span class="pre">=</span></span><span class="default_value"><span class="pre">''</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.Cell" title="Permalink to this definition">¶</a></dt>
<dd><p>Core class: creates Goo cell object.</p>
<p>The class instantiates <a class="reference internal" href="#goo.Cell" title="goo.Cell"><code class="xref py py-class docutils literal notranslate"><span class="pre">Cell</span></code></a> objects.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>name</strong> (<em>str</em>) – The name of the cell.</p></li>
<li><p><strong>loc</strong> (<em>tuple</em>) – The coordinates of the cell.</p></li>
</ul>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py class">
<dt class="sig sig-object py" id="goo.Force">
<em class="property"><span class="pre">class</span><span class="w"> </span></em><span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">Force</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">force_name</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">cell_name</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">strength</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.Force" title="Permalink to this definition">¶</a></dt>
<dd><p>Core class: creates Goo force objects.</p>
<p>The class instantiates <a class="reference internal" href="#goo.Force" title="goo.Force"><code class="xref py py-class docutils literal notranslate"><span class="pre">Force</span></code></a> objects that represent 
adhesion forces between cells in Blender.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>force_name</strong> (<em>str</em>) – The name of the force.</p></li>
<li><p><strong>cell_name</strong> (<em>str</em>) – The name of the cell.</p></li>
<li><p><strong>strength</strong> (<em>float</em>) – The strength of the force.</p></li>
<li><p><strong>falloff_power</strong> (<em>float</em>) – The power of the falloff of the force.</p></li>
</ul>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code class="docutils literal notranslate"><span class="pre">falloff_power</span></code> is a positive (<code class="xref py py-class docutils literal notranslate"><span class="pre">float</span></code>). 
By default, the type of the falloff is set to <cite>SPHERE</cite> 
and its shape is set to <cite>SURFACE</cite>.</p>
</div>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.add_material_cell">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">add_material_cell</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">mat_name</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">r</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">g</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">b</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.add_material_cell" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: creates a soap bubble-like Blender material for use in rendering cells.</p>
<p>The material has a name that allows it to be shared across multiple cells.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>mat_name</strong> (<em>str</em>) – The name of the material.</p></li>
<li><p><strong>r</strong> (<em>float</em>) – The value of the red in RGB [0 to 1].</p></li>
<li><p><strong>g</strong> (<em>float</em>) – The value of the green value in RGB [0 to 1].</p></li>
<li><p><strong>b</strong> (<em>float</em>) – The value of the blue value in RGB [0 to 1].</p></li>
</ul>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.add_world_HDRI">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">add_world_HDRI</span></span><span class="sig-paren">(</span><span class="sig-paren">)</span><a class="headerlink" href="#goo.add_world_HDRI" title="Permalink to this definition">¶</a></dt>
<dd><p>Auxilliary function: sets up Blender World properties for use in rendering.</p>
<p>It adds an HDRI (High Dynamic Range Image) for illumination.</p>
<dl class="field-list simple">
<dt class="field-odd">Returns<span class="colon">:</span></dt>
<dd class="field-odd"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.calculate_contact_area">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">calculate_contact_area</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">obj</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.calculate_contact_area" title="Permalink to this definition">¶</a></dt>
<dd><p>Auxilliary function: calculates the contact area of a Blender cell with all surrounding objects.</p>
<p>The function looks for flat areas of the mesh. Not always a good assumption</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>obj</strong> (<em>bpy.data.objects</em><em>[</em><em>'name'</em><em>]</em>) – The Blender mesh.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>The contact area.</p>
</dd>
<dt class="field-odd">Return type<span class="colon">:</span></dt>
<dd class="field-odd"><p>float</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.calculate_volume">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">calculate_volume</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">obj</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.calculate_volume" title="Permalink to this definition">¶</a></dt>
<dd><p>Auxilliary function: calculates the volume of the Blender mesh.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>obj</strong> (<em>bpy.data.objects</em><em>[</em><em>'name'</em><em>]</em>) – The Blender mesh.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>The volume of the mesh.</p>
</dd>
<dt class="field-odd">Return type<span class="colon">:</span></dt>
<dd class="field-odd"><p>float</p>
</dd>
</dl>
<div class="admonition seealso">
<p class="admonition-title">See also</p>
<p>In order to retrieve the mesh as it is currrently evaluated - including 
the effect of all modifiers - in the simulation, its corresponding evaluated 
ID is obtained from the dependency graph for the current context. 
<a class="reference external" href="https://docs.blender.org/api/current/bpy.types.ID.html?highlight=evaluated_get#bpy.types.ID.evaluated_get">Blender API Documentation &gt; evaluated_get(depsgraph)</a></p>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The function may return a negative volume - see <code class="docutils literal notranslate"><span class="pre">calc_volume(signed=True)</span></code>.</p>
</div>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.delete_cell">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">delete_cell</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">cell</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.delete_cell" title="Permalink to this definition">¶</a></dt>
<dd><p>Auxilliary function: deletes a Blender mesh.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>cell</strong> (<a class="reference internal" href="#goo.Cell" title="goo.Cell"><em>Cell</em></a>) – The Goo <a class="reference internal" href="#goo.Cell" title="goo.Cell"><code class="xref py py-class docutils literal notranslate"><span class="pre">Cell</span></code></a> object.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.divide">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">divide</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">obj</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.divide" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: divides a mother Blender mesh into two daughter Blender meshes.</p>
<p>The division plane is orthogonal to the major axis of the parent mesh. 
Additionally, this function may translate daughter cells, 
translating one mesh, filling the two holes, and retriangulating the meshes</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>obj</strong> (<em>bpy.data.objects</em><em>[</em><em>'mother_name'</em><em>]</em>) – The soon-to-be mother Blender mesh.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p><ul class="simple">
<li><p>daughter1 (<cite>bpy.data.objects[‘daughter1_name’]</cite>) - The Blender mesh of one of the daughter cells.</p></li>
<li><p>daughter2 (<cite>bpy.data.objects[‘daughter2_name’]</cite>) - The Blender mesh of the other daughter cell.</p></li>
</ul>
</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.get_division_angles">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">get_division_angles</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">axis</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.get_division_angles" title="Permalink to this definition">¶</a></dt>
<dd><p>Auxilliary function: retrieves the 2 angles associated with the long axis of a cell.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>axis</strong> (<em>tuple</em>) – Coordinates of the long axis to the division plane - as retrived by <code class="docutils literal notranslate"><span class="pre">get_major_axis(obj)</span></code>.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p><ul class="simple">
<li><p>phi (<code class="xref py py-class docutils literal notranslate"><span class="pre">tuple</span></code>) - Phi is the angle between the division axis and the z-axis in spherical coordinates.</p></li>
<li><p>theta (<code class="xref py py-class docutils literal notranslate"><span class="pre">tuple</span></code>) - Theta is the angle projected on the xy plane in cartesian 3D coordinates.</p></li>
</ul>
</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.get_major_axis">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">get_major_axis</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">obj</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.get_major_axis" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: calculates the long axis of a mesh.</p>
<p>This function calculates the first eigenvector of the vertices in the mesh, 
which corresponds to the long axis.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>obj</strong> (<em>bpy.data.objects</em><em>[</em><em>'name'</em><em>]</em>) – The Blender mesh.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>The coordinates of the long axis of the mesh as a tuple(x, y, z) which gives direction from the origin (0, 0, 0).</p>
</dd>
<dt class="field-odd">Return type<span class="colon">:</span></dt>
<dd class="field-odd"><p>tuple</p>
</dd>
</dl>
</dd></dl>

<dl class="py class">
<dt class="sig sig-object py" id="goo.handler_class">
<em class="property"><span class="pre">class</span><span class="w"> </span></em><span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">handler_class</span></span><a class="headerlink" href="#goo.handler_class" title="Permalink to this definition">¶</a></dt>
<dd><p>Core class: creates handler objects.</p>
<p>Handlers trigger actions on Goo cells when certain criteria are met.</p>
<dl class="field-list simple">
<dt class="field-odd">Returns<span class="colon">:</span></dt>
<dd class="field-odd"><p>None</p>
</dd>
</dl>
<dl class="py method">
<dt class="sig sig-object py" id="goo.handler_class.apply_forces">
<span class="sig-name descname"><span class="pre">apply_forces</span></span><span class="sig-paren">(</span><span class="sig-paren">)</span><a class="headerlink" href="#goo.handler_class.apply_forces" title="Permalink to this definition">¶</a></dt>
<dd><p>Adds force fields to force collections and make them affect the
corresponding cell types.</p>
<dl class="field-list simple">
<dt class="field-odd">Returns<span class="colon">:</span></dt>
<dd class="field-odd"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt class="sig sig-object py" id="goo.handler_class.set_adhesion">
<span class="sig-name descname"><span class="pre">set_adhesion</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">type1</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">type2</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">force</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.handler_class.set_adhesion" title="Permalink to this definition">¶</a></dt>
<dd><p>Sets a value adhesion_forces in the handler class that 
apply_forces() can reference later</p>
<p>The cell type must be one of the actives.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>type1</strong> (<em>str</em>) – The name of cell type that the force is attatched to.</p></li>
<li><p><strong>type2</strong> (<em>str</em>) – The name of cell type that the force affects.</p></li>
<li><p><strong>force</strong> (<em>int</em>) – The strength of the force between type1 and type2 cells.</p></li>
</ul>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt class="sig sig-object py" id="goo.handler_class.set_division_rate">
<span class="sig-name descname"><span class="pre">set_division_rate</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">cell_type</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">rate</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.handler_class.set_division_rate" title="Permalink to this definition">¶</a></dt>
<dd><p>Sets division rate in the handler class that div_handler() can reference later.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>cell_type</strong> (<em>str</em>) – The name of cell type to apply this division rate to.</p></li>
<li><p><strong>rate</strong> (<em>int</em>) – The number of frames between each division.</p></li>
</ul>
</dd>
</dl>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The cell type must be one of the active cell types.</p>
</div>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The rate is in divisions per second ans assumes 60 frames per second.</p>
</div>
<dl class="field-list simple">
<dt class="field-odd">Returns<span class="colon">:</span></dt>
<dd class="field-odd"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt class="sig sig-object py" id="goo.handler_class.set_growth_rate">
<span class="sig-name descname"><span class="pre">set_growth_rate</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">cell_type</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">rate</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.handler_class.set_growth_rate" title="Permalink to this definition">¶</a></dt>
<dd><p>Sets growth rate in the handler class that growth_handler() can reference later.</p>
<p>The growth rate should be between 0 and 1.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>cell_type</strong> (<em>str</em>) – The name of cell type to apply this division rate to.</p></li>
<li><p><strong>rate</strong> (<em>float</em>) – The amount to change <code class="docutils literal notranslate"><span class="pre">cell.modifiers[&quot;Cloth&quot;].settings.shrink_min</span></code> each frame.</p></li>
</ul>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py method">
<dt class="sig sig-object py" id="goo.handler_class.set_scale">
<span class="sig-name descname"><span class="pre">set_scale</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">scale</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">cell_type</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.handler_class.set_scale" title="Permalink to this definition">¶</a></dt>
<dd><p>Changes the size of all cells of a certain type.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>scale</strong> (<em>float</em>) – value to set <code class="docutils literal notranslate"><span class="pre">cell.modifiers[&quot;Cloth&quot;].settings.shrink_min</span></code> to.</p></li>
<li><p><strong>cell_type</strong> (<em>str</em>) – Name of cell type to scale.</p></li>
</ul>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.make_cell">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">make_cell</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">cell</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.make_cell" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: creates a Blender mesh corresponding to a Goo <a class="reference internal" href="#goo.Cell" title="goo.Cell"><code class="xref py py-class docutils literal notranslate"><span class="pre">Cell</span></code></a> object.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>cell</strong> (<a class="reference internal" href="#goo.Cell" title="goo.Cell"><em>Cell</em></a>) – The Goo <a class="reference internal" href="#goo.Cell" title="goo.Cell"><code class="xref py py-class docutils literal notranslate"><span class="pre">Cell</span></code></a> object.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.make_force">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">make_force</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">force</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.make_force" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: creates a Blender force from a Goo <a class="reference internal" href="#goo.Force" title="goo.Force"><code class="xref py py-class docutils literal notranslate"><span class="pre">Force</span></code></a> object.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>force</strong> (<a class="reference internal" href="#goo.Force" title="goo.Force"><em>Force</em></a>) – The Goo <a class="reference internal" href="#goo.Force" title="goo.Force"><code class="xref py py-class docutils literal notranslate"><span class="pre">Force</span></code></a> object.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.make_force_collections">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">make_force_collections</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">master_collection</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">cell_types</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.make_force_collections" title="Permalink to this definition">¶</a></dt>
<dd><p>Auxilliary function: makes collections for forces to be stored in.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>master_collection</strong> (<em>bpy.context.view_layer.active_layer_collection</em>) – The collection in which the force
collections will be contained.</p></li>
<li><p><strong>cell_types</strong> (<em>list</em>) – The list of active cell types.</p></li>
</ul>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.print_info">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">print_info</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">obj</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.print_info" title="Permalink to this definition">¶</a></dt>
<dd><p>Auxilliary function: Retrieves the number of vertices, edges and faces of a Blender object</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>obj</strong> (<em>bpy.data.objects</em><em>[</em><em>'name'</em><em>]</em>) – The Blender mesh.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>The number of vertices, faces and edges of <code class="docutils literal notranslate"><span class="pre">obj</span></code>.</p>
</dd>
<dt class="field-odd">Return type<span class="colon">:</span></dt>
<dd class="field-odd"><p>list of float</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.render">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">render</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">file_path</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">scene</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">start</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">end</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.render" title="Permalink to this definition">¶</a></dt>
<dd><p>Auxilliary function: renders a simulation to create a set of still images that can be made into a movie</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>file_path</strong> (<em>str</em>) – The path of the folder used to store output images.</p></li>
<li><p><strong>scene</strong> (<em>bpy.context.scene</em>) – The Blender current scene.</p></li>
<li><p><strong>start</strong> (<em>int</em>) – The Blender starting frame.</p></li>
<li><p><strong>end</strong> (<em>int</em>) – The Blender ending frame.</p></li>
</ul>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.repair_hole">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">repair_hole</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">obj</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.repair_hole" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: repair the holes created by the bissection of the Blender mesh.</p>
<p>This function adds a new face to the cell after division (bissection - in two equal parts) 
of the mesh and regularizes the mesh so that the mesh is evenly covered with faces.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>obj</strong> (<em>bpy.data.objects</em><em>[</em><em>'name'</em><em>]</em>) – The Blender mesh.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.select_translate_cell">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">select_translate_cell</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">obj</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">COM</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">division_axis</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.select_translate_cell" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: selects one of the daughter cells to translate.</p>
<p>After dividing the mother cell, this function compares the 
center of mass of the original mother cell to that of the 
corresponding daughter cells. To do so, the signed distance 
between the daughter cell’s center of mass and the original 
plane of division is calculated.
If this distance is positive, the function returns True
and this selected daughter cell will be translated later.
If this distance is negative, the function returns False
and the other daughter cell will be translated later</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>obj</strong> (<em>bpy.data.objects</em><em>[</em><em>'name'</em><em>]</em>) – The Blender mesh of the mother cell.</p></li>
<li><p><strong>COM</strong> (<em>tuple</em>) – The XYZ coordinates of the center of mass of the mother cell.</p></li>
<li><p><strong>major_axis</strong> (<em>tuple</em>) – The major axis of the mother mesh specified by XYZ coordinates from the origin.</p></li>
</ul>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>A boolean flag indicating which cell has to be translated in <code class="docutils literal notranslate"><span class="pre">translate_cell(obj,</span> <span class="pre">axis)</span></code>.</p>
</dd>
<dt class="field-odd">Return type<span class="colon">:</span></dt>
<dd class="field-odd"><p>Boolean</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.seperate_cell">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">seperate_cell</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">obj</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.seperate_cell" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: splits one cell into two for cell division.</p>
<p>The mother Blender mesh is split in two given a division plane. 
The division plane is specified by a point on this plane, that is the center of mass of the mother,
and the direction of this point, given by the long axis of the mother mesh.
By naming convention, the daughter cells inherit their mother name added with .001.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><p><strong>obj</strong> (<em>bpy.data.objects</em><em>[</em><em>'name'</em><em>]</em>) – the Blender mesh to divide in two.</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p><ul class="simple">
<li><p>mother_name (<code class="xref py py-class docutils literal notranslate"><span class="pre">str</span></code>) - The name of the mother cell.</p></li>
<li><p>daughter_name (<code class="xref py py-class docutils literal notranslate"><span class="pre">str</span></code>) - The name of the daughter cell.</p></li>
<li><p>COM (<code class="xref py py-class docutils literal notranslate"><span class="pre">tuple</span></code>) - The XYZ coordinates of the center of mass of the mother cell.</p></li>
<li><p>major_axis (<code class="xref py py-class docutils literal notranslate"><span class="pre">tuple</span></code>) - The XYZ coordinates of the long axis of the mother cell.</p></li>
</ul>
</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.setup_world">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">setup_world</span></span><span class="sig-paren">(</span><span class="sig-paren">)</span><a class="headerlink" href="#goo.setup_world" title="Permalink to this definition">¶</a></dt>
<dd><p>Auxilliary function: sets up the default values used for simulations in Goo 
including units and rendering background.</p>
<dl class="field-list simple">
<dt class="field-odd">Returns<span class="colon">:</span></dt>
<dd class="field-odd"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.translate_cell">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">translate_cell</span></span><span class="sig-paren">(</span><em class="sig-param"><span class="n"><span class="pre">obj</span></span></em>, <em class="sig-param"><span class="n"><span class="pre">axis</span></span></em><span class="sig-paren">)</span><a class="headerlink" href="#goo.translate_cell" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: translates cells along the given axis.</p>
<p>This function is used during cell division so daughters have some space.</p>
<dl class="field-list simple">
<dt class="field-odd">Parameters<span class="colon">:</span></dt>
<dd class="field-odd"><ul class="simple">
<li><p><strong>obj</strong> (<em>bpy.data.objects</em><em>[</em><em>'name'</em><em>]</em>) – The Blender mesh to translate.</p></li>
<li><p><strong>axis</strong> (<em>tuple</em>) – The XYZ coordinates of the major axis of the Blender mesh to translate.</p></li>
</ul>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.turn_off_physics">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">turn_off_physics</span></span><span class="sig-paren">(</span><span class="sig-paren">)</span><a class="headerlink" href="#goo.turn_off_physics" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: turns physics off for the currently selected Blender object.</p>
<p>The cloth physics for cells are turned off before division to avoid irregular mesh behavior after.</p>
<dl class="field-list simple">
<dt class="field-odd">Param<span class="colon">:</span></dt>
<dd class="field-odd"><p>None</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

<dl class="py function">
<dt class="sig sig-object py" id="goo.turn_on_physics">
<span class="sig-prename descclassname"><span class="pre">goo.</span></span><span class="sig-name descname"><span class="pre">turn_on_physics</span></span><span class="sig-paren">(</span><span class="sig-paren">)</span><a class="headerlink" href="#goo.turn_on_physics" title="Permalink to this definition">¶</a></dt>
<dd><p>Core function: turns physics on for the currently selected Blender object.</p>
<p>Physics are turned back on after cell division occurs to avoid irregular mesh behavior post-division.</p>
<dl class="field-list simple">
<dt class="field-odd">Param<span class="colon">:</span></dt>
<dd class="field-odd"><p>None</p>
</dd>
<dt class="field-even">Returns<span class="colon">:</span></dt>
<dd class="field-even"><p>None</p>
</dd>
</dl>
</dd></dl>

</section>


            <div class="clearer"></div>
          </div>
        </div>
      </div>
      <div class="sphinxsidebar" role="navigation" aria-label="main navigation">
        <div class="sphinxsidebarwrapper">
  <div>
    <h3><a href="index.html">Table of Contents</a></h3>
    <ul>
<li><a class="reference internal" href="#">Functions and Classes</a><ul>
<li><a class="reference internal" href="#goo.Cell"><code class="docutils literal notranslate"><span class="pre">Cell</span></code></a></li>
<li><a class="reference internal" href="#goo.Force"><code class="docutils literal notranslate"><span class="pre">Force</span></code></a></li>
<li><a class="reference internal" href="#goo.add_material_cell"><code class="docutils literal notranslate"><span class="pre">add_material_cell()</span></code></a></li>
<li><a class="reference internal" href="#goo.add_world_HDRI"><code class="docutils literal notranslate"><span class="pre">add_world_HDRI()</span></code></a></li>
<li><a class="reference internal" href="#goo.calculate_contact_area"><code class="docutils literal notranslate"><span class="pre">calculate_contact_area()</span></code></a></li>
<li><a class="reference internal" href="#goo.calculate_volume"><code class="docutils literal notranslate"><span class="pre">calculate_volume()</span></code></a></li>
<li><a class="reference internal" href="#goo.delete_cell"><code class="docutils literal notranslate"><span class="pre">delete_cell()</span></code></a></li>
<li><a class="reference internal" href="#goo.divide"><code class="docutils literal notranslate"><span class="pre">divide()</span></code></a></li>
<li><a class="reference internal" href="#goo.get_division_angles"><code class="docutils literal notranslate"><span class="pre">get_division_angles()</span></code></a></li>
<li><a class="reference internal" href="#goo.get_major_axis"><code class="docutils literal notranslate"><span class="pre">get_major_axis()</span></code></a></li>
<li><a class="reference internal" href="#goo.handler_class"><code class="docutils literal notranslate"><span class="pre">handler_class</span></code></a><ul>
<li><a class="reference internal" href="#goo.handler_class.apply_forces"><code class="docutils literal notranslate"><span class="pre">handler_class.apply_forces()</span></code></a></li>
<li><a class="reference internal" href="#goo.handler_class.set_adhesion"><code class="docutils literal notranslate"><span class="pre">handler_class.set_adhesion()</span></code></a></li>
<li><a class="reference internal" href="#goo.handler_class.set_division_rate"><code class="docutils literal notranslate"><span class="pre">handler_class.set_division_rate()</span></code></a></li>
<li><a class="reference internal" href="#goo.handler_class.set_growth_rate"><code class="docutils literal notranslate"><span class="pre">handler_class.set_growth_rate()</span></code></a></li>
<li><a class="reference internal" href="#goo.handler_class.set_scale"><code class="docutils literal notranslate"><span class="pre">handler_class.set_scale()</span></code></a></li>
</ul>
</li>
<li><a class="reference internal" href="#goo.make_cell"><code class="docutils literal notranslate"><span class="pre">make_cell()</span></code></a></li>
<li><a class="reference internal" href="#goo.make_force"><code class="docutils literal notranslate"><span class="pre">make_force()</span></code></a></li>
<li><a class="reference internal" href="#goo.make_force_collections"><code class="docutils literal notranslate"><span class="pre">make_force_collections()</span></code></a></li>
<li><a class="reference internal" href="#goo.print_info"><code class="docutils literal notranslate"><span class="pre">print_info()</span></code></a></li>
<li><a class="reference internal" href="#goo.render"><code class="docutils literal notranslate"><span class="pre">render()</span></code></a></li>
<li><a class="reference internal" href="#goo.repair_hole"><code class="docutils literal notranslate"><span class="pre">repair_hole()</span></code></a></li>
<li><a class="reference internal" href="#goo.select_translate_cell"><code class="docutils literal notranslate"><span class="pre">select_translate_cell()</span></code></a></li>
<li><a class="reference internal" href="#goo.seperate_cell"><code class="docutils literal notranslate"><span class="pre">seperate_cell()</span></code></a></li>
<li><a class="reference internal" href="#goo.setup_world"><code class="docutils literal notranslate"><span class="pre">setup_world()</span></code></a></li>
<li><a class="reference internal" href="#goo.translate_cell"><code class="docutils literal notranslate"><span class="pre">translate_cell()</span></code></a></li>
<li><a class="reference internal" href="#goo.turn_off_physics"><code class="docutils literal notranslate"><span class="pre">turn_off_physics()</span></code></a></li>
<li><a class="reference internal" href="#goo.turn_on_physics"><code class="docutils literal notranslate"><span class="pre">turn_on_physics()</span></code></a></li>
</ul>
</li>
</ul>

  </div>
  <div>
    <h4>Previous topic</h4>
    <p class="topless"><a href="summary.html"
                          title="previous chapter">Goo Overview</a></p>
  </div>
  <div>
    <h4>Next topic</h4>
    <p class="topless"><a href="userguide.html"
                          title="next chapter">User’s Guide</a></p>
  </div>
  <div role="note" aria-label="source link">
    <h3>This Page</h3>
    <ul class="this-page-menu">
      <li><a href="_sources/code.rst.txt"
            rel="nofollow">Show Source</a></li>
    </ul>
   </div>
<div id="searchbox" style="display: none" role="search">
  <h3 id="searchlabel">Quick search</h3>
    <div class="searchformwrapper">
    <form class="search" action="search.html" method="get">
      <input type="text" name="q" aria-labelledby="searchlabel" autocomplete="off" autocorrect="off" autocapitalize="off" spellcheck="false"/>
      <input type="submit" value="Go" />
    </form>
    </div>
</div>
<script>document.getElementById('searchbox').style.display = "block"</script>
        </div>
      </div>
      <div class="clearer"></div>
    </div>
    <div class="related" role="navigation" aria-label="related navigation">
      <h3>Navigation</h3>
      <ul>
        <li class="right" style="margin-right: 10px">
          <a href="genindex.html" title="General Index"
             >index</a></li>
        <li class="right" >
          <a href="py-modindex.html" title="Python Module Index"
             >modules</a> |</li>
        <li class="right" >
          <a href="userguide.html" title="User’s Guide"
             >next</a> |</li>
        <li class="right" >
          <a href="summary.html" title="Goo Overview"
             >previous</a> |</li>
        <li class="nav-item nav-item-0"><a href="index.html">Goo 0.0.1 documentation</a> &#187;</li>
        <li class="nav-item nav-item-this"><a href="">Functions and Classes</a></li> 
      </ul>
    </div>
    <div class="footer" role="contentinfo">
        &#169; Copyright 2022. President and Fellows of Harvard College.
      Created using <a href="https://www.sphinx-doc.org/">Sphinx</a> 5.3.0.
    </div>
  </body>
</html>