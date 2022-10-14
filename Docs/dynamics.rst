
###############################
Dynamic Meshes
###############################

.. role:: folder
.. role:: material2

.. _dynamics:

Dynamic Meshes are meshes that are not using the main skeleton. These meshes have extra bones (chains) to be used for dynamic simulations (either with physics assets, Anim Dynamics node, or by plugins like `KawaiiPhysics <https://github.com/pafuhana1213/KawaiiPhysics/>`_)

A Dynamic Mesh is put into its own folder because it has its own skeleton ( [ SK_\*\*\*_Dynamic_Skeleton ] ) and animation blueprint ( [ ABP_\*\*\*_Dynamic ] ). Sometimes it also has a Physics Assets ( [ SK_\*\*\*_Dynamic_Physics ] ). The folder is named \*\*\*_Dynamic.

Dynamic Folders
===============

.. image:: /images/dynamics/dynamic-folders.jpg
	:align: center


The animation blueprint is being used by < BP_Shenya_Modular_Dynamic > inside the the :abbr:`📁Blueprints (Shenya\\Blueprints)` folder.

|

Hair2_Dynamic
-------------

These are the extra bones for < SK_Shenya_Hair1_Dynamic >.

Hair1_Dynamic is simulated with Anim Dynamics nodes (Animation Blueprint) so it doesn't comes with any physics asset.

.. image:: /images/dynamics/hair2-extra-bones.jpg
	:align: center

|

List of Bones for Hair1_Dynamic
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. admonition:: Target List
	:class: refbox

	:Hair2: * front_A_01, front_A_02, front_A_03, front_A_04, front_A_end
				* side_left_A_01, side_left_A_02, side_left_A_03, side_left_A_04, side_left_A_05, side_left_A_06, side_left_A_end
				* side_left_B_01, side_left_B_02, side_left_B_03, side_left_B_04, side_left_B_05, side_left_B_06, side_left_B_end
				* side_right_A_01, side_right_A_02, side_right_A_03, side_right_A_04, side_right_A_05, side_right_A_06, side_right_A_end
				* side_right_B_01, side_right_B_02, side_right_B_03, side_right_B_04, side_right_B_05, side_right_B_06, side_right_B_end
				* ponytail_01, ponytail_02, ponytail_03, ponytail_04, ponytail_05, ponytail_06, ponytail_07, ponytail_08, ponytail_09, ponytail_end

|
|

Jacket1_Dynamic
---------------

These are the extra bones for < SK_Shenya_Coresuit1_Jacket1_Dynamic >

.. image:: /images/dynamics/jacket1-extra-bones.jpg
	:align: center

|

Jacket1_Dynamic is simulated with RigidBody node (Animation Blueprint) so it has a physics asset.

.. image:: /images/dynamics/jacket1-physics-asset.jpg
	:align: center

|

List of Bones for Jacket1_Dynamic
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. admonition:: Target List
	:class: refbox

	:Jacket1: * jacket_front_01_l, jacket_front_02_l, jacket_front_03_l, jacket_front_04_l, jacket_front_l_end
				* jacket_front_01_r, jacket_front_02_r, jacket_front_03_r, jacket_front_04_r, jacket_front_r_end
				* jacket_side_A_01_l, jacket_side_A_02_l, jacket_side_A_03_l, jacket_side_A_04_l, jacket_side_A_l_end
				* jacket_side_A_01_r, jacket_side_A_02_r, jacket_side_A_03_r, jacket_side_A_04_r, jacket_side_A_r_end
				* jacket_side_B_01_l, jacket_side_B_02_l, jacket_side_B_03_l, jacket_side_B_04_l, jacket_side_B_l_end
				* jacket_side_B_01_r, jacket_side_B_02_r, jacket_side_B_03_r, jacket_side_B_04_r, jacket_side_B_r_end
				* jacket_back_A_01_l, jacket_back_A_02_l, jacket_back_A_03_l, jacket_back_A_04_l, jacket_back_A_l_end
				* jacket_back_A_01_r, jacket_back_A_02_r, jacket_back_A_03_r, jacket_back_A_04_r, jacket_back_A_r_end
				* jacket_back_B_01_l, jacket_back_B_02_l, jacket_back_B_03_l, jacket_back_B_04_l, jacket_back_B_l_end
				* jacket_back_B_01_r, jacket_back_B_02_r, jacket_back_B_03_r, jacket_back_B_04_r, jacket_back_B_r_end

|

