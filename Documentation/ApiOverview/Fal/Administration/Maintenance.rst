.. include:: /Includes.rst.txt
.. index:: File abstraction layer; Maintenance
.. _fal-administration-maintenance:

===========
Maintenance
===========

There are various maintenance tasks which can be performed
to maintain a healthy TYPO3 CMS installation with the
file abstraction layer.


.. index:: pair: File abstraction layer; Scheduler
.. _fal-administration-maintenance-scheduler:

Scheduler tasks
===============

Two base tasks provided by the Scheduler are related to the
file abstraction layer.

File abstraction layer: Update storage index
  This task goes through a storage and makes sures that every file
  is properly indexed. When files are manipulated only via the TYPO3 CMS
  backend, they are always indexed. However if files get added via other
  means (e.g. FTP) or if some storages are based on drivers accessing
  remote systems, it is crucial to run this task regularly so that
  the TYPO3 CMS installation knows about all existing files in order
  to make them available to users.

  This task is defined per storage.

File abstraction layer: Extract metadata in storage
  This task goes through all files in a storage and updates their
  metadata. Again this is especially important when files can be
  manipulated by other means or actually reside on external systems.

  This task is defined per storage.


.. index::
   File abstraction layer; Processed files
   Folder; fileadmin/_processed_
   Folder; _processed_
   Maintenance tool; Remove Temporary Assets
.. _fal-administration-maintenance-processed-files:

Processed files
===============

If you change some graphics-related settings, it may be necessary
to force a regeneration of all processed files. This can be achieved
by deleting all existing processed files in
:guilabel:`Admin Tools > Maintenance > Remove Temporary Assets`.

.. include:: /Images/AutomaticScreenshots/AdminTools/MaintenanceRemoveTemporaryAssets.rst.txt

Here you can choose to delete all files in :file:`fileadmin/_processed_/`

This cleanup is also good if processed files have accumulated for a
long time. Many of them may then be obsolete.
