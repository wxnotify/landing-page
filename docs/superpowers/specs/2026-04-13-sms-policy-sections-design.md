# SMS Policy Sections Design

**Date:** 2026-04-13  
**Scope:** Add SMS text messaging boilerplate sections to `terms-of-use.html` and `privacy-policy.html`

---

## Overview

WxNotify sends a single one-time SMS verification code to users during account registration. Neither file currently contains any language governing SMS messaging. This spec covers the addition of one new section to each file.

---

## Terms of Use — "SMS Text Messaging" Section

### Placement
Inserted as a new card section at the end of the terms content, immediately before the existing "Limitation on Liability" section.

### Styling
Matches the existing card pattern used throughout `terms-of-use.html`:
- Outer wrapper: `reveal-up tw-flex tw-flex-col tw-gap-4`
- Heading: `<h2>` with classes `tw-text-3xl tw-font-medium tw-text-gray-200 tw-flex tw-items-center tw-gap-3`
- Bootstrap icon: `bi bi-chat-text tw-text-purple-400`
- Card body: `tw-p-6 tw-rounded-lg tw-border tw-border-outlineColor tw-bg-secondary`

### Content
- By registering, the user consents to receive a one-time SMS verification code.
- Message frequency: one message per registration.
- Purpose is strictly account verification — no promotional or marketing SMS.
- Message and data rates may apply depending on carrier and plan.
- Opt-out: reply STOP to any SMS from WxNotify.
- Help: reply HELP or use the contact form.
- Consent to SMS is not a condition of purchasing or using the service.

---

## Privacy Policy — "SMS and Phone Number Privacy" Section

### Placement
Inserted as a new section near the end of the privacy policy content, immediately before the existing "Acceptance of this policy" section.

### Styling
Matches the existing plain-div pattern used throughout `privacy-policy.html`:
- Section heading: `<div style="font-size: 24pt;">` containing the heading text
- Body text: plain `<div>` block(s) with paragraph text

### Content
- Phone number is collected solely to send a one-time verification code during registration.
- WxNotify will never sell, rent, or share the phone number with third parties for marketing or any purpose unrelated to the Service.
- The SMS delivery provider receives the phone number solely to transmit the verification message and is contractually prohibited from any other use.
- Users may request deletion of their phone number via account settings.
- TCPA opt-out rights apply: reply STOP to any SMS from WxNotify to cease further messages.

---

## Out of Scope
- No changes to any other sections of either file.
- No visual or structural redesign of either page.
- No changes to any other HTML files.
