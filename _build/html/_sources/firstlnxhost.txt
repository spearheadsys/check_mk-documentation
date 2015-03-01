Adding a Linux host
==========
In order to monitor

OMD command
-----------
The omd command is used to create, update, delete, configure, start, stop and
provides many other options for your monitoring sistes. omd can be used as the
root user and thus it will have access to all of the monitoring sites or as
the respective user of any one monitoring site in which case it will have
access to only that particular site.

Here is example output from the omd command called as a site user: ::

    [siteuser@omd ~]$ omd

    Usage (called as site user):
    omd help                        Show general help
    omd version    [SITE]           Show version of OMD
    omd versions                    List installed OMD versions
    omd sites                       Show list of sites
    omd update                      Update site to other version of OMD
    omd start      [SERVICE]        Start services of one or all sites
    omd stop       [SERVICE]        Stop services of site(s)
    omd restart    [SERVICE]        Restart services of site(s)
    omd reload     [SERVICE]        Reload services of site(s)
    omd status     [SERVICE]        Show status of services of site(s)
    omd config     ...              Show and set site configuration parameters
    omd diff       ([RELBASE])      Shows differences compared to the original version files
    omd umount                      Umount ramdisk volumes of site(s)
    omd backup     SITE [-|ARCHIVE_PATH] Create a backup tarball of a site, writing it to a file or stdout

    General Options:
    -V <version>                    set specific version, useful in combination with update/create
    omd COMMAND -h, --help          show available options of COMMAND

Here is example out form the omd command called as the root user: ::

    omd [root@cmk mariusp]# omd
    Usage (called as root):

    omd help                               Show general help
    omd setup                              Prepare operating system for OMD (installs packages)
    omd uninstall                          Remove OMD and all sites!
    omd setversion VERSION                 Sets the default version of OMD which will be used by new sites
    omd version    [SITE]                  Show version of OMD
    omd versions                           List installed OMD versions
    omd sites                              Show list of sites
    omd create     SITE                    Create a new site (-u UID, -g GID)
    omd init       SITE                    Populate site directory with default files and enable the site
    omd rm         SITE                    Remove a site (and its data)
    omd disable    SITE                    Disable a site (stop it, unmount tmpfs, remove Apache hook)
    omd enable     SITE                    Enable a site (reenable a formerly disabled site)
    omd mv         SITE NEWNAME            Rename a site
    omd cp         SITE NEWNAME            Make a copy of a site
    omd update     SITE                    Update site to other version of OMD
    omd start      [SITE] [SERVICE]        Start services of one or all sites
    omd stop       [SITE] [SERVICE]        Stop services of site(s)
    omd restart    [SITE] [SERVICE]        Restart services of site(s)
    omd reload     [SITE] [SERVICE]        Reload services of site(s)
    omd status     [SITE] [SERVICE]        Show status of services of site(s)
    omd config     SITE ...                Show and set site configuration parameters
    omd diff       SITE ([RELBASE])        Shows differences compared to the original version files
    omd su         SITE                    Run a shell as a site-user
    omd umount     [SITE]                  Umount ramdisk volumes of site(s)
    omd backup     SITE SITE [-|ARCHIVE_PATH] Create a backup tarball of a site, writing it to a file or stdout
    omd restore    [SITE] [-|ARCHIVE_PATH] Restores the backup of a site to an existing site or creates a new site

    General Options:
    -V <version>                    set specific version, useful in combination with update/create
    omd COMMAND -h, --help          show available options of COMMAND


OMD config command
------------------
To configure your site as a user you issue the following

``omd config``

To configure your site as the root user you must also specify the site name as
follows

``omd config siteone``

In either case you will get a graphical interface to aid you in configuration.

.. image:: _images/ev-config1.png

We recommend that for your first site you do not make any modifications since
these options are for advanced usage.

Basic
 * Autostart: Lets you choose if your site is started automatically during reboot of your server
 * Core: Allows you to use the traditional nagios core or the microcore
 * Crontab: Disables or enables site specific crontabs at boot time
 * tmpfs: Disables or enables the use of a ramdisk for temporary files

Web GUI
 * Apache Mode: Lets you choose to run a dedicated apache webserver for this site, or use the system webserver process directly
 * Apache TCP_ADDR: Lets you choose the ip address of your apache webserver
 * Apache TCP_PORT: Lets you choose the tcp port apache uses
 * Default_GUI: Lets you choose other GUIs besides Check_MKs multisite GUI
 * DOKUWIKI_AUTH: Enables the use of the dokuwiki user database for authentication instead of ~/etc/passwd
 * MULTISITE_AUTHORISATION: Lets multisite manage the permissions of the addon users
 * MULTISITE_COOKIE_AUTH: Enable or disable cookie based authentication
 * NAGIOS_THEME: Switch between installed Nagios themes

Addons
 * MKEVENTD: This option enables mkeventd - the event correlation and classification daemon of Check_MK
 * MKNOTIFYD: Enables of disables Check_MKs notification spooler
 * NAGVIS_URLS: Lets you choose which GUI is used when clicking on the NagVis map icons
 * PNP4NAGIOS: Lets you enable or disable PNP4Nagios, a great addon to store nagios performance data to round robin databases

Distributed Monitoring
 * LIVEPROXYD: This option enables the livestatus proxy daemon
 * LIVESTATUS_TCP: Make the livestatus proxy daemon listen on a tcp port in addition to the unix socket
