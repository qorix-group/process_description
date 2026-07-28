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

Guideline
#########

.. gd_guidl:: Implementation Guideline
   :id: gd_guidl__implementation
   :status: valid
   :version: 2
   :complies: std_req__iso26262__software_744[version==1],
              std_req__iso26262__software_841[version==1],
              std_req__iso26262__software_842[version==1],
              std_req__aspice_40__iic-11-05[version==1]

This document describes the general guidance for implementation based on the concept which is defined :need:`[[title]]<doc_concept__imp_concept>`.
An example of a Detailed Design is maintained in the
`module template documentation <https://eclipse-score.github.io/module_template/detailed_design_example.html>`_.

Workflow for Implementation
===========================

Detailed description which steps are need for implementation.

#. Consult which programming languages, design/coding guidelines and tools are used for Software
   development according the rules given in the project specific :need:`SW development Plan <wp__sw_development_plan>`.
#. Create a Detailed Design. Based on the :need:`Component Requirements <wp__requirements_comp>`
   and the :need:`Component Architecture <wp__component_arch>`, the component is broken down into
   smaller, independent units that can be tested separately during the unit testing phase.
   A detailed design shall exist for every unit. It is captured primarily in the source code
   itself (unit interfaces and contracts, e.g. public API headers, trait or function signatures,
   and doxygen-style comments). A separate detailed design document following the template
   :need:`gd_temp__detailed_design` including static and dynamic views is **optional** and is
   only created where it helps to explain complex components or a large number of unit
   interactions (see :need:`doc_concept__imp_concept`). The detailed design shall be so exact,
   that test and implementation can be run simultaneously.
#. Document and justify the detailed design decisions, in particular those that shape the
   decomposition of the component into units. The rationale shall be captured close to the design,
   i.e. in the source and header files (e.g. as doxygen-style comments) and, where applicable, in the
   detailed design documentation (see :need:`doc_concept__imp_concept`).
#. Implement the source code, by using the coding guidelines given within the project specific :need:`SW development Plan <wp__sw_development_plan>` for the programming languages in your project.
#. Create a pull request for your change.
#. Detail Design and Code Inspection is done to review the code of the software and detect errors in it.
#. Check the results of the static and dynamic code analysis (this includes compiler warnings). Acceptance criteria are defined in the Verification Plan :need:`gd_temp__verification_plan`.
#. Fix or justify the errors.
#. Merge the pull request.
#. Create a follow up ticket if not all findings could be fixed.


Basis for Unit Testing
======================

The basis (test oracle) for unit testing is the **detailed design of the unit**, i.e. the
unit's specified interfaces and behaviour as documented in the source code (public API
headers, trait or function signatures and their contracts). The source code is the object
under test, not the reference against which it is tested.

Requirements are owned by the **component**, not by individual units, and there is no
formal allocation of requirements to units. The component requirements are distributed
across the units implicitly by the detailed design, and they are verified collectively by
the units and primarily by the component integration tests (see :need:`wp__component_arch`
and the verification process area). Separate requirements at unit granularity are therefore
**not** required.

Unit tests thus verify the detailed design of the unit. Only in the exceptional case where
a single unit fully realises a component requirement may the corresponding unit test cover
and link to that component requirement directly.

Traceability
============

The traceability of a component to its units is achieved primarily through naming
conventions: the decomposition of a component into its units is mainly described by the
directory and file name structure. Each component (and sub-component) maps to a namespace
and thus to a directory, its units are represented by the corresponding source and header
files within that directory, and sub-components are reflected by nested sub-directories so
that the folder hierarchy mirrors the decomposition of the component into sub-components
and units. Units therefore belong to their component and inherit the accordance to the
architecture from their location (see :need:`doc_concept__imp_concept`). Unit tests and
the detailed design are implicitly related by file naming and header inclusion, so no
additional explicit linking is required for these.

A static and a dynamic view for unit interactions are optional and are only added when
they help to explain complex components or a large number of unit interactions. If such
diagrams are provided, they are linked to the architecture and the component requirements
as shown below.

.. figure:: _assets/static_view.drawio.svg
   :align: center
   :width: 30%
   :name: static_view_fig

If used, the static diagram satisfies the architecture and implements the requirements of the related component. The static diagram includes Unit1+2.


.. figure:: _assets/dynamic_view.drawio.svg
   :align: center
   :width: 30%
   :name: dynamic_view_fig

If used, the dynamic diagram satisfies the architecture and implements the requirements of the related component.

.. figure:: _assets/dd_traceability.drawio.svg
   :align: center
   :width: 30%
   :name: dd_traceability_fig

The unit description is provided by the interface documentation and the comments in the source code itself.
