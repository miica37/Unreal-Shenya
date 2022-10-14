
###############################
Animations & Retargeting
###############################

.. role:: folder

.. role:: strike
    :class: strike

Folder Locations
================

In order to differentiate between original animations and retargeted animations, animations are located inside two different folders. Original Animations are inside the :abbr:`📁Animations (Content\\Shenya\\📁Animations)` folder while Retargeted Animations are inside the :abbr:`📁Demo (Content\\Shenya\\Demo)` folder.

In fact, since there are almost no original animations (besides a facial morph target animation :guilabel:`Anim_smile_blink`), you will find **most** of the animation in the :abbr:`📁Demo (Content\\Shenya\\Demo)` folder. This folder contains a few animations retargeted from UE4 Mannequin, Paragon's Yin and Windwalker Echo.

The mannequin's animations are retargeted with UE4 while Paragon's Yin and Windwalker Echo's animation are retargeted using Maya's HumanIK.

|

.. _retarget:

Retargeting Animations
======================

Since Shenya's skeleton is a different proportion than UE4 skeleton which most animation in the marketplace is based on, you will have to do some retargeting for animation.

Documentation:
   You can read more about retargeting for UE4 at the official `Unreal Engine 4.27 Documentation - Animation Retargeting <https://docs.unrealengine.com/4.27/en-US/AnimatingObjects/SkeletalMeshAnimation/AnimationRetargeting/>`_, and UE5 at `Unreal Engine 5.0 Documentation - IK Rig Retargeting <https://docs.unrealengine.com/5.0/en-US/ik-rig-animation-retargeting-in-unreal-engine/>`_.

Below is some step by step instructions:

|

.. note::
	The following guide is for another character Meryl but it should also works the same for Shenya.

|

Unreal Engine 4
---------------

.. note::
	Step by Step Video at Youtube:
		`Animation Retargeting in UE4 // Meryl <https://www.youtube.com/watch?v=EqlSjc5xunU>`_

Step1: 

 - Select the animations that you want to retarget from
 
 - Right click on them and choose *Retarget Anim Assets -> Duplicate Anim Assets and Retarget*

.. image:: /images/retarget-step1.jpg
	:align: center

|

Step2: 

 - In the "Select Skeleton" pop up Window...
 
 - Uncheck "Show Only Compatible Skeletons"
 
 - Select SK_Shenya_Skeleton
 
 - Change the output location if you want

 - Click on Retarget.

.. image:: /images/retarget-step2.jpg
	:align: center


|
|

.. _retarget_ue5:

Unreal Engine 5
---------------

UE5 has a different retargeting process from UE4 which involve creating an IK Rig first for the character. But don't worry it's already been setup and you can find it under :folder:`Shenya ➧ Meshes ➧ UE5` (< IK_Shenya >).

.. warning::
   Note that the following guide is made for another character Meryl and I have modified the text to show Shenya but the images remains the one from Meryl. I have tested it to verify the steps can be applied to Shenya too.

.. note::
	Step by Step Video at Youtube:
		`Animation Retargeting in UE5 // Meryl <https://www.youtube.com/watch?v=JUodYLNm-b4>`_


Create IK Retargeter
^^^^^^^^^^^^^^^^^^^^

   #. Note that you will need < IK_Shenya > and < SK_Shenya_UE5 > and they are inside folder :folder:`Shenya ➧ Meshes ➧ UE5`

      .. image:: /images/animations/retarget-ue5-copy-asset.jpg
		:align: center

   #. Go to folder :folder:`Characters ➧ Mannequins ➧ Rigs`,
     
	  Duplicate < RTG_Mannequin > and name it < RTG_Shenya_to_UE5 > 

	  .. image:: /images/animations/retarget-ue5-duplicate-retargeter.jpg
		:align: center

   #. Open < RTG_Shenya_to_UE5 >
     
	  Set the **Target IKRig** to < IK_Shenya > and **Target Preview Mesh** to < SK_Shenya_UE5 >

	  .. image:: /images/animations/retarget-ue5-set-target-ikrig.jpg
		:align: center

      |

	  I find that I also need to turn OFF the **Retarget IK** option otherwise the retargeted animation looks strange.

	  .. image:: /images/animations/retarget-ue5-turn-off-retarget-ik.jpg
		:align: center

   #. Switch to **Asset Browser** panel and play some animations to check if everything looks alright

|

Duplicate Animation Blueprint
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

   #. Go to folder :folder:`Characters ➧ Mannequins ➧ Animations`,

      Right click on < ABP_Manny > and select **Retarget Animation Assets ➧ Duplicate and Retarget Animation Blueprint**

	  .. image:: /images/animations/retarget-ue5-retarget-animbp.jpg
		:align: center

   #. In the "Duplicate and Retarget Animation Blueprint" Window,

      Set IK Retargeter to < RTG_Shenya_to_UE5 >

      Set Search "Manny" and Replace "Shenya"

      Set the output Folder to :folder:`Shenya ➧ Demo`

	  .. image:: /images/animations/retarget-ue5-retarget-animbp-window.jpg
		:align: center
	
	  |

      Hit the "Retarget" Button. You will find the retargeted animations and anim blueprint at the folder you set above.

|

Duplicate Character Blueprint
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

   #. Go to folder :folder:`ThirdPerson ➧ Blueprints`,

      Duplicate < BP_ThirdPersonCharacter > and name it < BP_Shenya_UE5 >

	  .. image:: /images/animations/retarget-ue5-duplicate-bp.jpg
		:align: center

   #. Open the blueprint < BP_Shenya_UE5 >,

      Change the mesh to < SK_Shenya_UE5 > and set the animation blueprint to < ABP_Shenya >

	  .. image:: /images/animations/retarget-ue5-edit-bp.jpg
		:align: center

   #. Compile and Save

|

Set Player
^^^^^^^^^^

   #. In the World Settings, under **Game Mode ➧ Selected GameMode**,

      Set **Default Pawn Class** to < BP_Shenya_UE5 > (created from the step above)

	  .. image:: /images/animations/retarget-ue5-world-settings.jpg
		:align: center

   #. Play the game to see the retargeted character.

      .. image:: /images/animations/retarget-ue5-done.jpg
		:align: center

|