==================
Hakai Segmentation
==================

Segmentation Tools for Remotely Sensed RPAS Imagery

.. image:: https://github.com/tayden/hakai-segmentation/actions/workflows/unit-test.yml/badge.svg?branch=main&event=push
  :target: https://github.com/tayden/hakai-segmentation/actions/workflows/unit-test.yml
  :alt: Test Status
  :height: 20px

.. image:: https://readthedocs.org/projects/hakai-segmentation/badge/?version=latest
  :target: https://hakai-segmentation.readthedocs.io/en/latest/?badge=latest
  :alt: Documentation Status
  :height: 20px

.. image:: https://anaconda.org/hakai-institute/hakai-segmentation/badges/license.svg
  :target: https://github.com/tayden/hakai-segmentation/blob/main/LICENSE.txt
  :alt: License
  :height: 20px

.. image:: https://anaconda.org/hakai-institute/hakai-segmentation/badges/version.svg
  :target: https://anaconda.org/Hakai-Institute/hakai-segmentation
  :alt: Version
  :height: 20px

Features:
---------

- Kelp detection in RGB RPAS imagery
- Mussel detection in RGB RPAS imagery

Installation:
-------------
The most reliable way to install ``hakai_segmentation`` is with `Conda <https://docs.anaconda.com/anaconda/>`_.

The library is currently available for Python versions 3.7 through 3.9.

Use the Anaconda Navigator GUI to create a new environment and add the *hakai-institute*, *conda-forge*, and *pytorch* channels
before searching for and installing the ``hakai-segmentation`` package in your environment.

Alternatively, install using your terminal or the Anaconda prompt (for Windows users) by running the following command:

.. code-block:: bash

    conda install -c conda-forge -c pytorch -c hakai-institute hakai-segmentation


Usage:
------

Expectations:
~~~~~~~~~~~~~~~~~~

All interfaces to ``hakai-segmentation`` tool make the following assumptions about input images:

1. The range of values in the input are in the interval [0, 255] and the datatype is Unsigned 8-bit (Often called "uint8" or "Byte" GIS software).
2. The first three channels of the image are the Red, Green, and Blue bands, in that order.
3. The *nodata* value for the image is defined properly in the geotiff metadata.
    - For images with a black background, this value should be 0, white background would be 255, etc.
    - This is not a hard requirement, but speeds up the processing time considerably


.. Usage
.. toctree::
   :maxdepth: 2

   cli
   lib


About:
------


Overview
~~~~~~~~

Training Process
~~~~~~~~~~~~~~~~

Data
~~~~

Metrics
~~~~~~~

For all metrics, let:

:math:`A` equal the set of human-labelled pixels for an image.

:math:`B` be defined as the corresponding set of pixel labels predicted by the model.

:math:`A_i` and :math:`B_i` be the sets of pixels for a particular class of interest, :math:`i` for label images :math:`A` and :math:`B`.

Accuracy
    The ratio of counts of pixels correctly classified by the model divided over the total number of pixels in an image.


IoU
    The "intersection over union", also called the "Jaccard Index". Defined as:

    .. math::

        IoU_i (A,B) = \frac{|A_i \cap B_i|}{|A_i \cup B_i|}

Mean IoU
    The mean of the intersection over union values over all classes. Defined as:

    .. math::

        mIoU (A,B) = \frac{\sum_{i=1}^{c} IoU_{i}(A,B)}{c}

Performance
~~~~~~~~~~~

+------------------+----------------------------------------------------------------+-------------------------+-------------+-------------+----------+----------+-------------+-------------+----------+----------+
| Tool             | Model Architecture                                             | Output Classes          | Validation                                      | Test                                            |
+                  +                                                                +                         +-------------+-------------+----------+----------+-------------+-------------+----------+----------+
|                  |                                                                |                         | Class 0 IoU | Class 1 IoU | Mean IoU | Accuracy | Class 0 IoU | Class 1 IoU | Mean IoU | Accuracy |
+==================+================================================================+=========================+=============+=============+==========+==========+=============+=============+==========+==========+
| ``find-kelp``    | `LRASPP MobileNetV3-Large <https://arxiv.org/abs/1905.02244>`_ | 0=background, 1=kelp    | 0.9437      | 0.6609      | 0.8023   | 0.9555   | 0.9286      | 0.5930      | 0.76077  | 0.93844  |
+------------------+----------------------------------------------------------------+-------------------------+-------------+-------------+----------+----------+-------------+-------------+----------+----------+
| ``find-mussels`` | `LRASPP MobileNetV3-Large <https://arxiv.org/abs/1905.02244>`_ | 0=background, 1=mussels | 0.9622      | 0.7188      | 0.8405   | 0.9678   | -           | -           | -        | -        |
+------------------+----------------------------------------------------------------+-------------------------+-------------+-------------+----------+----------+-------------+-------------+----------+----------+

Contribute:
~~~~~~~~~~~

- Issue Tracker: https://github.com/tayden/hakai_segmentation/issues
- Source Code: https://github.com/tayden/hakai_segmentation

License:
~~~~~~~~

The project is licensed under the `MIT license <https://raw.githubusercontent.com/tayden/hakai-segmentation/main/LICENSE.txt>`_.

Indices and tables
~~~~~~~~~~~~~~~~~~

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
