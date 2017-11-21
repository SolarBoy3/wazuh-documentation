.. _install-custom-wpk:

Installing custom WPK package
==============================

1. Install the root CA into the agent
--------------------------------------

The root CA certificate, or failing that, the certificate used to sign the WPK package, must be installed in the agent before running an upgrade.

You have two options:

    a. Overwrite the shipped root CA with your certificate. This will prevent your agent from upgrading using WPK packages from Wazuh.

    .. code-block:: console

        cp /path/to/certificate etc/wpk_root.pem

    b. Add a new certificate by editing the ossec.conf file:

    .. code-block:: xml

        <active-response>
          <ca_store>/var/ossec/etc/wpk_root.pem</ca_store>
          <ca_store>/path/to/certificate</ca_store>
        </active-response>


2. Run the upgrade
--------------------

Get the WPK package into the Wazuh manager and run:

.. code-block:: console

    /var/ossec/bin/agent_upgrade -a 001 -f path/to/myagent.wpk -x upgrade.sh

Where:
    - **-a 001** specifies the agent to upgrade.
    - **-f path/to/myagent.wpk** is the path to the WPK package.
    - **-x upgrade.sh** is the name of the upgrading script contained in the package.

Output example:

.. code-block:: console

    Sending WPK: [=========================] 100%
    Installation started... Please wait.
    Agent upgraded successfully
