---
# Copyright 2026 MikeGC contributors. Licensed under the Apache License,
# Version 2.0: see third-party-licenses/mikegc-workflows-Apache-2.0.txt
# and NOTICE at the repository root. Copied from
# open-legal-products/mikegc-workflows at 39a8065 and modified; see
# metadata.source-changes.
name: "contract-markup"
description: "Propose tracked changes and comments on an uploaded contract from the user's negotiating position, for the user to accept or reject, and summarise each change with its rationale and fallback."
license: "Apache-2.0"
metadata:
  version: "1.0.0"
  author: "MikeGC"
  language: "English"
  mike-display-name: "Contract Markup"
  mike-type: "assistant"
  mike-availability: "add-on"
  practice: "General Transactions"
  jurisdictions: "General"
  source-repository: "open-legal-products/mikegc-workflows"
  source-revision: "39a806580fc5dcfd5605e564a62a5dd98855f2ca"
  source-path: "assistant-workflows/contract-markup"
  source-url: "https://github.com/open-legal-products/mikegc-workflows/tree/39a806580fc5dcfd5605e564a62a5dd98855f2ca/assistant-workflows/contract-markup"
  source-changes: "Modified 2026-11-24 for the Legal Workflows catalogue: changes are proposed as tracked changes for the user to accept or reject instead of being made directly on a file copy; the untracked-edit fallback is replaced by an edit plan that leaves the document unchanged; description and deliverable wording updated to match. Provenance fields and notice comment added."
---
# Contract Markup

## Instructions

If the user has not provided a contract, ask them to upload one. If it is not
clear which party the user represents, ask before marking up.

Read the whole contract, including definitions, schedules, and exhibits,
before changing anything. A defined term or schedule can change how a clause
operates.

Apply the user's instructions and any playbook, standard positions, or
precedent they provide. Without a playbook, note the contract type and
governing law from the document, and ask the user once for any deal context
the materials do not show, such as what is being bought or sold, its value,
and how much risk the user will accept. Then take reasonable market-standard
positions for the user's side under that governing law. If the user gives no
context, change only provisions that create a clear legal risk for the user's
side, and list other issues under Points for Business Input instead of
changing them.

Use the markup level the user asks for, or Standard if they do not say:

- **Light** — Must-have changes only.
- **Standard** — Must-have and Important changes.
- **Full** — Must-have, Important, and Nice-to-have changes.

At every level, do not redraft for style.

If the contract cannot be edited in its uploaded format without losing
content, such as a scanned or protected PDF, stop and ask the user for an
editable version. Never work from a flattened or incomplete version.

Propose every change as a tracked change through the host's document editor,
which shows each proposed change to the user to accept or reject. Do not edit
the uploaded contract directly or work on a separate copy, and do not accept,
apply, or finalise a proposed change on the user's behalf: the contract changes
only when the user accepts a change. Give each change a short reason, and where
the host supports margin comments, add a short comment explaining each
significant change. Write reasons and comments for the counterparty: keep
internal reasoning, fallback positions, and negotiation strategy out of the
document.

If the contract already contains tracked changes or comments, such as the
counterparty's last turn, leave them in place. Do not accept, reject, or delete
them unless the user asks. Make any counter-proposal as your own tracked change
or reply comment.

Keep edits surgical. Change the fewest words needed, and preserve the
document's format, styles, numbering, defined terms, and cross-references. When
a change adds, removes, or renumbers a definition or clause, update every
dependent reference. Keep inserted wording consistent with the contract's
existing drafting style and defined terms.

If the host cannot propose tracked changes on this document, do not edit it.
Deliver the table below as an edit plan, giving the exact current wording and
the proposed replacement in Change, and tell the user that the contract was not
changed.

## Deliverable

Present the proposed tracked changes on the uploaded contract for the user to
accept or reject. Do not describe the contract as changed until the user has
accepted the changes.

Then provide a Markdown table with exactly these columns:

- Priority
- Location
- Change
- Rationale
- Fallback Position

Use these priorities, and sort the table with Must-have changes first:

- **Must-have** — the user should not sign without this change.
- **Important** — a significant risk or cost that is worth negotiating.
- **Nice-to-have** — an improvement the user could concede.

In Location, give the clause, section, schedule, or page reference. In Fallback
Position, give the user's fallback if they supplied one. Otherwise, give a
fallback labelled "Suggested:", or write "Needs business input" where the
fallback is a commercial decision.

Include a row for each existing counterparty change, recommending whether to
accept, reject, or modify it.

After the table, list under **Points for Business Input** any issues left
unmarked because they need a commercial decision, such as pricing, service
levels, or scope.

Do not invent facts, parties, amounts, dates, or obligations. Where a change
needs information the user has not provided, propose a clearly marked
placeholder and list it in the summary.
