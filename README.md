# Beneath the Policy: Hidden Inductive Biases in Robot Learning

### Toward a full-stack science of learnable robot systems

**Type:** Half-day workshop
**Venue:** CoRL 2026, JW Marriott Austin, November 9, 2026
**Tentative website:** beneath-the-policy.github.io

---

## Organizers

- **Younghyo Park**, MIT CSAIL (lead contact, will attend in person)
<!-- - **[Industry collaborator, e.g. Elie Aljalbout, NVIDIA]** -->
- **[Senior anchor, e.g. Pulkit Agrawal, MIT]**

---

## 1. Motivation and Open Challenges

Modern robot learning pipelines are stacks of design choices: embodiments and kinematics, motor and actuator dynamics, action space parameterizations, reset and demonstration distributions, observation modalities, reward shaping, simulation contact and integration parameters, control frequencies, controller gains, and other low-level controller settings. Each is typically picked by convention, copied from prior code, or tuned silently. Yet recent results suggest that these "hidden" choices act as powerful inductive biases that shape what policies can learn, how well they transfer, and which algorithms appear to win.

These choices show up at many levels of the stack. A motor-level setting, transmission choice, controller-gain default, or embodiment geometry can make one behavior easy and another unreachable; an action-space parameterization can silently determine what exploration is possible; a demonstration interface can filter which behaviors ever enter the dataset; a reset distribution can decide what counts as generalization; a simulator contact model or integration scheme can make some contact-rich strategies discoverable and others invisible. None of these are merely implementation details. They are *learning-interface* parameters: part of the experimental substrate that determines what policies can learn.

If true generally, this changes how the field should do science. Benchmarks comparing two algorithms while holding a hidden bias fixed are not really comparing algorithms. Architecture innovations may be re-discovering the effect of an unreported interface choice. We do not yet have a vocabulary, a methodology, or a community norm for studying the substrate beneath the policy.

This workshop targets four concrete open challenges:

1. **Identification.** What are the load-bearing hidden design choices in current robot learning pipelines, and how do we even measure them? Many are undocumented or buried in vendor defaults.
2. **Interaction.** How do these choices compose? Are motor dynamics, embodiment geometry, controller gains, action spaces, control rates, and demonstration interfaces independent knobs, or do they interact in ways that make any single-axis study misleading?
3. **Methodology.** What does a rigorous experiment look like in this space? Factorial designs, scaling-style ablations, and "model organism" task selection are all candidates, but the field has no shared template.
4. **Reporting.** What should papers be required to report so that results are reproducible and comparable? Can we converge on a community checklist of design choices, analogous to model cards or datasheets?

We deliberately scope away from generic themes like "robot manipulation" or "foundation models." The workshop is about the substrate that those headline results sit on.

### Relation to Prior Workshops

CoRL has hosted two workshops adjacent to this theme. The 2022 "Geometry, Physics, and Human Knowledge as Inductive Bias in Robot Learning" workshop addressed inductive bias as a positive design tool: priors a researcher chooses to add. The 2024 "Advancing Robot Skills" workshop included environment design among nine topic areas in a broad best-practices survey. Neither centered the methodological question of how the field should identify, measure, and report hidden design choices that already shape every published result. In the broader ML community, *Implementation Matters in Deep RL* (Engstrom et al. 2020), *What Matters in On-Policy RL* (Andrychowicz et al. 2020), and *Empirical Design in Reinforcement Learning* (Patterson et al. 2024) are evidence that the same reckoning is overdue in robot learning, where the substrate (hardware, controllers, simulators, teleop interfaces) is richer and the hidden-bias surface is larger.

## 2. Why Now

Three trends make this workshop timely:

- **Scale exposes the substrate.** Large datasets like DROID and Open X-Embodiment mix data from heterogeneous hardware, embodiments, controllers, action spaces, and teleop interfaces, often without documentation. Practitioners are discovering that "data quantity" hides large variance in implicit interfaces.
- **Reproducibility crises.** Several recent results in manipulation and locomotion have failed to replicate across labs, with post-hoc diagnosis pointing to hardware or interface settings, reset distributions, or simulator versions rather than algorithmic differences.
- **The methodology gap.** Empirical robot learning lacks the experimental scaffolding of adjacent fields (factorial design from biology, scaling laws from LLMs, model-organism choice from neuroscience). The community is ready for a serious conversation on how to do science here.

## 3. Format

The half-day is organized around four invited talks, a poster session, and a moderated panel. Speakers are asked to attend the full session so they can take part in the panel and engage with contributed work. Exact placement will depend on whether CoRL assigns the workshop to the morning or afternoon block.

**Morning schedule**

| Time | Session |
|---|---|
| 8:30-8:40 | **Opening framing.** Organizers introduce the four open challenges and the reporting-artifact goal. |
| 8:40-9:10 | **Speaker 1.** Invited talk. |
| 9:10-9:40 | **Speaker 2.** Invited talk. |
| 9:40-10:10 | **Speaker 3.** Invited talk. |
| 10:10-10:30 | **Lightning previews.** Short contributed-paper previews and poster setup before the conference coffee break. |
| 10:30-11:00 | **Coffee break and posters.** Accepted papers are presented as posters during the conference coffee break. |
| 11:00-11:30 | **Speaker 4.** Invited talk. |
| 11:30-12:10 | **Panel discussion.** Speakers and contributed-paper authors discuss what papers should report and how the field should study the substrate, with time for audience discussion. |
| 12:10-12:30 | **Closing synthesis.** Themes from talks, posters, and panel; checklist takeaways and pointers to the post-workshop artifact. |

**Afternoon schedule**

