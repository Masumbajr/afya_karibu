# Hospitali Online: Google Play Data safety answers

**Where:** Play Console → Policy and programs → App content → Data safety.

**Status:** DRAFT. The answers follow the app as the earlier development session described it and as `PRIVACY_POLICY.md` states it. I could not see the code. Section 4 lists the checks that can change an answer. Google holds you responsible for the answers, so check each one against the real build.

**Rules that shape the answers** (from Google's [Data safety help page](https://support.google.com/googleplay/android-developer/answer/10787469))
- *Collect* means data leaves the phone. Data used only on the phone is not collected, so the user's own location (used only on the phone) is not declared.
- *Share* means a transfer to a third party. Sending data to a service provider that handles it for you, on your instructions, does not count as sharing. Firebase (Google) holding the submissions is treated that way.
- Disclose what your libraries collect too, not only your own code.

---

## 1. Data collection and security

| Question | Answer |
|---|---|
| Does the app collect or share any required user data types? | **Yes** (submissions, see section 2) |
| Is all collected data encrypted in transit? | **Yes**, if every connection uses HTTPS (see check 3) |
| Account creation methods | **The app does not allow users to create an account** |
| Can users ask for their data to be deleted? | **Yes**: by email, as described in sections 5 and 6 of the privacy policy |

## 2. Data types

Declare only these. Leave everything else unticked.

| Category → type | Collected? | Shared? | Processed ephemerally? | Required or optional | Purpose |
|---|---|---|---|---|---|
| App activity → **Other user-generated content** (the text of a correction or new-facility suggestion) | Yes | No | No | **Optional** (the user chooses to send it) | App functionality |
| Personal info → **Email address** and/or **Phone number** (only if the submission form has an optional contact field) | Yes | No | No | **Optional** | App functionality |
| Location → **Approximate location** (map pictures requested from OpenStreetMap, see check 2) | Yes | **Yes**, with OpenStreetMap | Yes | Required for the map to load | App functionality |

If the submission form has no contact field, delete the second row. If the map comes from a provider under contract with you, the third row may become "not shared" (see check 2).

## 3. Not declared, and why

| Data | Reason |
|---|---|
| User's own GPS location | Used only on the phone. If a submission can include it, see check 1. |
| Search terms | Stay on the phone |
| Health information | Not collected. The policy tells users not to enter it. |
| Account details, purchases, contacts, messages | The app has none of these |
| Advertising ID, analytics events | No ads and no analytics |
| Crash logs, diagnostics | Only if no crash-reporting tool is installed (see check 4) |
| Photos | Only if the submission form cannot attach photos (see check 5) |

## 4. Checks that can change an answer

1. **Does a submission ever include the user's own location?** For example a "use my current location for this facility" button. If yes, add Location → **Precise location**, collected, optional, App functionality, and **change section 1 of the privacy policy and the listing text**, which say location never leaves the phone.
2. **OpenStreetMap map pictures.** The map loads pictures from OpenStreetMap's servers, which can see the user's IP address and the area being viewed. If that area is centred on the user's position, it is approximate location going to a third party. I recommend declaring it as in the table, because it matches what the privacy policy tells users, and a wrong "no" is the riskier mistake. A tile provider you have a contract with would count as a service provider, which removes the "shared" answer and also avoids OpenStreetMap's limits on heavy use of its public servers.
3. **HTTPS everywhere.** The map address must start with `https://`. If anything uses plain `http://`, answer "No" to encryption, and Android would block it anyway.
4. **Other Firebase products and SDKs.** Look at the app's dependencies for `firebase_crashlytics`, `firebase_analytics`, `firebase_performance` and `firebase_messaging`. Each one collects more data and changes both the form and the privacy policy.
5. **Photos or files.** If the form can attach a photo (Firebase Storage), add Photos and videos → **Photos**, collected, optional.
6. **Firebase's own disclosures.** Firebase's [Play data disclosure guide](https://firebase.google.com/docs/android/play-data-disclosure) says which Firebase features collect installation IDs and IP addresses. For each Firebase product the app uses, follow it. If an installation ID is collected, add Device or other IDs → **Device or other IDs**, collected, not shared, purpose App functionality and Fraud prevention, security, and compliance.

Quick way to check items 1, 4, 5: run these in the app folder on your Mac.

```bash
cd /Users/user/Desktop/CODING/afya_karibu && grep -rn -E "firebase|geolocator|image_picker|http://" pubspec.yaml lib
```

## 5. What visitors will see

With the table in section 2, the listing says the app may share approximate location and may collect personal info and app activity. It also says data is encrypted in transit and that you can ask for it to be deleted. It will not say "No data shared with third parties", because of the OpenStreetMap row. With a contracted tile provider, that line can appear.

## 6. Consistency with the privacy policy

| Policy says | Form says |
|---|---|
| No accounts | No account creation |
| Location stays on the phone | Own location not declared (subject to check 1) |
| OpenStreetMap sees IP address and map area | Approximate location shared with OpenStreetMap |
| Submissions go to Firebase | Other user-generated content collected, not shared |
| Contact detail optional, deleted within 90 days | Email / phone collected, optional |
| Encrypted connection to Firebase | Encrypted in transit: Yes |
| Contact us to delete | Deletion requests: Yes |

If you change an answer, change the policy and the listing text to match.
