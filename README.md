# NIPUN App Releases

Central release index for the **NIPUN Android Application** across DEV, STAGE, and PROD environments. 

> APK files are stored on Google Drive. This repository tracks the latest distributed builds and release notes.

### Play Store

[Download NIPUN App from Google Play Store](https://play.google.com/store/apps/details?id=com.nipun&hl=en_IN)

---

## Current Releases

### ESDS (Swaraj Cloud) Kubernetes

| Environment | Version | Build | Release Type | Build Date | Status | APK |
|---|---|---|---|---|---|---|
| 🟣 **ESDS DEV** | `2.0.0` | `10070` | Release | 19 Nov 2026 | 🧪 Development | [⬇️ Download](https://drive.google.com/file/d/1gq1G2kQi1Dm4OMeqyYHfrcKsiokhwWbH/view?usp=sharing) |
| 🟠 **ESDS STAGE** | `2.0.1` | `100073` | Release | 24 Nov 2026 | 🔍 Testing | [⬇️ Download](https://drive.google.com/file/d/1tQ9qFJtzgBDFCJrp-OAppGaaOTvxvFW-/view?usp=drive_link) |
| 🟢 **ESDS PROD** | `2.0.1` | `100073` | Release | 24 Nov 2026 | 🔍 Production | [⬇️ Download](https://drive.google.com/file/d/1HMDQ5YnBpDQfyV7yzjuwQ3dPHIU0zpkV/view?usp=drive_link) |


### VOPA-AWS

| Environment | Version | Build | Release Type | Build Date | Status | APK |
|---|---|---|---|---|---|---|
| 🔵 **DEV** | `1.7.52` | `10069` | Debug | 22 Oct 2026 | 🧪 Development | [⬇️ Download](https://drive.google.com/file/d/1Hvg-bOoWCTnd2ivi5U4C-aBOB_bnFq1T/view?usp=sharing) |
| 🟠 **STAGE** | `1.7.53` | `10069` | Release | 02 Nov 2026 | 🔍 Testing | [⬇️ Download](https://drive.google.com/file/d/1CTGxSbmx4j7RWS-5TuNJ-Dj1EONxHLfG/view?usp=sharing) |
| 🟢 **PROD** | `1.7.53` | `10069` | Release | 02 Nov 2026 | ✅ Live | [⬇️ Download](https://drive.google.com/file/d/10JzS1_LpOxYpUWviU0n4OtGhaRAgjUDs/view?usp=sharing) |


## Release Flow

```mermaid
flowchart LR
    A["💻 Development"] --> B["🧪 Dev Testing (QA if needed)"]
    B --> C["📦 STAGE Build<br/>Debug / Release"]
    C --> D["🔍 QA Testing"]
    D --> E["👥 NIPUN Team Testing"]
    E --> F["💬 Issue Review<br/>& Discussion"]
    F --> G["🛠️ Bug / Issue<br/>Resolution"]
    G --> H["🔄 Re-testing"]
    H --> I{"Issues Resolved?"}

    I -- "No" --> F
    I -- "Yes" --> J["✅ QA + NIPUN<br/>Approved"]
    J --> K["🚀 Production<br/>Release"]
```

> **Release rule:** Any issues identified during STAGE testing go through **Review → Resolution → Re-testing** until QA and the NIPUN Team approve the build for production.

---

## Targeted Release

**Source:** 🟠 ESDS STAGE
**Target:** Oct 2nd Week  
**Status:** QA / NIPUN Team Testing

> The approved STAGE build will be promoted to PROD and submitted to the Play Store.

---

## Release Notes: ESDS STAGE

**App Version:** 2.0.1
**Applies to:** 🟠 ESDS (Swaraj Cloud) Kubernetes STAGE

#### What Changed and How to Test

**1. Assessment capture: the levels fetch no longer blocks the UI**

- The levels fetch now runs in the background. A new levels gate screen appears if the levels are not ready.
- Test:
  - Open assessment capture for a student on a fast network, a slow network and offline.
  - Confirm the screen doesn't freeze.
  - Confirm the gate screen shows and clears correctly once the levels load.
  - Confirm assessment data is saved correctly.
  - Confirm the levels dropdown now shows descriptions.
  - Confirm the class list is in ascending order.

**2. NIPUN Tarang games: metrics now carry student context**

- The student context is now attached before WebView game events fire.
- Test:
  - Play sheet games as different students.
  - Confirm metrics and activity are recorded against the correct student.
  - Confirm nothing is lost or attributed to the wrong student when switching students.

**3. Student assessment timeline: year tabs fix**

- Stale student-list responses are now ignored when you switch year tabs.
- Test:
  - Switch year tabs quickly.
  - Confirm the list always matches the selected year.
  - Confirm there is no flicker or wrong data.

**4. UI and branding changes**

- Logo images were replaced (Headmaster, Inspector). Check them on all profile cards.
- The promotional screen has a new background, and the profile chooser has a new backdrop. Check these on different screen sizes.
- Minor UI change on the Assign Teachers screen.
- Translation updates in English and Marathi. Check for missing, truncated or wrong strings, especially on the About Us, Assign Teachers and profile screens.
- The parent profile gate and utils changed. Test the parent profile selection flow.

**5. Onboarding screens: UI fixes**

- Fixed UI issues on the onboarding screens. Check them on different screen sizes.

**6. Assessment screens: UI fixes**

- Fixed UI issues on the assessment screens. Check them on different screen sizes.

**7. Assessment result: WPM renamed to CWPM**

- The Speed result in the assessment result now shows CWPM instead of WPM.
- Test: Complete an assessment and confirm the Speed result shows CWPM in both English and Marathi.

**8. Parent Dashboard: first name only**

- The Parent Dashboard now displays only the first name. Names in uppercase are shown in title case.
- Test: Open the Parent Dashboard with a name stored in uppercase (for example, "RAHUL KUMAR") and confirm it shows "Rahul".

**9. WebView screens: confirmation modal replaces native alerts**

- Native Alert dialogs in GamesWebViewScreen and WebViewScreen are replaced with the global confirmation modal.
- Test: Trigger a confirmation in a game and in a web page. Confirm the global modal appears, and that both confirm and cancel work.

---

## Release Notes: ESDS PROD

**Applies to:** 🟢 ESDS (Swaraj Cloud) Kubernetes PROD

**1. Nudges**

- Added a nudges list and nudges in the drawer.

**2. About Us**

- The About Us PDFs are updated, and a new PDF viewer is added.
- Test: Open each PDF from About Us and confirm it loads, scrolls and closes correctly.

**3. Onboarding screens: UI changes**

- Made UI changes on the onboarding screens.

---

## Issue Reporting - Linear

Include the following when reporting an issue:

```text
Environment:
App Version:
Build Number:
Device:
Android Version:

Issue:
Steps to Reproduce:
Expected Behaviour:
Actual Behaviour:
Screenshot / Video:
```

---

## Developer's Note: Updating a Release

For every new build:

1. Upload APK to Google Drive.
2. Update the corresponding row in **Current Releases**.
3. Update **Current Release Notes** if required.
4. Update **Next Play Store Release** when the STAGE build becomes a release candidate.
5. Commit and push.

```bash
git add README.md
git commit -m "(version - date): ESDS/AWS DEV/STAGE/PROD release/debug update"
git push
```

---

**Maintained by:** VOPA Technology Team