| Time | Session |
|---|---|
| 2:00-2:10 | **Opening framing.** Organizers introduce the four open challenges and the reporting-artifact goal. |
| 2:10-2:40 | **Speaker 1.** Invited talk. |
| 2:40-3:10 | **Speaker 2.** Invited talk. |
| 3:10-3:30 | **Lightning previews.** Short contributed-paper previews and poster setup before the conference coffee break. |
| 3:30-4:00 | **Coffee break and posters.** Accepted papers are presented as posters during the conference coffee break. |
| 4:00-4:30 | **Speaker 3.** Invited talk. |
| 4:30-5:00 | **Speaker 4.** Invited talk. |
| 5:00-5:40 | **Panel discussion.** Speakers and contributed-paper authors discuss what papers should report and how the field should study the substrate, with time for audience discussion. |
| 5:40-6:00 | **Closing synthesis.** Themes from talks, posters, and panel; checklist takeaways and pointers to the post-workshop artifact. |

The poster session and panel ensure the day is not a back-to-back talk schedule: every attendee has structured time to engage authors directly and to shape the panel agenda.

## 4. Invited Speakers

We will invite 4 speakers to keep the session focused, per CoRL 2026 guidance. The list below is illustrative and balances seniority, gender, geography, institution type, and sub-area. We will also coordinate to avoid overlap with the speaker pool of recent adjacent CoRL workshops.

1. **[Senior academic, simulation and contact dynamics, e.g. Karen Liu, Stanford].** Brings expertise on how simulator integration, contact models, and embodiment choices act as biases in learned policies. Female, senior, US academia.
2. **[Early-career researcher, demonstration interfaces, e.g. Cheng Chi, Stanford / TRI].** Author of work on UMI and demonstration-interface design, directly relevant to the "data collection as inductive bias" axis. Early career, US.
3. **[European researcher, control and learning interface, e.g. Roberto Calandra, TU Dresden].** Bridges hardware-aware control and learning, well positioned to speak to actuation, embodiment, and action-space choices. Geographic diversity, mid-career.
4. **[Industry researcher, female, e.g. Aleksandra Faust, Google DeepMind, or Ankur Handa, NVIDIA].** Brings the industry view: what does production-scale robot learning reveal about which substrate choices matter most? Industry diversity.

We will additionally line up 2 to 3 confirmed discussants (postdocs and senior PhD students from underrepresented backgrounds) to anchor the response slots in Block A and moderate the carousel in Block B. Discussants are an explicit pipeline for diversifying the speaking voices in a 4-speaker format.

All invitations will include the CoRL 2026 two-workshop limit and a request to commit to full-session attendance, framed as essential to the format (their participation in the carousel and breakout is integral, not optional).

## 5. Contributed Papers

**Call.** We will solicit 4-page (excluding references) contributed papers on any axis of hidden inductive bias in robot learning. Examples of in-scope contributions:

- Empirical studies isolating a single design choice (motor dynamics, transmission or compliance, embodiment and kinematics, controller gains or other controller settings, action space, reward, reset distribution, demo interface, sim contact model) and characterizing its effect on learning.
- Factorial or scaling-style studies that vary multiple choices.
- Negative or surprising results where a design choice changed a published conclusion.
- Methodology papers proposing new experimental designs, metrics, or reporting conventions.
- Tools, benchmarks, or datasets that expose or normalize hidden choices.

**Exclusions.** Per CoRL 2026 policy, papers already accepted to the main CoRL 2026 conference are not eligible. Concurrent submissions to other venues are permitted if disclosed.

**Review.** Double-blind, 2 to 3 reviewers per paper, drawn from a program committee of approximately 20 researchers we will recruit across the four design axes. We will use OpenReview. Acceptance criteria emphasize *what the paper teaches us about the substrate*, not state-of-the-art numbers. Best paper and best negative-result awards.

**Format.** All accepted papers receive a poster slot in the poster session; a small subset of authors will be invited to join the panel discussion as anchor voices alongside the invited speakers.

## 6. Workshop Artifact

We commit to producing a **Design Choice Reporting Checklist v0.1** as the workshop artifact, synthesized by the organizers from the invited talks, contributed papers, and panel discussion. The checklist will be structured per design axis (hardware and embodiment, motors and actuation, kinematics, controller gains and control rates, action spaces, observations, demos, sim, reward, reset) with the goal of being adoptable by reviewers and authors at CoRL 2027. We will circulate a draft to invited speakers and contributed-paper authors for comment before public release.

In addition, we will write a short whitepaper summarizing the open challenges, the leading candidate methodologies discussed, and an organized agenda for community follow-up. Both artifacts will be released openly via the workshop website.

## 7. Diversity Plan

- **Speakers:** Of 4 invited speakers, target at least 2 women or non-binary researchers, at least 1 outside North America, at least 1 from industry, and a mix of career stages (no more than 2 full professors).
- **Discussants and PC:** Discussants and program committee members are an explicit second tier for amplifying underrepresented voices. Target at least 50% women and non-binary representation across discussants.
- **Attendees:** Travel support requests will be flagged in the contributed-paper submission form; if any DEI funds are available through CoRL, we will prioritize first-time CoRL attendees and students from underrepresented institutions.
- **Format:** The carousel and breakout structure is itself a diversity lever: it gives many more people a substantive speaking role than a traditional talk-driven workshop.

## 8. Confirmations

- At least one organizer (Younghyo Park) will attend CoRL 2026 in person.
- Organizers will attend the CoRL 2026 workshop organizers meeting.
- We are willing to discuss merger with overlapping proposals if the chairs identify any.

## 9. Special Requirements

- Standard half-day room with poster space for the carousel block (approximately 8 to 10 poster boards).
- Microphones for breakout moderation.
- A shared writable document (e.g., HackMD or Google Doc) projected during Block C for live checklist drafting.
