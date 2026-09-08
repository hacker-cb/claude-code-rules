# GitHub / GitLab language

Low priority — a project's own convention (CLAUDE.md, existing repo history)
always wins over this default.

**When in doubt, look at recent history.** Before writing anything, check the
language used in the repo's last few issues, PRs, and commits, and match it. This
overrides the defaults below whenever the repo shows a clear existing convention.

Defaults when there's nothing to go by (e.g. an empty or brand-new repo):
- Issues (titles, descriptions, comments): Russian
- PR body / comments: Russian
- PR title: English
- Commit messages: English

**Keywords the forge parses stay in English**, whatever language the prose
around them is in — in issues, PR bodies and commit messages alike. A translated
keyword fails silently: nothing errors, the thing simply does not happen. GitHub
matches `close`/`closes`/`closed`, `fix`/`fixes`/`fixed`,
`resolve`/`resolves`/`resolved`; GitLab those plus `implement*`. The same holds
for GitLab quick actions (`/close`, `/assign @user`), GitHub alerts (`> [!NOTE]`)
and commit trailers (`feat:`, `Co-authored-by:`, `[skip ci]`).

If the history is mixed or ambiguous and the defaults don't obviously fit, ask
the user which language to use rather than guessing.
