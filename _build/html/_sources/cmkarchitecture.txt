Check_MK Architecture
======================

Before you go any further get to know the check_mk architecture. There are many
parts involved and it helps to know your way around. Luckily the check_mk
monitoring system is rock solid and you should never have to deal with the
components directly unless you need to change some defaults or something is not
working as expected.

.. image:: _images/cmk-architecture.png


Check_MK Components
===================
There are many components that make up the Check_MK monitoring system. Below you
will find information about each of the major components.

Configuration & Check Engine
----------------------------
The Check_MK CCE provides an elegant method for configuring your monitoring
platform independently of the monitoring core you are using. You do not have to
deal directly with typical configuration files since Check_MK takes care of
automatic service discovery and the actual configuration.
Check_MK provides a highly efficient method for doing checks: your hosts are
contacted only once per Check Interval. The results are then sent to the
monitoring core as passive checks. This results in a substantial reduction in
resource usage.

  Compare the above to how typical nagios (and most monitoring platforms)
  function: For every Check Interval (usually once per minute) you poll your hosts
  for every metric that you are interested in. So if you have one CPU and one Hard
  Disk you would have two checks every minute (one for the CPU and one for Hard
  Disk). Check_MK obtains both metrics in one efficient check. Imagine now that
  you have thousands of hosts and up to hundreds of thousands of checks, check_mk
  would save you considerable resources.

The Check_MK CCE takes care of creating complete configuration data necessary
for your monitoring system. You can focus on gathering the information that is
important to you and less on configuration files.

Official Check_MK CCE documentation is available here
http://mathias-kettner.com/checkmk_ways_to_install.html

Livestatus
----------
Livestatus provides a direct connection to Status Data on Hosts and Services via
a UNIX-Socket. This enables Addons such as NagVis to have quick and efficient
access to Status Data. The access is provided via a simple protocol and is
possible from all programming languages with no need for a special library -
even from the Shell.

Official Livestatus documentation is available here
http://mathias-kettner.com/checkmk_livestatus.html

Multisite
---------
The Web-GUI Multisite is usable without Check_MK's Configuration & Check Engine.
It is a modern-looking web interface with rapid page loading that offers user-
definable configurations, distributed monitoring by integrating multiple
Monitoring-entities via Livestatus, integration of NagVis and PNP4Nagios, an
integrated LDAP-connection, an access to Status Data via Web-services and much
more. Multisite utilizes Livestatus for access to the Status Data.

Official Multisite documentation is available here
http://mathias-kettner.com/checkmk_multisite.html

WATO
----
Check_MK's Web Administration Tool makes the complete administration of a
Check_MK-based system possible over a Browser. This is not restricted to the
management of Hosts and Services and the typical Check_MK-rules, but also
includes the management of users, roles, groups, time periods, classical
Nagios-Checks and much more. With a modern roles concept authorizations can be
assigned so that tasks can be reliably given to colleagues.

Official WATO documentation is available here
http://mathias-kettner.com/checkmk_wato.html

Notify
------
Check_MK's new Notifications System makes the configuration of notifications
simple and flexible. Multiple channels can be defined and differently configured
per user. In this way for example, a full day's emails, but SMS only for serious
problems during on-call hours can be generated - without needing to define
multiple artificial users. The users can additionally configure their
notifications themselves.

Official Notify documentation is available here
http://mathias-kettner.com/checkmk_flexible_notifications.html

Business Intelligence
---------------------
The BI-Module is integrated in the Multisite-GUI. It aggregates Status Data from
numerous hosts and services to provide a complete status of complex applications
and similar processes. This provides a quick overview for managers and users.
Likewise questions about how concrete problems are affecting applications can be
quickly answered. The integrated "What if?" - Analysis simplifies the downtime
planning.

Official Business Intelligence documentation is available here
http://mathias-kettner.com/checkmk_bi.html

Mobile
------
The Mobile-Version of the Multisite-GUI is optimized for Smartphones and enables
access to all Status Data. Commands such as Acknowledge and Set for Downtimes
can be executed. The Mobile-GUI is automatically available when Multisite is
installed. Mobile devices are automatically recognized.

Event Console
-------------
The Check_MK Event Console integrates the processing of log messages and
SNMP-Traps into the monitoring. Its own Daemon - the mkeventd - is configured
through a flexible Rule Set and determines which and how incoming messages are
classified. In this way messages can be counted, correlated, anticipated,
transcribed and much more. The Event Console even utilizes an inbuilt
Syslog-Daemon that receives messages directly from Port 514.

Official Event Console documentation is available here
http://mathias-kettner.com/checkmk_mkeventd.html
