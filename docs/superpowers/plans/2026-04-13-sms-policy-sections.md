# SMS Policy Sections Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add SMS text messaging boilerplate sections to `terms-of-use.html` and `privacy-policy.html`.

**Architecture:** Two independent HTML edits — one new card section inserted into `terms-of-use.html` before "Limitation on Liability", and one new plain-div section inserted into `privacy-policy.html` before "Acceptance of this policy". No JavaScript, no CSS changes, no new files.

**Tech Stack:** Static HTML, Tailwind CSS utility classes (pre-built), Bootstrap Icons.

**Spec:** `docs/superpowers/specs/2026-04-13-sms-policy-sections-design.md`

---

## File Map

| File | Change |
|------|--------|
| `terms-of-use.html` | Insert new SMS card section before the "Limitation on Liability" `<div>` (line ~231) |
| `privacy-policy.html` | Insert new SMS plain-div section before the "Acceptance of this policy" `<div>` (line ~311) |

---

### Task 1: Add SMS section to terms-of-use.html

**Files:**
- Modify: `terms-of-use.html` (insert before "Limitation on Liability" section)

- [ ] **Step 1: Locate the insertion point**

Open `terms-of-use.html` and find the "Limitation on Liability" section. It begins with:

```html
<!-- Limitation on Liability -->
<div class="reveal-up tw-flex tw-flex-col tw-gap-4">
    <h2 class="tw-text-3xl tw-font-medium tw-text-gray-200 tw-flex tw-items-center tw-gap-3">
        <i class="bi bi-exclamation-triangle tw-text-purple-400"></i>
        Limitation on Liability
    </h2>
```

- [ ] **Step 2: Insert the SMS section immediately before "Limitation on Liability"**

Insert the following block immediately before the `<!-- Limitation on Liability -->` comment:

```html
                <!-- SMS Text Messaging -->
                <div class="reveal-up tw-flex tw-flex-col tw-gap-4">
                    <h2 class="tw-text-3xl tw-font-medium tw-text-gray-200 tw-flex tw-items-center tw-gap-3">
                        <i class="bi bi-chat-text tw-text-purple-400"></i>
                        SMS Text Messaging
                    </h2>
                    <div class="tw-p-6 tw-rounded-lg tw-border tw-border-outlineColor tw-bg-secondary">
                        <p class="tw-text-gray-300 tw-mb-4">
                            By registering for a WxNotify account, you consent to receive a one-time SMS verification code to the mobile number you provide. This consent is given for the sole purpose of verifying your identity during account creation.
                        </p>
                        <ul class="tw-text-gray-300 tw-flex tw-flex-col tw-gap-2 tw-list-disc tw-pl-6">
                            <li><strong>Message frequency:</strong> One message per registration.</li>
                            <li><strong>Purpose:</strong> SMS messages are sent solely to verify your identity during account creation. WxNotify does not send promotional or marketing SMS messages.</li>
                            <li><strong>Message and data rates may apply</strong> depending on your mobile carrier and plan.</li>
                            <li>To opt out, reply <strong>STOP</strong> to any SMS message from WxNotify.</li>
                            <li>For help, reply <strong>HELP</strong> or contact us through the <a href="/contact.html" class="tw-text-purple-400 hover:tw-text-purple-300 tw-underline">contact form</a>.</li>
                            <li>Consent to receive SMS messages is not a condition of purchasing or using the WxNotify service.</li>
                        </ul>
                    </div>
                </div>

```

- [ ] **Step 3: Verify the structure**

Confirm in the file that the order of sections now reads:
1. Indemnification
2. **SMS Text Messaging** ← new
3. Limitation on Liability

- [ ] **Step 4: Open the page in a browser and visually verify**

Open `terms-of-use.html` in a browser. Confirm:
- The "SMS Text Messaging" section appears before "Limitation on Liability"
- It renders with the purple `bi-chat-text` icon and the card border/background
- All six bullet points are visible and readable

- [ ] **Step 5: Commit**

```bash
git add terms-of-use.html
git commit -m "Add SMS text messaging section to Terms of Use"
```

---

### Task 2: Add SMS section to privacy-policy.html

**Files:**
- Modify: `privacy-policy.html` (insert before "Acceptance of this policy" section)

- [ ] **Step 1: Locate the insertion point**

Open `privacy-policy.html` and find the "Acceptance of this policy" section. It begins with:

```html
                <div style="font-size: 24pt;">
                Acceptance of this policy
                </div>
```

- [ ] **Step 2: Insert the SMS section immediately before "Acceptance of this policy"**

Insert the following block immediately before that `<div>`:

```html
                <div style="font-size: 24pt;">
                SMS and Phone Number Privacy
                </div>

                <div>
                If you provide a mobile phone number during registration, WxNotify uses it solely to send a one-time verification code for account creation. Your phone number will never be sold, rented, or shared with third parties for marketing or any other purpose unrelated to the operation of the Service.
                </div>

                <div>
                We may share your phone number with our SMS service provider solely to deliver the verification message on our behalf. That provider is contractually prohibited from using your phone number for any other purpose.
                </div>

                <div>
                You may request deletion of your phone number at any time through the account settings page. Standard TCPA opt-out rights apply: you may reply STOP to any SMS from WxNotify to cease further messages.
                </div>

```

- [ ] **Step 3: Verify the structure**

Confirm in the file that the order of sections now reads:
1. Data breach
2. Changes and amendments
3. **SMS and Phone Number Privacy** ← new
4. Acceptance of this policy
5. Contacting us

- [ ] **Step 4: Open the page in a browser and visually verify**

Open `privacy-policy.html` in a browser. Confirm:
- The "SMS and Phone Number Privacy" heading appears before "Acceptance of this policy"
- The heading renders at the same size as other section headings on the page
- All three body paragraphs are visible and readable

- [ ] **Step 5: Commit**

```bash
git add privacy-policy.html
git commit -m "Add SMS and phone number privacy section to Privacy Policy"
```
