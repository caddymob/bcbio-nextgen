bcbio-nextgen
-------------

A python toolkit providing best-practice pipelines for fully automated
high throughput sequencing analysis. You write a high level
configuration file specifying your inputs and analysis parameters.
This input drives a parallel run that handles distributed
execution, idempotent processing restarts and safe transactional
steps. The goal is to provide a shared community resource that handles
the data processing component of sequencing analysis, providing
researchers with more time to focus on the downstream biology.

Features
--------

- Community developed: We welcome contributors with the goal of
  overcoming the biological, algorithmic and computational challenges
  that face individual developers working on complex pipelines in
  quickly changing research areas. See our `users page`_ for examples
  of bcbio-nextgen deployments, and the `developer documentation`_ for
  tips on contributing.

- Installation: `A single installer script`_ prepares all
  third party software, data libraries and system configuration files.

- `Automated validation`_: Compare variant calls against common reference
  materials or sample specific SNP arrays to ensure call correctness.
  Incorporation of multiple approaches for alignment, preparation and
  variant calling enable unbiased comparisons of algorithms.

- Distributed: Focus on `parallel analysis and scaling`_ to handle
  large population studies and whole genome analysis. Runs on single
  multicore computers, in compute clusters using `IPython parallel`_,
  or on the Amazon cloud. See the `parallel documentation`_ for full
  details.

- Multiple analysis algorithms: bcbio-nextgen provides configurable
  `variant calling and RNA-seq pipelines`_.

.. _IPython parallel: http://ipython.org/ipython-doc/dev/index.html
.. _parallel documentation: https://bcbio-nextgen.readthedocs.org/en/latest/contents/parallel.html
.. _A single installer script: https://bcbio-nextgen.readthedocs.org/en/latest/contents/installation.html#automated
.. _users page: https://bcbio-nextgen.readthedocs.org/en/latest/contents/introduction.html#users
.. _developer documentation: https://bcbio-nextgen.readthedocs.org/en/latest/contents/code.html
.. _variant calling and RNA-seq pipelines: https://bcbio-nextgen.readthedocs.org/en/latest/contents/pipelines.html
.. _parallel analysis and scaling: http://bcbio.wordpress.com/2013/05/22/scaling-variant-detection-pipelines-for-whole-genome-sequencing-analysis/
.. _Automated validation: http://bcbio.wordpress.com/2013/05/06/framework-for-evaluating-variant-detection-methods-comparison-of-aligners-and-callers/

Quick start
-----------

1. `Install`_ ``bcbio-nextgen`` with all tool dependencies and data files::

         wget https://raw.github.com/chapmanb/bcbio-nextgen/master/scripts/bcbio_nextgen_install.py
         python bcbio_nextgen_install.py /usr/local/share/bcbio-nextgen --tooldir=/usr/local

   producing an editable `system configuration file`_ referencing the installed
   software, data and system information.

2. `Automatically create a processing description`_ of sample FASTQ and BAM files
   from your project, and a CSV file of sample metadata::

         bcbio_nextgen.py -w template freebayes-variant project1.csv sample1.bam sample2_1.fq sample2_2.fq

   This produces a `sample description file`_ containing pipeline `configuration options`_.

3. Run analysis, distributed across 8 local cores::

         cd project1/work
         bcbio_nextgen.py ../config/project1.yaml -n 8

.. _system configuration file: https://github.com/chapmanb/bcbio-nextgen/blob/master/config/bcbio_system.yaml
.. _sample description file: https://github.com/chapmanb/bcbio-nextgen/blob/master/config/bcbio_sample.yaml
.. _Automatically create a processing description: https://bcbio-nextgen.readthedocs.org/en/latest/contents/configuration.html#automated-sample-configuration
.. _Install: https://bcbio-nextgen.readthedocs.org/en/latest/contents/installation.html#automated
.. _configuration options: https://bcbio-nextgen.readthedocs.org/en/latest/contents/configuration.html

Documentation
-------------

See the `full documentation at ReadTheDocs`_. We welcome enhancements
or problem reports using `GitHub`_ and discussion on the
`biovalidation mailing list`_.

.. _full documentation at ReadTheDocs: https://bcbio-nextgen.readthedocs.org
.. _GitHub: https://github.com/chapmanb/bcbio-nextgen/issues
.. _biovalidation mailing list: https://groups.google.com/d/forum/biovalidation

Contributors
------------

- `Miika Ahdesmaki`_, AstraZeneca
- `Luca Beltrame`_, IRCCS "Mario Negri" Institute for Pharmacological Research, Milan, Italy
- `Alla Bushoy`_, AstraZeneca
- `Guillermo Carrasco`_, Science for Life Laboratory, Stockholm
- `Brad Chapman`_, Harvard School of Public Health
- `Peter Cock`_, The James Hutton Institute
- `Mario Giovacchini`_, Science for Life Laboratory, Stockholm
- `Rory Kirchner`_, Harvard School of Public Health
- `Jakub Nowacki`_, AstraZeneca
- `Brent Pedersen`_, University of Colorado Denver
- `James Porter`_, The University of Chicago
- `Valentine Svensson`_, Science for Life Laboratory, Stockholm
- `Paul Tang`_, UCSF
- `Roman Valls`_, Science for Life Laboratory, Stockholm
- `Kevin Ying`_, Garvan Institute of Medical Research, Sydney, Australia
- `Jeff Hammerbacher`_, Icahn School of Medicine at Mount Sinai

.. _Miika Ahdesmaki: https://github.com/mjafin
.. _Luca Beltrame: https://github.com/lbeltrame
.. _Guillermo Carrasco: https://github.com/guillermo-carrasco
.. _Brad Chapman: https://github.com/chapmanb
.. _Peter Cock: https://github.com/peterjc
.. _Mario Giovacchini: https://github.com/mariogiov
.. _Rory Kirchner: https://github.com/roryk
.. _Jakub Nowacki: https://github.com/jsnowacki
.. _Brent Pedersen: https://github.com/brentp
.. _James Porter: https://github.com/porterjamesj
.. _Valentine Svensson: https://github.com/vals
.. _Paul Tang: https://github.com/tanglingfung
.. _Roman Valls: https://github.com/brainstorm
.. _Kevin Ying: https://github.com/kevyin
.. _Alla Bushoy: https://github.com/abushoy
.. _Jeff Hammerbacher: https://github.com/hammer

License
-------

The code is freely available under the `MIT license`_.

.. _MIT license: http://www.opensource.org/licenses/mit-license.html
