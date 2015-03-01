What is Monitoring all about?
=============================
We monitor entire systems, networks and applications to get information about
their state as well as events.

The gathered information gives us an overview of the health of the
infrastructure. It helps us react faster to incidents but more importantly it
helps us in becoming more proactive by utilizing trending and historical
information we will know to act before an issue becomes critical.

Keeping an eye on the entire it infrastructure provides many benefits for the
business side as well. With a properly configured monitoring solution you will
have trending and historical information that can be used to make decisions such
as capacity planning (what systems need upgrading in the next 6 months; or which
file servers need more space).

So now that we have this short overview of what monitoring can do for us lets
look at what monitoring is all about from the check_mk perspective.

States
------
States are determined by a measurement or a check.  This verification or polling
needs to be carried out regularly.

States give us information such as: is the service running, how much memory is
being used and is a very reliable process.

Events
------
Events are more dynamic in their nature and therefore are not easily identified
by a regular polling interval. Events may also be errors which only occur once
making them that much more difficult to identify by regular checks. Examples of
events are: disk I/O errors or hot-plug/add of a device.

What is a monitoring system?
----------------------------
A monitoring system is a piece of software that offers monitoring facilities.
Usually such a system is state based that retrieves information from the
monitored hosts via some mechanism. This information often called the check
result is then processed, stored and possibly archived. The system will also
provide methods to retrieve and display the check results.

What is a check?
----------------
A check is also a piece of software running on a computer that does the
measurement of a service. An example of a check is: opening a TCP connection to
a web server and verifying the result. The check determines the state of a
service.

Active vs. Passive Checks
-------------------------
In monitoring there is the concept of active and passive checks. An active check
is triggered by the monitoring server usually through a poll or request.

A passive check is sent directly by the monitored server and the server has no
influence on when this result is sent. Furthermore a passive check may not send
a result during a specified time-frame and the monitoring server can raise an
alarm at that point.
