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
   

Notice that there is only one node in the Execution graph, the ``Result`` node.   Our final output should be connected to this node


Create Grid
^^^^^^^^^^^

Right click on an empty area in the Execution Graph and from the context menu select ``Layout Graph > Create Grid``

.. figure:: /images/tutorial/04/menu/L_CreateGrid.png
   :align: center


.. figure:: /images/tutorial/04/21.png
   :align: center
   

Connect this node to the ``Result`` node and hit play 


   
.. figure:: /images/tutorial/04/22.png
   :align: center

   
.. figure:: /images/tutorial/04/11.png
   :align: center
   

This node creates an initial grid to work with 

.. figure:: /images/tutorial/04/23.png
   :align: center


In this builder, you first design your level in an abstract layout graph like this and then move the final result to a tilemap


Create Main Path
^^^^^^^^^^^^^^^^

We'll next create a main path within this grid. The main path has a spawn point and goal

Create a new node ``Layout Graph > Create Math Path``

.. figure:: /images/tutorial/04/menu/L_CreateMainPath.png
   :align: center
   


Unlink the ``Create Grid`` node from the ``Result`` node (do this by right clicking on the node's orange border)


.. figure:: /images/tutorial/04/24.png
   :align: center


Link the nodes up like below and hit Play

.. figure:: /images/tutorial/04/25.png
   :align: center


This node creates a main path in the grid.  Keep hitting the play button for different result

.. figure:: /images/tutorial/04/26.gif
   :align: center
   
.. note::
   If you do not see random results when you hit play, make sure randomize is enabled.  Enable this by clicking on an empty area in the Execution Graph to show the properties. In the inspector, select ``Randomize Seed``


Select the ``Create Main Path`` node and inspect the properties

.. figure:: /images/tutorial/04/27.png
   :align: center

We'll leave everything to default for now

Notice the `Path Name` parameter is set to ``main``   This is the name of the path and we will be referencing this path in the future nodes with this name

You can adjust the size of the path.   ``Start Marker Name`` and ``Goal Marker Name`` lets you specify a name for the markers. You can then create these markers in the theme file and add any object you like.    In the `Prehistoric` theme, there's a marker already created with these names and a player controller is placed under ``SpawnPoint`` marker and a level goal handler prefab is placed under ``LevelGoal`` marker

.. figure:: /images/tutorial/04/28.jpg
   :align: center


Create Alternate Path
^^^^^^^^^^^^^^^^^^^^^

We'll next create an alternate path pathing off the main path so the player has another way of reaching the goal

Create a new node ``Layout Graph > Create Path``

.. figure:: /images/tutorial/04/menu/L_CreatePath.png
   :align: center

Connect the nodes together like below

.. figure:: /images/tutorial/04/29.png
   :align: center

Leave all the properties as default and hit play

.. figure:: /images/tutorial/04/30.png
   :align: center


Select the ``Create Path`` node and inspect the properties

.. figure:: /images/tutorial/04/31.png
   :align: center


Change the `Path Name` from ``path`` to ``alt``.  We will be referencing this path as ``alt`` in the future

.. figure:: /images/tutorial/04/32.png
   :align: center


You can specify the paths from which this path should start and end.    The `Start From Path` parameter is set to ``main``, referencing the main path we created in the previous section

The `End On Path` is left empty, so the end of this path doesn't connect back to anything.   We'd like this path to connect back to the main path. 

Set the `End On Path`` parameter to ``main``

.. figure:: /images/tutorial/04/33.png
   :align: center


======================= =======================
**Min Path Size**       3
**Max Path Size**       3
**Path Name**           alt
**Node Color**          orange
**Start From Path**     main
**End On Path**         main
======================= =======================

This will make the alternate path (orange) connect back to the main path (green)

.. figure:: /images/tutorial/04/34.png
   :align: center


Keep hitting Play for different results

.. figure:: /images/tutorial/04/35.gif
   :align: center


Create Treasure Room (Main)
^^^^^^^^^^^^^^^^^^^^^^^^^^^

We'll add a treasure room connected to the main path

Add a new node ``Layout Graph > Create Path`` and set it up as follows:

.. figure:: /images/tutorial/04/37.png
   :align: center

.. figure:: /images/tutorial/04/36.png
   :align: center

======================= =======================
**Min Path Size**       1
**Max Path Size**       3
**Path Name**           treasure_main
**Node Color**          yellow
**Start From Path**     main
**End On Path**         main
======================= =======================

.. figure:: /images/tutorial/04/38.png
   :align: center


Create Treasure Room (Alt)
^^^^^^^^^^^^^^^^^^^^^^^^^^

We'll add another treasure room connected to the ``alt`` path but keep the ``End On Path`` parameter empty so it doesn't connect back to anything:

Add a new node ``Layout Graph > Create Path`` and set it up as follows:

.. figure:: /images/tutorial/04/39.png
   :align: center

.. figure:: /images/tutorial/04/40.png
   :align: center

======================= =======================
**Min Path Size**       1
**Max Path Size**       1
**Path Name**           treasure_alt
**Node Color**          yellow
**Start From Path**     alt
**End On Path**         
======================= =======================

.. figure:: /images/tutorial/04/41.png
   :align: center


Create Key Room
^^^^^^^^^^^^^^^

We'll create a room connected to the main path which will act as the key room. We'll later configure this room to have a key that opens up a lock in the main path. It will also have a NPC (key guardian) guarding the key

Add a new node ``Layout Graph > Create Path`` and set it up as follows:


.. figure:: /images/tutorial/04/42.png
   :align: center

.. figure:: /images/tutorial/04/43.png
   :align: center

======================= =======================
**Min Path Size**       1
**Max Path Size**       1
**Path Name**           key_room
**Node Color**          cyan
**Start From Path**     main
**End On Path**         
======================= =======================

.. figure:: /images/tutorial/04/44.png
   :align: center

.. note:: We've named this path ``key_room``. It will be referenced later on when creating the key locks


Create Key-Lock (Main)
^^^^^^^^^^^^^^^^^^^^^^

We'll next create a key-lock system on the main path.  Our key will go on the Key Room we created earlier (``key_room`` path) and the lock will be somewhere in the main branch (``main`` path)


Add a new node ``Layout Graph > Create Key Lock`` and set it up as follows:


.. figure:: /images/tutorial/04/45.png
   :align: center

.. figure:: /images/tutorial/04/46.png
   :align: center

======================= =======================
**Key Branch**          key_room
**Lock Branch**         main
**Key Marker Name**     KeyMain
**Lock Marker Name**    LockMain
======================= =======================

.. figure:: /images/tutorial/04/47.png
   :align: center


Specify the `Key Branch` as ``key_room`` and `Lock Branch` as ``main``

Set marker name for the key as ``KeyMain`` and lock as ``LockMain``.    Then in the theme file, you'd create marker nodes with these names and add your key and locked gate prefabs.   

The prehistoric theme already has these setup

.. figure:: /images/tutorial/04/48.png
   :align: center
   

Create Key-Lock (Treasure Main)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We need a key-lock to guard the treasure room in the main branch

Add a new node ``Layout Graph > Create Key Lock`` and set it up as follows:


.. figure:: /images/tutorial/04/49.png
   :align: center

.. figure:: /images/tutorial/04/50.png
   :align: center

======================= =======================
**Key Branch**          main
**Lock Branch**         treasure_main
**Key Marker Name**     KeyTreasure
**Lock Marker Name**    LockTreasure
======================= =======================


.. figure:: /images/tutorial/04/51.png
   :align: center


Set marker name for the key as ``KeyTreasure`` and lock as ``LockTreasure``.    Then in the theme file, you'd create marker nodes with these names and add your key and locked gate prefabs.   

The prehistoric theme already has these setup

.. figure:: /images/tutorial/04/52.png
   :align: center
   
   
Spawn Enemies (Main, Alt)
^^^^^^^^^^^^^^^^^^^^^^^^^

We'll use the ``Spawn Items`` node to spawn enemies on the ``main`` and ``alt`` paths

Create a new node ``Layout Graph > Spawn Items`` and set it up as follows:


.. figure:: /images/tutorial/04/53.png
   :align: center

.. figure:: /images/tutorial/04/54.png
   :align: center

======================= =======================
**Paths**               main, alt
**Item Type**           Enemy
**Marker Name**         Grunt
**Min Count**           1
**Max Count**           5
======================= =======================

.. figure:: /images/tutorial/04/55.png
   :align: center


This will spawn enemies in the nodes, gradually increasing the number of enemies based on the difficulty. The difficulty increases as we get closer to the goal. You can control this from the `Spawn Method` properties. Leave it to default for now


We've specified the marker name as ``Grunt`` and an appropriate marker node should be created in the theme file so we can spawn prefabs under it.  The pre-historic theme already has this marker


.. figure:: /images/tutorial/04/56.png
   :align: center


You can control the placement of items (in the tilemap) from the `Placement Method` property section. Leave it to default for now

Spawn Bonus (Treasure Chests)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Spawn treasure chests in your bonus rooms using the `Spawn Items` node


Create a new node ``Layout Graph > Spawn Items`` and set it up as follows:


.. figure:: /images/tutorial/04/57.png
   :align: center

.. figure:: /images/tutorial/04/58.png
   :align: center

======================= =======================
**Paths**               treasure_main, treasure_alt
**Item Type**           Bonus
**Marker Name**         Treasure
**Min Count**           1
**Max Count**           1
======================= =======================

.. figure:: /images/tutorial/04/59.png
   :align: center
   

We've specified the marker name as ``Treasure`` and an appropriate marker node should be created in the theme file so we can spawn prefabs the treasure chest under it.  The pre-historic theme already has this marker

.. figure:: /images/tutorial/04/60.png
   :align: center
   

Spawn Key Guardian
^^^^^^^^^^^^^^^^^^

We'll add an NPC in the Key room guarding the key

Create a new node ``Layout Graph > Spawn Items`` and set it up as follows:



.. figure:: /images/tutorial/04/61.png
   :align: center

.. figure:: /images/tutorial/04/62.png
   :align: center

========================= =======================
**Paths**                 key_room
**Item Type**             Enemy
**Marker Name**           KeyGuardian
**Min Count**             1
**Max Count**             1
**Min Spawn Difficulty**  1
========================= =======================

.. figure:: /images/tutorial/04/63.png
   :align: center
   
You'll need to create a marker named ``KeyGuardian`` in the theme file and place your NPC prefab under it.   This marker doesn't exist in the `Prehistoric` theme and you'll need to create it yourself if you want to visualize it


The `Min Spawn Difficulty` is set to ``1``.   The first node in the branch will have a difficulty of ``0`` and the last node ``1``.  Sometimes, the yellow branch may be 3 nodes long.  Since we want the chest to occur only on the last node, we've set this value to ``1``

Spawn Health Pack
^^^^^^^^^^^^^^^^^

We'll use the `Spawn Items` node to spawn a few health pickups along the `main` and `alt` paths

This section also shows you how to use the `Custom` Item Type 

Create a new node ``Layout Graph > Spawn Items`` and set it up as follows:



.. figure:: /images/tutorial/04/64.png
   :align: center

.. figure:: /images/tutorial/04/65.png
   :align: center

========================= =======================
**Paths**                 main, alt
**Item Type**             Custom
**Marker Name**           HealthPickup
**Min Count**             0
**Max Count**             1
**Spawn Probability**     0.5 

**Custom Item Info**
-------------------------------------------------
>> **Item Type**          health_pickup
>> **Text**               Health
>> **Text Color**         [Red]
>> **Background Color**   [White]
========================= =======================

.. figure:: /images/tutorial/04/66.png
   :align: center
   
   
.. note:: You'll need to create a marker named ``HealthPickup`` in your theme file and add your health pack prefab



Finalize Layout Graph
^^^^^^^^^^^^^^^^^^^^^

After we are done designing the layout graph, we'll need to finalize it with the `Finalize Graph` node.    This node does a few things:

* Move the locks from the nodes on to the links
* Create one way doors (so we don't go around locked doors)
* Assign room types (Room, Corridor, Cave)

Create a new node ``Layout Graph > Finalize Graph`` and set it up as follows:

Leave all the properties to default

.. figure:: /images/tutorial/04/67.png
   :align: center

.. figure:: /images/tutorial/04/68.png
   :align: center


.. figure:: /images/tutorial/04/69.gif
   :align: center




