---
name: design-parental-consent
description: "Design the parental consent flow for a children's EdTech product — from consent collection to ongoing management. Use when building or redesigning the onboarding flow for a product that collects data from children under 13 (COPPA) or under 16 (GDPR)."
---

## Design Parental Consent Flow

Parental consent is the gateway to your product. A poorly designed consent flow either fails compliance (legal risk) or creates so much friction that parents abandon onboarding (business risk). This skill designs a flow that is legally sound, parent-friendly, and conversion-optimized within compliance constraints.

### Domain Context

**COPPA's "Verifiable Parental Consent" (VPC)** requires that the operator make "reasonable efforts" to ensure that a parent — not the child — has provided consent. The FTC evaluates VPC methods on a sliding scale based on how the data will be used:

**For internal use only** (no sharing with third parties):
- "Email plus" is acceptable: Send email to parent's address, require them to respond or click a link to confirm, then send a follow-up confirmation.

**For sharing data with third parties or public-facing data:**
- Higher-assurance methods required: credit card verification, government ID, video conference, knowledge-based authentication, or signed consent form.

**The conversion-compliance tradeoff:**
Higher-assurance methods are more legally defensible but create more friction. The art is choosing the minimum viable verification for your data practices.

### Context

You are designing the parental consent flow for **$ARGUMENTS**.

### Instructions

1. **Determine Required Consent Level**

   Based on data practices (from `assess-coppa-compliance`):

   | Data Practice | Consent Level | Recommended Method |
   |--------------|--------------|-------------------|
   | Internal use only, no persistent IDs | Email plus | Email with confirmation link |
   | Persistent identifiers for analytics | Email plus | Email with confirmation link |
   | Voice/image collection | Higher assurance | Credit card or app store purchase |
   | Sharing with third parties | Highest assurance | ID verification or signed form |
   | Real-time communication features | Highest assurance | ID verification |

2. **Design the Flow Architecture**

   The consent flow has 5 stages:

   **Stage 1: Age Gate** → Determine if the user is a child
   **Stage 2: Parent Identification** → Collect parent's contact information
   **Stage 3: Direct Notice** → Inform parent of data practices
   **Stage 4: Consent Collection** → Obtain verifiable consent
   **Stage 5: Consent Confirmation** → Confirm and document consent

   Design each stage:

   **Stage 1 — Age Gate:**
   - **Neutral age input:** Ask for birth year (not "Are you over 13?" which invites lying). Use a date picker that doesn't highlight the threshold.
   - **If child (under threshold):** Redirect to parent flow. Do NOT collect any data from the child yet.
   - **If adult:** Proceed to normal registration.
   - **If parent registering for child:** Collect parent info first, then child info after consent.

   **Stage 2 — Parent Identification:**
   - Collect parent's email address (minimum)
   - Explain WHY: "We need a parent or guardian's permission before [child's name] can start learning."
   - Tone: Respectful, not bureaucratic. "We take your child's privacy seriously."

   **Stage 3 — Direct Notice:**
   - Present the privacy notice WITHIN the flow (not a link to a separate page)
   - Must include: data collected, purposes, third parties, retention, parent rights
   - Keep it scannable: use a summary box + expandable details
   - Translated into the user's language

   **Stage 4 — Consent Collection:**
   - Implement the verification method determined in Step 1
   - For email plus: Send email → parent clicks confirmation link → confirmation email sent back
   - For credit card: Small authorization hold ($0.50) that is immediately reversed
   - For app store: Require parent to complete an in-app purchase (can be $0.00 + verification)

   **Stage 5 — Confirmation:**
   - Show confirmation to parent: "You've given permission for [child] to use [product]. Here's what you can do..."
   - Provide links to: review data, revoke consent, manage settings, contact support
   - Store consent record: timestamp, method, parent identifier, version of privacy notice shown

3. **Design the Consent Management Dashboard**

   After initial consent, parents need ongoing control:

   - **View child's data:** What information is stored about their child
   - **Download data:** Export in readable format
   - **Delete data:** Request deletion of all child data (must be honored within 30 days)
   - **Revoke consent:** Withdraw permission (product must stop collecting and delete existing data)
   - **Update consent:** If data practices change, re-consent is required
   - **Manage notifications:** Control what communications the parent receives

4. **Design for Re-Consent**

   Re-consent is required when:
   - Data practices change materially (new data types, new third parties)
   - Product adds features that collect new categories of information
   - Regulatory requirements change

   Design a re-consent flow that:
   - Clearly explains what changed ("We've added a new voice feature that records audio")
   - Makes it easy to consent or decline the new practice specifically
   - Does not hold existing functionality hostage (child can keep using current features while parent decides)

5. **Handle Edge Cases**

   - **Child tries to bypass age gate:** Design the age gate to be neutral (not "click here if you're over 13"). If a child enters an adult age, monitor for age-inconsistent behavior (not always feasible).
   - **Parent doesn't respond to consent request:** Set a timeout (48-72 hours). Child cannot use the product until consent is obtained. Send a reminder email at 24h.
   - **Shared device:** If parent and child use the same device, ensure consent flow can't be accidentally completed by the child.
   - **Multiple children:** Allow one parent account to consent for multiple children without repeating the full verification process.
   - **Custody situations:** Don't require both parents. One legal guardian is sufficient under COPPA.

### Output Format

```markdown
# Parental Consent Flow Design: [Product Name]

## Consent Level Determination
- **Data practices**: [summary from compliance audit]
- **Required consent level**: [email plus / higher assurance / highest]
- **Selected verification method**: [method]

## Flow Architecture

### Stage 1: Age Gate
- **Input method**: [neutral date picker / birth year]
- **Threshold age**: [13 for COPPA / 16 for GDPR / lowest applicable]
- **Under-threshold behavior**: [redirect to parent flow]

### Stage 2: Parent Identification
- **Data collected**: [email / phone / name]
- **UX copy**: [messaging shown to parent]

### Stage 3: Direct Notice
- **Summary version**: [scannable privacy notice]
- **Full version**: [link to complete privacy policy]
- **Languages**: [supported languages]

### Stage 4: Consent Collection
- **Method**: [detailed implementation]
- **Timeout**: [hours before expiration]
- **Retry flow**: [if parent doesn't respond]

### Stage 5: Confirmation
- **Parent confirmation**: [what they see]
- **Consent record**: [what is stored]

## Consent Management Dashboard
| Feature | Description | Access |
|---------|------------|--------|
| View data | [details] | Parent settings |
| Delete data | [details] | Parent settings |
| Revoke consent | [details] | Parent settings |

## Edge Case Handling
| Scenario | Detection | Response |
|----------|-----------|----------|
| [case] | [how detected] | [behavior] |

## Conversion Metrics to Track
- Age gate → parent email submission rate
- Email submission → consent completion rate
- Overall onboarding completion rate
- Time from child registration to first session
```

Save as `parental-consent-[product-name].md`.

### Further Reading
- FTC. "Complying with COPPA: Frequently Asked Questions." (Updated 2023)
- FTC. "COPPA Rule: A Six-Step Compliance Plan for Your Business."
- Privo. "COPPA Verifiable Parental Consent Methods." privo.com.
- SuperAwesome (now Epic Games). "Kids Digital Media Compliance." superawesome.com.
