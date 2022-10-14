
################################
ALS (Advanced Locomotion System)
################################

.. role:: folder

.. _als:

`Advanced Locomotion System V4 at Unreal Engine Marketplace <https://www.unrealengine.com/marketplace/en-US/product/advanced-locomotion-system-v1>`_

.. image:: /images/als/als-ue-marketplace.jpg
    :align: center

I got the character to be able to work with ALS on UE4 somewhat, but please be aware that since the body porpotion isn't the same as the ALS character, some actions doesn't look right and requires some advanced editing to the blueprint to solve those issues.

This guide shows what I did to get it somewhat working. Other issues like incorrect hand positions when holding weapons are left unresolved as I haven't found out how to solve those yet.

Following resorces can be helpful to setup the character if you are new to ALS.

Resources:
   * `ALSV3 - Working with Other Characters (ALS Old Secret Playlist) <https://www.youtube.com/playlist?list=PLAR8Kc1ZLLKZjnKI_idX7Ik7mN0VORSm_>`_
   * `How to use my female characters with ALS v4 by Quang Phan <https://www.youtube.com/watch?v=ae9uyVWF3Wg>`_
   * PDF guide by @smu on `Quang Phan Discord <https://discord.com/channels/512242191465185300/518274796111527948>`_ (you can download the pdf somewhere under #tutorials-ue4)
     \* *There's a section about Weapon alignment at the bottom of the pdf which you might be interested in.*


|

Issues
=================

.. warning::
   These are among some of the issues that I haven't find how to solve:
   
   .. image:: /images/als/issues.jpg
      :align: center

|

Step by Step Demo
=================

.. warning::
   Note that the following guide is made for another character Meryl and I have modified the text to show Charles but the images remains the one from Meryl. I have tested it to verify the steps can be applied to Charles too.

.. note::
   Youtube Video:
      `Meryl ALS (Advanced Locomotion System) Guide <https://youtu.be/g18-Mmszp5w>`_


.. warning::
   This demo is using Unreal Engine **4.27** and ALS **V4** (Not V3 or any other version).

Assign Skeleton
---------------

#. This UE4 Project starts with ALS asset and Charles asset.

   .. image:: /images/als/launcher-als.jpg
      :align: left
   
   .. image:: /images/als/launcher-meryl.jpg
      :align: right

   .. image:: /images/als/content.jpg
      :align: center

#. Go to folder :folder:`Content ➧ Charles ➧ Meshes`,

   Select the Skeletal Mesh < SK_Charles > and assign it the skeleton < ALS_Mannequin_Skeleton >

   .. image:: /images/als/step-assign-skeleton.jpg
      :align: center

#. Go to folder :folder:`Content ➧ AdvancedLocomotionV4 ➧ Blueprints ➧ CharacterLogic`,

   .. image:: /images/als/content-bp.jpg
      :align: center

   Open the blueprint < ALS_AnimMan_CharacterBP > and change the skeletal mesh to < SK_Charles >.

   .. image:: /images/als/step-bp-change-skeletal-mesh.jpg
      :align: center
   
   Reset all the materials.

   .. image:: /images/als/step-bp-reset-materials.jpg
      :align: center

#. Still in < ALS_AnimMan_CharacterBP >, in the **Event Graph**, find **Update Coloring System** and disconnect it. This will solve some Errors popping up.

   .. image:: /images/als/step-bp-disconnect-coloring-system.jpg
      :align: center

#. Compile and Save < ALS_AnimMan_CharacterBP >.

   When you Play, the character's legs will jitter. I find that if I reopen the project, this goes away.

#. Save All the assets and reopen the project (Restart Unreal Engine).

Fix Knees
---------

   #. Go to folder :folder:`Content ➧ AdvancedLocomotionV4 ➧ CharacterAssets ➧ MannequinSkeleton`,

      .. image:: /images/als/content-animbp.jpg
         :align: center
   
      Open < ALS_AnimBP > and change the preview mesh to < SK_Charles >.

      .. image:: /images/als/step-animbp-preview-scene-settings.jpg
         :align: center
      
      Set Viewport to display bones for the character.

      .. image:: /images/als/step-animbp-preview-show-bones.jpg
         :align: center

      .. image:: /images/als/step-animbp-preview-before.jpg
         :align: center

   #. Still in < ALS_AnimBP >, go into **Fook IK**, locate **Modify Knee Targets** and apply following settings

      *  **Transform (Modify) Bone (Left)** Translation Z: 12

      *  **Transform (Modify) Bone (Right)** Translation Z: -12
      
      *  **Two Bone IK (Left)** Effector Location Z: 5
      
      *  **Two Bone IK (Right)** Effector Location Z: -5

      .. image:: /images/als/step-animbp-modify-knee-targets.jpg
         :align: center

   #. Still in < ALS_AnimBP >, under **My Blueprint** tab, find the variable **PelvisAlpha**, set the Value to 1.0, and set the value of **PelvisOffset** Z to 3.5.

      .. image:: /images/als/step-animbp-pelvis-variables.jpg
         :align: center
      
      Knees Fixed:

      .. image:: /images/als/step-animbp-preview-after.jpg
         :align: center

Fix Ragdoll
-----------

   #. Go to folder :folder:`Content ➧ Charles ➧ Meshes`,
 
      Open < SK_Charles_PhysicsAsset >

   #. Display Bones in Skeleton Tree

      .. image:: /images/als/step-physics-show-bones.jpg
         :align: center
      
      Add a Body to **root** (by right click on the root bone, select "Add Shape -> Add Sphere").

      .. image:: /images/als/step-physics-add-body-to-root.jpg
         :align: center

      With the Body selected, set its settings in the Details panel. Set Physics Type to "Kinematic" and set Collision Response to "Disabled".

      .. image:: /images/als/step-physics-edit-root-body-settings.jpg
         :align: center
      
   #. Display Constraints in Skeleton Tree

      .. image:: /images/als/step-physics-show-constraints.jpg
         :align: center

      Select **spine_02 : pelvis Constraint** and lock all the 3 **Angular Limits**. Do the same for **spine_03 : spine_02 Constraint**

      .. image:: /images/als/step-physics-set-constraints.jpg
         :align: center
   
   #. Save the asset.