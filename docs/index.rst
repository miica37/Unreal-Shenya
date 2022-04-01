.. Shenya Documentation master file, created by
	 sphinx-quickstart on Sat Sep  1 12:46:37 2018 (modifiend on March 2021).
	 You can adapt this file completely to your liking, but it should at least
	 contain the root `toctree` directive.

Shenya
======

Some notes about the character Shenya on Unreal Engine Marketplace.

.. image:: /images/Shenya-cover.jpg
	:align: center

|

Polycount
=========

+---------------+-------+
| Model Parts   | Tris  |
+===============+=======+
| Head          | 10208 |
+---------------+-------+
| Body          | 19864 |
+---------------+-------+
| Teeths Tongue | 1226  |
+---------------+-------+
| Eyebrowlashes | 5088  |
+---------------+-------+
| Hairs         | 13496 |
+---------------+-------+
| Hat           | 2154  |
+---------------+-------+
| Cap           | 1547  |
+---------------+-------+
| Tanktop       | 2678  |
+---------------+-------+
| Jacket        | 13391 |
+---------------+-------+
| Jeans         | 7647  |
+---------------+-------+
| Belt          | 1718  |
+---------------+-------+
| Boots         | 7056  |
+---------------+-------+
| Eyes          | 1280  |
+---------------+-------+
| Eyes Shadow   | 760   |
+---------------+-------+
| ---Total---   | 88113 |
+---------------+-------+

|

Retargeting Animations
======================

Step1: 

 - Select the animations that you want to retarget from
 
 - Right click on them and choose *Retarget Anim Assets -> Duplicate Anim Assets and Retarget*

.. image:: /images/retarget-step1.jpg
	:align: center


Step2: 

 - In the "Select Skeleton" pop up Window...
 
 - Uncheck "Show Only Compatible Skeletons"
 
 - Select SK_Shenya_Skeleton
 
 - Change the output location if you want

 - Click on Retarget.

.. image:: /images/retarget-step2.jpg
	:align: center

|

Notes on Blendshapes / Morph Targets
====================================

jeans_loose_end
---------------
Default jeans is tucked into the boots, this blendshape can be used in situation if the jeans are not using boots (eg. bare feet, wearing slippers, etc)

.. image:: /images/jeans-loose-end.gif
	:align: center

|

Using RGB Maps for Customizing Colors
=====================================

Materials that has "tint" in their name can utilize RGB texture to assign which area to colorize for the texture.

.. image:: /images/tint-material.jpg
	:align: center

.. image:: /images/material-settings.jpg
	:align: center


For example, for the tanktop, you can create your own design in Photoshop, use the Red, Green and Blue Channel to set the 3 color areas, and use the mask in the material.

.. image:: /images/rgb-mask.jpg
	:align: center

|

to achieve something like this:

.. image:: /images/rgb-mask-example.jpg
	:align: center

|

Using Cap
=========

The default skeletal mesh (SK_Shenya) doesn't have a cap on it, to use the cap, you need to construct the character parts inside a Blueprint.

.. image:: /images/using-cap1.jpg
	:align: center

The default hair (SK_Shenya_Hairs) will intersect with the cap, so a separate hair mesh (SK_Shenya_Hairs_Capfit) is created to fit it inside the cap.

.. image:: /images/using-cap2.jpg
	:align: center


Two type of mesh are provided for the cap, one is bound to the skeleton (SK_Shenya_Cap), easy to setup but will be very hard to tweak the position and rotation.

The other cap mesh (SM_Shenya_Cap) can be attached to a socket and allows you to adjust the translation, rotation or scale of the hat more easily.

.. image:: /images/cap-meshes.jpg
	:align: center


|


About Animation
===============

.. image:: /images/animations-list.jpg
	:align: center

Shenya comes with some pre-retargeted animations.

Side Note: Echo's Animation is not retargeted inside Unreal Engine but retargeted inside Maya using HumanIK.

.. image:: /images/anim-smile-blink.jpg
	:align: center

Anim_Smile_Blink is the only unique animation and it is just blendshapes animation (ie. no skeletal animation data inside).

Example of how it is used inside the Animation Blueprint:

.. image:: /images/using-smile-blink-animation.jpg
	:align: center

|


Credits for Resources Used
==========================

.. image:: /images/thalurania-glaucopis.jpg
	:align: center

The bird drawing on the tanktop is using photo provided by `BioDivLibrary <https://www.flickr.com/photos/biodivlibrary/7462498198/in/photostream/>`_ (Creative Commons).

|
