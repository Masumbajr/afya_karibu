# Afya Karibu: privacy policy review brief

**Purpose:** a short brief to send to a lawyer, with the questions to settle before the app goes on Google Play.

**Status:** DRAFT. It was written from a development-session summary of the app's draft `PRIVACY.md`, not from the file itself. Check every statement in section 2 against the real `PRIVACY.md` and the code before sending. Square brackets mark facts still to be filled in.

## 1. The app

- Android app (built with Flutter) that works offline.
- Directory of about 5,651 health facilities in Tanzania, with search and a map.
- Shows a prominent warning that the app is not a substitute for emergency services.
- Publisher: DayBridge Enterprises Ltd, Ilala, Dar es Salaam, Tanzania. Contact person: Sunday Arthur Masumba, masumbasunday9@gmail.com, +255 755 300 033, +255 718 405 302.
- Planned release: Google Play, [Tanzania only / wider].
- The policy text to review is in `PRIVACY_POLICY.md` (one placeholder for the effective date and one for the data source remain).

## 2. What the draft policy says about data

| Topic | Draft position | To confirm |
|---|---|---|
| Accounts, analytics, ads | None | Confirm no analytics or ad SDKs are in the build |
| Device location | Used on the phone for "nearby" results. Never leaves the phone. | Confirm in code |
| Map tiles | Loaded from OpenStreetMap, so OSM can see the device's IP address and the area requested | Which tile provider ships in version 1 |
| Corrections and new-facility submissions | Sent to Firebase (Google) | Does this feature ship in version 1? What does a submission contain? Is any name or contact detail collected? |
| Moderation | A moderator at DayBridge Enterprises Ltd reviews every submission before publishing | Who the moderator is in practice. Retention chosen: contact details deleted within 90 days of a submission being resolved. |
| Facility data | Registry-style facility list bundled in the app | Source, licence and permission to use [source] |

## 3. Questions for the lawyer

1. **Registration.** Under the Personal Data Protection Act, 2022, are we a data controller or processor? Must we register with the Personal Data Protection Commission before launch? What are the fee and timeline?
2. **Cross-border transfer.** Firebase servers are outside Tanzania. What does the Act require (consent, contract clauses, other safeguards)?
3. **Sensitive data.** Does anything the app handles count as sensitive (health) data, given that searching for facilities may hint at a health condition? Does the answer change for user submissions?
4. **Submissions.** What consent wording, retention period and deletion process do we need? Who handles access and deletion requests, and how?
5. **Third parties.** Is naming OpenStreetMap (IP address) and Google/Firebase enough disclosure?
6. **Children.** What should the policy say about users under 18?
7. **Disclaimers.** Wording for the emergency warning and for the accuracy of facility details (hours and services may be out of date), and how far liability can be limited.
8. **Language.** Do we need a Swahili version of the policy and the in-app notice, as well as English?
9. **Breach.** What are the notification duties and timelines, and who is the named contact?

## 4. Google Play requirements to keep in mind

- The policy must be a public web page, not a PDF, reachable without logging in.
- It must name the publisher, say what is collected, used and shared, and explain retention and deletion.
- It must match the answers given in Play Console's Data safety form.
- The app should link to the policy from inside the app.

## 5. Still to fill in

- [x] Publisher and contact details (DayBridge Enterprises Ltd)
- [x] Submissions feature kept in version 1
- [ ] Effective date (set on the day of publication)
- [ ] Source and licence of the facility data (also goes in section 9 of the policy)
- [ ] Public web address where the policy will be hosted
- [ ] Emergency numbers: the policy deliberately gives none. Sources disagree and coverage varies by region, so confirm official numbers with the authorities and make the app's emergency screen match. Do not use a personal phone number there.

*This brief is for discussion with a lawyer. It is not legal advice.*
