---
name: github-vscode-tablet-ship
description: Build or update the user's apps and websites using the connected GitHub repository and VS Code workflow; configure for tablet use, create a home-screen launch icon, and verify the complete working experience. Use for app or website builds, GitHub handoffs, VS Code implementation, tablet setup, home-screen icons, voice launch setup, or project completion.
---

# GitHub, VS Code, and tablet delivery

Use this skill when building or updating an app or website and the user expects the work sent to GitHub, handled through VS Code-compatible project files, configured for their tablet, and tested through completion.

## Completion standard

A project is complete only when the intended app or website is implemented, its key user flows pass checks, the verified source is pushed to the intended GitHub repository, and the user has a working tablet launch path. When device access permits, install or pin a clearly named project icon to the tablet home screen and open it to verify the flow. Never report completion based only on a successful build or GitHub push.

If the tablet cannot be accessed directly, finish all independent work, provide the exact installation or shortcut steps and a reachable URL/package, and label physical setup and verification as outstanding. Do not claim the project is fully ready on the tablet until the shortcut or installed app has been opened and checked there. Keep working until complete or until a concrete external blocker prevents the next step; identify that blocker and a precise way to remove it.

## Workflow

1. **Find the right project.** Inspect the current workspace, project instructions, Git remote, and relevant conversation context. Use GitHub tools to find the user's matching repository when available. Reuse the correct repo and branch; do not create a duplicate repository or overwrite unrelated work. If GitHub is not connected or the right repo cannot be identified, continue local implementation and ask only for the missing repo or access detail.
2. **Work in VS Code-compatible source.** Inspect the framework, scripts, environment, and existing conventions. Make changes in reviewable project source so the user can edit them in VS Code. If the user is using GitHub Codespaces or VS Code for Web, provide/open the repository there when supported. Do not claim to control the user's VS Code window or device unless an active tool confirms that access.
3. **Choose a tablet-supported delivery.** Determine whether the deliverable is a responsive web app, PWA, or native app. For web projects, build tablet-sized layouts, touch-friendly controls, sensible orientation behavior, and an install path when useful. For native projects, configure the correct tablet target, build variant, and install method. If a desktop-only app cannot run on Android, do not create a misleading tablet icon; provide a compatible web/tablet companion path when the project supports one, or clearly state the platform limitation.
4. **Configure and build.** Follow project setup instructions. Configure required runtime services and environment without committing secrets or private user data. Run available lint, typecheck, tests, and production builds. Launch the app and inspect the main flows at tablet viewport sizes. Fix errors, broken navigation, clipped layouts, unsafe configuration, and touch or keyboard problems; rerun affected checks.
5. **Push the verified source.** Commit and push to the intended repository and branch using the available GitHub integration. Confirm the destination and resulting commit; never claim a push succeeded unless the tool reports it. Keep credentials in environment variables or the hosting provider's secret store.
6. **Make a reliable tablet launch path.** For a website, use a reachable HTTPS preview or deployment when available. For a local server, confirm network binding and LAN reachability; a computer's `localhost` is not reachable from the tablet. For native apps, provide a tablet-compatible package and installation route. Keep deployments private when requested.
7. **Add and verify the home-screen icon.** When device access permits, install the app or add a home-screen shortcut with the project name and appropriate icon, pointing directly to the working app rather than a repository, editor, or temporary development page. Check that tapping it opens the correct project and that its primary flow works. For PWAs, check the manifest, app name, icons, display mode, and HTTPS/install requirements. Do not encode localhost or secrets in a QR code. If direct tablet access is unavailable, prepare the icon assets/manifest and give concise, exact steps for the user to finish pinning it; mark this as unverified until they open it.
8. **Optional hands-free launch.** When requested, prefer the device's supported assistant to open the ChatGPT app or the project shortcut, then enable the app's supported start-in-voice option when available. For ChatGPT on supported Android app versions, direct the user to Settings → Voice → Start with Voice; Background conversations can keep an active voice conversation going while using other apps or with the screen locked. Verify on the actual tablet. Do not promise a custom always-listening wake word or install a third-party background microphone service without explicit user request and confirmation of its permissions and privacy behavior.
9. **Test on the target.** When tablet control is available, open the installed app or home-screen icon and test the primary flow, navigation, touch interactions, reload behavior, and voice launch if requested. Otherwise use browser/device emulation at tablet sizes, clearly list what passed there, and keep physical-device setup and checks outstanding.
10. **Iterate and report.** When testing finds an issue, fix it, push the update, refresh the preview/package, and retest. Report the project/repository/branch/commit, tests and target checks completed, the exact tablet launch path, whether the home-screen icon was opened successfully, and any remaining blocker. A project is only reported complete when the completion standard above is satisfied.

## Rules

- Continue through reversible implementation, setup, and testing without asking for repeated confirmation.
- Ask one focused question only when a consequential choice cannot be inferred, such as which of several repositories to use or whether the user wants public production deployment.
- Do not request passwords, personal access tokens, signing keys, or private credentials in chat. Use the authorized GitHub connection and secure environment-variable settings.
- Keep preview and production separate. Treat public production publishing, paid services, data migrations, and irreversible changes with care and follow the user's explicit instructions.
- If a check cannot run, explain exactly which access, tool, device, or credential is missing and complete all independent work.
- Keep progress updates concise. Do not stop at a plan when implementation is authorized; keep configuring, pushing, and testing until done or blocked.
