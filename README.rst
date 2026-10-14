.. image:: https://img.shields.io/coveralls/github/timcera/tsgettoolbox_coops
    :alt: Test Coverage
    :target: https://coveralls.io/r/timcera/tsgettoolbox_coops?branch=master
    :height: 20

.. image:: https://img.shields.io/pypi/v/tsgettoolbox_coops
    :alt: Latest release
    :target: https://pypi.python.org/pypi/tsgettoolbox_coops/
    :height: 20

.. image:: https://img.shields.io/pypi/l/tsgettoolbox_coops
    :alt: BSD-3 clause license
    :target: https://pypi.python.org/pypi/tsgettoolbox_coops/
    :height: 20

.. image:: https://img.shields.io/pypi/pyversions/tsgettoolbox_coops
    :alt: PyPI - Python Version
    :target: https://pypi.org/project/tsgettoolbox_coops/
    :height: 20

tsgettoolbox_coops - Quick Guide
================================
The 'tsgettoolbox_coops' is a plugin-in for 'tsgettoolbox' that supplies
a command line interface and Python library to get time-series data from the
US National Oceanic and Atmospheric Administration (NOAA) Center for
Operational Oceanographic Products and Services (CO-OPS).  The
tsgettoolbox_coops will work with Python 3.10+.

Documentation
-------------
Reference documentation is at `tsgettoolbox COOPS API`_.

Installation
------------
At the command line::

    $ pip install tsgettoolbox_coops

Usage Summary - Command Line
----------------------------
Just run 'tsgettoolbox --help' to get a list of subcommands.  To get detailed
help for a particular sub-command, for instance 'coops', type 'tsgettoolbox
coops --help'.

+-------------+----------+--------+----------+----------+----------------------------+
| Sub-command | Spatial  | Time   | Type     | Time     | Description                |
|             | Extent   | Extent |          | Interval |                            |
+=============+==========+========+==========+==========+============================+
| coops       | global   | varies | station  | 1T,6T,H, | Center for Operational     |
|             |          |        |          | D,M      | Oceanographic Products and |
|             |          |        |          |          | Services                   |
+-------------+----------+--------+----------+----------+----------------------------+

+-------------------+-------------+
| Time Interval     | Description |
| Code              |             |
+===================+=============+
| T                 | Minute      |
+-------------------+-------------+
| H                 | Hourly      |
+-------------------+-------------+
| D                 | Daily       |
+-------------------+-------------+
| M                 | Monthly     |
+-------------------+-------------+

Usage Summary - Python Library
------------------------------
To use the tsgettoolbox in a project::

    from tsgettoolbox import tsgettoolbox
    df = tsgettoolbox.coops(
        station="8720218",
        product="hourly_height",
        time_zone="lst",
        datum="navd",
        begin_date="01/01/2017",
        end_date="2017-12-31",
    )
    print(df.head())

Refer to the API Documentation at `tsgettoolbox COOPS API`_.

Usage Summary - Command Line
----------------------------

    tsgettoolbox coops \
        --station="8720218" \
        --product="hourly_height" \
        --time_zone="lst" \
        --datum="navd" \
        --begin_date="01/01/2017" \
        --end_date="2017-12-31" > output.csv

Refer to the command line documentation at `tsgettoolbox COOPS CLI`_.

Development
~~~~~~~~~~~
Development is managed on bitbucket or github.
https://bitbucket.org/timcera/tsgettoolbox_coops/overview.
https://github.com/timcera/tsgettoolbox_coops

.. _tsgettoolbox_documentation: https://timcera.bitbucket.io/tsgettoolbox/docs/index.html#tsgettoolbox-documentation_coops
.. _tsgettoolbox COOPS API: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/_function_autosummary/tsgettoolbox.coops.html
.. _tsgettoolbox COOPS CLI: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/command_line.html#coops
