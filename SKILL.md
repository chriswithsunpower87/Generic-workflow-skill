---
name: github-vscode-tablet-ship
description: Build or update the user's apps and websites using the connected GitHub repository and VS Code workflow; configure for tablet use, preview on the tablet, and keep testing and fixing until the key flows work. Use for app or website builds, GitHub handoffs, VS Code implementation, tablet configuration, or project verification.
---

# GitHub, VS Code, and tablet delivery

Use this skill when building or updating an app or website and the user expects the work sent to GitHub, handled through VS Code, configured for their tablet, and tested through completion.

## Workflow

1. **Find the right project.** Inspect the current workspace, project instructions, Git remote, and relevant conversation context. Use GitHub tools to find the user's matching repository when available. Reuse the correct repo and branch; do not create a duplicate repository or overwrite unrelated work. If GitHub is not connected or the right repo cannot be identified, continue local implementation and ask only for the missing repo or access detail.
2. **Work through VS Code-compatible project files.** Inspect the framework, scripts, environment, and existing conventions. Make changes in the project source so they are reviewable and editable in VS Code. If the user is using GitHub Codespaces or VS Code for Web, provide/open the repository there when supported. Do not claim to control the user's VS Code window or device unless an active tool confirms that access.
3. **Configure for the tablet.** First determine whether the deliverable is a responsive web app, PWA, or native app. For web projects, implement tablet-sized layouts, touch-friendly controls, orientation behavior, and a sensible install path when useful. For native projects, configure the correct target device, build variant, and installation method. Preserve existing project behavior and styling.
4. **Build and verify locally or in the connected environment.** Follow the project's own setup instructions. Run its available lint, typecheck, test, and production-build commands. Launch it and inspect core flows at tablet viewport sizes. Fix errors, broken navigation, clipped layouts, unsafe configuration, and touch or keyboard problems, then rerun affected checks.
5. **Push to GitHub.** Keep secrets and private user data out of commits. Use environment variables or the hosting provider's secret store. Commit the verified changes to the intended branch and push with the available GitHub integration. Confirm the repository, branch, and commit result; never say a push succeeded unless the tool reports success.
6. **Make it open on the tablet.** For a website, use a reachable HTTPS preview/deployment when available. If using a local dev server, bind it to `0.0.0.0`, use the computer's LAN address, and verify the tablet can access the same network URL; `localhost` on the computer does not work on the tablet. For native apps, provide the tablet-compatible build/package and installation route supported by the platform. Do not deploy publicly when the user asked to keep it private.
7. **Test on the target.** When tablet control is available, open the app and test the primary flow, layout, touch interactions, navigation, and reload/install behavior. Otherwise use browser/device emulation at tablet sizes and clearly state that physical tablet testing remains for the user. Never imply an app was installed or tested on the physical device unless observed.
8. **Iterate to completion.** When testing finds an issue, fix it, push the updated source, refresh the preview or package, and retest. Continue the loop until the agreed key flows pass or a specific external blocker such as missing account access, credentials, device connection, or platform signing is identified.
9. **Report the result.** Summarize what was built, checks passed and not run, GitHub repo/branch/commit, how to open it on the tablet, and remaining blockers. Include a QR code only if it genuinely helps open a reachable preview URL; put the URL beside it as a fallback. Never encode localhost or secrets in a QR code.

## Rules

- Continue through reversible implementation and testing without asking for repeated confirmation.
- Ask one focused question only when a consequential choice cannot be inferred, such as which of several repositories to use or whether the user wants a public production deployment.
- Do not request passwords, personal access tokens, signing keys, or private credentials in chat. Use the authorized GitHub connection and secure environment-variable settings.
- Keep preview and production separate. Treat production publishing, paid services, data migrations, and irreversible changes with care and follow the user's explicit instructions.
- If a check cannot run, explain exactly which access, tool, device, or credential is missing and complete all independent work.
- Keep progress updates concise. Do not end at a plan when implementation is authorized; keep building, pushing, and testing until done or blocked.
