..
   # *******************************************************************************
   # Copyright (c) 2025 Contributors to the Eclipse Foundation
   #
   # See the NOTICE file(s) distributed with this work for additional
   # information regarding copyright ownership.
   #
   # This program and the accompanying materials are made available under the
   # terms of the Apache License Version 2.0 which is available at
   # https://www.apache.org/licenses/LICENSE-2.0
   #
   # SPDX-License-Identifier: Apache-2.0
   # *******************************************************************************

.. _documentation_plan_template:

Template Documentation Management Plan
======================================

.. gd_temp:: Documentation Management Plan Template
   :id: gd_temp__document_mgt_plan
   :status: valid
   :version: 1
   :complies: std_req__iso26262__support_1041[version==1],
              std_req__iso26262__support_1042[version==1],
              std_req__iso26262__support_1043[version==1],
              std_req__iso26262__support_1044[version==1],
              std_req__iso26262__support_1046[version==1]

.. note::

  The documentation management plan is part of the Platform Management Plan and shall be
  continuously maintained during the project.
  For the document header use :need:`gd_temp__documentation`.

Purpose
-------
Description of the purpose of the Documentation Management Plan, i.e. how documents are handled
in the project.

Objectives and scope
--------------------
Description of the objectives and the scope of the plan. It should describe at least

* which documents exist
* which attributes and lifecycle they have
* how they are reviewed

Approach
--------

Work product types
^^^^^^^^^^^^^^^^^^
Description which work products are modelled specifically (e.g. requirements and architecture
with their own set of attributes) and which are modelled as general documents (e.g. plans,
verification reports). The plan deals with the general documents.

Document attributes
^^^^^^^^^^^^^^^^^^^
Description of the manually set attributes of a document, e.g.

* Title (mandatory)
* Unique Id following the naming pattern of the document title (mandatory)
* Safety (mandatory)
* Security (mandatory)
* Author (mandatory, may be set automatically by the version control system)
* Status (mandatory)
* Tags (optional)

Description of the attributes generated automatically during the documentation build
(e.g. approver and reviewer derived from the pull request review).

Document lifecycle
^^^^^^^^^^^^^^^^^^
Description of the lifecycle states of the documents (compare :need:`gd_req__doc_attr_status`),
the allowed transitions (e.g. from valid back to draft for the next release) and the handling
of invalidated documents (e.g. removal and availability via the version control history).

Review and approval
^^^^^^^^^^^^^^^^^^^
Description how documents are reviewed and approved, e.g. the review as defined for the type
of work product in the respective process description, the usage of checklists
(e.g. :need:`gd_chklst__documentation_review`) and the minimum number of independent reviewers.

Documentation build and versioning
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Description how the documentation is built (e.g. for each pull request) and how documents
are versioned, stored and kept available over time (reference to the configuration management plan).

Scheduling
^^^^^^^^^^
Description where the time schedule of the documentation activities is planned and tracked
(e.g. reference to the project management plan and the issue tracking system).

Document list
-------------
List of all documents including their status, structured according to the folder structure
of the project. Missing documents should be identifiable.

The list may be generated per folder, e.g.

.. code-block:: rst

   .. needtable::
      :style: table
      :columns: title;id;safety;security;status
      :colwidths: 25,45,10,10,10
      :sort: id

      results = []

      for need in needs.filter_types(["document"]):
          if need["docname"] is not None and "<folder>/" in need["docname"]:
             results.append(need)

.. needextend:: "c.this_doc()"
   :+tags: documentation_management
