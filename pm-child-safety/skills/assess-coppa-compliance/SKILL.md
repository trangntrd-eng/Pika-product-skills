---
name: assess-coppa-compliance
description: "Audit an EdTech product against COPPA (US), GDPR-K (EU), and Vietnam's Cybersecurity Law requirements for children's data. Use when launching a new feature, entering a new market, or preparing for app store review to ensure compliance with children's privacy regulations."
---

## Assess COPPA & Children's Privacy Compliance

Children's privacy law is the single highest-stakes compliance area for EdTech. Violations carry fines up to $50,000+ per incident (FTC), app store removal, and catastrophic parent trust damage. This skill produces a compliance audit against the three regulatory frameworks most relevant to B2C EdTech products.

### Domain Context

**Three regulatory frameworks for children's EdTech:**

**1. COPPA — Children's Online Privacy Protection Act (US, FTC)**
- Applies to: Children under 13 in the US
- Core requirements: Verifiable parental consent before collecting personal information from children. Direct notice to parents. Right to review/delete. Data minimization. Reasonable security.
- Enforced by: FTC. Recent enforcement trend: aggressive, with fines in the millions (Epic Games $275M, Google/YouTube $170M).
- App Store impact: Apple and Google both require COPPA compliance declarations.

**2. GDPR-K — General Data Protection Regulation, Article 8 (EU)**
- Applies to: Children under 16 (or as low as 13 depending on member state) in the EU
- Core requirements: Parental consent for data processing. Privacy notices in child-friendly language. Data Protection Impact Assessment (DPIA). Right to erasure. Privacy by design.
- Enforced by: National Data Protection Authorities. Fines up to 4% of global annual revenue.

