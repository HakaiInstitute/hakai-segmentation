===================
Hakai Segmentation!
===================

Segmentation Tools for Remotely Sensed RPAS Imagery

.. image:: https://github.com/tayden/hakai-segmentation/actions/workflows/test.yml/badge.svg?branch=main&event=push
  :target: https://github.com/tayden/hakai-segmentation/actions/workflows/test.yml
  :alt: Test Status
  :height: 20px

.. image:: https://readthedocs.org/projects/hakai-segmentation/badge/?version=latest
  :target: https://hakai-segmentation.readthedocs.io/en/latest/?badge=latest
  :alt: Documentation Status
  :height: 20px

.. image:: https://badgen.net/github/license/tayden/hakai-segmentation
  :target: https://github.com/tayden/hakai-segmentation/blob/main/LICENSE.txt
  :alt: License
  :height: 20px

.. image:: https://badgen.net/github/release/tayden/hakai-segmentation?icon=github
  :target: https://github.com/tayden/hakai-segmentation/releases
  :alt: License
  :height: 20px

.. image:: https://badgen.net/pypi/python/hakai-segmentation?icon=pypi
  :target: https://pypi.org/project/hakai-segmentation/
  :alt: License
  :height: 20px

Features
--------

- Kelp detection in RGB RPAS imagery
- Mussel detection in RGB RPAS imagery

Installation
------------
The most reliable way to install hakai_segmentation is with Anaconda.

.. code-block:: bash

    # Omit installing cudatoolkit for CPU only install.
    conda install -c nvidia cudatoolkit=10.2

    conda install -c hakai-institute hakai-segmentation


.. toctree::
   :maxdepth: 2
   :caption: Usage:

   cli
   lib

Contribute
----------

- Issue Tracker: https://github.com/tayden/hakai_segmentation/issues
- Source Code: https://github.com/tayden/hakai_segmentation

License
-------

The project is licensed under the `MIT license <https://raw.githubusercontent.com/tayden/hakai-segmentation/main/LICENSE.txt>`_.

Indices and tables
------------------

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
