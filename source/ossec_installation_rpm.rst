.. _ossec_installation_rpm:

RPM packages
============

Yum repository
--------------

To add the Wazuh yum repository, depending on your Linux distribution, create a file named ``/etc/yum.repos.d/wazuh.repo`` with the following content:

For Amazon Linux AMI: ::


   [wazuh]
   name = WAZUH OSSEC Repository - www.wazuh.com
   baseurl = http://ossec.wazuh.com/el/7/x86_64
   gpgcheck = 1
   gpgkey = http://ossec.wazuh.com/key/RPM-GPG-KEY-OSSEC
   enabled = 1

For RHEL and CentOS (version EL5): ::

   [wazuh]
   name = WAZUH OSSEC Repository - www.wazuh.com
   baseurl = http://ossec.wazuh.com/el/$releasever/$basearch
   gpgcheck = 1
   gpgkey = http://ossec.wazuh.com/key/RPM-GPG-KEY-OSSEC-RHEL5
   enabled = 1

For RHEL and CentOS (versions EL6 or EL7): ::

   [wazuh]
   name = WAZUH OSSEC Repository - www.wazuh.com
   baseurl = http://ossec.wazuh.com/el/$releasever/$basearch
   gpgcheck = 1
   gpgkey = http://ossec.wazuh.com/key/RPM-GPG-KEY-OSSEC
   enabled = 1

For Fedora (versions 21, 22 or 23): ::

   [wazuh]
   name = WAZUH OSSEC Repository - www.wazuh.com
   baseurl = http://ossec.wazuh.com/fc/$releasever/$basearch
   gpgcheck = 1
   gpgkey = http://ossec.wazuh.com/key/RPM-GPG-KEY-OSSEC
   enabled = 1

OSSEC manager installation
--------------------------

To install the OSSEC manager using Yum packages manager, run the following command: ::

   $ yum install wazuh-manager

On Fedora 23, to install the OSSEC manager with DNF packages manager, run the following command: ::

   $ dnf install wazuh-manager

If you like to install OSSEC manager version 2.8.3 manager, run the following command: ::

  $ yum install ossec-hids

On Fedora 23, to install the OSSEC manager with DNF packages manager, run the following command: ::

  $ dnf install ossec-hids

OSSEC agent installation
------------------------

To install the OSSEC manager using Yum packages manager, run the following command: ::

   $ yum install wazuh-agent

On Fedora 23, to install the OSSEC manager with DNF packages manager, run the following command: ::

   $ dnf install wazuh-agent

If you like to install OSSEC manager version 2.8.3 manager, run the following command: ::

  $ yum install ossec-hids-agent

On Fedora 23, to install the OSSEC manager with DNF packages manager, run the following command: ::

  $ dnf install ossec-hids-agent


.. note:: If it is your first installation from our repository, you will need to accept our repository GPG key when prompted during the installation. This key can be found at: `http://ossec.wazuh.com/key/RPM-GPG-KEY-OSSEC <http://ossec.wazuh.com/key/RPM-GPG-KEY-OSSEC>`_ also if you don't have the EPEL-RELEASE repository, these packages will install to resolve dependences.
