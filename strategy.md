# Background
The current contract for IETF IT infrastructure services is a black box contract - we specify the systems to be maintained along with a very basic SLA, and the provider is responsible for the the underlying infrastructure on which those systems operate, including the system administration strategy. The provider has always been much more accommodating than that in responding to requests for changes inside the black box, but these requests were for a long time piecemeal and not part of an overall strategy.

There have been regular complaints from the community that our infrastructure is more prone to failure, more difficult to upgrade and more difficult to accommodate new services, compared to a modern best practice infrastructure.  The IETF Administration LLC has consulted with the community via the tools-discuss list on the best way to address this and concluded that a new approach is required, which brings the community into the forefront of specifying an operational strategy for how the infrastructure should be operated.  This document sets out that new operational strategy.

The subject of who provides our IT infrastructure management, or what model that operates under, is out of scope and is left as a contract/sourcing decision for the IETF LLC. 

# Goals
The IETF IT infrastructure should be operated to meet the following goals, each of which is described in more depth in the sections below.  It is recognised that some of these goals overlap or are inter-dependent.

1. **Fit-for-purpose service availability**
1. **Fit-for-purpose service performance**
1. **Separated, cloud-first services**
1. **Automated, transparent and accessible infrastructure management**
1. **Secure and enduring services and data**
1. **Comprehensive, standards-based service monitoring**

## Fit-for-purpose service availability
The IETF is a global community with an uneven geographic spread, and the community uses the IETF infrastructure 24x7x365.  During IETF meetings, both the triannual plenaries and the many interim meetings, extremely high service availability is expected.  At other times, the activities are not so time critical that they cannot tolerate a delay of a few hours if planned and sufficient warning is given. 

The IETF requires its IT infrastructure to support a fit-for-purpose service availability, which means:
* No unplanned downtime.
* No planned downtime during or during the preparation phase, of IETF meetings.
* Frequency and length of planned downtime minimised and continually reduced.
* Planned downtime should be able to be scheduled for any day of the week at any time, to meet IETF operational requirements.

## Fit-for-purpose service performance
The demands on IETF services varies considerably with particular peaks in and around IETF meetings.  Also, there are a number of services intended for users to pull large amounts of data in order to maintain local copies of large datasets. While service performance can be adversely affected by a bottleneck at a level of the stack above the IT infrastructure, the IT infrastructure should not become the bottleneck.

The IETF requires its IT infrastructure to provide a fit-for-purpose service performance, which means:
* All relevant and potentially relevant performance/utilisation data collected.
* An infrastructure that scales to match load, with minimal manual intervention.
* An evidence based approach used in setting all resource limits.
* All performance bottlenecks immediately addressed.

## Separated, cloud-first services
The IETF has a wide variety of services, a high rate of change/growth in services, increasing integrations between services, significant fluctuations in usage with an underlying increase, and a wide variety of deployment models.

The IETF requires its IT infrastructure to operate with separated, cloud-first services, which means:
* All services containerised so that
  1. They are entirely separated at the filesystem/package level and any one can have any supporting package upgraded without any other service being affected.
  1. Any service can be customised, upgraded and migrated to another platform with either no dependency or only entirely unavoidable dependency, on any other service or component of any other service.
* All services able to run on any of the major cloud platforms.
* All containers to support orchestration, including automated deployment, scaling and management (recognising that some services may not).

## Automated, transparent and accessible infrastructure management
The IETF has an active community of volunteers contributing to its systems development efforts and its meetings NOC team, and it is likely that there will be a similar depth of community contribution to our IT infrastructure management, if this is enabled.  In addition, the IETF has a small and growing team of in-house developers and key development contractors, who like much of the development community, are increasingly adopting devops practices.

The IETF requires the management of its infrastructure to be automated, transparent and accessible, which means:
* All build and configuration managed through an automation platform.
* Automation scripts in a public Git repository.
* Credentials and other secret information used in automation scripts to be properly protected.
* Where reasonable, all the elements available to allow any member of the IETF community to build a replica of any IETF service, minus any confidential information.
* Active response to community contributions both on mailing lists and through a formal change management system (e.g. GitHub Pull Requests).

## Secure and enduring services and data
The IETF is vulnerable to the same threats as any other organisation and needs to mitigate those at many levels. The threat model for the IETF is unusual with more of an emphasis on data integrity and preserving the accuracy and availability of historical data, than on protecting confidential information.

The IETF requires its services and data to be secure and enduring, which means:
* An embedded risk-aware culture, with regular peer review and external audit of all strategies, processes and systems.
* Security-first network/service design and network/service management.
* A formal access control model.
* A patch management process that minimises the threat from unpatched systems.
* A backup strategy that provides strong assurance of data integrity and high confidence of system rebuild.

## Comprehensive, standards-based service monitoring
As the IETF services evolve, they are becoming more integrated and more inter-dependent making the task of identifying the source of problems a more complex task and ultimately reliant on good data. The tools used for capturing, processing, analysing and presenting data have developed rapidly in recent years and within any team that relies on data there will be a wide range of tools used. Also, as noted above, the number of data consumers is likely to grow significantas as the IETF community begins to contribute to our IT infrastructure.

The IETF requires comprehensive, standards-based service monitoring, which means:
* Every part of the infrastructure instrumented.
* Centralised collection of monitoring data to enable cross-service analysis.
* Controlled publication of monitoring data that maintains operational security while providing maximum access to the IETF community.
* Standards based collection and distribution to enable the widest tools support.
