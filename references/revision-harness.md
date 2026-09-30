# Revision harness

Use this harness when rewriting an AI-shaped coding-agent message, repository
document, commit message, PR description, comment, or docstring. It is a silent
editing pass, not a report to show the user unless they ask for the diagnosis.

The goal is not to erase every recognizable construction. Preserve the payload,
remove rhetoric that does no work, and rebuild the prose around the actual
engineering judgment.

## Protect the payload

Before rewriting, identify what the draft is allowed to say:

- verified behavior, measurements, commands, test results, and changed state;
- inference, assumptions, proposals, and unknowns at their current confidence;
- decisions or input still required from the user;
- material risks, failed checks, skipped checks, and scope limits;
- exact literals such as symbols, identifiers, paths, error messages, quoted
  text, numbers, and versions.

Do not strengthen a claim while making it more direct. A likely cause must not
become a confirmed cause. A correlation must not become a mechanism. Excluding
one explanation does not prove another. If the draft lacks a concrete fact,
leave the claim appropriately general or mark the missing evidence; do not
invent detail to make the rewrite sound grounded.

## Diagnose the move

Read by rhetorical function rather than scanning for forbidden words. A passage
deserves revision when its shape substitutes for information:

- **Staging:** an opener announces analysis, importance, candor, or a coming
  explanation before giving the result.
- **Manufactured contrast:** the prose negates an unclaimed alternative, then
  presents the ordinary conclusion as a revelation.
- **Performed emphasis:** a fragment, slogan, or final line asks for attention
  but contributes no new fact or consequence.
- **Imaginary debate:** the draft defends against an objection or alternative
  that is absent from the request and evidence.
- **Mechanical composition:** repeated openings, automatic triads, balanced
  sections, uniform bullet shapes, or habitual punctuation determine the form
  instead of the relationships among ideas.
- **Unearned weight:** terms such as important, robust, fundamental, or aligned
  carry the conclusion because the behavior, measurement, source, or mechanism
  is missing.
- **Conversation residue:** the response describes its own analysis, announces
  its organization, repeats shared context, or leaves a generic offer after the
  answer is complete.

One occurrence is not automatically a defect. Ask whether it carries information
this reader needs in this context. A real contrast, three actual states, or a
short consequential sentence should remain.

## Rebuild from the engineering point

Start with the smallest claim that answers the reader's question. Then attach
only the evidence, mechanism, consequence, limitation, or next decision needed
to make that claim usable.

Rewrite the sentence or paragraph as a unit when its structure is the problem.
Do not patch a flagged phrase with a milder synonym. Typical repairs include:

- replace announced importance with the behavior and its consequence;
- replace a fake contrast with the positive claim, unless the rejected option is
  a real live alternative;
- fold a repetitive closer into the causal explanation or delete it;
- turn a ceremonial list into connected prose, or keep a list only when the
  items are genuinely parallel;
- name the actor and relationship when the source provides them;
- end on the last useful fact, risk, or required decision instead of fabricating
  a takeaway.

Do not manufacture quirks after removing formulaic prose. Slang, forced
fragments, arbitrary sentence-length variation, casual first person, and
deliberate roughness are another kind of performance.

## Check fidelity

Compare the revision with the source before delivering it:

- Every fact, number, name, identifier, and quoted value still means the same
  thing.
- Uncertainty, causality, priority, ordering, and scope have not shifted.
- No test, command, deployment, or inspection is described as completed unless
  the evidence says it completed.
- Specificity comes from the user, repository, or observed result rather than
  from plausible invention.
- A useful caveat or minority case was not removed merely because it made the
  answer less tidy.

If the original already passes these checks and fits its reader, leave it alone.
The presence of a familiar word or punctuation mark is not a reason to edit.

## Run a residue pass

Read the final version once as the intended recipient:

- Does the first sentence deliver the current result, cause, blocker, or
  decision?
- Does each contrast correspond to a belief or option that is actually in play?
- Does the rhythm follow the content, or can the list and paragraph shapes be
  predicted before reading them?
- Does an emphatic sentence add a consequence, or merely ask the reader to feel
  the previous sentence more strongly?
- Are importance and quality claims supported by concrete behavior or evidence?
- Does the last sentence complete the answer, or repeat it and reopen a finished
  conversation?

Fix the underlying passage once. Do not keep cycling through synonyms or
reformatting a message that already says the right thing clearly.
