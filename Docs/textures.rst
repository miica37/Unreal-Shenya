
###############################
Textures
###############################

.. role:: material2
.. role:: red
.. role:: bold-italic


.. image:: /images/textures/content-textures.jpg
    :align: center

Textures for the character are created in Substance Painter and Photoshop.

.. _textures:

PBR Textures
------------
Textures are using PBR (Physically Based Rendering) **Metallic Roughness** Workflow.

A character mesh part usually comes with 4 basic textures: :red:`Diffuse` ( [ T_***_D ] ), :red:`Normal` ( [ T_***_N ] ), :red:`MRAO`  ( [ T_***_MRAO ] ) and :red:`RGB`  ( [ T_***_RGB ] ).

.. image:: /images/textures/content-texture-set.jpg
    :align: center

MRAO
----
MRAO stands for :bold-italic:`M` etallic, :bold-italic:`R` oughness and :bold-italic:`AO` (Ambient Occlusion).

Instead of having 3 different textures (Metallic, Roughness and AO), MRAO is a merged texture of all 3 (packed into the Red, Green and Blue channel).

RGB
---
RGB stands for Red, Green, Blue.

This texture contains 3 masks, each packed into the Red, Green and Blue channel. The different masks are used to tint different areas of the color texture.

Hoodie Jacket RGB Texture Example
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. image:: /images/textures/hoodie-jacket-rgb-texture-example1.jpg
    :align: center

.. image:: /images/textures/hoodie-jacket-rgb-texture-example2.jpg
    :align: center


T_Uniform_RGB
^^^^^^^^^^^^^
[ T_Uniform_RGB ] can be used instead when a certain mesh that doesn't come with a RGB texture.

It can also be used if you want to change the color of the **whole** mesh.

|
