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

SW-Platform Assumptions of Use
##############################

.. document:: SW-Platform Assumptions of Use
   :id: doc__platform_name_platform_aou
   :status: draft
   :version: 1
   :safety: ASIL_B
   :security: YES
   :realizes: wp__requirements_sw_platform_aou[version==1]
   :tags: template

.. attention::
    The above directive must be updated.

    - Adjust ``status`` to ``valid``
    - Adjust ``safety``, ``security`` and ``tags`` according to your needs

<Short description of the scope of the SW-platform AoUs. Name the roles used in the AoU text
(e.g. Supplier = provider of an external SW element used by the SW-platform,
System Integrator = user of the SW-platform as part of their system).>

Assumptions on Environment
==========================

<Assumptions which need to be fulfilled by the architecture level below the SW-platform,
i.e. by elements outside of the SW-platform but used by it (e.g. operating system, hypervisor,
programming language libraries, processing hardware).>

.. code-block:: rst

   .. aou_req:: Some Environment Title
      :id: aou_req__platform__some_environment_title
      :reqtype: Non-Functional
      :security: YES
      :safety: ASIL_B
      :status: invalid
      :version: 1
      :tags: environment

      The system integrator shall use an <element> which ...

Assumptions on External SW Element Integration
==============================================

<Assumptions towards the suppliers of external SW elements (e.g. operating system) which are
integrated into the SW-platform. If integration levels are defined, structure this section
accordingly.>

.. code-block:: rst

   .. aou_req:: Some Integration Title
      :id: aou_req__platform__some_integration_title
      :reqtype: Process
      :security: YES
      :safety: ASIL_B
      :status: invalid
      :version: 1

      The supplier shall provide ...

Assumptions on Applications
===========================

<Assumptions towards the applications using the SW-platform.>

.. code-block:: rst

   .. aou_req:: Some Application Title
      :id: aou_req__platform__some_application_title
      :reqtype: Functional
      :security: YES
      :safety: ASIL_B
      :status: invalid
      :version: 1
      :tags: user

      The user shall ...

Assumptions on Safety System
============================

<Assumptions towards the safety system the SW-platform is integrated in
(e.g. health management, hardware safety mechanisms).>

.. code-block:: rst

   .. aou_req:: Some Safety System Title
      :id: aou_req__platform__some_safety_system_title
      :reqtype: Non-Functional
      :security: NO
      :safety: ASIL_B
      :status: invalid
      :version: 1
      :tags: environment

      The system integrator shall ...

.. attention::
    The above directives must be updated according to the SW-platform assumptions of use.

    - Replace the example content by the real content for your AoUs (according to :need:`gd_guidl__req_engineering`)
    - Remove the sections which are not needed
    - Set ``safety`` and ``security`` to the right value (ASIL B/QM; YES/NO)
    - Set ``reqtype`` with a link to the right value (<Functional|Interface|Process|Non-Functional>)
    - Add other needed AoUs for the SW-platform
    - Set ``status`` to ``valid`` and start the review/merge process

.. needextend:: c.this_doc() and "platform" in id
   :+tags: platform
