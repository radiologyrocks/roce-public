# Twilio A2P Campaign Form — Copy/Paste Reference

Use the values below directly in the Twilio campaign registration form.
Character counts have been pre-checked against Twilio's stated limits.

> Live under the `radiologyrocks` GitHub org at `https://radiologyrocks.github.io/roce-public/`.

---

## Privacy Policy URL

```
https://radiologyrocks.github.io/roce-public/privacy.html
```

## Terms and Conditions URL

```
https://radiologyrocks.github.io/roce-public/terms.html
```

## Example Scheduling URL

Use this live URL as reviewer evidence in the Message Flow / CTA section:

```
https://radiologyrocks.github.io/roce-public/s/abc123/
```

## Patient Intake Opt-In URL

Use this live URL as reviewer evidence for the opt-in checkbox:

```
https://radiologyrocks.github.io/roce-public/intake.html
```

## Written Consent / Verbal Script URL

Use this live URL as reviewer evidence for point-of-care written consent,
verbal consent, and order-entry staff documentation:

```
https://radiologyrocks.github.io/roce-public/consent-forms.html
```

## Screenshot Attachments

Attach these screenshots to the Twilio resubmission after pulling the latest
repo:

```
screenshots/intake-opt-in.png
screenshots/written-consent.png
screenshots/consent-scripts.png
```

---

## How do end-users consent to receive messages?

**(40–2048 characters; the version below is focused on one verifiable opt-in path.)**

```
Patients of participating radiology practices opt in to receive
scheduling-related text messages from the Radiology Order Conversion Engine
(ROCE) program through one or more of the following methods, all operated by
or on behalf of the patient's radiology practice:

1) Point of Care (In-Person Registration): When registering with Advanced
Medical Imaging, patients provide their mobile phone number and are presented
with written consent language on a form or tablet, which they must sign or
initial:

"I agree to receive scheduling-related text messages from Advanced Medical
Imaging regarding my appointments. Message & data rates may apply. Up to 4
messages per appointment. Reply STOP to opt out, HELP for help. See our Terms
and Privacy Policy. Consent is not a condition of receiving medical care."

2) Verbal Consent / Order Entry: If verbal consent is obtained, staff read:
"We can send you text messages to help schedule your radiology appointment.
Message & data rates may apply. Up to 4 messages per appointment. Reply STOP
to opt out, HELP for help. SMS consent is not a condition of receiving medical
care. Do you agree to receive these messages?" Staff document the patient's
response in the medical record before any messages are sent.

3) Web Form / Patient Portal: Patients may opt in by submitting their phone
number through a web form or patient portal page that includes the same
unchecked opt-in checkbox, message frequency disclosure, message and data
rates disclosure, STOP/HELP instructions, Terms link, Privacy Policy link,
and "not a condition of care" disclosure.

Reviewer evidence:
Web opt-in form: https://radiologyrocks.github.io/roce-public/intake.html
Written/verbal/order-entry examples: https://radiologyrocks.github.io/roce-public/consent-forms.html
Terms: https://radiologyrocks.github.io/roce-public/terms.html
Privacy: https://radiologyrocks.github.io/roce-public/privacy.html

In all cases, consent is for transactional scheduling-related messages only,
never marketing. Personal information and SMS consent will not be shared with
third parties or affiliates for marketing purposes. Patients can opt out at
any time by replying STOP and can request help by replying HELP.
```

---

## Opt-in Keywords (max 255 characters)

Enter as separate tags in the Twilio UI (the form treats this as a tag
list — press Enter after each one):

```
START
SCHEDULE
BEGIN
YES
SUBSCRIBE
```

---

## Opt-in Message (20–320 characters)

The auto-reply sent when a patient texts a keyword above. (~285 chars,
within the 320 limit.)

```
ROCE Radiology Scheduling: You're enrolled. We'll text you a secure link
to schedule your imaging exam and reminders before your appointment.
Msg & data rates may apply. Up to 4 msgs per appt. Reply HELP for help,
STOP to cancel. Terms: advancedmedicalimaging.com/terms
```

---

## Other Twilio fields you may also see

These often appear on the same form. Suggested values:

**Opt-out keywords** (Twilio handles these natively, but if asked):

```
STOP
END
CANCEL
UNSUBSCRIBE
QUIT
```

**Opt-out message** (auto-reply on STOP, ~155 chars):

```
ROCE Radiology Scheduling: You are unsubscribed and will receive no further
messages. Reply START to re-enroll. For help, email elliottbrown@gmail.com.
```

**Help keywords** (Twilio handles natively):

```
HELP
INFO
```

**Help message** (auto-reply on HELP, ~205 chars):

```
ROCE Radiology Scheduling: We send scheduling links and reminders for your
imaging exam. Msg & data rates may apply. Reply STOP to cancel. Support:
elliottbrown@gmail.com. Terms: advancedmedicalimaging.com/terms
```

**Sample messages** (Twilio asks you to paste 1–2 representative production messages):

1. Initial scheduling invitation:

```
This message is from Advanced Medical Imaging. Hi Alex, your imaging exam is
ready to schedule. Tap here to pick a time:
https://advancedmedicalimaging.com/schedule/abc123 Reply Q if you'd like us
to call you, HELP for help, or STOP to opt out.
```

2. 24-hour reminder:

```
Hi Alex, this is a reminder of your imaging exam tomorrow at 9:00 AM at
Main Street Imaging. Reply C to confirm, R to reschedule, or STOP to opt
out. HELP for help.
```

---

## Submission checklist

Before you click submit on the Twilio campaign form:

- [ ] Pages `index.html`, `terms.html`, `privacy.html` are publicly reachable (open in incognito).
- [ ] Privacy Policy URL above resolves with no auth wall.
- [ ] Terms URL above resolves and shows **HELP** and **STOP** in bold.
- [ ] Sample messages match what your application will actually send.
- [ ] Sample messages use the production/practice domain, not a GitHub URL.
- [ ] CTA evidence includes the live GitHub Pages opt-in and scheduling demo URLs.
- [ ] Attach screenshots from `screenshots/` to the resubmission.
- [ ] Brand name on this form ("Radiology Order Conversion Engine") matches the brand you registered earlier in Twilio.
