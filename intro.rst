What is Monitoring all about?
=============================
There are many definitions of what monitoring is and where it might be useful.
For [https://spearhead.systems](our) purposes, as an IT service provider, the
following defition fits well:

    "Monitoring is a process by which we obtain information that we use to
    determine availbility and performance of systems".

Systems are a bit harder to define and generally mean anything that has an
IP address but it gets blurry as we start to look at services, processes, etc.
Suffice it to say we monitor all aspects of modern IT infrastructures and
all that they entail (containers, functions, clouds, physica/virtual
servers, cooling units, storages, routers, etc.).

Why monitor things?
===================
Keeping an eye on IT systems provides many benefits for the entire business.

Availability, or the time the system is available and functional within
normal parameters, is of interest to everyeone: any deviation from normal
functionality could have impact to more than just computer systems, it could
mean loss of money, damages or other negative results.

Through monitoring we obtain useful information about what these systems are
doing and we use information that to help us better optimize and plan for the
future (we call this future planning "capacity planning").

An immediate effect of monitoring is that we get almost instant alerts when
something is not functioning or is alltogether missing. Longer term however
we get insight into the systems and applications via trends, historical
information and graphics that quickly identify patterns that may have
otherwise never been observed.

With relevant and timely information you can move to a more ordered and
predictable state. For some this means a shift in methodology from a
"putting out the fires" mentality to a keeping them from happening in the first
place.

So what can monitoring do for us? Lets take a look at it from the *checkmk*
perspective and define some standard terminology to help us along.

States
------
States are determined by a measurement or a check. This verification or polling
needs to be carried out regularly.

States give us information such as: is the system running, how much memory is
being used?

Events
------
Events are more dynamic in their nature and therefore are not easily identified
by a regular polling interval. Events may also be errors which only occur once
making them that much more difficult to identify by regular checks. Examples of
events are: disk I/O errors or hot-plug/add of a device.

What is a monitoring system?
----------------------------
A monitoring system is a piece of hardware or software that offers monitoring
facilities. Usually such a system is `state based`_ that retrieves information
from the monitored hosts via some mechanism. This information often called the
check result is then processed, stored and possibly archived. The system will
also provide methods to retrieve and display the check results.

What is a check?
----------------
A check is usually a piece of software running on a computer that does the
measurement of a service. An example of a check is: opening a TCP connection to
a web server and verifying the result. The check determines the state of a
service.

Active vs. Passive Checks
-------------------------
In monitoring there is the concept of active and passive checks. An active
check is triggered by the monitoring server usually through a poll or request.

A passive check is sent directly by the monitored server and the server has no
influence on when this result is sent. Furthermore a passive check may not send
a result during a specified time-frame and the monitoring server can raise an
alarm at that point.


Now that we've got that out of the way let's take a look at the checkmk
architecture.

.. _state based: https://todo_define_state_based
