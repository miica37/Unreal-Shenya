
.. role:: folder
.. role:: bold-italic
.. role:: red
.. role:: green
.. role:: orange

Preview Map
===========

|

.. image:: /images/map-preview1.jpg
	:align: center

|

.. image:: /images/map-preview2.jpg
	:align: center

|

Features
========

* Follows UE4's Epic Skeleton (UE4 Mannequin)

* :ref:`Apple BlendShapes <blendshapes>`

* :ref:`Dynamic Hair and Jacket <dynamics>`

* :ref:`PBR Textures <textures>`

* :ref:`Modular <meshes>` (separated body and cloth parts)

* Full Body under clothes

* RGB Mask provided to make custom skins for character

* Dirt Textures

|
|

Scale (Character Size)
======================

Shenya should be somewhere around 20-24 year old.

.. image:: /images/scale-reference.jpg
	:align: center

|
|

Polycount
=========

+----------------------+------+
|Precombined Meshes    |  LOD0|
+======================+======+
|SK_Shenya             | 73754|
+----------------------+------+
|SK_Shenya2            | 64769|
+----------------------+------+

More about polycount for other parts at the :ref:`Meshes section <meshes>`

|
|

Skeleton
========

Shenya Skeleton VS UE4 Mannequin Skeleton:

* Joint Names [:green:`Match`]
* Number of Bones [:green:`Match`] (No extra bones)
* Parent/Child Relationships (Structure) [:green:`Match`]
* Joint Orientations [:orange:`Slightly vary`]
* Proportions [:red:`Different`]

The joint orientation is hand placed so it's not 100% matching but should be pretty close.

Since the body proportion is quite different from UE's mannequin you will need to do some :ref:`retargeting on animations <retarget>`.

.. image:: /images/skeleton.jpg
	:align: center

The picture below shows the bones orientation in Maya:

.. image:: /images/character-vs-mannequin-skeleton.jpg
	:align: center

|
|

Source Fbx Files
================

Source fbx files for Shenya are provided under the folder :abbr:`📁Content\\Shenya\\Fbx (Content\\Shenya\\Fbx)`, they can be useful if you would like to make some modification to the character.

These are exported out from **Maya** and imported into Unreal Engine.

The folder's content appears to be empty in Unreal Engine's Content Browser but if you do "Show in Explorer" (open the folder with Windows Explorer or the explorer app of your Operating System), you will see the fbx files.

Blender
-------

One of the issues that you might encounter when exporting mesh out from UE to Blender is the missing shape keys and material slots.

You can use `Fbx Converter <https://www.autodesk.com/developer-network/platform-technologies/fbx-converter-archives>`_ from Autodesk (`as pointed out by TheBasti82 in this Unreal Engine forum thread <https://forums.unrealengine.com/t/export-shape-keys-morph-targets-from-ue4-to-blender-workaround/133040>`_) to convert the fbx files (from UE) before importing them into Blender.

\* However using the provided source fbx files above don't have this problem.

|
|

Unreal Engine 5
===============

.. image:: /images/ue5/ue5-viewport.jpg
    :align: center

Shenya is developed on UE 4.22, normally it should work on future versions of Unreal Engine however if you find it misbehave on any later version please report back and I will try to fix them ASAP.

UE4 to UE5 Project Conversion:
    One thing I noticed when opening the preview map in UE5 (and also UE4.27) is it looks much brighter than the same map in UE4. The exposure compensation setting for PostProcessVolume has reverted back to 1.0, so turning it back to 0.0 should line up the looks with UE 4.22. 

.. image:: /images/ue5/ue5-after.jpg
    :align: center

|

.. note::
    :ref:`Retargeting Guide for UE5 <retarget_ue5>`

|
|

Viewing Image for this Document
===============================

The images of this documentation are automatically resized to fit the width of the contents area, some images actually have a higher resolution so you can try...

#. Right click on the image
#. Select "Open Image in New Tab"

to open the original image in another tab to see it better.

.. image:: /images/viewing-full-image-resolution.jpg
	:align: center

|
|

Supports
========

📧 Email
---------
You can post Questions at Unreal Marketplace or send me an email: miicaneo@gmail.com and I will try to reply to you as soon as I can. (*my response can be a bit slow during Thursday and Weekends, apologize in advance*)


.. Discord
   -------
    I also created a Discord Server as another option:

    https://discord.gg/WzspRd3QrG

    .. Note::
        The Discord setup is very simple for now as I don't have much experience with Discord.

|
