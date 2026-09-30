# Mantel — VS Code Theme

A VS Code colour theme built from the [Mantel Group brand guidelines](https://mantelgroup.com.au) (V1.1, 2025). Ships two variants:

- **Mantel Deep Ocean (Dark)** — Deep Ocean (`#002A41`) background with Sky Blue, Flamingo and teal accents.
- **Mantel Cloud (Light)** — Cloud (`#EEF9FD`) background with Ocean and darkened Flamingo accents, and Deep Ocean chrome.

## Palette

| Name       | Hex       | Role in the theme                                    |
|------------|-----------|------------------------------------------------------|
| Deep Ocean | `#002A41` | Editor background (dark), all chrome, primary text (light) |
| Ocean      | `#1E5E82` | Buttons, functions, links, selection                 |
| Flamingo   | `#D86E89` | Keywords, accents, badges, active-tab indicator      |
| Sky Blue   | `#81CCEA` | Cursor, functions and properties (dark), focus border |
| Cloud      | `#EEF9FD` | Editor background (light), foreground text (dark)    |

Pure black is never used — the darkest surfaces are a slightly deepened Deep Ocean (`#001E30`), per brand rules. On the light theme, syntax colours are darkened toward Ocean and Deep Ocean so they stay readable against Cloud, and the activity/status/title bars stay Deep Ocean to keep the signature Mantel look.

## Install

### From the GitHub release

Download the packaged extension from the [v1.0.0 release](https://github.com/tonyhallworth-mantel/mantel-vscode-theme/releases/tag/v1.0.0) and install it:

```bash
curl -fsSLO https://github.com/tonyhallworth-mantel/mantel-vscode-theme/releases/download/v1.0.0/mantel-theme-1.0.0.vsix
code --install-extension mantel-theme-1.0.0.vsix
```

Or download `mantel-theme-1.0.0.vsix` from the release page, then in the Extensions view choose **...** → **Install from VSIX...** and pick the file.

Then open the Command Palette (`Cmd/Ctrl+Shift+P`) → **Preferences: Color Theme** → pick **Mantel Deep Ocean (Dark)** or **Mantel Cloud (Light)**.

### From source (local)

1. Copy this folder into your VS Code extensions directory:
   - macOS / Linux: `~/.vscode/extensions/`
   - Windows: `%USERPROFILE%\.vscode\extensions\`
2. Reload VS Code.
3. Open the Command Palette (`Cmd/Ctrl+Shift+P`) → **Preferences: Color Theme** → pick **Mantel Deep Ocean (Dark)** or **Mantel Cloud (Light)**.

### Package as a `.vsix`

```bash
npm install -g @vscode/vsce
vsce package
code --install-extension mantel-theme-1.0.0.vsix
```

## Enable semantic highlighting

Both variants define semantic token colours. For the richest result, keep semantic highlighting on (it is on by default):

```json
"editor.semanticHighlighting.enabled": true
```

## Customise

Override individual colours in your `settings.json` without editing the theme:

```json
"workbench.colorCustomizations": {
  "[Mantel Deep Ocean (Dark)]": {
    "editor.background": "#002A41"
  }
}
```

## Notes

- Colours follow the Mantel V1.1 palette. Flamingo is used as an accent only (keywords, badges, the active-tab top border) — never as a large fill, per the guidelines.
- The theme files are JSONC; the `//`-prefixed keys are section separators and are ignored by VS Code.