**3. Vietnam's Cybersecurity Law & PDPD (Personal Data Protection Decree, 2023)**
- Applies to: Children under 16 in Vietnam (the decree classifies children's data as "sensitive personal data")
- Core requirements: Consent from parent/guardian for processing children's data. Purpose limitation. Data stored on servers in Vietnam (localization requirement). Impact assessment for sensitive data.
- Enforced by: Ministry of Public Security. Evolving enforcement.

**Additional frameworks to consider:**
- **AADC (UK Age-Appropriate Design Code)** — 15 standards for services likely accessed by children. Not technically law but enforced by ICO.
- **Apple App Store Guidelines (Section 1.3, Kids Category)** — No third-party analytics, no ads, no links out. Very strict.
- **Google Play Families Policy** — Similar to Apple. Requires teacher-approved content for education apps.

### Context

You are auditing compliance for **$ARGUMENTS**.

### Instructions

1. **Determine Regulatory Scope**

   Based on the product's market and target age:

   | Factor | Your Product |
   |--------|-------------|
   | Target age range | [must specify] |
   | Markets served | [US / EU / Vietnam / other] |
   | Platform | [iOS / Android / Web / Robot / Multi] |
   | Data subjects | [children only / children + parents / family accounts] |

   **Which regulations apply:**
   - US market + under 13 → COPPA required
   - EU market + under 16 → GDPR Article 8 required
   - Vietnam market + under 16 → PDPD child data rules required
   - iOS Kids Category → Apple 1.3 guidelines required
   - All of the above? → Must meet the strictest standard across all

2. **Audit Data Collection Practices**

   Inventory EVERY piece of data the product collects from or about children:

   | Data Type | Collection Method | Purpose | Necessary? | Shared With? |
   |-----------|------------------|---------|-----------|-------------|
   | Name | Registration form | Personalization | Needed — but first name only? | None |
   | Age/DOB | Registration | Age gating, content selection | Yes (required for compliance) | None |
   | Voice recordings | In-app voice feature | Speech recognition | [assess] | [check processors] |
   | Photos | Camera feature | Photo-to-lesson | [assess] | [check processors] |
   | Location | Device permissions | [why?] | Probably not | [check] |
   | Usage data | Auto-collected | Analytics, personalization | Minimize | [check analytics tools] |
   | Learning progress | Auto-collected | Pedagogy, parent reports | Yes | Parents |
   | Device identifiers | Auto-collected | Analytics, crash reports | Minimize | [check SDKs] |

   **Red flags to check:**
   - Third-party SDKs that collect data independently (analytics, crash reporting, ad networks)
   - Persistent identifiers that enable cross-app tracking
   - Biometric data (voice prints, face recognition) — requires heightened scrutiny
   - Any data collection without clear, documented purpose
   - Data retained beyond stated purpose

3. **Assess Parental Consent Mechanism**

   COPPA requires "verifiable" parental consent. Evaluate current mechanism:

   | Method | COPPA Acceptability | Strength | Notes |
   |--------|-------------------|----------|-------|
   | Email to parent (click link) | ✅ Acceptable for internal use | Low | "Email plus" — adequate if not sharing data |
   | Credit card verification | ✅ Strong | High | Small charge as verification |
   | Government ID upload | ✅ Strong | High | Privacy concerns with storing ID |
   | Knowledge-based Q&A | ⚠️ Weak | Low | FTC has questioned this method |
   | Checkbox "I am a parent" | ❌ Not acceptable | None | Too easy for child to bypass |
   | Phone call to parent | ✅ Strong | High | Doesn't scale well |
   | In-app purchase verification | ✅ Acceptable | Medium | Leverages app store authentication |

   **Evaluate:**
   - Is consent collected BEFORE any data collection begins?
   - Can parents revoke consent? How?
   - Is the consent mechanism age-gated (child can't pretend to be parent)?

4. **Assess Privacy Notice**

   Must be provided to parents BEFORE consent. Check:
   - [ ] Written in plain language (not legal jargon)
   - [ ] Lists ALL data collected from children
   - [ ] Explains purpose for each data type
   - [ ] Identifies all third parties who receive children's data
   - [ ] States data retention periods
   - [ ] Explains how to review child's data
   - [ ] Explains how to request deletion
   - [ ] Provides direct contact for privacy questions
   - [ ] Translated into all supported languages
   - [ ] For GDPR: includes child-friendly version for the child themselves

5. **Assess Data Minimization**

   For each data point collected, ask:
   - Can the feature work without this data? If yes → don't collect it.
   - Can we use a less identifying alternative? (e.g., age range instead of DOB, first name instead of full name)
   - Is data deleted when no longer needed for stated purpose?
   - Is data anonymized for analytics? (Aggregate, don't track individual children)

6. **Assess Third-Party Services**

   Inventory all third-party services that process children's data:

   | Service | Purpose | Data Accessed | COPPA Compliant? | Contract in Place? |
   |---------|---------|--------------|-----------------|-------------------|
   | Firebase Analytics | Usage analytics | Device ID, events | ⚠️ Must configure | [check] |
   | AWS S3 | Storage | User content | ✅ (processor) | [check DPA] |
   | [Speech API] | Voice recognition | Voice recordings | [check] | [check] |
   | [Push notification] | Re-engagement | Device token | [check] | [check] |

   **For each third party:**
   - Do they have a COPPA safe harbor certification?
   - Is there a Data Processing Agreement (DPA) signed?
   - Are they configured for child-directed use? (Many services have special modes)

7. **Generate Compliance Report**

### Output Format

```markdown
# Children's Privacy Compliance Audit: [Product Name]

## Regulatory Scope
| Regulation | Applicable? | Reason |
|-----------|------------|--------|
| COPPA (US) | [Yes/No] | [market + age] |
| GDPR Art. 8 (EU) | [Yes/No] | [market + age] |
| Vietnam PDPD | [Yes/No] | [market + age] |
| Apple Kids Category | [Yes/No] | [platform] |
| Google Families Policy | [Yes/No] | [platform] |

## Data Collection Inventory
[Full table from Step 2]

## Compliance Scorecard

| Requirement | Status | Priority | Action Required |
|------------|--------|----------|----------------|
| Verifiable parental consent | ✅/⚠️/❌ | [P0-P2] | [action] |
| Privacy notice to parents | ✅/⚠️/❌ | [P0-P2] | [action] |
| Child-friendly privacy notice | ✅/⚠️/❌ | [P0-P2] | [action] |
| Data minimization | ✅/⚠️/❌ | [P0-P2] | [action] |
| Data retention limits | ✅/⚠️/❌ | [P0-P2] | [action] |
| Parent access/review/delete | ✅/⚠️/❌ | [P0-P2] | [action] |
| Third-party compliance | ✅/⚠️/❌ | [P0-P2] | [action] |
| Data security measures | ✅/⚠️/❌ | [P0-P2] | [action] |
| Data localization (Vietnam) | ✅/⚠️/❌ | [P0-P2] | [action] |

## Critical Gaps (P0)
[List with remediation plan and timeline]

## Recommendations
1. [Highest priority action]
2. [Second priority]
3. [Third priority]

## Third-Party Service Audit
[Full table from Step 6]
```

Save as `compliance-audit-[product-name].md`.

### Further Reading
- FTC. "Complying with COPPA: Frequently Asked Questions." ftc.gov/coppa.
- ICO. "Age Appropriate Design: A Code of Practice for Online Services." ico.org.uk.
- Vietnam Ministry of Public Security. "Decree No. 13/2023/ND-CP on Personal Data Protection."
- kidSAFE Seal Program. kidsafeseal.com. (COPPA safe harbor program)
- iKeepSafe COPPA certification. ikeepsafe.org.
