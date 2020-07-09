Thoth's one-time sync job
-------------------------

A job that syncs all the Thoth data to Thoth's knowledge graph.


Running the job
===============


.. code-block:: console

  oc process \
    DEADLINE_SECONDS="21600"
    IMAGE_VERSION="latest" \
    THOTH_SYNC_FORCE="0" \
    THOTH_SYNC_GRACEFUL="0" \
    THOTH_SYNC_DEBUG="0" \
  -f openshift.yaml | oc apply -f -

Cleaning objects
================

.. code-block:: console

  oc delete job -l component=sync
