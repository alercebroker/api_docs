
catsHTM XMatch
==============

Cats Service provides cone search and cross-match on different `catalogs <#available-catalogs>`_. This service is based on `catsHTM <https://github.com/maayane/catsHTM>`_.

Arguments and units in requests
-------------------------------

The parameters and units in the catsHTM API are the following:

==================      ========
Parameter               unit
==================      ========
catalog                 string
ra                      degrees
dec                     degrees
radius  (optional)      arcsec
==================      ========

Cone search
----------

Cone search on a specific catalog or on all of them.

.. code-block::

  GET catshtm.alerce.online/conesearch[_all]


Cone search on a catalog
^^^^^^^^^^^^^^^^^^^^^^^

.. code-block::

  curl "catshtm.alerce.online/conesearch?catalog=GAIADR1&ra=357.73373&dec=14.20514&radius=100"


Cone search on all catalogs
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block::

  curl "catshtm.alerce.online/conesearch_all?ra=357.73373&dec=14.20514&radius=10"


Cross-match
----------

Get the closest object, given RA and Dec, for a catalog or all of them.

.. code-block::

  GET catshtm.alerce.online/crossmatch[_all]



Cross-match on a catalog
^^^^^^^^^^^^^^^^^^^^^^^

Since the radius argument is optional, there are two ways to perform cross-match on a catalog.


#. Providing a value for the radius:

.. code-block::

   curl "catshtm.alerce.online/crossmatch?catalog=SDSSDR10&ra=357.73373&dec=14.20514&radius=10"


#. Not providing one:

.. code-block::

   curl "catshtm.alerce.online/crossmatch?catalog=SDSSDR10&ra=357.73373&dec=14.20514"

If a radius is provided, then that value is used. If not, the default value for that catalog is used. See default values in `Available catalogs <#available-catalogs>`_

Cross-match on all catalogs
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For cross-matching on all catalogs, the same rule of providing a radius or not applies. Therefore, there are two ways to send the request.


#. With radius:

.. code-block::

   curl "catshtm.alerce.online/crossmatch_all?ra=357.73373&dec=14.20514&radius=100"


#. Without radius:

.. code-block::

   curl "catshtm.alerce.online/crossmatch_all?ra=357.73373&dec=14.20514"

Available catalogs:
-------------------

For catalogs that have a value listed, this value is the radius used for cone search and cross-match. Otherwise, the default radius of 50 arcsec is used.

* AAVSO_VSX
* AKARI
* APASS (2 arcsec)
* CRTS_per_var
* Cosmos
* DECaLS (0.1 arcsec)
* FIRST
* GAIADR1 (0.1 arcsec)
* GAIADR2 (0.1 arcsec)
* GALEX
* HSCv2
* IPHAS
* IRACgc
* NEDz
* NVSS (10.8 arcsec)
* PTFpc
* ROSATfsc
* SAGE
* SDSSDR10
* SDSSoffset (0.1 arcsec)
* SWIREz
* SkyMapper (0.4 arcsec)
* SpecSDSS
* TMASS (2MASS)
* TMASSxsc (2MASSxsc)
* UCAC4
* UKIDSS
* VISTAviking
* VSTatlas
* VSTkids
* WISE
* XMM (8 arcsec)
* unWISE
