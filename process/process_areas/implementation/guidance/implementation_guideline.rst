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
   :version: 1
   :complies: std_req__iso26262__software_744[version==1],
              std_req__iso26262__software_841[version==1],
              std_req__iso26262__software_842[version==1],
              std_req__iso26262__software_843[version==1],
              std_req__iso26262__software_844[version==1],
              std_req__iso26262__software_845[version==1],
              std_req__aspice_40__SWE-3-BP1[version==1],
              std_req__aspice_40__SWE-3-BP2[version==1],
              std_req__aspice_40__SWE-3-BP3[version==1],
              std_req__aspice_40__SWE-3-BP4[version==1],
              std_req__aspice_40__iic-11-05[version==1]

This document describes the general guidance for implementation based on the concept which is defined :need:`[[title]]<doc_concept__imp_concept>`.
An example of a Detailed Design is maintained in the
`module template documentation <https://eclipse-score.github.io/module_template/detailed_design_example.html>`_.

**Scope:** This guideline applies to both QM (Quality Management) and ASIL B components. Where specific requirements differ between QM and ASIL B (e.g., complexity thresholds, design principles), they are explicitly noted.

Workflow for Implementation
===========================

Detailed description which steps are need for implementation.

#. Consult which programming languages, design/coding guidelines and tools are used for Software
   development according the rules given in the project specific :need:`SW development Plan <wp__sw_development_plan>`.
#. Create a Detailed Design by using the template :need:`gd_temp__detailed_design`.
   Based on the :need:`Component Requirements <wp__requirements_comp>` and the
   :need:`Component Architecture <wp__component_arch>`, the components are broken down into smaller,
   independent units that can be tested separately during the unit testing phase.
   The detailed design shall be so exact that test and implementation can be run simultaneously.
#. Implement the source code, by using the coding guidelines given within the project specific :need:`SW development Plan <wp__sw_development_plan>` for the programming languages in your project.
#. Create a pull request for your change.
#. Detail Design and Code Inspection is done to review the code of the software and detect errors in it. See the detailed design and code :need:`inspection checklist <doc__feature_name_req_inspection>` for evaluation criteria.
#. Check the results of the static and dynamic code analysis (this includes compiler warnings). Acceptance criteria are defined in the Verification Plan :need:`gd_temp__verification_plan`.
#. Fix or justify the errors.
#. Merge the pull request.
#. Create a follow up ticket if not all findings could be fixed.


Traceability
============

The detailed design is created by using the template :need:`gd_temp__detailed_design`. In the template
the static and the dynamic view for unit interactions is described.

Traceability from requirements to units is established implicitly through the verification work products:
:need:`unit tests <wf__sw_unit_test>` and integration tests reference specific requirement IDs and exercise
the units that implement those requirements. This creates the necessary requirement-to-unit link for compliance
and audit purposes. See the :need:`verification process area <process_areas>` for details on how requirements
are verified through tests that exercise specific units.

.. figure:: _assets/static_view.drawio.svg
   :align: center
   :width: 30%
   :name: static_view_fig

The static diagram satisfies the architecture and implements the requirements of the related component. The static diagram includes Unit1+2.


.. figure:: _assets/dynamic_view.drawio.svg
   :align: center
   :width: 30%
   :name: dynamic_view_fig

The dynamic diagram satisfies the architecture and implements the requirements of the related component.

.. figure:: _assets/dd_traceability.drawio.svg
   :align: center
   :width: 30%
   :name: dd_traceability_fig

The unit description will be generated automatically based on the comments in the source code and from the interface description.

Detailed Design Guidance
========================

Definition of a Unit
--------------------

A **unit** is a **granular, independent entity** of a component that can be **tested separately**
during the unit testing phase. Each unit represents a **self-contained functionality** and is
derived from the decomposition of a component.

**Characteristics of a Unit**

-  **Independent** - Can be tested in isolation.
-  **Granular** - Represents a small, well-defined part of the system.
-  **Relational** - Has associations with other units, defined using **UML 2.0 notations** such as
   aggregation, composition, and generalization.

**Examples:**
The definition of a unit depends on the used programming language. Examples for a unit are
a source file, a definition file (e.g. c++ header), classes, structs, and functions.
This list is not complete or exclusive.

**Units in UML Diagrams**

-  **C++ development** - Each **class** can be considered a **unit** in the design.
-  **Rust development** - A **unit** is modeled using a **combination of ``struct`` and ``trait``**,
   as Rust does not have traditional classes.

