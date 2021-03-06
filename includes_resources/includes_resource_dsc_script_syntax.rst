.. The contents of this file are included in multiple topics.
.. This file should not be changed in a way that hinders its ability to appear in multiple documentation sets.

The syntax for using the |resource dsc_script| resource in a recipe is as follows:

.. code-block:: ruby

   dsc_script "name" do
     attribute "value" # see attributes section below
     ...
     action :action # see actions section below
   end

where 

* ``dsc_script`` tells the |chef client| that a |windows powershell_dsc_short| resource is based on a |windows powershell| script
* ``name`` is the name of the configuration within a |windows powershell_dsc_short| script; when the ``configuration_name`` attribute is not specified as part of a recipe, ``name`` must also be the name of a valid |windows powershell| cmdlet
* ``attribute`` is zero (or more) of the attributes that are available for this resource
* ``:action`` identifies which steps the |chef client| will take to bring the node into the desired state
