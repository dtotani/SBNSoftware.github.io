---
layout: page
title: GPVM migration
description: GPVM and build nodes migration from SL7 to EL9
toc: true
---

GPVM migration
------------------------------------------------------------------------------------------------

SL7 is reaching EOF on June 30th.
Computing had many of its services already migrated to EL9 (AlmaLinux9),
migration for remaining services is underway.

The migration to EL9 will include migration of GPVMs and build nodes.
Computing set up test VMs and installed build nodes for users to get acquainted with EL9, those nodes are:

ICARUS:
- icarusbuild02.fnal.gov
- icarusgpvm-test-al9.fnal.gov

SBND:
- sbndbuild03.fnal.gov
- sbndgpvm-test-al9.fnal.gov

As part of the migration to EL9 build nodes that can't be upgraded to EL9 will be retired by June 30th.
This will affect sbndbuild01/02 and icarusbuild01.

SL7 development container
------------------------------------------------------------------------------------------------

Computing understands that there could be the need to be able to use
SL7 nodes during the migration and possibly also shortly after the migration.  
For this purpose we are preparing SL7 containers that can be used on
EL9 GPVMs and build nodes to run some SL7 task, as code development.
The contanier has development packages that allow to build SBN/SBND/ICARUS code stack.

To start the SL7 container users can run the following script:  
`sh /exp/$(id -ng)/data/users/vito/podman/start_Sl7dev.sh`  
this will give the prompt:  
`Apptainer>`

It could be needed to source the bashrc script from withing the SL7 container to get it more similar to usual SL7 VMs.  
`source ~/.bashrc`

Container features:
- it mounts the user home directory,
- it mounts /cvmfs to allow access to CVMFS repositories,
- it mounts /exp to allow access to app and data Ceph volumes,
- it mounts /pnfs to allow access to dCache (make sure to not overload the /pnfs mount point),
- the working directory is the user app area.


Contact
------------------------------------------------------------------------------------------------

For any question/comment feel free to reach out by email or on slack the SBND/ICARUS CS-Liaison: Vito Di Benedetto
