# Antique Shop runtime assets

Static illustration and Japanese runtime dependencies for **白薔薇の古道具屋**.
The character card, worldbook, private preset, user accounts, conversations and connection credentials are not included.

Release: `v2026.10.30.1`. Use the immutable release tag in character-card imports.

- `assets/opening.webp`: 1672 × 941 illustration, 335488 bytes. Retained from the owner-provided Japanese coastal antique-shop edition. Loaded externally; never embedded as a data URL.
- `vendor/mvu.js`: Japanese localization of the exact MagVarUpdate artifact used by the source card. Upstream checkout `d03b7dc8a6ebf9bd611c7e2dc91f3b35462deebc`, upstream artifact SHA-256 `a5d6166d43a78c7fad05669864efd76852f58eea905814dcd89f8e1b29fa4b27`. Original artifact build identifier: `7574d47`.
- `vendor/mvu-zod.js`: same source Zod adapter behavior, with Japanese diagnostics.
- `vendor/modules/`: recursively mirrored ESM imports. Relative imports keep the entire static dependency graph inside this release. `DEPENDENCIES.json` records origins, resolved versions and hashes.
- `source/MagVarUpdate/`: maintainable localized source. The current upstream incremental-repair, trigger-tag, minimum-length and thinking-level functionality is preserved. Japanese UI has 504 messages.

Japanese settings use `mvu_jp_settings`, store `MVU変数フレームワーク`, and modes `主AI追従出力` / `追加モデル解析`. Known historical settings names are accepted only at the input boundary; canonical Japanese keys win conflicts. Unknown fields, false/zero, profile names and credentials are retained without text replacement. The shared script registration identity remains unchanged for coexistence. Seven actions are preserved, including incremental repair.

Build: from `source/MagVarUpdate`, `npm ci --ignore-scripts --legacy-peer-deps`, then `CI=true npm run build`. The task's build required Ajv 8 to satisfy ajv-keywords 5. ESM downloads are mirrored after compilation; no provider requests are made during build or validation.

Upstream copyright notices, bundled license notices and available license texts are retained. See `LICENSES.json`, `LICENSE-MagVarUpdate`, `LICENSE-tavern_resource` and `licenses/`. Upstream Chinese comments and compatibility aliases are technical provenance, not Japanese UI text.
