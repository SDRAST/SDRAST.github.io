.. Radio Astronomy Software Tools documentation master file, created by
   sphinx-quickstart on Wed Oct 30 14:49:29 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.
   
.. image:: DSNRAlogo.gif
    :align: left

Single Dish
===========
Radio Astronomy Software Tools
==============================

Radio Astronomy Software Tools is a `collection of software
packages` <https://github.com/SDRAST/> that have proven useful in doing radio 
astronomy with NASA's Deep Space Network.  

The two main activities in radio astronomy (besides building equipment) are
monitor and control of data acquisition (observing), and data reduction.
Consequently the two largest packages in this collection are ``Data_Reduction`` 
and ``MonitorControl``.

The **monitor and control** system is overlaid on the existing monitor and 
control (*e.g.* antenna controller, receiver control, *etc.*) to provide features
necessary or useful for conducting radio astronomy research. The collection
may provide a quick way to start a small single dish radio astronomy
*ab initio* because it is able to manage a telescope system in which all
subsystems have their own, network-accessible controllers.  The base classes
are ``Device`` for modifying a signal, 
``Signal`` which is modified by a device,
and ``Port`` by which signals enter and leave a device. Subclasses implement
specific instances of these.  The actual hardware is controlled by *servers*
while the user software is based on *clients*.

The **data reduction package** is based on a number of base classes. ``Observation``
is the base class for a single set of data, often called a *scan*. ``Map``
is an example of a subclass of ``Observation``.  A set of observations
comprises a ``Session`` characterized by a project, a telescope, and a date.

The way data are accessed depends on how they were generated and stored during
the observing session and are observatory (and sometimes time) dependent.
Each situation is captured by a module which has subclasses (of the base classes)
which are aware of the context.

The **other modules** provide support for the two main packages. 
In astronomy there is the need to transform coordinates into various 
coordinate systems and to compensate frequencies for the various motions of 
the observer, the Earth, and the Sun; to compute frequencies such as 
recombination lines; to
calibrate signals in terms of temperature and flux density; to allow for
time dispersion of signals by free electrons, *etc.*, which led to 
additional packages
for astrophysics, physics, and radio astronomy engineering. 

.. toctree::
   :maxdepth: 1
   :caption: Contents:

   aboutastronomy
   aboutastrophysics
   aboutdatareduction
   aboutdatestimes
   aboutDSP
   aboutElectronics
   aboutmath
   aboutmonitorcontrol
   aboutphysics
   aboutradioastronomy
   aboutsupport

.. toctree::
   :maxdepth: 1
   :caption: Resources:
   
   aboutgit
   aboutpages
   
   
Interdependencies
=================
.. image:: import-map-3.png
   
To Do
=====

#. Convert ``MonitorControl``.
#. Find a way for Sphinx to handle mixin classes.
#. Register collection with `Best Practices Badge <https://bestpractices.coreinfrastructure.org/en>`_ program.
#. Incorporate `Physical Quantities <https://github.com/hplgit/physical-quantities>`_ into the collection as the owner has passed away and his colleagues have not expressed an interest in it.

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

Revised by Tom Kuiper, 2020 July 2

