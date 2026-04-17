# Build for iOS: Developer Guide

*For developers using Codex to scaffold, build, and debug SwiftUI apps on iPhone and iPad.*

---

## What the use case is saying

OpenAI’s iOS use case is explicit: use Codex to scaffold, build, and debug SwiftUI apps for iPhone and iPad.

The recommended posture is:

- stay CLI-first
- use `xcodebuild` or Tuist for the build loop
- bring in XcodeBuildMCP when you need scheme discovery, simulator output, screenshots, or UI automation
- add focused SwiftUI skills when the task gets more specialized

---

## Best fit

This is strongest for:

- greenfield SwiftUI apps
- existing iPhone or iPad projects that need controlled iteration
- long-running UI tasks that should stay agentic instead of depending on Xcode GUI poking

The page calls this work "Advanced" with a roughly 1 hour horizon.

---

## Recommended workflow

The page’s workflow is roughly:

1. Scaffold a SwiftUI app or inspect the existing project.
2. Keep the loop CLI-first.
3. Build and run with `xcodebuild` or Tuist.
4. Use XcodeBuildMCP to list targets or schemes and capture simulator evidence when needed.
5. Reuse existing models, navigation, and shared utilities.
6. Iterate with a narrow validation loop before broadening the checks.

That keeps the agent from drifting into heavy-handed changes too early.

---

## Starter prompt shape

The page’s starter prompt is essentially:

```text
Scaffold a starter SwiftUI app and add a build-and-launch script.
Stay CLI-first.
Prefer xcodebuild; Tuist is okay if it helps.
If the repo already has an Xcode project, use XcodeBuildMCP to find the right scheme, build, launch, and capture screenshots as you iterate.
Reuse existing models, navigation, and shared utilities.
```

The important part is not the exact wording. It is the combination of scope, build loop, and verification.

---

## Verification habits

Codex should not just "make code changes" and hope.

Use:

- scheme discovery
- simulator output
- screenshots
- small build-and-launch loops
- specific checks for the change at hand

The page also suggests telling Codex whether it treated the task as a greenfield scaffold or an existing-project change.

---

## When to bring in the extras

The page points at the `Build iOS Apps` skill for:

- SwiftUI UI work
- Liquid Glass patterns
- runtime performance audits
- simulator debugging with XcodeBuildMCP

That is the point where generic coding help stops being enough and iOS-specific workflow starts paying off.

---

## Failure modes

Common mistakes:

- starting too broad
- not knowing the target scheme
- skipping simulator evidence
- using the GUI when the task should stay terminal-driven
- changing too many things before a narrow build passes

---

## Practical rule

Start with the smallest app slice that can prove the loop works.

Then widen the scope only after the first build, launch, and verification pass is solid.

---

*Source: OpenAI Codex use cases page, "Build for iOS"*
