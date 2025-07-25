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

Concept Description
###################

.. doc_concept:: Concept Description
   :id: doc_concept__problem__process
   :status: valid
   :tags: problem_resolution

In this section a concept for the Problem Resolution will be discussed. Inputs for this concepts
are both the requirements of ISO26262 Part-2 and ASPICE Requirements from SUP.9 additionally
including the requirements of the different stakeholders for the Problem Resolution process.

Key concept
***********
A Problem Report is the **ONLY** way to report deviations of an expected result for
existing features in the project. Deviations include problems found by user,
bugs found during verification activities by tester, quality issues found by quality
checks, safety anomalies, vulnerabilities or any other malfunction.

Inputs
******

#. Stakeholders for the Problem report?
#. Which categories are required?
#. Which attributes are required?
#. Which activities are required?

Stakeholders for the Problem Report
***********************************

#. :need:`Contributor <rl__contributor>`

   * In general contributes features and components to grow the project content
   * Reports problems, analyze problems, implement problem resolutions

#. :need:`Committer <rl__committer>`

   * Verifies that the contribution including problem resolutions fulfills the project policies
   * Approves all problem resolution activities besides problem closing
   * Is responsible to initiate the the closure of the problem reported

#. :need:`Technical Lead <rl__technical_lead>`, :need:`Module Lead <rl__module_lead>`

   * Supports all problem resolution activities
   * Approves the closing of the problem resolution

#. :need:`Safety Manager <rl__safety_manager>`, :need:`Security Manager <rl__security_manager>`, :need:`Quality Manager <rl__quality_manager>`

   * Supports all problem resolution activities


Standard Requirements
=====================

Also requirements of standards need to be taken into consideration:

* ISO 26262
* ASPICE
* ISO/SAE 21434

.. _prm_attributes:

Problem Report Attributes
*************************

The required attributes for the Problem Report are defined here: :ref:`prm_process_problem_attributes`.

Activities for Problem Resolution
*********************************

.. _prm_creation:

Creation of the Problem Report
==============================

Use the content :ref:`Problem Report Template <prm_templates>` to create the Problem Report.

In case safety or security is affected, in addition the impact analysis template
: :ref:`Impact Analysis Template <chm_impact_analysis_templates>`  can be used to detail out the
impact on safety/security as part of the description.

(needs to be updated)

.. _prm_analysis:

Analysis of the Problem Report
==============================

Based on the analysis results decision about the acceptance or rejection must be taken
by authorized persons.

Authorized person includes

#. :need:`Technical Lead <rl__technical_lead>`
#. :need:`Module Lead <rl__module_lead>`
#. :need:`Safety Manager <rl__safety_manager>`
#. :need:`Security Manager <rl__security_manager>`
#. :need:`Quality Manager <rl__quality_manager>`

Further prioritization must be done, e.g. based on release planning.

.. _prm_implementation_monitoring:

Implementation and Monitoring of the Problem Resolution
=======================================================
If the Problem Report is accepted, the implementation of the resolution must be initiated and
monitored.

The Problem Resolution implementation must be tracked until it is closed.

The status of the Problem Report must be communicated by the
:need:`Technical Lead <rl__technical_lead>` or :need:`Module Lead <rl__module_lead>` until
the implementation is completed and confirmed.

.. _prm_closing:

Closing of the Problem Resolution
=================================

Use the :ref:`Problem Report Checklist <prm_checklist>` to control the completeness of the
Problem Report to be closed.

Especially the effectiveness of the solution measures must be shown, based on convincing
arguments, e.g. verification measures must be used to confirm the implementation.
