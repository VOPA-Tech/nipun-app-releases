# NIPUN App Releases

Central release index for the **NIPUN Android Application** across DEV, STAGE, and PROD environments. 

> APK files are stored on Google Drive. This repository tracks the latest distributed builds and release notes.

### Play Store

[Download NIPUN App from Google Play Store](https://play.google.com/store/apps/details?id=com.nipun&hl=en_IN)

---

## Current Releases

| Environment | Version | Build | Release Type | Build Date | Status | APK |
|---|---|---|---|---|---|---|
| 🔵 **DEV** | `1.7.5` | `10067` | Debug | 08 Oct 2026 | 🧪 Development | [⬇️ Download](https://drive.google.com/file/d/16-JcL-tZR9nxEjQcyt5gjJ86EetChf-G/view?usp=drive_link) |
| 🟠 **STAGE** | `1.7.5` | `10067` | Release | 08 Oct 2026 | 🔍 Testing | [⬇️ Download](https://drive.google.com/file/d/1vN03g-1T62y6Fff2DB674xLDnZOeIUJ_/view?usp=drive_link) |
| 🟢 **PROD** | `1.7.4` | `10065` | Release | 24 Sep 2026 | ✅ Live | [⬇️ Download](https://drive.google.com/file/d/1ZyD6p_wThZPCCpVCJuTj2Pr2_YyIcphM/view?usp=sharing) |

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

**Source:** 🟠 STAGE  
**Target:** Oct 2nd Week  
**Status:** QA / NIPUN Team Testing

> The approved STAGE build will be promoted to PROD and submitted to the Play Store.

---

## Release Notes

**Environment:** 🔵 DEV + 🟠 STAGE  
**Release Type:** Release Version

#### What's New

- Updated assessment flow
- Improved student progress flow
- Updated assessment-related validations
- Teacher assessment testing
- Integrated student progress timeline v2 API's
- Student list: Remaining / Assessed / All tabs (search removed)
- Class card: separate action buttons instead of whole-card tap

#### Bug Fixes

- Fixed login-related issues
- Fixed assessment submission issues
- General performance improvements
- Fixed student progress timeline issues

#### Features To Be Tested

**Headmaster**

- शाळेची माहिती (School Information)
- माझ्या शाळेतील शिक्षक (Teachers in My School)
- वर्गनिहाय शिक्षक नोंदणी करा (Assign Teachers to Class)
- AI द्वारा वाचन सराव
- निपुण संवादिका (Social Media)
- विद्यार्थ्यांचे मूल्यांकन तपशील (Student Assessment Timeline)
- Nipun Games

**Teacher**

- पालकांचे फोन क्रमांक अद्ययावत करा (Update Parents Phone Number)
- AI द्वारा वाचन सराव
- निपुण संवादिका (Social Media)
- Assessment flow
- विद्यार्थ्यांचे मूल्यांकन तपशील (Student Assessment Timeline)
- Nipun Games

**Parent**

- निपुण संवादिका (Social Media)
- AI द्वारा वाचन सराव
- Notification
- Profile
- Nipun Games

**Admin**

- पर्यवेक्षकांसाठी विविध अहवाल (Reports)
- AI द्वारा वाचन सराव
- निपुण संवादिका (Social Media)
- विद्यार्थ्यांचे मूल्यांकन तपशील (Student Assessment Timeline)
- Nipun Games

#### Features Not To Be Tested

**All Roles**

- Audio Guide
- शाळेचे विश्लेषण पहा (School Analysis)
- Learning material

**Parent**

- My child
- Student progress timeline
- पुनर्रचनी सुरू करा

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
git commit -m "(version - date): release/debug update"
git push
```

---

**Maintained by:** VOPA Technology Team  
**Last Updated:** 08 Oct 2026
