=====================================================
|chef ctl| (executable)
=====================================================

.. include:: ../../includes_ctl_chef/includes_ctl_chef.rst

chef exec
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_exec.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_exec_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_exec_options.rst

Examples
-----------------------------------------------------
None.

chef gem
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_gem.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_gem_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_gem_options.rst

Examples
-----------------------------------------------------

**Show an existing gem in the chef-dk**

.. code-block:: bash

   $ chef gem list chef-dk

to return something similar to:

.. code-block:: bash

   *** LOCAL GEMS ***
   
   chef-dk (0.1.0)

**Install a gem**

.. code-block:: bash

   $ chef gem install knife-config

to return something similar to:

.. code-block:: bash

   Successfully installed knife-config-1.1.0
   1 gem installed

**View the contents of a gem**

.. code-block:: bash

   $ chef gem content knife-config

to return something similar to:

.. code-block:: bash

   /Users/user/.chefdk/gem/ruby/2.1.0/gems/knife-config-1.1.0/LICENSE
   /Users/user/.chefdk/gem/ruby/2.1.0/gems/knife-config-1.1.0/README.md
   /Users/user/.chefdk/gem/ruby/2.1.0/gems/knife-config-1.1.0/lib/chef/knife/config.rb
   /Users/user/.chefdk/gem/ruby/2.1.0/gems/knife-config-1.1.0/lib/knife-config.rb

chef generate app
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_app.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_app_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_app_options.rst

Examples
-----------------------------------------------------

**Create an application**

.. code-block:: bash

   $ chef generate app chef-repo
   
will return something similar to:

.. code-block:: bash

   Recipe: code_generator::app
     * directory[/Users/grantmc/chef-repo] action create
       - create new directory /Users/grantmc/chef-repo
   
     * template[/Users/grantmc/chef-repo/.kitchen.yml] action create
       - create new file /Users/grantmc/chef-repo/.kitchen.yml
   
     * template[/Users/grantmc/chef-repo/README.md] action create
       - create new file /Users/grantmc/chef-repo/README.md
   
     * directory[/Users/grantmc/chef-repo/cookbooks] action create
       - create new directory /Users/grantmc/chef-repo/cookbooks
   
     * directory[/Users/grantmc/chef-repo/cookbooks/grantmc] action create
       - create new directory /Users/grantmc/chef-repo/cookbooks/grantmc
   
     * template[/Users/grantmc/chef-repo/cookbooks/grantmc/metadata.rb] action create
       - create new file /Users/grantmc/chef-repo/cookbooks/grantmc/metadata.rb
   
     * cookbook_file[/Users/grantmc/chef-repo/cookbooks/grantmc/chefignore] action create
       - create new file /Users/grantmc/chef-repo/cookbooks/grantmc/chefignore

     * cookbook_file[/Users/grantmc/chef-repo/cookbooks/grantmc/Berksfile] action create
       - create new file /Users/grantmc/chef-repo/cookbooks/grantmc/Berksfile

     * directory[/Users/grantmc/chef-repo/cookbooks/grantmc/recipes] action create
       - create new directory /Users/grantmc/chef-repo/cookbooks/grantmc/recipes

     * template[/Users/grantmc/chef-repo/cookbooks/grantmc/recipes/default.rb] action create
       - create new file /Users/grantmc/chef-repo/cookbooks/grantmc/recipes/default.rb
   
     * execute[initialize-git] action run
       - execute git init .
   
     * cookbook_file[/Users/grantmc/chef-repo/.gitignore] action create
       - create new file /Users/grantmc/chef-repo/.gitignore

and which creates a directory structure similar to::

   /chef-repo
     /.git
	 .gitignore
	 .kitchen.yml
     /cookbooks
	   /chef-repo
	     Berksfile
		 chefignore
		 metadata.rb
		 /recipes
		   default.rb
	  README.md

chef generate attribute
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_attribute.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_attribute_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_attribute_options.rst

Examples
-----------------------------------------------------

**Create an attribute**

.. code-block:: bash

   $ chef generate attribute /path/to/cookbook FOO
   
will return something similar to:

.. code-block:: bash

   Recipe: code_generator::attribute
     * directory[/Users/grantmc/chef-repo/cookbooks/chef-repo/attributes] action create
       - create new directory /Users/grantmc/chef-repo/cookbooks/chef-repo/attributes
   
     * template[/Users/grantmc/chef-repo/cookbooks/chef-repo/attributes/FOO.rb] action create
       - create new file /Users/grantmc/chef-repo/cookbooks/chef-repo/attributes/FOO.rb
   

chef generate cookbook
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_cookbook.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_cookbook_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_cookbook_options.rst

Examples
-----------------------------------------------------

**Create a cookbook**

.. code-block:: bash

   $ chef generate cookbook chefdocs

will return something similar to:

