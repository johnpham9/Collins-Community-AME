# Collins Community AME

A simple SwiftUI iOS app for Collins Community African Methodist Episcopal Church.

## Features

- Home screen with church welcome, motto, and location
- Bible tab with KJV passage lookup and local starter passages
- Weekly schedule modeled from the provided church program
- Church program order of service
- Announcements section for church updates from a published Google Sheet

## Open In Xcode

Open `CollinsCommunityAME.xcodeproj`, select the `CollinsCommunityAME` scheme, and run on an iPhone simulator.

## Google Sheets Announcements

Create a Google Sheet with this header row:

```csv
Title,Date,Message
```

Publish the sheet as CSV:

1. In Google Sheets, choose `File > Share > Publish to web`.
2. Select the announcements sheet tab.
3. Choose `Comma-separated values (.csv)`.
4. Copy the published URL.
5. Paste that URL into the app from `Announcements > Pastor Setup`.

The app falls back to the bundled announcements if the sheet is unavailable or the URL is blank.

For production, paste the church's published CSV URL into `AnnouncementSettings.sharedGoogleSheetCSVURL` before release so every installed app reads the same Sheet. The in-app Pastor Setup screen stores a local override on that device.

For pastor-facing instructions, see `PASTOR_ANNOUNCEMENTS_GUIDE.md`.

## Support

For app support, bug reports, or feature requests, please use GitHub Issues for this repository.

When opening an issue, include:

- A short description of the problem or request
- The device model and iOS version
- The app version or build number, if available
- Steps to reproduce the problem
- Screenshots, if they help explain the issue

Please do not include private information, passwords, personal contact details, or confidential church member information in public GitHub issues.

## Privacy Policy

Collins Community AME is designed to provide church information, worship resources, announcements, schedule details, and Bible passage lookup.

### Data Collection

The app does not require users to create an account and does not intentionally collect personal information from app users.

The app does not include advertising, analytics tracking, or third-party marketing trackers.

### Data Stored On Device

The app may store a Google Sheets CSV announcement URL locally on the device when the Pastor Setup screen is used. This setting is used only to load church announcements.

### Network Requests

The app may make network requests for these features:

- Bible passage lookup using `bible-api.com`
- Announcements loaded from a published Google Sheets CSV URL, when configured

These third-party services may receive standard technical information associated with web requests, such as IP address, device/browser networking metadata, request time, and the requested URL. Their handling of that information is governed by their own privacy practices.

### Church Announcement Content

Announcement content may be loaded from a published Google Sheet. Do not publish private, sensitive, or confidential information in the announcement sheet because published CSV links can be accessible to anyone with the link.

### Children's Privacy

The app is not designed to collect personal information from children.

### Contact

For privacy questions or support, please open a GitHub Issue in this repository or contact the church directly through its official communication channels.

### Changes

This privacy policy may be updated as the app changes. Updates will be posted in this README.
