# Twilio A2P Campaign Form — Copy/Paste Reference

Use the values below directly in the Twilio campaign registration form.
Character counts have been pre-checked against Twilio's stated limits.

> Replace `Brownster` in the URLs with your actual GitHub username if different.

---

## Privacy Policy URL

```
https://brownster.github.io/roce-public/privacy.html
```

## Terms and Conditions URL

```
https://brownster.github.io/roce-public/terms.html
```

---

## How do end-users consent to receive messages?

**(40–2048 characters; the version below is ~1,720 characters — well within the limit.)**

```
Patients of participating radiology practices opt in to receive scheduling
text messages from the Radiology Order Conversion Engine (ROCE) program
through one or more of the following methods, all of which are operated by,
or on behalf of, the patient's radiology practice:

1) Point of care: When the patient registers with the radiology practice,
they provide a mobile phone number and either sign a written consent or
give verbal consent (recorded in the patient's chart) to receive
scheduling-related text messages from the practice.

2) Order entry: When an imaging order is placed, practice staff verbally
confirm that the patient agrees to receive scheduling SMS for that order
and document the consent in the patient's medical record before any
messages are sent.

3) Web form / patient portal: The patient submits their phone number
through a practice web form or patient-portal page that includes a
clearly-labeled opt-in checkbox describing the SMS scheduling program,
expected message types, message frequency, message-and-data-rates
disclosure, and links to the program's Terms and Conditions and Privacy
Policy at https://brownster.github.io/roce-public/.

4) Reply-keyword opt-in: The patient texts an opt-in keyword (such as
START, SCHEDULE, BEGIN, or YES) to the program number, after which an
automated welcome message confirms enrollment and references the Terms
and Privacy Policy.

In all cases, consent is for transactional, scheduling-related messages
only — never for marketing — and is not a condition of receiving medical
care. Patients can opt out at any time by replying STOP, and can request
help by replying HELP.
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
Msg & data rates may apply. Up to 6 msgs per order. Reply HELP for help,
STOP to cancel. Terms: brownster.github.io/roce-public/terms.html
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
elliottbrown@gmail.com.  Terms: brownster.github.io/roce-public/terms.html
```

**Sample messages** (Twilio asks you to paste 1–2 representative production messages):

1. Initial scheduling invitation:

```
Hi Alex, your imaging exam is ready to schedule. Tap here to pick a time:
https://example.test/s/abc123. Reply Q if you'd like us to call you, or
STOP to opt out.
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
- [ ] Brand name on this form ("Radiology Order Conversion Engine") matches the brand you registered earlier in Twilio.
