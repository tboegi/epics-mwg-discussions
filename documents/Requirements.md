# Requirements for Enhanced Motor Support in EPICS

## Overview
This document is intended to provided the requirements for enhanced motor support in EPICS.
It contains:
  - A brief the history of motor support in EPICS
  - A statement of the problems with the current motor support
  - The proposed requirements for enhanced support
  - Proposals for possible implementation of the enhanced support.

## History
EPICS motor support has largely been through the EPICS motor record.  

The architecture of this support was initially to have separate device support and drivers for 
each controller type.  The interface between the device support and the driver was specific
to the motor module, and only implemented the features defined for the motor record.
This type of device support is now called Model 1 device support.  A number of widely used
controllers still only have Model 1 device support, for example the OMS-58.

In 2006 a collaboration between folks at the APS and Diamond created a new architecture.
It used asyn interfaces between the device support and the driver.  In this architecture
the device support layer was device independent.  There was also a device-independent
driver layer, sitting above a device-dependent driver layer.  Everything was implemented
in C,not C++.  This architecture allowed taking advanced of controller-specific features
beyond those in the motor record.  However, it was not a simple to do this as one would 
like.  The interface contained an API for multi-axis coordinated motion.  However, this was never
implemented in any real drivers.  It also contained a simulated motor that allowed
testing of the interfaces without any real hardware.  This architecture is now called
the Model 2 architecture.

In December 2009 a new architecture was proposed based on C++ base class derived from
asynPortDriver.  This proposal was originally made in this 
[EPICS tech-talk message](http://www.aps.anl.gov/epics/tech-talk/2009/msg01765.php)
This is the architecture successfully used in areaDetector and a number of other
driver classes.  The base classes asynMotorController and asynMotorAxis were developed,
and many motor drivers written since this time use this new architecture, which is now
called the Model 3 architecture.  
This architecture contains an API for multi-axis complex coordinated motion.  
This has only been implemented for the Newport XPS controller.

Multi-axis complex coordinated motion was implemented for a number of Model 1 and Model 2 drivers by
writing EPICS State Notation Language (SNL) programs that communicated directly with the controller,
without using the motor record drivers.  This was done for the Newport XPS, the OMS-MAXv, and
the Aerotech Ensemble (single-axis complex motion only).  The XPS SNL implementation has since
been replaced by the Model 3 "Profile move" API.  The MAXv and Ensemble implementations are still SNL 

## Statement of the problem


## Requirements

## Strawman for Proposed Implementation

