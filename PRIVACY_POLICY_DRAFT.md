# PUBLISHER NOTES (delete this whole section before publishing)

**Status:** near-final English text. It is not final until (1) every `[BRACKET]` below is filled in, (2) a lawyer has reviewed it, and (3) each statement has been checked against the real app. It was written from a development-session description of the app's earlier `PRIVACY.md`, not from the code.

**Fill in**

| Placeholder | What to put |
|---|---|
| `[PUBLISHER NAME]` | Your legal name or company name, as it will appear in Play Console |
| `[EMAIL]`, `[PHONE OR ADDRESS]` | Public contact details. A dedicated email address is better than a personal one. |
| `[DATE]` | The date you publish |
| `[EMERGENCY NUMBERS]` | The same numbers the app shows in its emergency warning |
| `[DATA SOURCE]` | Where the facility list comes from (for example, the Ministry of Health registry) and its licence |
| `[MODERATOR]` | Who reviews submissions (a role is enough, for example "our moderator") |
| `[RETENTION PERIOD]` | How long rejected or unverified submissions are kept (for example 90 days) |

**Choose one for section 2.** Keep Option A if version 1 can send submissions, and delete Option B. If version 1 is read-only, keep Option B, delete Option A, and also delete the Firebase lines in sections 3 and 4.

**Check against the app before publishing**
- Search terms and any saved places stay on the phone, with nothing sent.
- Which fields a submission contains, and whether any can include the user's own location or contact details. If a submission can include the user's location, section 1 is wrong and must change.
- No analytics, ads or crash-reporting SDKs are in the build. A crash reporter would collect data and would have to be disclosed.
- Which map tile provider ships in version 1.
- The age wording in section 8.

**Keep consistent with Play Console.** The Data safety form must say the same as this policy. With Option A, you are likely to declare user-generated content (the submissions), and possibly technical identifiers that Firebase uses. Check Firebase's own data disclosures when filling in the form. With Option B and no network calls, you would declare no data collected, except that map tiles load from the tile provider.

**Items for the lawyer** are marked **[LAWYER]** in the text.

---

# Afya Karibu Privacy Policy

**Effective date:** [DATE]
**Published by:** [PUBLISHER NAME] ("we", "us")
**Contact:** [EMAIL], [PHONE OR ADDRESS]

Afya Karibu is a free Android app that helps you find health facilities in Tanzania. It has no accounts, no advertising and no analytics. Your location stays on your phone. This policy explains what the app does with information.

> **Not for emergencies.** Afya Karibu is a directory. It is not medical advice and it is not an emergency service. In an emergency, call [EMERGENCY NUMBERS] or go to the nearest health facility straight away.

## 1. What stays on your phone

- **The facility directory.** The list of facilities is built into the app, so searching and browsing work without an internet connection.
- **Your location.** If you allow the location permission, the app uses your phone's location to show facilities near you and your position on the map. This is worked out on your phone. We do not receive, store or send your location. You can refuse or withdraw the permission in your Android settings, and search will still work.
- **Your searches.** What you search for is handled on your phone and is not sent to us.

## 2. What you send us

**Option A: app with submissions**

You can suggest a correction or a new facility. If you do, the app sends what you type, which is [LIST THE FIELDS, for example facility name, location of the facility, description, and an optional contact detail], to our database hosted on Google Firebase. Google also receives technical information that comes with any internet request, such as your IP address.

We use submissions only to check them and, if they are verified, to update the directory. [MODERATOR] reviews every submission before anything is published. We never publish your contact details. Please do not put your own health information, or anyone else's, in a submission.

**Option B: read-only app**

This version of the app does not send any information to us.

## 3. Other services the app uses

- **OpenStreetMap (maps).** The map pictures are loaded from [OpenStreetMap's servers]. Like any website or app that loads a picture, their servers can see your IP address and which part of the map you are viewing. See the [OpenStreetMap Foundation privacy policy](https://osmfoundation.org/wiki/Privacy_Policy). Map data is © OpenStreetMap contributors.
- **Google Firebase (submissions only).** If you send a submission, it is stored and processed by Google. See [Firebase privacy information](https://firebase.google.com/support/privacy).

We do not sell your information. We do not use it for advertising. We do not share it with anyone other than the services above.

## 4. Where information is processed

Google's servers, and those of the map provider, may be outside Tanzania. If you send a submission, it is processed outside Tanzania. **[LAWYER: confirm the wording and any consent or safeguards the Personal Data Protection Act, 2022 requires for transfers abroad.]**

## 5. How long we keep information

Submissions are kept until we have checked them. Once a submission has been added to the directory or rejected, we delete your contact detail, if you gave one, within [RETENTION PERIOD]. You can ask us to delete a submission earlier (see section 6). Everything the app stores on your phone is removed when you uninstall the app.

## 6. Your rights

Under the Personal Data Protection Act, 2022 of Tanzania, you may ask us whether we hold personal information about you, ask for a copy, ask us to correct or delete it, and object to how it is used. **[LAWYER: confirm the list of rights and any time limits.]** To do any of these, contact us at [EMAIL]. If you are not satisfied with our reply, you may complain to the Personal Data Protection Commission of Tanzania.

## 7. Security

Submissions are sent to Firebase over an encrypted connection. We limit who can see them to [MODERATOR] and the people who maintain the app. No system is completely secure, so we cannot guarantee absolute security.

## 8. Children

Afya Karibu is not aimed at children. We do not knowingly collect personal information from anyone under 18. If you think a child has sent us personal information, contact us and we will delete it. **[LAWYER: confirm the age threshold.]**

## 9. Accuracy of the directory

The facility information comes from [DATA SOURCE] and from corrections sent by users. Hours, services and phone numbers change. We cannot promise that every entry is correct or up to date, so please phone ahead when you can. We are not responsible for decisions made from information in the app. **[LAWYER: confirm the limit of liability wording.]**

## 10. Changes to this policy

If we change this policy, we will update the effective date above and publish the new version at this address. If a change affects what the app does with your information, we will also say so in the app's update notes.

## 11. Contact us

[PUBLISHER NAME]
[EMAIL]
[PHONE OR ADDRESS]
