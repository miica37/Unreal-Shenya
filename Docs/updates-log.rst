
###############################
Updates Log
###############################

.. role:: folder
.. role:: material
.. role:: material2

.. _updates_v2:

2.0 (@@/10/2022)
--------------------
Skeleton:
   * Fixed right arm bones rotated to the back and not being symmetrical to the left arm bone
   * Skeleton is reoriented to match more closely to UE4's mannequin to produce better results when retargeting

Meshes:
   *  New Outfit
     -  < SK_Shenya2 >
     -  < SK_Shenya_Hair2 >
     -  < SK_Shenya_Hoodie_Jacket >
     -  < SK_Shenya_Short_Jeans > (but still share the same textures and material with the long Jeans)
     -  < SK_Shenya_Long_Boots >
     -  < SK_Shenya_Sunglasses >

   *  Added a few Static Meshes
     -  < SM_Shenya_Cap >
     -  < SM_Shenya_Sunglasses >
   
   *  Added Modular Body Parts
     -  < SK_Shenya_Abdomen >
     -  < SK_Shenya_Arms1 >
     -  < SK_Shenya_Chest_Top >
     -  < SK_Shenya_Legs >
     -  < SK_Shenya_Legs2 >
     -  < SK_Shenya_Upperbody1 >

   *  < SK_Shenya_Hairs > is now < SK_Shenya_Hair1 >
     -  Hair mesh is modified (previous polycount 13496, current polycount 15202)
     -  Hair textures are modified too

   *  Head Blendshapes
     -  Fix eyelashes not moving during eye movements
     -  Fix eyebrows not moving with skin during brows movements
     -  Fix teeths and tongues not moving during jaw movements
     -  Rework some blendshapes like Jaw Open, Mouth Close, Mouth Left, Mouth Right, Mouth Lower Down, Mouth Upper Up
     -  Added tongue and teeth movements: Tongue Left, Tongue Right, Lower Teeth Up
     -  Added a new blendshape "Remove Default Smile" because a bit of smile is added to the base expression, this new blendshape can be used to create a neutral expression.
   
   *  For the head the mesh is tweaked around the brows area to soften the look; the eyes area (together with the eyeballs) are also being pushed to the front slightly
   
   *  Added vertex colors to the eyes to work with Duo Eye Colors material.

   *  Remove jeans blendshapes (Jeans Loose End), instead of blendshapes, a different mesh is provided to fit the boots. New Jeans mesh: < SK_Shenya_Jeans_FitBoots > and < SK_Shenya_Jeans_FitBoots2 >

Materials:
   *  [ M_Skin_Master ] is upgraded to [ M_Shenya_Fullbody_Master ] which now able to assign the head and body with the same material ( [ MI_Shenya_Head ] and [ MI_Shenya_Body ] are now [ MI_Shenya_Fullbody ] ).
   *  Added [ M_Shenya_Fullbody_Dirt_Master ] material to add dirt to the skin

   *  Remove "Use Color" Switch parameters from all tint master materials (to avoid shaders recompiling).
   *  Added [ M_Generic_Tint_Dirt_Master ] material to add dirt to the base color
   *  Added [ M_Generic_Tint_Dirt_Design_Master ] material to add a custom design to the base color
   *  Added [ M_Generic_Tint_Dirt_Design_Overlay_Master ] (same as above but using Overlay instead of alpha blend)
   *  Added [ M_Generic_Tint_Cutout_Master ] (but this is not being used anywhere)
   *  Added [ M_Hair_Band_Tint_Master ] which is used for the hand band of Hair2
   *  Added [ M_Shenya_Glass_Master ] which is used for the glass of Sunglasses
   *  [ M_Shenya_Eyes_Shadow ] added an option to adjust the opacity of eyes shadow
   *  [ M_Eyes_Master ] added an option to change the eyes color
   *  Added [ M_Duo_Eyes_Master ] material to give the eyes two colors
   *  Redid all the material presets (7 new character skins and the old one is removed)
   *  Added [ M_Grid ] for the environment
   *  Added [ M_Wireframe ] (but not being used)
 
Preview Map:
   *  Added Grid Material ( [ M_Grid ] and [ MI_Grid_Floor ] ) for the Preview level
   *  Added a Scale Reference area to compare Shenya's size with the size of UE4's Mannequin

Animations:
   *  Retargeted all the animations because the base skeleton has changed.
   *  Redid Anim_Smile_Blink
   *  Added a few poses: < Center_Pose >, < Folded_Arms_Pose >, < Pakelang_Pose >, < Seven_Pose >

Dynamics:
   *  Added < Hair2_Dynamic > and < Jacket_Dynamic > (with extra bones for dynamic simulations)

Textures:
   * Added *Master* Textures to be used just for the Master Materials (in the folder :folder:`Shenya\\Textures\\Master` : < T_Master_D >, < T_Master_MRAO >, < T_Master_N >, < T_Master_RGB >)
   *  Changed the skin texture. It is now based on the skin texture of another character Meryl. Old texture still exist and renamed to < T_Shenya_Body_D0 > and < T_Shenya_Head_D0 > (added a zero at the end)
   *  Modified the Jeans and Cap base color textures to more neutral grayish for them to work better when tinting (previous colors are too dark to work well with tinting)
   *  Added < T_Shenya_Eyes_D3 > which is based on another character Meryl's eyes texture
   *  Added < T_Shenya_Fingernails_Mask > to change the color of fingernails
   *  Added some dirts textures
   *  Modified Hairs textures which is now slightly thinner and less wavy.

Fbx:
   * Added Fbx files (in the folder :folder:`Shenya\\Fbx`)

Unreal Engine 5:
   * Added IK Rig for retargeting in UE5 (in the folder :folder:`Shenya\\Meshes` < IK_Shenya > )

Documentation:
   * More efforts on documentation and updated to reflect new changes

|



1.01 (20/06/2022)
--------------------

  * Fix incorrect orientation of root bone
  
  * Fix incorrect position of IK bones

|

1.0 (09/04/2022)
--------------------

First Release
