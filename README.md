# Jean-Claude Joanna

I work on software security, reliability, and open-source maintenance across
Rust, Swift and macOS, TypeScript and Node.js, Python, and GitHub Actions.

My strongest work sits at the point where a vague failure becomes a precise,
reviewable change: isolate the defect, identify the trust boundary, make the
smallest complete fix, and prove it with tests, builds, static analysis, or a
reproducible field check. I care about patches that survive contact with real
maintainers, not code that merely looks plausible in a diff.

I build in public. The links below distinguish work merged upstream from work
that is still under review, so the profile stays useful as a portfolio and as a
record that maintainers can audit.

## Selected Open-Source Work

I have 28 authored external pull requests merged across eleven open-source
projects.

### Security and trust boundaries

- **Apple Mail SMTP delivery:** [#214](https://github.com/sweetrb/apple-mail-mcp/pull/214)
  shipped in [v2.17.8](https://github.com/sweetrb/apple-mail-mcp/releases/tag/v2.17.8).
  It repairs IMAP reply/forward routing, preserves reply-thread headers, rejects
  unrelated sending identities, and prevents silent transport fallback or lost
  forward content. The [maintainer credited the diagnosis and regression coverage](https://github.com/sweetrb/apple-mail-mcp/pull/214#issuecomment-5551476302),
  specifically recognizing the latent cross-account-send gap. GitHub records me
  as the [merge commit author](https://github.com/sweetrb/apple-mail-mcp/commit/0a75ee7c455d0f4d09bc2ad23386b4d6e61c1d1f);
  the release notes document the contributed fixes. The released tree exactly
  matches the tested PR head.
- **Apple Mail MCP:** [#97](https://github.com/sweetrb/apple-mail-mcp/pull/97)
  hardened account-scoped mail operations, sender authorization, attachment
  limits, and file creation; the owner verified 392 unit tests, 47 integration
  tests, and a reproducible bundle before it shipped in [v2.8.10](https://github.com/sweetrb/apple-mail-mcp/releases/tag/v2.8.10).
- **Dependency security:** [#119](https://github.com/sweetrb/apple-mail-mcp/pull/119)
  and [#123](https://github.com/sweetrb/apple-mail-mcp/pull/123) completed the
  `brace-expansion` remediation across the legacy CommonJS and current paths.
  The work kept the advisory visible, preserved API compatibility, and used a
  10,000-character reproduction plus an independent v5 floor to make the
  sequence-bound performance gap checkable.
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
  These merged changes were included in the historical [v2.10.31](https://github.com/sweetrb/apple-mail-mcp/releases/tag/v2.10.31)
  release milestone; that is not the current latest release.
- **Markdown Preview:** [#152](https://github.com/pluk-inc/markdown-preview/pull/152)
  fixed Quick Look asset containment and [#156](https://github.com/pluk-inc/markdown-preview/pull/156)
  added native trackpad pinch zoom, both credited in [v0.0.29](https://github.com/pluk-inc/markdown-preview/releases/tag/v0.0.29).
  [#185](https://github.com/pluk-inc/markdown-preview/pull/185) repaired
  large-document selection behavior in read mode and shipped in [v0.0.34](https://github.com/pluk-inc/markdown-preview/releases/tag/v0.0.34).
- **Downstream credit:** the Apple Mail maintainer credited the original
  dependency finding in maintainer-authored follow-through for [Apple Notes #113](https://github.com/sweetrb/apple-notes-mcp/pull/113),
  [Apple Numbers #49](https://github.com/sweetrb/apple-numbers-mcp/pull/49),
  and [Apple Photos #60](https://github.com/sweetrb/apple-photos-mcp/pull/60).
  Those are not PRs authored by me.

### Reliability and product behavior

- **GoalBuddy:** aligned runtime receipt contracts ([#28](https://github.com/tolibear/goalbuddy/pull/28)),
  exposed residual Codex state ([#29](https://github.com/tolibear/goalbuddy/pull/29)),
  added deterministic reset cleanup ([#30](https://github.com/tolibear/goalbuddy/pull/30)),
  and fixed local-board rendering for multiple active tasks ([#34](https://github.com/tolibear/goalbuddy/pull/34)).
- **liteparse:** [#313](https://github.com/run-llama/liteparse/pull/313)
  fixed batch-output path handling for nested input directories in both the Rust
  CLI and Python binding.
- **Snapzy:** [#256](https://github.com/duongductrong/Snapzy/pull/256)
  removed Quick Access dismissal lag by separating immediate UI removal from
  deferred cleanup.
- **Impeccable:** [#271](https://github.com/pbakaus/impeccable/pull/271)
  fixed a stale callback race that could let an older toast animate or remove a
  newer one.
- **Make Interfaces Feel Better:** [#1](https://github.com/jakubkrehel/make-interfaces-feel-better/pull/1)
  delivered the merged licensing and polish contribution that the earlier
  profile rewrite omitted.
- **IINA:** [#6189](https://github.com/iina/iina/pull/6189) separates malformed
  URL input from a valid network URL that fails later while opening. The focused
  Swift fix merged into `develop` and closed [#6134](https://github.com/iina/iina/issues/6134)
  without expanding into the separate `file://` acceptance path.
- **Retransmission:** [#256](https://github.com/retransmission/retransmission/pull/256)
  moves blocking UPnP gateway validation off the session thread during
  shutdown, preserves miniupnpc ownership and diagnostic status, and handles
  an empty discovery result explicitly. Both core maintainers approved the
  final revision, and the full CodeQL and cross-platform Sanity matrix passed
  before merge. The verified squash commit credits me as its author and links
  `jjoanna2-debug` again in its co-author trailer.
- **TokenTelemetry:** [#299](https://github.com/VasiHemanth/tokentelemetry/pull/299)
  makes the default dashboard genuinely loopback-only, keeps explicit remote
  mode working, corrects the Node 20.9 minimum, updates vulnerable frontend
  dependencies, and clears the lint baseline. The owner independently
  reproduced the LAN exposure and verified both launch modes before merging;
  [#300](https://github.com/VasiHemanth/tokentelemetry/pull/300) landed first so
  lockfile-only dependency updates also reach existing installs. The merged
  history credits `jjoanna2-debug` on all three contributed commits.
- **LinkedIn MCP:** [#854](https://github.com/stickerdaniel/linkedin-mcp-server/pull/854)
  restores fresh-install initialization by keeping FastMCP below v4 while the
  current tool registrations still use the removed `exclude_args` argument.
  The merged change aligns project, lock, and wheel metadata and adds a
  migration-trigger regression test. GitHub credits `jjoanna2-debug` on the
  verified merge commit. The fix shipped in [v4.23.3](https://github.com/stickerdaniel/linkedin-mcp-server/releases/tag/v4.23.3),
  whose notes feature #854 under Bug Fixes and name `@jjoanna2-debug` as a new
  contributor. PyPI 4.23.3 carries the corrected `fastmcp<4,>=3.4.4` range.

## Current Upstream Work

As of September 5, 2026, six authored external pull requests remain open. None
is presented as merged, shipped, or maintainer-approved.

- **LinkedIn MCP [#863](https://github.com/stickerdaniel/linkedin-mcp-server/pull/863)
  and [#865](https://github.com/stickerdaniel/linkedin-mcp-server/pull/865):**
  #863 packages an opt-in, version-pinned Codex plugin with independent MCP
  enablement and release synchronization; initialization and tool discovery
  expose all 19 tools without starting Chrome or moving focus. The separate
  test-only #865 isolates host terminal and Python startup-hook behavior; its
  full local suite passes 2,982 tests with 148 declared skips and zero failures.
  Both PRs include current upstream changes and remain open, mergeable, and
  fully green, with maintainer review pending.
- **Transmission [#8984](https://github.com/transmission/transmission/pull/8984):**
  remains open as the original Transmission integration path after the same
  focused fix merged in Retransmission [#256](https://github.com/retransmission/retransmission/pull/256).
  GitHub reports #8984 as mergeable but unstable, with no approving maintainer
  review or current check runs. The merged and verified delivery is the
  Retransmission port; this entry remains only because the original upstream PR
  is still open.
- **IINA [#6190](https://github.com/iina/iina/pull/6190) and [#6191](https://github.com/iina/iina/pull/6191):**
  focused fixes for portable playlist paths and plugin default-branch updates.
  Both are open and mergeable against `develop`. Maintainers are discussing the
  path-compatibility boundary for #6190, while #6191 awaits plugin-maintainer
  review; neither is presented as accepted upstream work.
- **Daytona [#181](https://github.com/daytona/content/pull/181):** a Sapat
  provider guide covering endpoint control, credentials, generated-artifact
  cleanup, registry contracts, and bounded async polling. The PR is open and
  mergeable with a passing DCO check.

The personal-fork validation PRs [#4](https://github.com/jjoanna2-debug/iina/pull/4),
[#5](https://github.com/jjoanna2-debug/iina/pull/5), and [#6](https://github.com/jjoanna2-debug/iina/pull/6)
merged into the fork's `develop` branch. #4 validated the change that later
merged upstream as IINA #6189; #5 and #6 remain supporting fork history for the
two open upstream reviews, not upstream acceptance or release evidence.

## Featured Repository

[`test-project-tbd`](https://github.com/jjoanna2-debug/test-project-tbd) is a
compact Rust 2024 repository for learning, testing, and experimentation. It is
not a production security product, scanner warranty, or security audit. The
current public `main` is `4a1b9f0`; the repository has no runtime dependencies,
uses an exact Rust 1.97.1 toolchain, and protects its `Repository smoke test`
check.

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

The current [Basic Checks run](https://github.com/jjoanna2-debug/test-project-tbd/actions/runs/31983407142)
passed. The repository is deliberately compact: the value is in the enforced
contract that security controls, documentation, and automation describe the
same system.

## Evidence-Bounded Reports

- [Codex #34807](https://github.com/openai/codex/issues/34807) and [#33994](https://github.com/openai/codex/issues/33994)
  remain open reports with evidence tied to reproducible desktop and scan-state
  failures.
- [ProtonMail iOS Mail #109](https://github.com/ProtonMail/ios-mail/issues/109)
  remains an open, unresolved regression report.
- [Codex #33951](https://github.com/openai/codex/issues/33951) is retained as
  historical context, but GitHub closed it as not planned on August 16, 2026;
  it is not counted as an open report.

## What I Work On

- focused security review, threat modeling, and fail-closed repository or
  filesystem boundaries;
- Rust tooling, Swift and native macOS defects, and TypeScript, Node.js, and
  Python maintenance;
- concurrency, lifecycle, race-condition, dependency, and CI/CD fixes;
- technical documentation and release evidence checked against the
  implementation.

## Working Standard

I keep changes narrow enough to audit, but complete enough to merge. Security
boundaries fail closed. Public claims are tied to evidence. Generated artifacts
are rebuilt and compared. Documentation is updated in the same change when the
contract moves. A green check is useful only when it validates the revision
actually under review.

## Sponsorship and Engineering Work

I am open to sponsorship, focused security reviews, repository hardening,
maintainer support, difficult bug fixes, CI modernization, and technical writing
for developer tools. A good engagement has a scoped review or patch,
reproducible verification, and durable handoff documentation. Sponsorship funds
more upstream work with public patches rather than private one-off output.

Professional contact:
[LinkedIn](https://us.linkedin.com/in/jeanclaudejoanna)

_Last reviewed: 2026-09-05._
