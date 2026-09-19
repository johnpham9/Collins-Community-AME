# Collins Community AME

An iPhone and iPad app for Collins Community African Methodist Episcopal Church in Oklahoma City. Built with SwiftUI, with a WidgetKit verse widget.

## What is in the app

- **Home:** church welcome, address, a motivational verse selected on each fresh launch, and shortcuts to the main sections.
- **Bible:** bundled starter passages and King James Version lookup by reference. Other passages require an internet connection to `bible-api.com`.
- **Confession:** Holy Communion and related readings.
- **Program:** order of service.
- **Schedule:** weekly services and monthly Sunday observances.
- **My Faith:** a private prayer journal, personal notes, and a weekly worship checklist. These are stored on the device, not sent to the church.
- **Verse for Today widget:** small and medium Home Screen widgets with bundled Scripture that changes daily. The widget works without a network connection. Its verse is chosen independently of the Home screen verse.

The app does not currently have a News or Announcements tab, Pastor Setup, accounts, or a church-managed backend.

## Open and run

1. Open `CollinsCommunityAME.xcodeproj` in Xcode.
2. Select the `CollinsCommunityAME` scheme and an iPhone or iPad simulator.
3. Select an Apple Developer team for both the app and `CollinsCommunityAMEWidget` targets under Signing & Capabilities.
4. Build and run with **Product > Run**.

The app targets iOS 17.6 and later. If Xcode reports a signing conflict, verify that the app and widget bundle identifiers are available to your team:

- App: `com.collinscommunityame.church`
- Widget: `com.collinscommunityame.church.widget`

The widget is embedded in the main app. After installing the app, add it from the iPhone Home Screen's widget gallery by searching for **Collins AME** or **Verse for Today**.

## Release builds

For TestFlight or App Store uploads, select the app scheme and **Any iOS Device**, then use **Product > Archive**. Increase the app's build number before each new upload. Confirm the widget extension is signed by the same team and included in the archive.

## Data and privacy

Prayer entries, notes, and checklist progress use local `UserDefaults` storage. The checklist resets at the start of a new calendar week. The app does not provide an account or cross-device sync for these entries. Deleting the app normally removes its local data, though copies may remain in a device backup according to the user's backup settings.

Bible searches outside the bundled examples are sent to `bible-api.com` over HTTPS. The daily verses shown by the app and widget are bundled locally. See [privacy.md](privacy.md) for the full privacy policy.

## Project layout

- `CollinsCommunityAME/ContentView.swift`: navigation and the Home, Bible, Confession, Program, and Schedule screens.
- `CollinsCommunityAME/FaithView.swift`: prayer journal, notes, and checklist screens.
- `CollinsCommunityAME/FaithStore.swift`: local persistence for My Faith.
- `CollinsCommunityAME/ChurchData.swift`: church program, bundled passages, and motivational verses.
- `CollinsCommunityAME/BibleAPI.swift`: online KJV passage lookup.
- `CollinsCommunityAMEWidget/`: WidgetKit extension and its bundle metadata.

The repository still contains an older announcement service file and pastor guide for historical reference; they are not part of the current app interface.

## Support

For app help or privacy questions, contact Collins Community AME Church through its official channels or at 4125 N.E. 16th Street, Oklahoma City, Oklahoma 73117. Do not include prayer journal entries or other sensitive information in a public bug report.
