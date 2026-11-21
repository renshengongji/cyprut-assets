# Cloud plugin changelogs

Write one UTF-8 JSON file per language in
`launcher/plugins/<id>/versions/<version>/changelog/<locale>.json`, such as `en-US.json` or `zh-Hans.json`.

```json
{
  "added": ["Add a replay speed setting."],
  "fixed": ["Show the correct score during replays."]
}
```

The top-level object accepts four case-sensitive categories, displayed in this order:

| Category | Use for |
| --- | --- |
| `added` | New features or options |
| `changed` | Changes to existing behavior |
| `fixed` | Bug fixes |
| `removed` | Removed features or options |

Use an array of non-blank plain-text strings for each category. Do not include
Markdown or bullet prefixes. Entries within a category keep their array order,
regardless of the order of the categories in the file. Omit unused categories
and do not create a file for a version or language with no notes.

Launcher reads the current language first, then `en-US.json` if the requested
file is missing, empty of entries, or invalid. A release without usable notes
can still be installed. Changelogs are not part of `manifest.json` or `version.json`.
