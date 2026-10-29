..
   # *******************************************************************************
   # Copyright (c) 2026 Contributors to the Eclipse Foundation
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

..
   AI Disclosure: This file was largely AI-generated. The AI-generated
   portions are made available under CC0-1.0 and not subject to the
   project's license. The human contributor has reviewed and verified
   that the content is correct.
   SPDX-License-Identifier: Apache-2.0 AND CC0-1.0
   Assisted-by: Anthropic Claude Opus 5.5 (claude-opus-5-5)

.. _ai_usage_guideline:

AI Usage Guideline
##################

.. gd_guidl:: Usage of Generative AI
   :id: gd_guidl__ai_usage
   :status: valid
   :version: 1
   :tags: process_management

   This guideline defines how the
   `Eclipse Generative AI Usage Guidelines <https://www.eclipse.org/projects/guidelines/genai/>`_,
   made applicable by :need:`wp__policies`, are applied in *S-CORE*. It applies to every
   contribution to any *S-CORE* repository (source code, documentation, process description,
   tests, tooling and infrastructure) and to all GitHub content (issues, pull requests, review
   comments).

   The Eclipse guidelines remain the governing document. This guideline only makes them
   concrete where the Eclipse guidelines leave a choice to the project.

Responsibility
==============

#. The contributor (:need:`Contributor <rl__contributor>`) shall be responsible for every
   change they submit, independent of whether it was created with the help of a generative AI
   tool. The contributor shall have reviewed and understood every change and shall be able to
   defend it in the review.
#. The use of a generative AI tool shall not reduce the scope of the review, the acceptance
   criteria or the automated checks that apply to a contribution.
#. The contributor shall follow the terms of use of the AI tool and the policy of their
   employer on the use of generative AI.
#. The contributor shall not enter confidential information, personally identifiable
   information or other sensitive information into an AI tool.

Disclosure
==========

#. The contributor shall disclose the use of a generative AI tool, if the AI contributed in a
   way for which a human would be given credit.

   No disclosure is required for trivial assistance, for example spelling and grammar
   corrections, formatting, code completion of single statements or rote boilerplate that
   the contributor modifies and supplements.

#. The disclosure shall be given in both of the following places:

   - in every affected commit, as ``Assisted-by:`` trailer in the commit message, and
   - in the description of the pull request, in a section "AI disclosure" with a statement
     that the contributor has reviewed every change and takes responsibility for it, followed
     by the ``Assisted-by:`` line.

   Disclosing in both places keeps the information in the history also when commits are
   squashed during merge.

#. The AI tool shall be identified in the following format, as complete as possible:

   .. code-block:: text

      Assisted-by: <Provider> <Model> (<Version/ID>)

   Examples:

   .. code-block:: text

      Assisted-by: GitHub Copilot (GPT-4o-2024-08-06)
      Assisted-by: Anthropic Claude Opus 5.5 (claude-opus-5-5)

   If several AI tools were used, one ``Assisted-by:`` line per tool shall be given.

#. A file that is largely or entirely AI-generated shall carry, in addition to the standard
   *S-CORE* copyright header, an AI disclosure block directly below it:

   .. code-block:: text

      AI Disclosure: This file was largely AI-generated. The AI-generated
      portions are made available under CC0-1.0 and not subject to the
      project's license. The human contributor has reviewed and verified
      that the content is correct.
      SPDX-License-Identifier: Apache-2.0 AND CC0-1.0
      Assisted-by: <Provider> <Model> (<Version/ID>)

   The standard copyright header shall stay unchanged, so that the automated copyright
   checks keep working.

Review and Merge
================

#. Every merge into an *S-CORE* repository shall be approved by a human committer
   (:need:`Committer <rl__committer>`). AI agents or bots shall not push directly to protected
   branches or merge pull requests.
#. A committer may reject an AI-assisted contribution that they do not understand or are not
   willing to maintain, or request that it is split into smaller pull requests.
#. A committer may request the missing disclosure, if a contribution appears to be AI-assisted
   and is not disclosed.

Functional Safety and Security
==============================

#. AI-assisted content in safety or security related work products shall follow the same
   process, review and verification requirements as any other content. No additional rules
   apply.
#. The output of an AI tool shall not be used as verification evidence on its own. If AI
   output becomes part of a work product without a complete human review, the AI tool shall be
   handled by Tool Management (:need:`wf__tool_evaluate_tool`).
