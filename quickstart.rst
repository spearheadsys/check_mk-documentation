Check_MK Quickstart
======================

The Check_MK monitoring system is designed to be quick to set-up so there is
really only one way to go about this and it is quick by nature. Below we detail
the steps necessary to get a Check_MK instance running.

Prerequisites
-------------

Operating System
----------------
You will need a preinstalled linux server running in a virtual machine, cloud or
a physical server. Check_MK can be installed on the following linux server
platforms:

 * SuSE LINUX Enterprise Server (SLES) from version 11
 * Red Hat Enterprise Linux (RHEL) from version 5.5
 * CentOS from version 5.5
 * Debian from version 6.0
 * Ubuntu from version 10.04

Disk Space
----------
Depending on the size of your install you will need to allocate the necessary
disk space. Check_MK will store all of its files in the /opt/omd directory.
While it is not a requirement for /opt/omd to be on a separate partition it
could be advantageous for performance reasons to do so.

The necessary disk space will vary depending on the size of your installation
which in turn depends on the number of hosts and services you will be monitoring.
We have a site with about 40 hosts and 1000 services that takes up roughly 5GB.
We usually recommend no less than 50GB for /opt for a site with up to 50 hosts.
Your mileage will vary.

SMTP for outgoing emails
----------------------------
In order to send emails your SMTP service has to be configured correctly. Look at your distributions documentation for the proper configuration
steps if you would like to use email notifications.

Time services
----------
Monitoring is a time sensitive operation. You should make sure your server
provides the right time. We recommend configuring the NTP time service to grab
the right time from your local NTP servers. Once you set-up your monitoring
instance it will automatically monitor time services.

Time is also important for geographically distributed sites. We recommend you
set-up your hardware clock to UTC.


Repository
---------
In order to install check_mk on a CentOS/Red Hat based server you need to have
extra packages that are not available with the default system. To get your
system ready you must set-up the EPEL Repository. This is easily accomplished
with the installation of an RPM package for your specific distribution.

If for example you were running CentOS 6 or RHEL 6 the following command would
set-up the EPEL repository.

``root@linux# yum install https://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm``

Debian and Ubuntu systems have all the necessary packages.

SuSE Linux needs some special attention which we will not cover here. You can
get more details about what needs to be done for SuSE set-ups at the following
link.

http://mathias-kettner.com/cms_install_packages.html#H1:2.%20Setting%20up%20the%20repositories

Downloading Check_MK
--------------------
In your `subscription area <https://checkmk.com/download.php?>`_ you can download the package for your operating
environment.

Take note of the following selecting the package to download:

* First, select a version of Check_MK. If there are no reasons to the contrary, we recommend using the latest stable version.
* Name and version of your distribution must match exactly
* The architecture (32 or 64 bit) must match
* We always recommend the minimal packages. Full packages contain alternative software components such as Icinga or Thruk, which we offer but don't support.

Copy the package to the Linux system where Check_MK is to be installed.

Installation
------------

Debian and Ubuntu

On Debian,  install the package gdebi (with Ubuntu, this is installed by default):

``root@linux# apt-get install gdebi-core``

Then install the Check_MK package using gdebi (with Ubuntu, not of course wheezy
, but the appropriate package):

``root@linux# gdebi omd-<version-arch>.deb``

Finally, ensure that the Apache modules mod_proxy and mod_proxy_http are active using the following command:

``root@linux# a2enmod proxy_http``

``root@linux# /etc/init.d/apache2 restart``

SLES

With SLES, use the zypper tool with the install command:

``root@linux# zypper install omd-<version-arch>.rpm``

Red Hat and CentOS

Here, the installation is done using yum localinstall:

``root@linux# yum localinstall omd-<version-arch>.rpm``

Confirmation
------------
After you have successfully installed Check_MK and all of the necessary
dependencies you will have access to the omd command. 

The omd command allows you to set-up and manage monitoring instances. 
For a quick confirmation thatyour system is ready try the following command:

``omd version``

You should get something like this as output:

 OMD - Open Monitoring Distribution Version 1.2.6b1.mmk
