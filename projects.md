---
layout: page
title: Projects
---

I realized that my private repo contributions no longer show on [GitHub](https://github.com/frimicc) after
I leave a job, so there's no record there that I've done anything. This is
a sampling, lightly scrubbed, of what I've actually been doing for work.

## 2026 - Dialpad
* Re-architected the Dialpad iOS app’s calling backchannel communications, using SIP registration instead of API calls to coordinate WebRTC peer connection details. This involved working with multiple front-end and back-end teams to ensure no messages were lost. Fixed many many race conditions between SIP, CallKit, and VOIP PushKit notifications.
* Rewrote the Dialpad iOS app’s Push Notification handling, separating it into layers and packages designed to send each type of notification to that feature’s code instead of handling everything in one module.
* Designed scripts to collect end-to-end notification data, from the server process that sends them to the iOS apps that receive them, and found numerous hidden cases where notifications were not being delivered. It wasn’t until I could look at the big picture that I could see these issues and many of them were easy fixes.
* Documented Microsoft Entra/Intune login issues and worked with the support team to post the document where customers could use it to help diagnose and fix login issues without having to contact our team.

## 2025 - Dialpad
* Finished leading a team effort to rewrite the entire phone calling feature set for the Dialpad iOS app. This took three years and changed thousands of lines of code. The new feature is made up of separate SPM packages, each focused on one factor of calling. CallKit and VOIP notifications are intelligently merged to avoid race conditions. Visuals are now fully SwiftUI, including multiple screen navigation and call-outs to the rest of the app. All API calls are on background threads. After a month of rollout, customer issues and crashes had decreased significantly and uptime was over 99%.
* Created analytics dashboards and reports in Amplitude for the new calling code, so we could tell how it was working at a glance. 
* Refactored caller id selection, both logic and visuals. You’d think this would be easy, but realize that any given user can choose between their personal number(s), every department they are part of, every call center, and every office, plus specific “local presence” numbers spread around the world. Each of these caller id sources bills the call differently and must be tracked explicitely to ensure correct function and billing. Worked with and mentored a junior SWE, who then took over the final phase of the project.
* Added support for viewing live transcriptions of phone calls, including receiving both partial and final text for each utterance and consolidating those into a scrollable transcript. Supports both choosing the language for the transcript both manually and automatically.

## 2024 - Dialpad
* Worked on the calling rewrite. Highlights of the year include: call parking, caller id choosing, ratings and dispositions, multiple-call handling (aka call waiting), and localization and testing.
* Created a massive testing spreadsheet for testing phone calling, which tested every single change to every feature with about 500 test cases. Handed off to QA who were unable to produce the list themselves.
* Investigated app “cold start” performance, identified several areas to dive into, and fixed bugs and reorganized launch processes to make startup *whole seconds faster*. Worked with the team to implement these ideas and suggestions.

## 2023 - Dialpad
* Designed and planned the calling rewrite. The plan was an outside-in refactoring-in-place of every major component, so we could deliver immediate fixes for some of the worst problems in the Dialpad app. Highlights include: peeling off CallKit and VOIP notification handling into separate self-contained packages with tests, separating the UI from the business logic using MVVM, moving all API calls into a testable package, and decoupling the display of call info throughout the app from what is needed to actually make or answer a live phone call.
* Created a CarPlay extension for the Dialpad app during a 1-week hackathon. The extension could show your contacts and let you call one using the CarPlay interface. 
* Updated the team’s processes by creating scripts for new packages that generate dependency graphs, test coverage reports, and check the architecture against the team documentation. In the process we found several dependency cycles that were then fixed.

## 2022 and earlier
* available upon request