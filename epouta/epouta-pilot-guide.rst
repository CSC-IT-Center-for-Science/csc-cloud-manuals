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

Getting access
--------------

The process of getting access to use the ePouta web interface and APIs is partly
the same one you would use for cPouta. You will need a computing project and
user accounts added to that computing project. If you don't already have a
computing project, you need to apply for one here:

`Applying for Computing Resources
<https://research.csc.fi/applying-for-computing-resources>`_

Using ePouta
------------

You can mostly follow the `cPouta User Guide
<https://research.csc.fi/pouta-user-guide>`_ for instructions on how to use
OpenStack. If you want to use `command line tools
<https://research.csc.fi/pouta-command-line-tools>`_, the only command line tool
that works with ePouta is the common "openstack" tool.

When you login, you need to specify a user domain. This is always "users".

.. image:: ../.static/images/horizon-login-domain-users.png

.. _differences-compared-to-cpouta:

Differences compared to cPouta
------------------------------

* No floating IPs are available to be attached to virtual machines nor will they
  be in the future.
* The web interface and the APIs are only accessible from whitelisted IP ranges.

Getting support
---------------

Questions and reports about issues can be sent to `cloud-support@csc.fi
<mailto:cloud-support@csc.fi>`_.
