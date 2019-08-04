Multisite
==========
Check_MK utilises the intuitive Multisite web GUI for displaying monitoring status information. Multisite is based on Livestatus therefore it is extremely fast and responsive in large installations.

Multisite brings many features such as:

- User definable Views
- Support for distributed monitoring via Livestatus
- Customizable sidebar with dynamic content
- Automation and Webservice (API)
- Dashboards
- Localization

Views
-----------
Multisite allows each user to customize the builtin views or create completely new views. This is done in the GUI by flexibly combining datasources, layouts, filters, sortings, groupings, column-painters and inter-view-links. The idea behind is, that the administrators of the monitoring system should be able to create custom views for their users or customers, while those are presented a GUI as simple as possible.

The elements of views - like layouts, filters and so on - can be extended via Python using a plugin concept.

Distributed monitoring
-----------
Distributed monitoring is extremely useful in many situations. Check_MK allows for the centralized viewing of data as well as replication of data to remote sites.

There are many other functionalities that Multisite can offer. Your best option is to dive in and test out the functionalities.

More details are available at the official documentation [https://checkmk.com/cms.html](https://checkmk.com/cms.html).
