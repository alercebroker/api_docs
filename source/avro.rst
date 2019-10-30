
ALeRCE AVRO/Stamps Access API
=============================

API to get an specified avro/stamp from alert files of an ZTF Object. This API uses **GET requests** parameters.

Request AVRO information
------------------------

GET avro.alerce.online/get_avro
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Get an specified avro

.. code-block::

       curl http://avro.alerce.online/get_stamp?oid=ZTF19abguqsi&candid=928474644915015004

Parameters:


* oid: ZTF Object ID.
* candid: ZTF Alert ID.

GET avro.alerce.online/get_avro_info
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Get an specified avro information as a JSON file
(This comes without the stamps )

.. code-block::

       curl http://avro.alerce.online/get_stamp_info?oid=ZTF19abguqsi&candid=928474644915015004

Parameters:


* oid: ZTF Object ID.
* candid: ZTF Alert ID.


GET avro.alerce.online/get_stamp
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Get an specific stamp

.. code-block::

    curl http://avro.alerce.online/get_stamp?oid=ZTF19abguqsi&candid=928474644915015004&format=png&type=science

Parameters:


* oid: ZTF Object ID.
* candid: ZTF Alert ID.
* format: ["png","fits"]
* type: ["science","template","difference"]
