SCAP Scan Results
=================

Components have different :term:`SCAP` scans that apply to their systems.

The `SCAP Security Guide`_ is the general metric by which SIMP systems are
measured.

The associated :term:`SCAP` profile should be referenced in each associated
document.

The following scan results are available for the various subsystems:

.. toctree::
   :maxdepth: 1
   :titlesonly:
   :glob:

   common.rst
   SCAP/*

How to Run a SCAN
-----------------

#. Download the latest `SSG Release OVAL ZIP file`_ onto the target system
#. Unzip the downloaded file and ``cd`` into the directory
#. Make sure that you have the ``openscap-scanner`` package installed
#. Run ``oscap xccdf eval --profile <profile_name> --results ~/scan-output.xml --report ~/scan-output.html ssg-<OS>-ds.xml``

   * You can get the list of available profiles by running ``oscap info ssg-<OS>-ds.xml``
   * For example, to run the ``STIG`` profile on ``CentOS 7``, you would run the following command:

     .. code-block:: bash

        oscap xccdf eval --profile xccdf_org.ssgproject.content_profile_stig-rhel7-disa --results ~/scan-output.xml --report ~/scan-output.html ssg-centos7-ds.xml

.. _SCAP Security Guide: https://github.com/OpenSCAP/scap-security-guide
.. _SSG Release OVAL ZIP file: https://github.com/OpenSCAP/scap-security-guide/releases
