Adding a Windows host
==========
In order to monitor your Windows hosts you must install the check_mk agent and provide a way for the check_mk server to communicate with the agents.

Installation of the check_mk agent can be performed a couple of different ways. Below we cover the most common options:

* Use the agent bakery and "bake" your own agent
* Grab one directly from your existing OMD site(s)

Agent bakery
-----------
The agent bakery allows you to use the same powerful rules based engine from WATO to create agents for you monitored servers. From WATO, access the Monitoring Agents section, click on the Rules button and configure your agents accordingly.

Once you have created the rules to your specifications go back to the Monitoring Agents main page and click on the Bake Agents button.

Depending on your rules you will have one or more agents for one or more operating environments (rpm, deb, msi). You can click on the DEB/RPM/MSI link and download your agent.

Copy that agent over to your monitored server(s) and install according to your operating environment requirements.

Prebuilt package
-----------
All OMD site instances have prebuilt agents available in ~share/check_mk/agents. You will find there the MSI, RPM and DEB agent as well as the pure (script) agents (check_mk_agent.linux).

These prebuilt agents are also available via the OMD site URL: http://hostname_or_ip/<omd site name>/check_mk/agents/. At this URL you will also find additional plugins as well as the xinetd.conf configuration file.

Windows installer
-----------
The windows installer supports the following command line arguments:

::

    /S - runs the installer silently
    /D= - sets the default installation directory


After installation the check_mk_agent service should have started automatically. You can confirm this by telnetting from your OMD site to the monitored server on tcp port 6556:

::

    user@host> telnet xyzhost123 6556
    <<<check_mk>>>
    Version: 1.2.5i5p3
    BuildDate: Jul 28 2014
    Architecture: 32bit
    AgentOS: windows
    Hostname: xyzhost123
    WorkingDirectory: C:\Windows\system32
    ConfigFile: C:\Program Files (x86)\check_mk\check_mk.ini
    AgentDirectory: C:\Program Files (x86)\check_mk
    PluginsDirectory: C:\Program Files (x86)\check_mk\plugins
    SpoolDirectory: C:\Program Files (x86)\check_mk\spool
    LocalDirectory: C:\Program Files (x86)\check_mk\local
    ScriptStatistics: Plugin C:0 E:0 T:0 Local C:0 E:0 T:0
    OnlyFrom: 0.0.0.0/0
    <<<uptime>>>
    1929017
    <<<df>>>
    C:\ NTFS 83991548 49014400 34977148 59% C:\
    Share&ExchangeBackup NTFS 251658236 222849392 28808844 89% D:\
    Exchange NTFS 150674428 73825484 76848944 49% E:\

Adding host to OMD
------------------
After confirming that the agent is accessible you can access WATO, Hosts and click on New host. For our example you can fill out just the hostname and click on Save & go to Services button.

If the hostname is resolvable via DNS you do not need to also specify the IP address however if it is not then the IP address is a required field.

After this step you will be taken to the Services page where you can select and configure the services that check_mk has discovered on your server.

For every service discovered you can choose to:

.. image:: custom/_images/srv-discovery.png

(1) View and edit parameters
(2) Edit and analyze check parameters
(3) Create a rule to permanently disable discovery of said service
(4) Temporarily ignore the service



* Additional details can be found at the check_mk site https://mathias-kettner.de/checkmk_windows.html
