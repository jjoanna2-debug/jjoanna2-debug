# Jean-Claude Joanna

I work on security and reliability in open-source software, mainly in Rust,
Swift and macOS, TypeScript and Node.js, Python, and GitHub Actions.

I like getting to the bottom of bugs: mail sent from the wrong account,
files written where they shouldn't be, a dashboard exposed to the network,
or an app that hangs on shutdown. I work through the cause, the fix, and the
tests needed to keep it from happening again.

Here are some of my contributions and the work still awaiting a decision.

## Selected Open-Source Work

I've authored 30 merged pull requests across 11 open-source projects.
Maintainers have also adopted and ported my work across Apple Mail, Numbers,
Photos, and Notes.

### Security and trust boundaries

- **Apple Mail schema security:** I migrated the vulnerable Zod 3 dependency
  to patched Zod 4 while preserving all 52 tools' schema contracts, integer
  validation, and string-valued template records. Rob Sweet carried my
  [#326](https://github.com/sweetrb/apple-mail-mcp/pull/326) forward unchanged in
  [#327](https://github.com/sweetrb/apple-mail-mcp/pull/327), which merged with me
  credited as co-author. He verified a byte-identical rebuild and live IMAP
  parity; Node 20, 22, and 24 checks, IMAP integration, the version guard, and
  CodeQL passed. The change shipped in
  [v2.20.29](https://github.com/sweetrb/apple-mail-mcp/releases/tag/v2.20.29).

- **Zod migration across the Apple MCP projects:** Rob Sweet adapted my approach
  for [Apple Numbers #106](https://github.com/sweetrb/apple-numbers-mcp/pull/106),
  [Apple Photos #114](https://github.com/sweetrb/apple-photos-mcp/pull/114), and
  [Apple Notes #307](https://github.com/sweetrb/apple-notes-mcp/pull/307).
  All three merged on October 24, with each PR crediting my original work.
  The ports preserve the existing schemas and integer behavior across 26
  Numbers tools, 21 Photos tools, and 89 Notes tools. Numbers shipped in
  [v1.2.11](https://github.com/sweetrb/apple-numbers-mcp/releases/tag/v1.2.11),
  Photos in [v2.1.22](https://github.com/sweetrb/apple-photos-mcp/releases/tag/v2.1.22),
  and Notes in [v2.15.11](https://github.com/sweetrb/apple-notes-mcp/releases/tag/v2.15.11).

- **Apple Mail SMTP delivery:** [#214](https://github.com/sweetrb/apple-mail-mcp/pull/214)
  shipped in [v2.17.8](https://github.com/sweetrb/apple-mail-mcp/releases/tag/v2.17.8).
  It fixed IMAP reply/forward routing, preserved reply-thread headers, rejected
  unrelated sending identities, and prevented silent transport fallback or lost
  forward content. The [maintainer's review](https://github.com/sweetrb/apple-mail-mcp/pull/214#issuecomment-5551476302)
  explains the cross-account sending issue and the regression tests.

- **Apple Mail MCP:** [#97](https://github.com/sweetrb/apple-mail-mcp/pull/97)
  hardened account-scoped mail operations, sender authorization, attachment
  limits, and file creation; the owner verified 392 unit tests, 47 integration
  tests, and a reproducible bundle before it shipped in [v2.8.10](https://github.com/sweetrb/apple-mail-mcp/releases/tag/v2.8.10).

- **Dependency security:** [#119](https://github.com/sweetrb/apple-mail-mcp/pull/119)
  and [#123](https://github.com/sweetrb/apple-mail-mcp/pull/123) completed the
  `brace-expansion` remediation across the legacy CommonJS and current paths.
  I included a 10,000-character reproduction to demonstrate the performance
  problem and kept the remediation compatible with existing callers.

- **Apple Mail hardening:** the August batch covered a repository threat model
  ([#158](https://github.com/sweetrb/apple-mail-mcp/pull/158)), atomic batch
  source pairing ([#159](https://github.com/sweetrb/apple-mail-mcp/pull/159)),
  ambiguous message IDs ([#160](https://github.com/sweetrb/apple-mail-mcp/pull/160)),
  exclusive attachment creation ([#161](https://github.com/sweetrb/apple-mail-mcp/pull/161)),
  bounded IMAP attachment reads ([#162](https://github.com/sweetrb/apple-mail-mcp/pull/162)),
  disabled-by-default mail rules ([#164](https://github.com/sweetrb/apple-mail-mcp/pull/164)),
  the Codex MCP runtime pin ([#166](https://github.com/sweetrb/apple-mail-mcp/pull/166)),
  constrained outbound attachment reads ([#168](https://github.com/sweetrb/apple-mail-mcp/pull/168)),
  and shared validation schemas ([#169](https://github.com/sweetrb/apple-mail-mcp/pull/169)).
  These changes shipped in [v2.10.31](https://github.com/sweetrb/apple-mail-mcp/releases/tag/v2.10.31).

- **Markdown Preview:** [#152](https://github.com/pluk-inc/markdown-preview/pull/152)
  fixed Quick Look asset containment and [#156](https://github.com/pluk-inc/markdown-preview/pull/156)
  added native trackpad pinch zoom, both credited in [v0.0.29](https://github.com/pluk-inc/markdown-preview/releases/tag/v0.0.29).
  [#185](https://github.com/pluk-inc/markdown-preview/pull/185) repaired
  large-document selection behavior in read mode and shipped in [v0.0.34](https://github.com/pluk-inc/markdown-preview/releases/tag/v0.0.34).

- **Downstream credit:** the Apple Mail maintainer credited the original
  dependency finding in maintainer-authored follow-through for [Apple Notes #113](https://github.com/sweetrb/apple-notes-mcp/pull/113),
  [Apple Numbers #49](https://github.com/sweetrb/apple-numbers-mcp/pull/49),
  and [Apple Photos #60](https://github.com/sweetrb/apple-photos-mcp/pull/60).

### Reliability and product behavior

- **GoalBuddy:** aligned runtime receipt contracts ([#28](https://github.com/tolimarchuk/goalbuddy/pull/28)),
  exposed residual Codex state ([#29](https://github.com/tolimarchuk/goalbuddy/pull/29)),
  added deterministic reset cleanup ([#30](https://github.com/tolimarchuk/goalbuddy/pull/30)),
  and fixed local-board rendering for multiple active tasks ([#34](https://github.com/tolimarchuk/goalbuddy/pull/34)).

- **liteparse:** [#313](https://github.com/run-llama/liteparse/pull/313)
  fixed batch-output path handling for nested input directories in both the Rust
  CLI and Python binding.

- **Snapzy:** [#256](https://github.com/duongductrong/Snapzy/pull/256)
  removed Quick Access dismissal lag by separating immediate UI removal from
  deferred cleanup.

- **Impeccable:** [#271](https://github.com/pbakaus/impeccable/pull/271)
  fixed a stale callback race that could let an older toast animate or remove a
  newer one.

- **Make Interfaces Feel Better:** I contributed licensing and interface polish
  in [#1](https://github.com/jakubkrehel/make-interfaces-feel-better/pull/1).

- **IINA:** [#6189](https://github.com/iina/iina/pull/6189) separates malformed
  URL input from a valid network URL that fails later while opening. The focused
  Swift fix merged into `develop` and closed [#6134](https://github.com/iina/iina/issues/6134).

- **Retransmission:** [#256](https://github.com/retransmission/retransmission/pull/256)
  moves blocking UPnP gateway validation off the session thread during
  shutdown, preserves miniupnpc ownership and diagnostic status, and handles
  an empty discovery result explicitly. Both core maintainers approved the
  final revision, and the full CodeQL and cross-platform Sanity matrix passed
  before merge. The squash commit credits me as its author.

- **TokenTelemetry:** [#299](https://github.com/VasiHemanth/tokentelemetry/pull/299)
  makes the default dashboard genuinely loopback-only, keeps explicit remote
  mode working, corrects the Node 20.9 minimum, updates vulnerable frontend
  dependencies, and clears the lint baseline. The owner independently
  reproduced the LAN exposure and verified both launch modes before merging;
  [#300](https://github.com/VasiHemanth/tokentelemetry/pull/300) landed first so
  lockfile-only dependency updates also reach existing installs. The merged
  change includes all three of my contributed commits.

- **LinkedIn MCP:** [#854](https://github.com/stickerdaniel/linkedin-mcp-server/pull/854)
  restored fresh-install initialization by keeping FastMCP below v4 while
  tool registrations still depended on the removed `exclude_args` argument.
  The fix aligned project, lock, and wheel metadata and added a regression test.
  It shipped in [v4.23.3](https://github.com/stickerdaniel/linkedin-mcp-server/releases/tag/v4.23.3),
  whose notes feature #854 under Bug Fixes and name me as a new
  contributor.

- **LinkedIn MCP plugin and test reliability:** [#863](https://github.com/stickerdaniel/linkedin-mcp-server/pull/863)
  added the opt-in Codex plugin released in [v4.24.0](https://github.com/stickerdaniel/linkedin-mcp-server/releases/tag/v4.24.0),
  whose release notes credit me. The plugin keeps its MCP package
  pin synchronized with releases and preserves independent enablement. The
  separate [#865](https://github.com/stickerdaniel/linkedin-mcp-server/pull/865)
  isolates terminal and Python startup-hook tests from host settings without
  changing production behavior. Both merged with all 14 final-head checks
  passing and closed their linked issues.

## Current Upstream Work

As of October 24, 2026, I have four pull requests awaiting upstream
decisions.

- **Transmission [#8984](https://github.com/transmission/transmission/pull/8984):**
  my shutdown fix is still open there. The same fix has already merged in
  Retransmission [#256](https://github.com/retransmission/retransmission/pull/256).

- **IINA [#6190](https://github.com/iina/iina/pull/6190) and [#6191](https://github.com/iina/iina/pull/6191):**
  focused fixes for portable playlist paths and plugin default-branch updates.
  Both remain open. #6190 is mergeable against `develop`, with the
  path-compatibility boundary still under discussion; #6191 now has merge
  conflicts and awaits plugin-maintainer review. Their CI and spelling
  workflow runs ended with a failure status without executing any jobs,
  so they provide no hosted validation.

- **Daytona [#181](https://github.com/daytona/content/pull/181):** a Sapat
  provider guide covering endpoint control, credentials, generated-artifact
  cleanup, registry contracts, and bounded async polling. The PR is open and
  mergeable with a passing DCO check.

## Featured Repository

[`test-project-tbd`](https://github.com/jjoanna2-debug/test-project-tbd) is
my Rust 2024 lab for repository tooling and automation. It has no runtime
dependencies, uses Rust 1.97.1, and requires its `Repository smoke test` check.

After 19 focused changes merged as [PRs #8–#26](https://github.com/jjoanna2-debug/test-project-tbd/pulls?q=is%3Apr+author%3Ajjoanna2-debug),
the repository doctor provides:

- bounded repository traversal and bounded text reads, with content-aware
  handling for text, binary files, and misleading extensions;
- provider-specific credential signatures, calibrated generic secret detection,
  and maintained internal precision, recall, F1, and average-precision floors;
- GitHub Actions permission, trigger, checkout, and immutable-reference policy,
  plus deterministic text, JSON, and native GitHub annotation output;
- checks that defend the repository's own CI and Dependabot guarantees from
  silent regression.

The [Basic Checks run](https://github.com/jjoanna2-debug/test-project-tbd/actions/runs/31983407142)
for the current main revision passed.

## Bug Reports

My report on [Proton Mail's iOS regressions](https://github.com/ProtonMail/ios-mail/issues/109)
remains open.

I closed my Codex reports on the [desktop configuration reset](https://github.com/openai/codex/issues/34807)
and the [stuck security scan](https://github.com/openai/codex/issues/33994).

## What I Work On

- focused security review, threat modeling, and fail-closed repository or
  filesystem boundaries;
- Rust tooling, Swift and native macOS defects, and TypeScript, Node.js, and
  Python maintenance;
- concurrency, lifecycle, race-condition, dependency, and CI/CD fixes;
- technical documentation and release evidence checked against the
  implementation.

## Working Standard

I keep patches focused, include a reproduction when I can, and test the behavior
I'm changing. I update the documentation alongside the implementation so the
next person doesn't have to reconstruct what happened.

## Sponsorship and Engineering Work

I'm available for security reviews, difficult bug fixes, repository maintenance,
CI improvements, and technical writing for developer tools. Sponsorship helps
me spend more time on open-source work.

Professional contact:
[LinkedIn](https://us.linkedin.com/in/jeanclaudejoanna)

_Updated October 24, 2026._
