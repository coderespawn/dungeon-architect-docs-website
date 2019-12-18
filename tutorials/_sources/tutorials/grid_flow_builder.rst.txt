Grid Flow Builder
=================

The Grid Flow Builder offers a rich set of tools to control the flow of your dungeons and item placement


Create a Grid Flow Dungeon
--------------------------

Setup Dungeon Prefab
^^^^^^^^^^^^^^^^^^^^

Create a new scene.  Navigate to ``Assets/DungeonArchitect/Prefabs`` and drop in the DungeonGridFlow prefab on to the scene

.. figure:: /images/tutorial/04/01.png
   :align: center
   

Select the DungeonGridFlow game object you just dropped and reset the transform

.. figure:: /images/tutorial/04/02.png
   :align: center
   

Setup Parent Object
^^^^^^^^^^^^^^^^^^^

Create a new Parent object where all the spawned dungeon items will go in. 

.. figure:: /images/tutorial/04/03.png
   :align: center
   
Reset the parent object's transform and set it to static

.. figure:: /images/tutorial/04/04.png
   :align: center


Assign the parent object

.. figure:: /images/tutorial/04/05.png
   :align: center


This makes sure all the spawned dungeon objects are placed under this parent object


Setup Theme
^^^^^^^^^^^

There's a theme available in the samples folder which we'll use for this tutorial section

Navigate to ``Assets\DungeonArchitect_Samples\DemoBuilder_GridFlow\Theme`` and assign the theme ``ThemePrehistoric`` to the DungeonGridFlow game object

.. figure:: /images/tutorial/04/06.png
   :align: center


Setup GridFlow Graph
^^^^^^^^^^^^^^^^^^^^

This builder requires another asset called the `Grid Flow Graph`.   This is a graph that helps you  control the flow of your dungeon. In this section, we'll use an existing graph from the samples folder

Navigate to ``Assets\DungeonArchitect_Samples\DemoBuilder_GridFlow\FlowGraph`` and assign the graph ``DemoGridFlow`` to the `DungeonGridFlow` game object's ``Flow Asset`` property

.. figure:: /images/tutorial/04/07.png
   :align: center



Build Dungeon
^^^^^^^^^^^^^

Select the ``DungeonGridFlow`` game object and click ``Build Dungeon`` button from the inspector window

.. figure:: /images/tutorial/04/08.jpg
   :align: center
   
   GridFlow dungeon built using the Prehistoric theme


.. figure:: /images/tutorial/04/09.jpg
   :align: center
   
   GridFlow dungeons support key-locks
   

Open Grid Flow Editor
^^^^^^^^^^^^^^^^^^^^^

Let's open the GridFlow asset in the editor:

Navigate to ``Assets\DungeonArchitect_Samples\DemoBuilder_GridFlow\FlowGraph`` and double click on ``DemoGridFlow``.   

Dock the editor window so you see both the scene view and the grid flow editor

.. figure:: /images/tutorial/04/10.jpg
   :align: center
   
Click the Play button on the top left of the flow editor to build a new dungeon in the Grid Flow Editor

.. figure:: /images/tutorial/04/11.png
   :align: center

.. figure:: /images/tutorial/04/flow_editor_anim.gif
   :align: center



Link Editor with Dungeon
^^^^^^^^^^^^^^^^^^^^^^^^

We are going to link up the dungeon we have on the scene (`DungeonGridFlow` game object) with the Grid Flow Editor so when we generate a new dungeon in the editor, it syncs up the dungeon on the scene


Click an empty space (grey area) in the Execution Graph

.. figure:: /images/tutorial/04/12.png
   :align: center
   
   Click anywhere in the empty area
   
   
This will show up the execution graph properties in the Inspector window


.. figure:: /images/tutorial/04/13.png
   :align: center
   
   Execution Graph properties


Assign the dungeon game object by dragging the DungeonGridFlow over

.. figure:: /images/tutorial/04/14.jpg
   :align: center
   
Now build the dungeon again by clicking the Play button in the Execution Graph Window

.. figure:: /images/tutorial/04/11.png
   :align: center
   

This will recreate the dungeon in the scene view.  The dungeon in the editor window is now synchronized with the dungeon in the scene view

If you double click on any of the tiles in the Tilemap window,  the scene view should focus on that tile/item


Double click on the Bonus Item (``B``) in the tilemap.  


.. figure:: /images/tutorial/04/15.png
   :align: center
   
The scene view should zoom in on the treasure chest

.. figure:: /images/tutorial/04/16.jpg
   :align: center
   

Explore Grid Flow Graph
^^^^^^^^^^^^^^^^^^^^^^^

After you've built a dungeon in the editor (by hitting the play button on the top left), you can select each node and see how the dungeon layout was built, as shown in the lower preview panels

.. figure:: /images/tutorial/04/flow_editor_node_preview.gif
   :align: center
   
   Select a node to preview the build process



Design a GridFlow Graph
-----------------------

In the previous section, we used an existing Grid Flow graph. In this section, we'll design one ourselves.

Setup
^^^^^

Destroy the existing dungeon and clear out the Flow Asset that we assigned earlier


.. figure:: /images/tutorial/04/17.png
   :align: center
   
   DungeonGridFlow game object properties


Create a new Grid Flow asset from either the Create menu or the Main Menu

.. figure:: /images/tutorial/04/18.png
   :align: center
   
   Create Menu


.. figure:: /images/tutorial/04/19.png
   :align: center
   
   Main Menu


Rename to something appropriate and double click the grid flow asset to open it in the editor

We won't be needing the scene view for some time.  Dock the editor so we have more working area

.. figure:: /images/tutorial/04/20.png
   :align: center
   

