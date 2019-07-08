.. image:: https://img.shields.io/badge/dmtn--122-lsst.io-brightgreen.svg
   :target: https://dmtn-122.lsst.io
.. image:: https://travis-ci.com/lsst-dm/dmtn-122.svg
   :target: https://travis-ci.com/lsst-dm/dmtn-122

####################
Data Backbone Design
####################

DMTN-122
========

The Data Backbone (DBB) is a key component that provides for data storage, transport, and replication, allowing data products to move between enclaves.
This service provides policy-based replication of files (including images and flat files to be loaded into databases as well as other raw and intermediate files) and databases (including metadata about files as well as other miscellaneous databases but not including the large Data Release catalogs) across multiple physical locations, including the Base, Commissioning Cluster, NCSA, and Data Access Centers.
It manages caches of files at each endpoint as well as persistence to long-term archival storage (e.g. tape).
It provides a registration mechanism for new datasets and database entries and a retrieval mechanism compatible with the Data Butler.

Links
=====

- Live drafts: https://dmtn-122.lsst.io
- GitHub: https://github.com/lsst-dm/dmtn-122

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-dm/dmtn-122

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the `acronyms.tex` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
