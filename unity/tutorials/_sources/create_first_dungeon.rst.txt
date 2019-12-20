Create your first Dungeon
=========================

Install Dungeon Architect
-------------------------

Install and import `Dungeon Architect <http://u3d.as/nAL>`_ from the Asset Store. You should see the following folders:

.. image:: /images/tutorial/01/da_folders.png
   :align: center

Setup Dungeon Prefab
--------------------

Create a new Scene

Navigate to ``DungeonArchitect > Prefabs`` and drop in the ``DungeonGrid`` prefab on to the scene

.. image:: /images/tutorial/01/drop_grid_prefab.png
   :align: center

Select the dungeon game object and inspect the properties. We'll need to assign a new theme before we can build the dungeon

.. figure:: /images/tutorial/01/select_dungeon_go.png
   :align: center

.. figure:: /images/tutorial/01/da_dungeon_prop.png
   :align: center


Assign Theme
------------

Assign an existing theme to the dungeon actor

 * Navigate to ``Assets\DungeonArchitect_Samples\Demo_Theme_Candy\Themes``
 * Assign theme file named ``CandyDungeonTheme`` as shown in the image below

.. figure:: /images/tutorial/01/dungeon_assign_theme.png
   :align: center


Build Dungeon
-------------

Select the ``DungeonGrid`` game object and click the ``Build Dungeon`` button in the Inspector window

.. figure:: /images/tutorial/01/build_dungeon.png
   :align: center

.. figure:: /images/tutorial/01/candy_dungeon.jpg
   :align: center


Randomize Dungeon
-----------------

Select the ``DungeonGrid`` game object and change the Seed value in the configuration.  Changing this value will create a dungeon with a different layout


.. figure:: /images/tutorial/01/rand_dungeon.png
   :align: center

Click ``Build Dungeon`` button to rebuild the dungeon with the new seed


Organization
------------

All the dungeon objects are created on the root hierarchy and makes it difficult to organize.   We'll configure it so all objects are spawned under a certain game object

.. figure:: /images/tutorial/01/org01.png
   :align: center

Lets destroy this current dungeon, configure it for better organization and then rebuild

Destroy Existing Dungeon
^^^^^^^^^^^^^^^^^^^^^^^^

Search for ``dungeon`` on the hierarchy search box

.. figure:: /images/tutorial/01/org02.png
   :align: center

   
Select the DungeonGrid game object and click the ``Destroy Dungeon`` button

Clear out the search text box in the hierarchy.  Your hierarchy should now look like this

.. figure:: /images/tutorial/01/org04.png
   :align: center


Configure Parent Object
^^^^^^^^^^^^^^^^^^^^^^^

Create an empty Game Object.  All our dungeon items will go inside this parent object

.. figure:: /images/tutorial/01/create_empty.png
   :align: center
   
   Create an empty game object


Rename the parent object (e.g. ``Dungeon Items``)

.. figure:: /images/tutorial/01/org05.png
   :align: center
   
   
Select the parent object and **Reset the transform**

.. figure:: /images/tutorial/01/org06.png
   :align: center

.. figure:: /images/tutorial/01/org07.png
   :align: center


Select the parent object and set it to **static**

.. figure:: /images/tutorial/01/org08.png
   :align: center


Assign the parent object to the GridDungeon game object

.. figure:: /images/tutorial/01/org09.png
   :align: center
   

Rebuild Dungeon
^^^^^^^^^^^^^^^

Select the GridDungeon game object and click ``Build Dungeon``

All your dungeon game objects will be organized under the parent object

.. figure:: /images/tutorial/01/org10.png
   :align: center
   
   
 


