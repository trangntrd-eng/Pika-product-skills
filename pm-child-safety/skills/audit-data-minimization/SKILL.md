---
name: audit-data-minimization
description: "Audit and redesign data collection practices to collect the minimum necessary data from children. Use when preparing for compliance review, reducing privacy risk, or simplifying data architecture — ensuring every data point collected from a child has a clear, documented purpose."
---

## Audit Data Minimization for Children

Data minimization is not just a compliance checkbox — it's a design philosophy. Every data point you collect from a child is a liability: storage cost, breach risk, regulatory exposure, and parent trust erosion. This skill systematically evaluates whether each piece of data is truly necessary and proposes alternatives that achieve the same product goals with less data.

### Domain Context

**Data minimization principle** appears in every major children's privacy regulation:
- **COPPA:** "An operator may collect no more personal information than is reasonably necessary for the child to participate in a game, contest, or other activity."
- **GDPR Article 5(1)(c):** Data must be "adequate, relevant and limited to what is necessary."
- **UK AADC Standard 4:** "Only collect and retain the minimum amount of personal data you need."

**The minimization hierarchy** (from most to least preferred):
1. **Don't collect** — Can the feature work without this data at all?
2. **Derive instead of collect** — Can you infer what you need from data you already have?
3. **Aggregate instead of individualize** — Do you need per-child data, or will cohort-level suffice?
4. **Anonymize** — Can you strip identifying information and still get value?
5. **Pseudonymize** — Replace identifiers with tokens (reversible, but limits exposure)
6. **Collect with limits** — If you must collect, set retention limits and access controls

### Context

You are auditing data minimization practices for **$ARGUMENTS**.

### Instructions

1. **Inventory All Data Collected from Children**

   Create an exhaustive inventory. Don't forget implicit data collection (SDK telemetry, crash reports, device fingerprints):

   | # | Data Point | Source | Purpose | Retention | Who Accesses |
   |---|-----------|--------|---------|-----------|-------------|
   | 1 | First name | Registration | Personalization | Account lifetime | App, parent dashboard |
   | 2 | Birth date | Registration | Age gating, content selection | Account lifetime | Age logic only |
   | 3 | Voice recordings | Voice feature | Speech recognition | [check] | Speech API |
   | 4 | Photos | Camera feature | Photo-to-lesson | [check] | Vision API |
   | 5 | Learning progress | Auto-collected | Adaptive path, parent reports | Account lifetime | App, parent, analytics |
   | 6 | Device ID | SDK auto-collect | Analytics, crash reporting | [check] | Firebase/analytics |
   | 7 | IP address | Server logs | Security, geo | [check] | Infrastructure |
   | ... | ... | ... | ... | ... | ... |

2. **Apply the Necessity Test to Each Data Point**

   For each row, answer:

   **Q1: Can the feature work without this data?**
   - If yes → **Eliminate**. Delete collection, update privacy notice.
   - If no → Continue to Q2.

   **Q2: Can you achieve the same purpose with less identifying data?**
   - Name → First name only? Nickname chosen by child? No name (use avatar)?
   - Birth date → Age range (6-8) instead of exact date?
   - Location → Country-level only? No location at all?
   - Voice → Process on-device, never send to server? Delete after transcription?
   - Photos → Process on-device, never store? Store processed output only, not raw image?
   - Device ID → Use a rotating, non-persistent identifier?
   - If alternatives exist → **Substitute**. Implement the less-identifying alternative.
   - If no alternatives → Continue to Q3.

   **Q3: Can you minimize retention?**
   - Learning data → Aggregate after 30 days, keep only summary stats?
   - Voice/photos → Delete immediately after processing?
   - Server logs → Auto-purge after 7 days?
   - Set explicit retention periods for everything. Default should be shortest viable.

   **Q4: Can you limit access?**
   - Does the analytics team really need individual child data, or will anonymized cohorts suffice?
   - Can third-party services operate on anonymized data?
   - Implement technical access controls (encryption at rest, role-based access).

3. **Audit Third-Party SDKs and Services**

   Third-party code is the most common source of unintentional over-collection:

   | SDK/Service | Data It Collects | Purpose | Configured for Kids? | Alternative |
   |------------|-----------------|---------|---------------------|-------------|
   | Firebase Analytics | Device ID, events, crashes | Analytics | ⚠️ Must enable "child-directed" flag | First-party analytics |
   | Google AdMob | AAID, location | Ads | ❌ Prohibited in kids apps | Remove entirely |
   | Facebook SDK | Device ID, app events | Attribution | ❌ Prohibited in kids apps | Remove entirely |
   | Crashlytics | Device info, crash logs | Debugging | ⚠️ Configure to minimize | [check settings] |
   | [Speech API] | Audio recordings | Voice features | [check data handling] | On-device processing |

   **Action:** For each SDK, either configure for child-directed use, replace with a child-safe alternative, or remove.

4. **Design the Data Lifecycle**

   For every data type that survives the necessity test, define the full lifecycle:

   ```
   Collection → Processing → Storage → Access → Retention → Deletion
   ```

   | Data Point | Collection Trigger | Processing | Storage Location | Access Controls | Retention Period | Deletion Method |
   |-----------|-------------------|-----------|-----------------|----------------|-----------------|----------------|
   | [data] | [when/how] | [on-device/server] | [where] | [who can access] | [how long] | [auto-delete/manual] |

5. **Generate Minimization Recommendations**

   Prioritize by risk reduction:

   | Priority | Current Practice | Recommended Change | Risk Reduction | Effort |
   |----------|-----------------|-------------------|---------------|--------|
   | P0 | [high-risk practice] | [change] | [impact] | [effort] |
   | P1 | ... | ... | ... | ... |

### Output Format

```markdown
# Data Minimization Audit: [Product Name]

## Data Inventory
[Full table from Step 1]

## Necessity Assessment
| # | Data Point | Necessary? | Alternative | Action | New Retention |
|---|-----------|-----------|-------------|--------|---------------|
| [#] | [data] | [yes/no/partial] | [less-identifying option] | [eliminate/substitute/limit] | [period] |

## Third-Party SDK Audit
[Table from Step 3]

## Data Lifecycle Design
[Table from Step 4]

## Recommendations (Prioritized)
[Table from Step 5]

## Compliance Impact
- Data points eliminated: [count]
- Data points reduced: [count]
- Third-party services removed/reconfigured: [count]
- New retention limits set: [count]
- Estimated risk reduction: [qualitative assessment]
```

Save as `data-minimization-audit-[product-name].md`.

### Further Reading
- FTC. "Children's Online Privacy Protection Rule: A Six-Step Compliance Plan."
- ICO (UK). "Age Appropriate Design Code — Standard 4: Data Minimisation."
- NIST Privacy Framework. "Data Processing Management."
- Zuboff, S. (2019). *The Age of Surveillance Capitalism*. Public Affairs. (Context for why data minimization matters)
