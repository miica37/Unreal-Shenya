
###############################
Materials
###############################

.. role:: folder
.. role:: material
.. role:: material2

Overviews
=========
The :abbr:`📁Materials (Content\\Charles\\Materials)` folder contains master materials ([ M_xxxxx_Master ]) and material instances ([ MI_xxxxx ]).

.. image:: /images/materials/content-materials-thumbnails.jpg
	:align: center

|
|

Common Material Parameters
==========================

.. image:: /images/materials/power-parameter.jpg
	:align: center

.. image:: /images/materials/rgb-texture-parameter.jpg
	:align: center

For example, you can create your own design in Photoshop, use the Red, Green and Blue Channel to set the 3 color areas, and use the mask in the material.

.. image:: /images/materials/rgb-mask.jpg
	:align: center

|

Master Materials
================
List of Master Materials under *subfolder* :abbr:`📁Master (Content\\Charles\\Materials\\Master)`:

.. image:: /images/materials/content-master-materials.jpg
	:align: center

|

Eyes Masters
------------

.. image:: /images/materials/content-eyes-master-material-highlight.jpg
	:align: center

|

:material:`M_Eyes_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^
Basic eye material with added option to change eye colors.

.. image:: /images/materials/mi-eyes-parameters.jpg
	:align: center

|

.. _duo_eyes:

:material:`M_Duo_Eyes_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Based on [ M_Eyes_Master ] and added an option to give left eye and right eye two different colors.

The eye mesh has vertex colors (one color for the left eye and another color for the right eye), which is converted into masking inside the material to give both sides different colors.

.. image:: /images/materials/mi-duo-eyes-preview.jpg
	:align: center

|

.. image:: /images/materials/mi-duo-eyes-parameters.jpg
	:align: center

|

Generic Masters
---------------

.. image:: /images/materials/content-generic-master-material-highlight.jpg
	:align: center

|

:material:`M_Generic_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
A very basic PBR material, with just 3 textures input (Base Color, Normal and MRAO), and a parameter to control its specular value.

.. image:: /images/materials/m-generic-master-parameters.jpg
	:align: center

|

:material:`M_Generic_Tint_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Based on [ M_Generic_Master ] above and added an option to select a RGB texture as input to change the color of diffuse texture.

`Power` Parameter:
	The `Power` parameter setting is used to adjust the brightness (or darkness) of the color.

.. image:: /images/materials/M_Generic_Tint_Master-example.jpg
	:align: center

|

:material:`M_Generic_Tint_Dirt_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Based on [ M_Generic_Tint_Master ] above and added an option to add a dirt texture which is multiplied on top of the Base Color Texture.

`Dirt1 Strength` Parameter:
	Set it to 0 to Turn Off Dirt

.. image:: /images/materials/M_Generic_Tint_Dirt_Master-example.jpg
	:align: center

|

:material:`M_Generic_Tint_Dirt_Design_Master` and :material:`M_Generic_Tint_Dirt_Design_Overlay_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Based on [ M_Generic_Tint_Dirt_Master ] above and added an option to select a design (black and white) and add it on top of the Base Color Texture.

You can make the design larger or smaller using the tile parameter. Use the Offset X and Y to move it around. Currently it doesn't have a rotate function nor a flip function.

The Overlay version uses overlay blend mode while the non-overlay one uses alpha (LERP node, Linear Interpolate) which produces slightly different kind of look.

.. image:: /images/materials/M_Generic_Tint_Dirt_Design_Master-example.jpg
	:align: center

|

:material:`M_Generic_Tint_Glow_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Based on [ M_Generic_Tint_Master ] with a glow component.

* Requires an Emissive Mask Texture *

* Currently not being used *

|

:material:`M_Generic_Tint_Cutout_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
A material initially created to mask out mesh sections. The idea is to use vertex colors to assign colors to different parts of the mesh, then the color will be read as a mask inside this material to make them transparent.

* Requires mesh to have vertex color (Red/Green/Blue) *

* Currently not being used *

|
|

Skin Masters
------------

