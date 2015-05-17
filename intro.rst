What is Monitoring all about?
=============================
Keeping an eye on the entire it infrastructure provides many benefits for an entire business not just IT support or operations departments.

We monitor entire systems, networks and applications to get information about what they are doing. The information we gather is helpful in keeping the systems running and in some cases for capacity planning or other decision making (what systems need upgrading; or which file servers need more space; which vm's are underutilized, etc.).

The IT support or operations departments have many things going on all the time such as new roll-outs or upgrades, keeping an eye on the existing systems, planning for future systems, the list just goes on. Monitoring is a fundamental strategy to keeping your systems up and running but to also provide insight into the entire IT infrastructure all the way up to applications.

With relevant and timely information you can move to a more ordered and predictable state. For some it means a shift in methodology from a "putting out the fires" mentality to a keeping them from happening in the first place.

So what can monitoring do for us? Lets take a look at it from the Check_MK perspective and define some standard terminology to help us along.

States
------
States are determined by a measurement or a check. This verification or polling needs to be carried out regularly.

States give us information such as: is the service running, how much memory is being used and is usually a very reliable process.

Events
------
Events are more dynamic in their nature and therefore are not easily identified by a regular polling interval. Events may also be errors which only occur once making them that much more difficult to identify by regular checks. Examples of
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


Now that we've got that out of the way let's take a look at the Check_MK architecture.
