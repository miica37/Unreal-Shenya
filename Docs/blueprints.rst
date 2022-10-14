
###############################
Blueprints
###############################

.. role:: folder

Overview
========

.. image:: /images/blueprints/content-blueprints.jpg
    :align: center

The :abbr:`📁Blueprints (Charles\\Blueprints)` folder contains character blueprints (BP_***) and animation blueprints (AnimBP_***) (which are based on the third person character template of UE 4.22).

< BP_Shenya > uses precombined mesh which is just a really basic setup while < BP_Shenya_Modular_Dynamic > shows a modular + dynamic version by assembling two dynamic skeletal meshes: < SK_Shenya_Hair2_Dynamic > and < SK_Shenya_Jacket_Dynamic >

< SK_Shenya_Hair2_Dynamic > and < SK_Shenya_Jacket_Dynamic > have their own skeleton with extra joint chains, which is why I put them into separate folders.

Some controls added to the < BP_Shenya >:
   
   *  Zoom with Mouse Wheel

   *  Pan Camera Vertically with :kbd:`Q` and :kbd:`E`

|

New Axis Mapping added to Project Settings to work with the blueprints:

.. image:: /images/blueprints/engine-input-settings.jpg
    :align: center
