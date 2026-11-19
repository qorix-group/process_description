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


Platform Security Analysis Checklist
====================================

.. document:: [Your Platform Name] Security Analysis Checklist
   :id: doc__platform_name_security_analysis_fdr
   :status: draft
   :version: 1
   :safety: ASIL_B
   :security: YES
   :realizes: wp__fdr_reports_security[version==1]
   :tags: template

.. attention::
    The above directive must be updated according to your Platform.

    - Modify ``Your Platform Name`` to be your Platform Name
    - Modify ``id`` to be your Platform Name in lower snake case preceded by ``doc__`` and followed by ``_security_analysis_fdr``
    - Adjust ``status`` to be ``valid``
    - Adjust ``safety``, ``security`` and ``tags`` according to your needs


**Purpose**
The purpose of this Security Analysis Checklist template is to collect the topics to be checked during verification of the Security Analysis.

**Checklist**

**Conduct**

As described in :need:`wf__p_formal_security_rv`, the formal document review is performed by a reviewer who did not create the security analysis:

- reviewer: **<reviewer with security manager skills, named here, not the author of the analysis>**
- scope: **<the security analysis of the platform, feature or component and its results>**

**Checklist**

Mark each item "YES" or "NO" and state the reason in the comment. A "NO" needs an issue.

.. list-table:: Security Analysis Checklist
      :header-rows: 1
      :widths: 10,30,10,30,20

      * - ID
        - Security analysis activity
        - Compliant to ISO/SAE 21434?
        - Reference (clause 9 and 15 of the standard)
        - Comment

      * - Sec 1
        - Is the item definition complete: the information on the item and its operational environment is identified?
        - [YES | NO ]
        - RQ-09-01, RQ-09-02
        - <Rationale for result>

      * - Sec 2
        - Is the analysis based on the item definition and performed with the defined method and templates?
        - [YES | NO ]
        - RQ-09-03
        - <Rationale for result>

      * - Sec 3
        - Are the threat scenarios, their impact and their risk values identified for the assets?
        - [YES | NO ]
        - RQ-09-03, RQ-09-04
        - <Rationale for result>

      * - Sec 4
        - Is a risk treatment decision taken for each threat scenario, and are the risks retained because of assumptions documented as such?
        - [YES | NO ]
        - RQ-09-04, RQ-09-06
        - <Rationale for result>

      * - Sec 5
        - Are the cybersecurity goals and claims consistent with the risk treatment decisions?
        - [YES | NO ]
        - RQ-09-05, RQ-09-06
        - <Rationale for result>

      * - Sec 6
        - Are the cybersecurity controls, requirements and their allocation to the item defined and consistent with the goals?
        - [YES | NO ]
        - RQ-09-08, RQ-09-09, RQ-09-10
        - <Rationale for result>

      * - Sec 7
        - Is the verification of the analysis result performed: correctness, completeness and consistency of the analysis, the treatment and the claims?
        - [YES | NO ]
        - RQ-09-07, RQ-09-11
        - <Rationale for result>

      * - Sec 8
        - Are the assumptions of use of the analysis the same as the assumptions in the security manual?
        - [YES | NO ]
        - RQ-06-18 (assumptions of out-of-context components)
        - <Rationale for result>

      * - Sec 9
        - Is the analysis updated when the item, its environment or the known threats change?
        - [YES | NO ]
        - RQ-06-07, RQ-06-09
        - <Rationale for result>

Note: the standard's clause 9 requirements are not modelled as needs in the upstream needs files. The references in this checklist are therefore plain text and must be checked against the standard text by the security manager.
