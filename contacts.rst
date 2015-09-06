Contacts
==========
Check_MK has the concept of Contacts, Contact Groups and Roles. With OMD you will have one admin user created automatically with the initial site creation. The default admin username is omd and the default password is omdadmin (change these after your initial login).

Contacts are managed via WATO. Before you create a new user you should first think about how your users and hosts are organized and how they will use the site.

.. image:: _images/sidebarusers.png
   :width: 40%
.. image:: _images/watousers.png

Contacts are usually people you want to notify when something happens within your infrastructure. There are however many different ways to use a Contact such as a Multisite only users that does not receive notifications.

Roles
-----
OMD has 3 default Roles. These are Admin, Guest and User.

  * Admins have complete administrative control
  * Users have some control over the objects they are assigned
  * Guests users are usually limited only viewing data

Permissions can be assigned on very granular level so new Roles can be created to provide more complex permissions. By default only the admin role can configure permissions.

The best way to ge the hang of roles is to take a look at the Matrix within Roles & Permissions. The "X" means that functionality is "enabled" for that Role.

Contact Groups
--------------
Think of Contact Groups as your any other group: a container for holding something. Contact groups allow users to view and/or edit their hosts and services within Multisite but also to receive alerts and notifications via email, sms, etc.


Between Users, Contact Groups and Roles you can configure and assign many complex permissions but there is yet one more feature to help and it is called Rules. You can configure rules that automatically assign hosts and/or services to Contact Groups. This is a very elegant way of providing even more control over what your users and see within the monitoring site.

To use Rules to configure automatic assignment of hosts and services to contact groups access WATO, Contact Groups and click on the Rules button.

.. image:: _static/cgrules.png