Units within the Component
--------------------------

The relationship between a unit and its parent component is established implicitly through the
**file path** - each component has its own directory, and units residing within that directory
belong to it and therefore align with the architecture. A separate static diagram per unit is
**not required**; the unit's attributes and behaviour are documented in the source code itself,
as the source code is sufficiently self-explanatory and adheres to the design principles outlined
in the development plan.

However, for components with complex interactions or a large number of units, a textual description,
a static or dynamic view can be beneficial for understanding the overall structure and relationships
between units. The developer may choose to add an additional unit-level description, static and dynamic
view if this helps explain the source code better.

It is important that the naming of the units, their interfaces and functions in any diagrams or
descriptions matches the naming in the source code to ensure traceability. This means the diagrams
and descriptions should not be outdated, should stay consistent with the source code, and should not
introduce new terminology or concepts that are not present in the code.

Design Principles of the Units
``````````````````````````````

The unit design and implementation should target quality attributes like simplicity, modularity and encapsulation,
using project-defined coding guidelines and static analysis tooling appropriate for the language
in use (e.g. MISRA C for C/C++, Clippy lints for Rust) as specified in the software development plan.

For ASIL B components, the software development plan shall mandate compliance with the design principles
specified in ISO 26262-6 §8.4.5 Table 6, including requirements for limited complexity (one-entry-one-exit,
no recursion, no unconditional jumps), restricted use of pointers, limited global variables, and absence
of hidden data/control flow. These principles shall be enforced through coding guidelines and automated
static analysis tooling.

The **source code** itself should be self-documenting with meaningful naming and structure.
**Code comments** may be used where the logic is not self-evident and to provide rationale.
These comments, along with commit messages, and any additional documentation accompanying the
source code should use natural language.

The interface documentation of a software unit is part of the source code (e.g. public API headers,
trait definitions, or documented function signatures). If interfaces of the units are also interfaces
of the component, they should follow the same documentation rules as the component interfaces
(see :need:`gd_guidl__arch_design`).

Especially for public interfaces, the interface naming should follow the naming of the logical
interface in the feature and component architecture to ensure traceability. The interface
documentation should be clear and comprehensive so users of the unit can understand how to interact
with it without needing to read implementation details. The documentation should be maintained and
updated as the implementation evolves.

Diagrams
--------

Developers may add **class diagrams** or **sequence diagrams** at the unit level if they believe
it helps to explain the source code better. These are optional and serve as supplementary
documentation.

Static View
```````````

If a static view is used, it should provide an overview of the **units** and their relationships
using **UML 2.0 notations**, such as **aggregation, composition, and generalization**. It is depicted
through **UML structural diagrams**, including:

-  **Class Diagrams** - Define classes, attributes, methods, and relationships (e.g. inheritance,
   associations, dependencies).
-  **Component Diagrams** - Show the organization and dependencies among software units, which can be
   used to represent the units within a component.
-  **Rust** - Uses ``struct`` and ``trait`` combinations to represent units in UML diagrams.

The static view need not cover every class or struct in the implementation - it should show the units
and relationships that are necessary to understand the detailed design.

The naming of the units and their interfaces in the static view should match the naming in the source
code to ensure traceability. Implementation details that are not relevant at the design level may be
omitted.

According to the software development plan of the project, the developer may use tools like PlantUML
or Draw.io for such diagrams.

Dynamic View
````````````

An optional **dynamic view** illustrates how the **units** within a component interact over their
**interfaces** to fulfill a specific **use case** or **functionality**. This is a **component-level**
view - individual per-unit dynamic diagrams are **not required**.

It is represented using **UML behavioural diagrams**, including:

-  **Sequence Diagrams** - Depict interactions between objects in a time-ordered sequence,
   highlighting how methods are invoked and how control flows between objects over time.
-  **State Machine Diagrams** - Show how the state of an object changes in response to events,
   allowing the modeling of complex state transitions (if there is stateful behaviour).

A dynamic view is optional when the component's behaviour is straightforward and can be understood
from the static view and interface documentation alone (similar to the rules depicted in
:need:`gd_guidl__arch_design`).

Example using PlantUML:

.. uml::

   @startuml
   participant UnitA
   participant UnitB

   UnitA -> UnitB : request()
   UnitB --> UnitA : response()
   @enduml
