ePouta pilot user guide
=======================

.. note::

   ePouta is currently only available for selected pilot users. If you are not a
   selected pilot user, then this documentation is most likely not very useful
   for you.

This guide gives some basic information about using ePouta. As a service it is
quite similar to cPouta, so if you are familiar with that service you should be
able to start using ePouta quite easily. There are some differences which are
listed under the heading ":ref:`differences-compared-to-cpouta`".

Pilot use disclaimer
--------------------

Any virtual machines or other resources that are launched during the pilot phase
may be removed either at some stage during the pilot phase if changes are made
or when the service moves into production. We will give you notice about any
destructive or potentially destructive changes beforehand. As with any IaaS
cloud service, it is a good practice to build your resources in a way that is
easy to replicate in a situation where existing resources get destroyed. We
recommend using configuration management tools when deploying virtual machines
in the cloud.

Initial setup for customers
---------------------------

Some initial steps are required before you can start using ePouta: connecting
your organization's network to ePouta and getting user accounts for those users
that need to manage (start/stop/destroy etc.) virtual machines.

Setting up networking between your site and ePouta
..................................................

Unlike in cPouta and other typical IaaS clouds, in ePouta the virtual machines
don't have access to the public Internet. Instead, virtual machines of an
individual customer are only connected to that customer's own network through
either an OPN (Optical Private Network) or - within FUNET and European academic
networks - an MPLS (Multiprotocol Label Switching)
connection. This means that in order to access your virtual machines, you will
go through your own organization's network instead of going over the public
Internet. This also means that running public web services on ePouta is not
possible. To get started with connecting your network to ePouta, please send a
request to `cloud-support@csc.fi <mailto:cloud-support@csc.fi>`_.

.. image:: ../.static/images/epouta-connections.png

The above image shows the connections to virtual machines and to the management
interface in ePouta ("OpenStack"). As can be seen in the image, the network of
the virtual machines running in ePouta is completely separate from the public
Internet.

To create the connection between your site and ePouta, some initial information
is required:

#. A range of IP addresses from which addresses will be allocated to virtual
   machines running in ePouta
#. The IP address of the gateway in the subnet in which the IP range is
#. The IP addresses of DNS servers that should be used by virtual machines and
   that are accessible from the subnet
#. A set of IP addresses or ranges ("Admin machine" in the image above) that
   will be allowed to access the management interfaces of ePouta ("OpenStack" in
   the image above)

During the process of setting up the connection between your site and ePouta, we
will send you email asking you to provide this information. If you later wish to
e.g. add more IP addresses to be whitelisted for access to the ePouta
interfaces, please send email to `cloud-support <mailto:cloud-support@csc.fi>`_.

Getting access to OpenStack
...........................

The process of getting access to use the ePouta web interface and APIs is partly
the same one you would use for cPouta. You will need a computing project and
user accounts added to that computing project. If you don't already have a
computing project, you need to apply for one here:

`Applying for Computing Resources
<https://research.csc.fi/applying-for-computing-resources>`_

Logging in
..........

The address for the ePouta web interface is https://epouta.csc.fi. You can
mostly follow the `cPouta User Guide
<https://research.csc.fi/pouta-user-guide>`_ for instructions on how to use
OpenStack.

When you login, you need to specify a user domain. This is always "users":

.. image:: ../.static/images/horizon-login-domain-users.png

.. _differences-compared-to-cpouta:

Using ePouta from the command line
..................................

.. note::

   You can only use the common "openstack" tool with ePouta. The other tools
   (nova, cinder, glance, neutron) do not work as they do not have support for
   domains.

You can find instructions on command line usage from the `cPouta user guide
<https://research.csc.fi/pouta-command-line-tools>`_. The commands listed on that
page should also work against ePouta with the exception of the commands for
using floating IP addresses, since you cannot attach floating IP addresses to
instances in ePouta. The process for using the tools is exactly the same: you go
to the web interface to get an openrc file, you source that file and then you
can start using commands like "openstack server list" or "openstack server
create".

Differences compared to cPouta
------------------------------

* No floating IPs are available to be attached to virtual machines nor will they
  be in the future.
* The web interface and the APIs are only accessible from whitelisted IP ranges.
* You need to specify a domain when logging in to the web interface. This is
  always "users".
* If you wish to use command line tools, the only command line tool that will
  work at the moment is the common "openstack" tool

Getting support
---------------

Questions and reports about issues can be sent to `cloud-support@csc.fi
<mailto:cloud-support@csc.fi>`_.
