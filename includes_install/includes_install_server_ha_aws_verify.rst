.. The contents of this file may be included in multiple topics.
.. This file should not be changed in a way that hinders its ability to appear in multiple documentation sets.

To verify that failover is working, stop |keepalived| on the primary machine.

#. To watch the failover occur as it happens, run the following command in terminal windows on both the primary and secondary backend servers prior to stopping |keepalived|:

   .. code-block:: bash

      $ watch -n1 sudo chef-server-ctl ha-status

#. Stop |keepalived| on the primary backend machine:

   .. code-block:: bash
      
      $ sudo chef-server-ctl stop keepalived

   A cluster failover should occur.

#. After a successful failover, restart |keepalived| on the primary backend machine:

   .. code-block:: bash

      $ sudo chef-server-ctl start keepalived

   The primary has now become the secondary, and vice-versa. If you wish to fail back to the original primary, repeat these using the new primary.