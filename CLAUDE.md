# Project notes

## Delivering files to the user

**Deliver the format that was asked for.** If the user says "Markdown," the artifact
they receive must still be Markdown when it lands. A destination that silently
transforms content (Google Drive converting `.md` to a Google Doc, a CMS rewriting
HTML, a paste target eating whitespace) has not delivered the format — it has
delivered something that reads like it.

**Check the write tool for a fidelity flag before uploading.** Many upload APIs
convert by default. Read the tool schema, not just the required fields:

- `mcp__Google_Drive__create_file` → set `disableConversionToGoogleType: true` for
  `.md`, `.txt`, `.csv`, and anything else whose markup matters. Without it,
  `text/markdown` and `text/plain` become `application/vnd.google-apps.document`
  and every `#`, `**`, `|`, and `>` is stripped. A `PreToolUse` hook in
  `.claude/settings.json` now blocks this call when the flag is missing.

**Verify the artifact after writing it, not just the tool's success response.** A
2xx means the bytes arrived, not that they arrived intact or in the right form.
Re-read the created file and confirm its actual type and that it ends where the
source ends. Uploads interrupted partway still return partial-success shapes.

**Splitting is a cost, not a feature.** Chunking a document for context limits makes
it harder to reference. Split only when a real limit forces it, use the fewest
pieces that clear the limit, and say why. If the whole thing fits, ship one file.

**Prefer the destination that preserves the artifact.** When a connector cannot
carry a file faithfully, say so and name the path that can (git, a direct file
transfer, a manual drag-and-drop) instead of degrading the deliverable to fit the
tool that happens to be wired up.
