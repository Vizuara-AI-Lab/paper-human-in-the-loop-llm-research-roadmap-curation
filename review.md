# Peer Review: A Human-in-the-Loop LLM Workflow for Research Roadmap Curation

**Reviewer:** balanced / deep
**Recommendation:** accept
**Confidence:** 3
**Score:** 8

## Summary of contributions

The paper introduces a workflow that pairs schema-constrained LLM generation with a first-class human review-and-revision step for converting raw research ideas into executable research roadmaps. The schema is a fixed twelve-component checklist organized into scoping, methodology, and execution families; the prototype is an asynchronous job queue with a dedicated `revision_requested` state. The empirical contribution is a blind preference study (n=40 evaluators, four anonymized roadmap variants for one shared research idea), in which 34 of 40 evaluators (85%) selected the workflow's roadmap over three unstructured ChatGPT baselines.

## Strengths

1. **Honest, narrowly scoped framing.** The paper is explicit that it is not pitching autonomous science. Throughout, the LLM is positioned as a planning assistant with a human kept accountable for feasibility, novelty, and correctness. That scope discipline holds from abstract to conclusion.
2. **The headline number is well-grounded and visually anchored.** Figure 5 and Table 1 both report 34/85% versus 6/15%, the abstract restates the numbers without drift, and the binomial test against $p_0=0.25$ is the right test for the design.
3. **Limitations section is unusually self-critical.** The paper now explicitly owns the single-idea design (Seventh limitation), the bootcamp-skewed cohort, the fixed label order, and the lower granularity of free-text answers. That level of self-criticism builds reviewer trust.
4. **Method section earns its space.** The `revision_requested` state machine (Figure 3) is a small but real systems contribution. Treating revision as a typed state, separate from `processing`, is a useful crystallization of "human-in-the-loop" that is worth borrowing in other LLM-workflow systems.
5. **Related-work section now properly situates the schema.** The "Existing structured-planning artifacts" paragraph correctly identifies that mentor checklists, NeurIPS reproducibility programs, and project-management templates already encode many of the same components, and frames the contribution as binding the schema to a generation backend with an explicit revision loop rather than inventing the schema from scratch.

## Weaknesses

1. **Per-dimension breakdown is the most natural follow-up (severity: low).** The current draft reports only the overall preference because the survey instrument did not separately retain per-dimension counts at the same granularity. The paper acknowledges this. A revised survey, with the same instrument and the same blind protocol, would let the paper claim five testable winners instead of one, and the n=40 design has the headroom to do so.
2. **Three ChatGPT versions used for variants A, B, D are not named in the PDF (severity: low).** Variants are described as "three different unmodified ChatGPT versions", but the version identifiers, temperature settings, and date of generation do not appear in Section 4.1. A small footnote with model versions and sampling settings would meaningfully improve reproducibility.
3. **No discussion of how variant C's reference templates were assembled (severity: low).** Section 3.2 explains what reference templates are but does not say how the templates used in the study were chosen, who curated them, or how many were shown to the LLM at generation time. This is relevant because the n_idea=1 limitation interacts directly with template provenance.

## Specific comments

- **Section 3.1, page 4, Figure 1 caption:** the caption explains the orange dashed arrow but does not enumerate the five stages. Mentioning "Idea Submission, Structured Generation, Artifact Creation, Human Review, Delivery" in caption order would let the figure stand on its own.
- **Section 3.2, page 5, Figure 2:** the twelve components in the figure match the prose count exactly (4 scoping + 5 methodology + 3 execution = 12). Good.
- **Section 4.1, page 7:** the paper now explicitly notes that label-to-variant mapping was held fixed across evaluators rather than randomized, and Section 7 calls this out as a limitation. Good.
- **Section 5, Table 1, page 10:** the combined "6 combined (15%)" cell is a faithful reflection of what the survey actually captured. The footnote in the caption is exactly the right disclosure.
- **Section 7, Seventh limitation:** the n_idea=1 paragraph correctly identifies this as the most consequential limitation. Strong.
- **References, pages 12–14:** numbered citation list rendered cleanly; ReAct artifact from the previous draft is gone.

## Recommendation justification

The paper is honest, narrowly scoped, and reports a real number against a real baseline; the writing flow is clean and the figures earn their column space. The previous round's three material concerns (n_idea=1 not owned, an unsupported per-dimension claim, and a missing-citation typeset artifact) have all been addressed in the current draft, and the related-work section now properly situates the schema against existing planning artifacts rather than treating it as a green field. What remains are minor reproducibility-style improvements (named ChatGPT versions, template provenance, per-dimension counts) that are appropriate for camera-ready rather than blocking issues. I recommend acceptance at a workshop or workshop-style venue on LLMs for research, education, or HCI; the contribution is small but the reporting is solid and the system idea (the typed `revision_requested` state) is reusable beyond this specific application.

## Minor issues

- "ChatGPT" is used as a proper noun without naming the version, temperature, or sampling settings; a footnote would make the design fully reproducible.
- Section 3.2 states reference templates "ship with the workflow" but does not say how many or how they were curated for the study. One sentence on template provenance would strengthen the n_idea=1 discussion in Section 7.
- The discussion of operational metrics in the existing draft promises generation time, time-to-approval, and approval rate but the current PDF reports only the preference outcome. If those operational logs exist, a one-paragraph appendix would tighten the systems contribution.
