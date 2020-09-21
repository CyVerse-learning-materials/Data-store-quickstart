.. include:: cyverse_rst_defined_substitutions.txt

|CyVerse_logo|_

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`_

**Data Store Quickstart**
===================


Goal:  Simple steps to get setup with the CyVerse Data Store
----

.. toctree::
	:maxdepth: 2
	CyVerse Discovery Environment
	Cyberduck
	Command Line

-----

Prerequisites
-------------

*In order to complete this tutorial you will need access to the following services/software*

.. list-table::
   :header-rows: 1

   * - Prerequisite
     - Preparation/Notes
     - Link/Download
   * - CyVerse account
     - You will need a CyVerse account to complete this exercise
     - |CyVerse User Portal|
   * - Computer, web browser, and internet access
     - To access the Discovery Environment (or the Data Store), you will need these things
   * - Cyberduck
     - Standalone software for upload/download to Data Store
     - |Download Cyberduck|
   * - i-commands
     - These are the command line tools to access the data store
     - | `Mac iCommands Installer 4.1.9 <https://wiki.cyverse.org/wiki/download/attachments/28117338/cyverse-icommands-4.1.9.pkg?version=3&modificationDate=1472845229000&api=v2>`_ or `Linux binaries and source <https://files.renci.org/pub/irods/releases/4.1.12/>`_

Platform(s)
~~~~~~~~~~~

*We will use the following CyVerse platform(s):*

 ..
   #### comment: delete any row not needed in this table ####

.. list-table::
    :header-rows: 1

    * - Platform
      - Interface
      - Link
      - Platform Documentation
      - Manual/Guide
    * - Data Store
      - GUI/Command line
      - |Data Store|
      - |Data Store Manual|
      - |Data Store Guide|
    * - Discovery Environment
      - Web/Point-and-click
      - |Discovery Environment|
      - |DE Manual|
      - |Discovery Environment Guide|

----


Get started
--------------

CyVerse Discovery Environment
~~~~~~~~~~~~~~~~~~~~~

#. Open a web browser

#. Log into the CyVerse Discovery Environment: https://de.cyverse.org

#. Press the "Data" icon on the left

#. That opens the data management window

#. The navigation bar on the left is where you navigate your folder, public folders, and folders/files shared with you
#. The menu bar at the top is where you can:
	#. Upload/Download data
	#. Create folders
	#. Share data
----

Cyberduck
~~~~~~~~~

#. Download and install `Cyberduck <https://cyberduck.io/>`_
#. Download the CyVerse `configuration profile <https://cyverse.atlassian.net/wiki/download/attachments/241869843/CyVerseDataStore.cyberduckprofile?version=1&modificationDate=1568640173000&cacheVersion=1&api=v2>`_ .
	#. Double-click on the downloaded file - this should open the installed Cyberduck software.

#. Enter your **CyVerse username** in the field 'iPlant username'.

#. Under 'Advanced Options' set 'Transfer Files' to **'Open Multiple Connections'**.

#. Double-click on the Data Store bookmark in the Cyberduck window. Enter your CyVerse credentials.

You should now be connected to the CyVerse Data Store and viewing the contents of your home directory.

----

Command Line
~~~~~~~~~~~~

1. Download and install iCommands following the instructions for `Linux https://cyverse.atlassian.net/wiki/spaces/DS/pages/241869823/Setting+Up+iCommands#SettingUpiCommands-linux`_, `Mac <https://cyverse.atlassian.net/wiki/spaces/DS/pages/241869823/Setting+Up+iCommands#SettingUpiCommands-mac>`_, or `Windows <https://cyverse.atlassian.net/wiki/spaces/DS/pages/241869823/Setting+Up+iCommands#SettingUpiCommands-other>`_
2. Set path for i-command binaries:
	#. Mac example: ``export PATH="/Applications/icommands/:$PATH"``
	#. Linux example: ``export PATH="/home/elyons/bin/:$PATH"``
3. Run iinit and configure irods environment

+------------+------------+
| Parameter   | value   |
+============+============+
| DNA | data.cyverse.org   |
+------------+------------+
| Port | 1247   |
+------------+------------+
| User name | <CyVerse user name>   |
+------------+------------+
| Zone | iplant   |
+------------+------------+
| Password | <your cyverse password   |
+------------+------------+

Example iinit:

.. code:: bash

 elyons@air (~) $ iinit
 One or more fields in your iRODS environment file (.irodsEnv) are
 missing; please enter them.
 Enter the host name (DNS) of the server to connect to:data.cyverse.org
 Enter the port number:1247
 Enter your irods user name:elyons
 Enter your irods zone:iplant
 Those values will be added to your environment file (for use by
 other i-commands) if the login succeeds.

 Enter your current iRODS password:``

4. ``ils`` get list of files in current working directory in the Data Store

5. ``icd <directory>`` change working directory in the Data Store

6. ``iget <filename>`` will get files from the Data Store

.. code:: bash

        $ iget -r # For recursive transfer of directories and their contents

        $ iget -P # display the progress of the upload

        $ iget -f # force the upload and overwrite

        $ iget -T # Renew socket connection after 10 min (May help connections
                  # that are failing due to some connection/firewall settings)

7. ``iput <filename>`` iput will put files from local machine to the Data Store

.. code:: bash

        $ iput -r # For recursive transfer of directories and their contents

        $ iput -P # display the progress of the upload

        $ iput -f # force the upload and overwrite

        $ iput -T # Renew socket connection after 10 min (May help connections
                  # that are failing due to some connection/firewall settings)
----

WebDAV mount
~~~~~~~~~~~~

Note: this is for a Mac

#. Open Finder

#. From the menu at the top of your screen, select "Go"

#. In the dropdown menu, select "Connect to Server..."

#. In the popup window called "Connect to Server" type in ``https://data.cyverse.org/dav/iplant/home/<your CyVerse user name>```

#. Another window will pop up.  For "Connect As:" select "Registered User".  Type in your CyVerse user name for "Name:" and your CyVerse password for "Password"

#. If you logged in successfully, your data store account will be available through Finder.  "data.cyverse.org" will be listed under "Locations" on the right menu in a Finder window



----


Summary
~~~~~~~~~~~

You now have the power to move data.  Use your power wisely.

----

Additional information, help
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

..
    Short description and links to any reading materials




----

|Home_Icon|_
`Learning Center Home <http://learning.cyverse.org/>`__
