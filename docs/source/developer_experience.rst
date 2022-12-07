Developer Experience
====================

In this section we give a description of the typical developer workflow, the suggested tools,
and some useful commands.


Setting Up Local Environment
----------------------------

Suggested Tools
~~~~~~~~~~~~~~~

IDE: Visual Studio Code
"""""""""""""""""""""""

**Website**: https://code.visualstudio.com/

Alongside Intellisense and debugging utilities, some extensions made
developing easier:

- `Dev Containers <https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers>`__: enables working without installing a single dependency in the developer's computer.
- `Peacock <https://marketplace.visualstudio.com/items?itemName=johnpapa.vscode-peacock>`__: allows theming each VSCode workspace with a custom color.
- `Todo Tree <https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree>`__: provides hihglighting for ``TODOs`` and ``FIXMEs``.


Shell output formatting: colout
"""""""""""""""""""""""""""""""

**Website**: https://nojhan.github.io/colout/

This tool allows coloring output with pattern matching. Having a certain color assigned to each
microservice allowed us to quickly find logs and the corresponding IDE window. 

Local Log Monitoring
~~~~~~~~~~~~~~~~~~~~

.. code-block:: console
    
    $ docker compose up | colout "fiuber.api-gateway.dev" yellow | colout "fiuber.service-trips.dev" blue | colout "fiuber.service-users.dev" green | colout "fiuber.service-pricing.dev" purple | colout "fiuber.service-payments.dev" red

..  image:: /images/compose_terminal.png
    :class: with-shadow
    :scale: 65

Some text ...  (will be displayed on the right of the image)

Memory & CPU Usage
~~~~~~~~~~~~~~~~~~

The following code snippet can be used to monitor resource usage in each container:

.. code-block:: console
    
    $ docker stats --format "table {{.Name}}\t{{.CPUPerc}}\t{{.MemUsage}}" | colout "fiuber.api-gateway.dev" yellow | colout "fiuber.service-trips.dev" blue | colout "fiuber.service-users.dev" green | colout "fiuber.service-pricing.dev" purple | colout "fiuber.service-payments.dev" red

..  image:: /images/docker_stats.png
    :alt: Left floating image
    :class: with-shadow
    :scale: 65

..  rst-class::  clear-both


Developing Inside Docker Containers
-----------------------------------

Using the suggested VSCode extensions enables linting, debugging, troubleshooting and Intellisense
inside each container, as seen in the video below:

.. video:: /docs/source/videos/attach_vscode.mp4
   :width: 500
   :height: 300
   