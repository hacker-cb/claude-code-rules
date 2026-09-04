# GitHub / GitLab language

Low priority — a project's own convention (CLAUDE.md, existing repo history)
always wins over the language defaults below.

**When in doubt, look at recent history.** Before writing anything, check the
language used in the repo's last few issues, PRs, and commits, and match it. This
overrides the defaults below whenever the repo shows a clear existing convention.

Defaults when there's nothing to go by (e.g. an empty or brand-new repo):
- Issues (titles, descriptions, comments): Russian
- PR body / comments: Russian
- PR title: English
- Commit messages: English

If the history is mixed or ambiguous and the defaults don't obviously fit, ask
the user which language to use rather than guessing.

## Machine-read tokens are not text

Everything above is about prose. A forge also *parses* some of what you write,
and a parsed token is written in the form the parser matches, whatever language
surrounds it. This is not a default and nothing overrides it — no project
convention can make a regex match a translation.

These tokens read as ordinary prose, which is exactly why they get translated
along with the sentence around them, and the failure is silent: nothing errors,
nothing warns, the thing simply does not happen.

- **Closing keywords** — GitHub matches `close`/`closes`/`closed`,
  `fix`/`fixes`/`fixed`, `resolve`/`resolves`/`resolved` (case-insensitive,
  colon optional); GitLab those plus `implement*` and the `-ing` forms.
  «Закрывает #12» in a Russian PR body leaves the issue open.
- **GitLab quick actions** — `/close`, `/assign @user`, `/label ~bug`: commands,
  not sentences.
- **GitHub alerts** — `> [!NOTE]`, `[!TIP]`, `[!IMPORTANT]`, `[!WARNING]`,
  `[!CAUTION]`; a translated word renders as a plain blockquote.
- **Commit trailers, types and directives** — `feat:`, `BREAKING CHANGE:`,
  `Co-authored-by:`, `Signed-off-by:`, `[skip ci]`.
- **Bot commands** — `@dependabot rebase`, `@copilot`, `/review`.

Where a token's vocabulary is in doubt, read the forge's docs rather than
guessing: a self-managed instance can be configured to match something else.
