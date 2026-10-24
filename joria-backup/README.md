# Joria backup

Each `notes/<id>.md` is one complete note: a Joria-owned YAML frontmatter block
followed by the original Markdown body. The header contains `joria_format`,
`joria_id`, `joria_created_at`, `joria_updated_at`, and `joria_pinned`.
Dates are quoted UTC ISO 8601 strings with millisecond precision.

IDs are portable across computers. Do not change IDs or the manifest version.
To delete a note, remove its Markdown file. Edit note text below the first closing
`---` line; the next pull/sync imports it. Commit your edits to `main` before pulling.

Joria always adds its own outer header, even when your original text already starts
with `---` or imitates frontmatter. Import removes only that one outer header and
restores the body without trimming whitespace or changing line endings. Original
frontmatter in the body remains your note text. Do not remove or duplicate the
Joria header fields; malformed headers stop syncing before local notes are changed.

Joria merges independent notes. If the same note changed on both
sides, the Conflict Resolution choice decides which complete record to keep.
Before the first sync on a computer, local and remote records are combined.

AI conversations, API keys, app preferences, SQLite files, and search vectors are excluded.
Unrelated files outside this directory are preserved.