.. code-block:: bash

   Recipe: code_generator::cookbook
     * directory[/Users/grantmc/chefdocs] action create
       - create new directory /Users/grantmc/chefdocs
   
     * template[/Users/grantmc/chefdocs/metadata.rb] action create
       - create new file /Users/grantmc/chefdocs/metadata.rb
   
     * template[/Users/grantmc/chefdocs/README.md] action create
       - create new file /Users/grantmc/chefdocs/README.md
   
     * cookbook_file[/Users/grantmc/chefdocs/chefignore] action create
       - create new file /Users/grantmc/chefdocs/chefignore
   
     * cookbook_file[/Users/grantmc/chefdocs/Berksfile] action create
       - create new file /Users/grantmc/chefdocs/Berksfile
   
     * template[/Users/grantmc/chefdocs/.kitchen.yml] action create
       - create new file /Users/grantmc/chefdocs/.kitchen.yml
   
     * directory[/Users/grantmc/chefdocs/recipes] action create
       - create new directory /Users/grantmc/chefdocs/recipes
   
     * template[/Users/grantmc/chefdocs/recipes/default.rb] action create
       - create new file /Users/grantmc/chefdocs/recipes/default.rb
   
     * execute[initialize-git] action run
       - execute git init .
   
     * cookbook_file[/Users/grantmc/chefdocs/.gitignore] action create
       - create new file /Users/grantmc/chefdocs/.gitignore

and which creates a directory structure similar to::

   /chefdocs
     /.git
	 .gitignore
     .kitchen.yml
     Berksfile
     chefignore
     metadata.rb
     README.md
     /recipes
       default.rb

**Create a cookbook using a custom skeleton cookbook**

If a custom skeleton cookbook is located on a |mac os x| desktop (and in this example, the ``chef_generator`` cookbook is simply a copy of the same cookbook that ships in the |chef dk|), the following command will use the skeleton cookbook at the custom location to generate a cookbook into the repository from which the ``chef`` command is run:

.. code-block:: bash

   $ chef generate cookbook --generator-cookbook ~/Desktop testcookbook

.. note:: The ``code_generator`` cookbook itself is not specified as part of the path.

will return something similar to:

.. code-block:: bash

   Compiling Cookbooks...
   Recipe: code_generator::cookbook
     * directory[/Users/grantmc/Desktop/chef-repo/test-cookbook] action create
       - create new directory /Users/grantmc/Desktop/chef-repo/test-cookbook
	   
     * template[/Users/grantmc/Desktop/chef-repo/test-cookbook/metadata.rb] action create
       - create new file /Users/grantmc/Desktop/chef-repo/test-cookbook/metadata.rb
	   
     * template[/Users/grantmc/Desktop/chef-repo/test-cookbook/README.md] action create
       - create new file /Users/grantmc/Desktop/chef-repo/test-cookbook/README.md

     * cookbook_file[/Users/grantmc/Desktop/chef-repo/test-cookbook/chefignore] action create
       - create new file /Users/grantmc/Desktop/chef-repo/test-cookbook/chefignore

     * cookbook_file[/Users/grantmc/Desktop/chef-repo/test-cookbook/Berksfile] action create
       - create new file /Users/grantmc/Desktop/chef-repo/test-cookbook/Berksfile

     * template[/Users/grantmc/Desktop/chef-repo/test-cookbook/.kitchen.yml] action create
       - create new file /Users/grantmc/Desktop/chef-repo/test-cookbook/.kitchen.yml
	   
     * directory[/Users/grantmc/Desktop/chef-repo/test-cookbook/recipes] action create
       - create new directory /Users/grantmc/Desktop/chef-repo/test-cookbook/recipes
	   
     * template[/Users/grantmc/Desktop/chef-repo/test-cookbook/recipes/default.rb] action create
       - create new file /Users/grantmc/Desktop/chef-repo/test-cookbook/recipes/default.rb


chef generate file
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_file.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_file_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_file_options.rst

Examples
-----------------------------------------------------
None.

chef generate lwrp
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_lwrp.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_lwrp_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_lwrp_options.rst

Examples
-----------------------------------------------------
None.

chef generate recipe
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_recipe.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_recipe_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_recipe_options.rst

Examples
-----------------------------------------------------
None.

chef generate template
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_template.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_template_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_generate_template_options.rst

Examples
-----------------------------------------------------
None.


chef install
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_install.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_install_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_install_options.rst

Examples
-----------------------------------------------------
None.


chef push
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_push.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_push_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_push_options.rst

Examples
-----------------------------------------------------
None.


chef shell-init
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_shell_init.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_shell_init_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_shell_init_options.rst

Examples
-----------------------------------------------------
None.

chef verify
=====================================================
.. include:: ../../includes_ctl_chef/includes_ctl_chef_verify.rst

Syntax
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_verify_syntax.rst

Options
-----------------------------------------------------
.. include:: ../../includes_ctl_chef/includes_ctl_chef_verify_options.rst

Examples
-----------------------------------------------------
None.