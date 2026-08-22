[FinWise Signal Diagnosis Dashboard.html](https://github.com/user-attachments/files/31339071/FinWise.Signal.Diagnosis.Dashboard.html)# The Signals · FinWise

> Module 4 · Data & Analytics. The data patterns, metrics priority, and signals that sharpen the FinWise growth hypothesis.

## North Star

**Trial users who import financial data and reach their first modeling output**

This is the clearest observable behavior in the provided dataset that represents a trial user progressing toward FinWise's core value.

---

## The data pattern

The strongest pattern in the 13-month dataset is a **conversion ceiling**.

Trial-to-paid conversion remains tightly clustered around **~2%**, with monthly conversion ranging only from approximately **1.87% to 2.08%**.

This is notable because the upstream product-usage metrics move much more dramatically:

- Financial Modeling Usage ranges from **10.78% to 58.26%**
- Import Feature Usage ranges from **30.51% to 45.42%**
- Average Session Duration falls from a high of **14.26 min** to **5.14 min** before partially recovering
- Sessions per User falls from **9 to 3**, then later recovers to **9**

Despite those movements, trial-to-paid conversion barely changes.

### Signal diagnosis

| Metric | Observed pattern | What I see |
|---|---|---|
| Trial-to-Paid Conversion | **Ceiling** | Conversion remains around 2% throughout the 13 months. |
| Financial Modeling Usage | **Volatile / no clean pattern** | Usage moves sharply up and down, including 58.06% → 36.04% from Sep to Oct. |
| Import Feature Usage | **Recovery into a ceiling** | Usage recovers from ~30% but appears to settle in the low-to-mid 40% range. |
| Avg Session Duration | **Slow leak + partial recovery** | Falls from 14.26 min in Mar to 5.14 min in Aug, then partially recovers. |
| Sessions per User | **Recovery / no clean pattern** | Falls from 9 to 3, then recovers back to 9. |

The important takeaway is that I should not force every metric into a Cliff, Slow Leak, or Ceiling if the data does not fit cleanly.

---

## Leading indicators

### 1. Get Started Import Feature Usage %

Importing financial data is the prerequisite for FinWise to generate personalized financial insights.

If users do not complete this step, they cannot reach the Aha moment.

### 2. Financial Modeling Feature Usage %

This measures whether users move beyond setup and engage with the analysis behavior closest to FinWise's current observable North Star.

However, the 13-month aggregate data shows only a **weak relationship** between Financial Modeling Usage and Trial-to-Paid Conversion.

That means generic feature usage alone is not precise enough to use as the final activation signal.

---

## Correlation check

At the monthly aggregate level:

**Financial Modeling Usage vs. Trial-to-Paid Conversion**

**Pearson r ≈ +0.25**

This is only a weak positive relationship.

Financial Modeling Usage changes significantly while conversion remains around 2%.

Therefore:

> **Correlation does not provide strong evidence that increasing generic modeling usage alone will materially increase conversion.**

The monthly aggregate dataset also cannot tell whether the same users who import data, review insights, return, collaborate, and ultimately convert.

---

## Lagging indicators

### Trial-to-Paid Conversion Rate

This is the primary lagging business result.

If activation and repeat value improve meaningfully, trial-to-paid conversion should eventually move beyond its current ~2% ceiling.

### One-Year Paid Retention

FinWise retains approximately **40% of paid customers after one year**.

Retention is the longer-term proof that users continue receiving enough value to stay, not simply that they converted once.

---

## Updated hypothesis

The data changed my original thinking.

I initially focused heavily on collaboration as a possible retention and conversion lever.

The Module 4 analysis suggests that **generic feature usage and collaboration should not yet be treated as proven causes of conversion**.

The more precise hypothesis to test is:

> **If FinWise helps users who reached their first Aha moment return within 7 days and experience another meaningful financial insight, repeat engagement and ultimately trial-to-paid conversion should improve because users begin experiencing FinWise as an ongoing financial decision tool rather than a one-time dashboard.**

The next instrumentation should therefore track the exact activation sequence:

`data_import_completed`
→ `meaningful_insight_generated`
→ `insight_reviewed`
→ `second_review_within_7d`
→ `trial_converted`

Collaboration should be measured separately:

`insight_shared_or_invite_sent`
→ `invite_accepted`
→ `collaborator_active`
→ `account_retained`

---

## Dashboard



<img width="1273" height="733" alt="Screenshot 2026-08-22 at 12 51 33 PM" src="https://github.com/user-attachments/assets/2d598572-5f23-4b7a-aee9-2ef89dcbfe88" />
<img width="1273" height="794" alt="Screenshot 2026-08-22 at 12 51 41 PM" src="https://github.com/user-attachments/assets/28ec52f0-5279-4dcf-97c8-eab4b0026143" />
<img width="1273" height="674" alt="Screenshot 2026-08-22 at 12 51 47 PM" src="https://github.com/user-attachments/assets/75faf7ff-847b-4b58-b72e-b7cc155e424a" />
<img width="1273" height="794" alt="Screenshot 2026-08-22 at 12 51 41 PM" src="https://github.com/user-attachments/assets/bf0fb4bb-06b6-4128-a4ec-f95bb366e3a6" />

The dashboard visualizes all five required 13-month trends and compares the chosen leading indicator with Trial-to-Paid Conversion.

---

## Key takeaway

**The clearest signal is not that users need more features. It is that conversion remains stuck near 2% even while upstream behaviors move substantially.**

The next experiment should therefore focus on a more precise activation behavior — reaching and repeating the Aha moment — before assuming that generic engagement, collaboration, acquisition, or pricing is the primary lever.
