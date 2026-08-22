
# The Validation · FinWise

> Module 5 · Experimentation Methods. The experiment brief that tests whether repeated financial value can become a habit.

## Method

### Standard A/B test

Eligible FinWise trial accounts will be randomly assigned to:

**Control**  
After receiving their first meaningful financial insight, users continue with the existing FinWise experience. There is no structured weekly financial check-in.

**Treatment**  
After reaching their first Aha moment, users receive a Weekly Financial Check-In when FinWise has a fresh, decision-worthy financial insight available.

### Why A/B

A standard A/B test gives the cleanest causal signal for this hypothesis because:

- users can be randomized at the account level
- there is one clearly defined product change
- the treatment and control experiences can run simultaneously
- the goal is learning whether the check-in causes repeat financial review, not dynamically optimizing multiple variants

I would not use a Multi-Armed Bandit, Geo Test, or Switchback because those methods solve constraints that are not present in this experiment.

A longer-term Holdout could be useful later to test whether the behavior ultimately improves retention and revenue.

---

## Hypothesis + primary metric

### Experiment name

**Weekly Financial Check-In Activation Test**

### Objective

Increase the percentage of activated FinWise trial users who return and experience meaningful financial value again after their first Aha moment.

### Hypothesis

> **If FinWise shows Aha-complete trial users a Weekly Financial Check-In when a new meaningful financial insight is ready, then the 7-Day Repeat Financial Review Rate will increase because users have a clear reason to return and experience FinWise's value again.**

### Primary metric

**7-Day Repeat Financial Review Rate**

Defined as:

> The percentage of trial accounts that receive their first meaningful insight and then return within 7 days to review a second fresh, decision-worthy financial insight.

### Success threshold

**≥15% relative lift versus control**

Example:

If the control group has a 40% repeat-review rate, treatment would need to reach at least 46%.

The 15% threshold is an experiment-design target, not an observed result from the existing FinWise dataset.

---

## What we're testing

### Current experience

After users connect financial data and receive their first personalized insight, FinWise does not provide a structured reason to return on a natural cadence.

### Single change

Treatment users receive:

> **Your weekly financial check-in is ready.**  
> We found a change worth reviewing.  
> **Review this week's insight →**

After reviewing the insight, the user can see progress in their Financial Review Momentum / Cash Safety Buffer.

A check-in only counts when the user reviews a real new financial insight. Simply opening the app does not count.

### Target segment

Trial accounts that:

- connected financial data
- received their first meaningful insight
- have not yet converted to paid

Users who have not reached the Aha moment are excluded because their problem is activation, not repeat engagement.

---

## Guardrail + read date

### Guardrail

**Weekly check-in notification opt-out / dismissal rate must not increase by more than 5% relative to control.**

This protects against creating artificial engagement through notification fatigue.

I would also monitor low-value / irrelevant insight feedback as a secondary diagnostic.

### Read rule

**Minimum run time: 14 days**

Do not make a decision before the planned read point.

The final read should occur only after:

- the minimum two-week window has completed
- the required sample size has been reached
- treatment and control exposure remain balanced
- no major colliding experiment compromised the surface

No interim peeking or early shipping based on an initial spike.

---

## Predicted outcome

If the hypothesis is correct, treatment users will show at least a **15% relative increase in 7-Day Repeat Financial Review Rate** without materially increasing notification opt-outs or dismissals.

### If successful

Roll out the Weekly Financial Check-In incrementally and then use a longer-term holdout to test whether repeated review also improves:

- trial-to-paid conversion
- 30/90-day retention
- one-year retention

### If unsuccessful

Do not immediately conclude that repeat financial review is the wrong behavior.

Investigate whether:

- the new insights were valuable enough
- weekly is the correct cadence
- users noticed the trigger
- the check-in created notification fatigue
- the real constraint still occurs before the first Aha moment

Then iterate or stop the mechanic based on the evidence.

---

## Decision rule

**Ship:** Primary metric clears the success threshold and guardrails remain healthy.

**Iterate:** Positive movement, but below the threshold.

**Investigate:** Primary metric improves but a guardrail degrades.

**Stop:** No meaningful improvement after the planned read.
