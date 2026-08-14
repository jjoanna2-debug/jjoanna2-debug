# Jean-Claude Joanna

I build in public and care about work that is readable, testable, and easy to
trust.

This account is my GitHub lab: small repos, clean docs, checked-in proof, and
practical assisted-coding workflows that stay grounded in real tests instead of
big promises.

Right now the main public signal is simple: keep the lab Rust-first, keep the
checks honest, and remove stale work instead of letting it blur the picture.

## What To Look At

- [test-project-tbd](https://github.com/jjoanna2-debug/test-project-tbd) - a
  small Rust practice repo with CI, a Rust-native repository doctor, pinned
  workflow actions, secret/evidence guardrails, issue templates, and public repo
  hygiene.
- Open-source pull requests - scoped patches, green checks, and proof-first
  descriptions.
- This profile - the home base for current experiments, cleanup work, and public
  learning.

## What I Care About

- clear first pages that make a repo easy to trust;
- boring public hygiene in the repos that need it: licenses, security notes,
  support paths, issue templates, and CI;
- guardrails that fail closed before secrets, private files, or sloppy workflows
  become public history;
- small patches with proof, not giant mystery drops;
- writing that feels human and useful;
- learning fast without making the workspace messy.

## Current Lab

[test-project-tbd](https://github.com/jjoanna2-debug/test-project-tbd) is my
public practice repo.

It is deliberately small: a Rust starter, GitHub Actions checks, issue
templates, repo policy files, a Rust-native repository doctor, and documentation
for how the project is organized. The point is not to look huge. The point is to
make the basics clean enough that someone can open it and understand what is
going on.

## Recent Focus

Fourteen external pull requests have now merged across seven open-source
projects:

- landing a merged documentation and accessibility-guidance pass for
  make-interfaces-feel-better
  ([jakubkrehel/make-interfaces-feel-better#1](https://github.com/jakubkrehel/make-interfaces-feel-better/pull/1)),
  covering Codex installation, font-family scope, context-specific hit areas,
  and a machine-detectable MIT license;
- landing approved and merged GoalBuddy Codex-runtime patches:
  [#28](https://github.com/tolibear/goalbuddy/pull/28),
  [#29](https://github.com/tolibear/goalbuddy/pull/29), and
  [#30](https://github.com/tolibear/goalbuddy/pull/30);
- landing a merged GoalBuddy local-board rendering fix for multiple active tasks
  ([tolibear/goalbuddy#34](https://github.com/tolibear/goalbuddy/pull/34));
- landing a merged liteparse batch-output directory fix
  ([run-llama/liteparse#313](https://github.com/run-llama/liteparse/pull/313));
- landing a merged Snapzy macOS patch for Quick Access dismiss lag
  ([duongductrong/Snapzy#256](https://github.com/duongductrong/Snapzy/pull/256)),
  included before the `v1.23.0` release line;
- landing three approved and merged Markdown Preview improvements: Quick Look
  asset containment
  ([pluk-inc/markdown-preview#152](https://github.com/pluk-inc/markdown-preview/pull/152))
  and native trackpad pinch zoom
  ([pluk-inc/markdown-preview#156](https://github.com/pluk-inc/markdown-preview/pull/156)),
  both included in
  [release 0.0.29](https://github.com/pluk-inc/markdown-preview/releases/tag/v0.0.29),
  plus reliable full-document selection in long edit-mode files and standard
  Shift-selection in read mode
  ([pluk-inc/markdown-preview#185](https://github.com/pluk-inc/markdown-preview/pull/185)),
  credited in
  [release 0.0.34](https://github.com/pluk-inc/markdown-preview/releases/tag/v0.0.34);
- landing a merged Impeccable live-mode toast race fix
  ([pbakaus/impeccable#271](https://github.com/pbakaus/impeccable/pull/271));
- shipping the Apple Mail MCP v2.8.10 hardening pass
  ([sweetrb/apple-mail-mcp#97](https://github.com/sweetrb/apple-mail-mcp/pull/97)),
  covering account-bound IMAP operations, SMTP sender allowlisting, bounded
  inline attachments, and canonicalized attachment-save containment; the owner
  verified 392 unit tests, 47 integration tests, and a reproducible bundle
  before publishing
  [release v2.8.10](https://github.com/sweetrb/apple-mail-mcp/releases/tag/v2.8.10);
- completing Apple Mail MCP's dev-only `brace-expansion` remediation in two
  evidence-backed steps: API-compatible v1 hardening
  ([sweetrb/apple-mail-mcp#119](https://github.com/sweetrb/apple-mail-mcp/pull/119))
  without suppressing the advisory or forcing an incompatible major version
  through ESLint's dependency path, followed by the complete v1/v5 sequence
  bounds after the repository's supply-chain age gate
  ([sweetrb/apple-mail-mcp#123](https://github.com/sweetrb/apple-mail-mcp/pull/123));
  the owner credited the 10,000-zero reproduction as decisive proof, added an
  independent v5 floor, and explicitly credited the original finding while
  porting it to
  [Apple Notes #113](https://github.com/sweetrb/apple-notes-mcp/pull/113),
  [Apple Numbers #49](https://github.com/sweetrb/apple-numbers-mcp/pull/49), and
  [Apple Photos #60](https://github.com/sweetrb/apple-photos-mcp/pull/60). The
  credit now appears in all four repositories' changelogs, and the downstream
  fix has shipped in
  [Apple Numbers v1.1.12](https://github.com/sweetrb/apple-numbers-mcp/releases/tag/v1.1.12)
  and
  [Apple Photos v2.1.6](https://github.com/sweetrb/apple-photos-mcp/releases/tag/v2.1.6);
- making the profile itself a useful entry point instead of a billboard;
- keeping the main lab Rust-first instead of accidentally letting helper code
  define the repo;
- tightening repository structure checks, secret/evidence guardrails, and cleanup
  habits;
- keeping CI simple, pinned, and honest;
- documenting local setup and GitHub workflow habits;
- using assisted coding tools while keeping authorship, review, and
  verification explicit.

## Current Open Work

As of August 14, 2026, seventeen external pull requests are open and tracked
against their live upstream state. The twelve Apple Mail MCP entries are all
open, Ready for review, mergeable, and required-check green; they are not
merged, shipped, accepted, or maintainer-approved.

Apple Mail MCP runtime hardening:

- numeric batch scope is required to stay atomic ([#159](https://github.com/sweetrb/apple-mail-mcp/pull/159), head `2b3244dd9afe1d253d1649627766aa62eedff0ee`; local 40 files/573 tests);
- ambiguous message IDs are refused ([#160](https://github.com/sweetrb/apple-mail-mcp/pull/160), head `1e303bc6f30a248f431e3cec7d33741eeb7735df`; local 41/575);
- attachment overwrites are prevented ([#161](https://github.com/sweetrb/apple-mail-mcp/pull/161), final head `d8c813c53c444c745558371c63063926d519b776`; local 40/575; fresh CodeQL reports no new alerts);
- IMAP attachment fetches are capped ([#162](https://github.com/sweetrb/apple-mail-mcp/pull/162), head `714925fbf685f3277b4a7d5bb9201c95e2df2a3d`; local 40/575);
- IMAP deletes remain recoverable ([#163](https://github.com/sweetrb/apple-mail-mcp/pull/163), head `5c7512d6c27f1323f57aa9ef7505247e69f0011f`; local 40/574);
- new mail rules default to disabled ([#164](https://github.com/sweetrb/apple-mail-mcp/pull/164), head `c05a933a2b358761789a17d873a03ef818b1d94e`; local 41/575);
- mail transport encryption is required ([#165](https://github.com/sweetrb/apple-mail-mcp/pull/165), head `16b7bc575a98c864efe7b1bd3287476f6fcc673d`; local 40/574); and
- outbound attachment reads are constrained ([#168](https://github.com/sweetrb/apple-mail-mcp/pull/168), head `0410e9fc74b0ee15324fd6b59b25689f75e37955`; local 41/570).

Apple Mail MCP governance and development assurance:

- repository threat model ([#158](https://github.com/sweetrb/apple-mail-mcp/pull/158), head `1256fcabb4df4755bc81ec309908e40ba8caa9ef`; local 40/573);
- Codex MCP runtime pin ([#166](https://github.com/sweetrb/apple-mail-mcp/pull/166), head `52e78cbedb05da7a0a1d1e4c126859cb86173005`; local 40/573);
- npm dev-dependency auto-merge governance ([#167](https://github.com/sweetrb/apple-mail-mcp/pull/167), head `8e721861658a114e4f01fff0fc757f96c9091bfb`; local 40/573); and
- shared validation schemas and security-test contract ([#169](https://github.com/sweetrb/apple-mail-mcp/pull/169), head `8afcf67f95101140436e5cc1ea3f88d8f81cd1d2`; local 40/575).

The remaining five external pull requests are:

- preventing a native macOS Transmission quit hang by moving blocking UPnP
  gateway validation off the session thread; the August 2 revision is rebased,
  narrowed to the single UPnP source file, and validated by 583 tests plus a
  universal arm64/x86_64 macOS build
  ([transmission/transmission#8984](https://github.com/transmission/transmission/pull/8984));
- correcting IINA's Open URL failure message, playlist-relative paths, and
  plugin default-branch update checks
  ([#6189](https://github.com/iina/iina/pull/6189),
  [#6190](https://github.com/iina/iina/pull/6190), and
  [#6191](https://github.com/iina/iina/pull/6191));
- extending Daytona's Sapat provider guide with current registry architecture,
  validation, and security boundaries
  ([daytonaio/content#181](https://github.com/daytonaio/content/pull/181)).

## Current Product Reports

I also keep evidence-bounded product reports current instead of treating issue
filing as the finish line. As of August 14, three Codex reports remain open after
focused July 22 routing requests to maintainers with demonstrated subsystem
ownership:

- ChatGPT Desktop resetting the bundled Computer Use MCP server to disabled
  while the plugin remains enabled
  ([openai/codex#34807](https://github.com/openai/codex/issues/34807));
- a completed Codex Security scan becoming impossible to close after its
  app-managed temporary artifacts disappear
  ([openai/codex#33994](https://github.com/openai/codex/issues/33994));
- the official LinkedIn connector returning an upstream `403 IP not authorized`
  and then masking it with a template-loading failure
  ([openai/codex#33951](https://github.com/openai/codex/issues/33951));

The former mobile Remote Control report
([openai/codex#22773](https://github.com/openai/codex/issues/22773)) was closed
as not planned on August 6, 2026 and is no longer counted as open.

None has received a maintainer response. The profile records that verified
state and does not present routing requests as acknowledgements or fixes.

## How I Work

- I keep changes small enough to review.
- I run the checks that prove the claim.
- I would rather delete stale work than let it rot.
- I like clear docs, plain language, and boring reliability.

## Connect

I like practical builders, careful reviewers, and people who enjoy turning messy
first drafts into something shippable.

The best starting point is this GitHub profile:
[github.com/jjoanna2-debug](https://github.com/jjoanna2-debug). If the work
here feels aligned, say hi through the contact path where you found me.
