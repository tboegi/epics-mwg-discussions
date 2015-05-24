# EPICS Motor Working Group

**discussions** is the repository for the discussions of the EPICS motor working group

## Overview

The APS is interested in forming a working group to discuss the development of the EPICS motion controls support.  Occasionally, the group might meet in person, perhaps at an EPICS collaboration meeting. Typically, the EPICS motor working group will meet in the internet using one of the collaboration technologies. 

This effort is to direct the future of motion control software support.  Existing support works for many single-axis controllers (includes controllers providing multiple axes, each operating independently).  More advanced features, such as coordinated multi-axis control are not within the feature set of the motor record we have now.  Yet scientists are presenting equipment with such needs (such as hexapod) and requests for such coordination (multi-axis coordinated scans such as X-ray energy of monochromator and undulator).  And more advanced controllers provide features such as motor grouping for which implementation in the motor record is problematic at the least.

In short, motion controllers are coming from the factory with far more capabilities than we exposing to users with the present motor support.  To cover these newer capabilities, it seems the EPICS community is starting to branch or fork.

We are looking to assemble a group that can identify what motion controls should be and then resolve a design that will be durable for the foreseeable future.  Some of us have some ideas for the future.  It would be great if we can work towards a common design.