.. image:: /images/materials/content-skins-master-material-highlight.jpg
	:align: center

:material:`M_Shenya_Fullbody_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Skin material that is applied to head (*excludes* eyes, eyebrows, eyelashes and teeths which got their own material) and body. It is using Subsurface as the Shading Model.

.. image:: /images/materials/fullbody-parameters.jpg
	:align: center

Change the fingernails color:

.. image:: /images/materials/fingernails.jpg
	:align: center

|

:material:`M_Shenya_Fullbody_Dirt_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Based on [ M_Shenya_Fullbody_Master ] and added an option to blend (multiply) a dirt texture on top of the Base Color texture.

Limitation
""""""""""
The dirt texture cannot be tiled or moved to prevent texture discontinuation at the uv seams. Although you can export the dirt texture and edit it or import a new dirt texture to quickly add dirt to character's skin.

.. image:: /images/materials/fullbody-dirt-master-parameters.jpg
	:align: center



|

:material:`M_Shenya_Fullbody_Cutout_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
The cutout version added the option to mask out certain parts of the body.

.. image:: /images/materials/fullbody-cutout-material-example.jpg
	:align: center

|

.. image:: /images/materials/fullbody-cutout-parameters.jpg
	:align: center

|
|

:material:`MF_Get_Material_ID_Mask`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
This is a **Material Function** and it is being used inside [ M_Shenya_Fullbody_Master ], it accepts an integer as an input to specify which section to use for masking, and outputs a black and white mask like the image below. The number of sections that this function assumes is hardcoded to 16 sections. 

Note that the input integer is based from zero, so to select the first section, use 0 (instead of 1) as the input.

For example, in the image below, the white area represents the 6th section (from the 16 sections)

.. image:: /images/materials/bnw-horizontal-split-16.jpg
	:align: center

|
|

.. _body_masking:

How Body Masking Works
^^^^^^^^^^^^^^^^^^^^^^
The fullbody cutout master material is created based on the concept in this video: `Reducing Draw Calls in Unreal! by PrismaticaDev <https://www.youtube.com/watch?v=ncwW5KNQ1Eg>`_.

Refer to the image below, the body mesh actually has a second uv channel that has its uv arranged into 16 sections. Each section represents a part of the body.

[ MF_Get_Material_ID_Mask ] is used to create a mask for each section and the mask is then added from different sections and the result plugged into the Opacity Mask.

|

.. image:: /images/materials/body-uv2.jpg
	:align: center

|

.. image:: /images/materials/body-material-id.jpg
	:align: center

|
|

Other Materials
===============

.. image:: /images/materials/other-materials.jpg
	:align: center

|

Wireframe Materials
-------------------
[ M_Wireframe ] and its instance [ MI_Wireframe ] is used only in the Preview map to show the wireframe.

:material:`M_Transparent`
-------------------------
[ M_Transparent ] can be used anywhere you want to hide the mesh.

:material:`M_Eyebrowlashes_Master`
----------------------------------

Note that there are two opacity texture mask that you can choose, one is thicker than the other. The thinner one is from the first release while the thicker one is added to give the eyebrow and eyelashes a stronger presence.

.. image:: /images/materials/eyebrowlashes-highlight.jpg
	:align: center

.. image:: /images/materials/eyebrowlashes-opacity-texture-parameter.jpg
	:align: center

.. image:: /images/materials/eyebrowlashes-opacity-texture-options.jpg
	:align: center

:material:`M_Shenya_Eyes_Shadow`
--------------------------------
Shenya eyes has an additional mesh layer that covers the eyes (with slight offsets) to add an additional layer of painted shadow to the eye.

.. image:: /images/materials/eyes-shadow-example.jpg
	:align: center


Change the opacity of eyes shadow:

.. image:: /images/materials/eyes-shadow-parameters.jpg
	:align: center


:material:`M_Shenya_Glass_Master`
---------------------------------

A translucent shader for the glass of sunglasses.

.. image:: /images/materials/glass-master-example1.jpg
	:align: center


.. image:: /images/materials/glass-master-example2.jpg
	:align: center

|

