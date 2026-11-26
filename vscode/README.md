# LILYTHIUM Mainframe Access

A phosphor-green terminal theme: `#5CF79B` on a black-green ground, one hue, square edges,
JetBrains Mono for code.

Part of LILYTHIUM, a set of places ported to whatever surface needs a face. This package is
the colour-theme edition, so it can be found and installed from a marketplace.

## Install in VS Code

Extensions → search **LILYTHIUM Mainframe Access** → Install → then pick it in
**File → Preferences → Color Theme** (`Ctrl+K Ctrl+T`).

## Install in Hermes Desktop

Hermes imports VS Code colour themes directly: **Settings → Appearance → Browse VS Code
marketplace**, search the name, install. The importer maps the six workbench keys that carry
a palette (background, foreground, accent, elevated surface, sidebar, error) and derives the
rest.

That import gives you the colours. It does not give you the plates: the Hermes skin builds
one lit glass plate per tool call, a hotter prompt and composer, and a lit sidebar seam,
which a colour theme has no way to express. For the full treatment install the skin from the
[hermes-skins repository](https://github.com/IonShieldQuad/hermes-skins).

## Palette

| Role | Value |
|---|---|
| Accent | `#5CF79B` |
| Accent ink | `#BCF7CE` |
| Body text | `#C8EED4` |
| Ground | `#020704` |
| Panel | `#071009` |
| Alert | `#FF7070` |
| Warning | `#FFC04D` |

## Building

```bash
cd vscode
npx @vscode/vsce package
```

That writes `lilythium-mainframe-access-1.0.0.vsix` next to `package.json`: a plain zip holding
`extension/package.json`, the theme JSON, the readme and the licence.

## Publishing

Needs an Azure DevOps personal access token with **Marketplace → Manage** on the account that
owns the publisher. Nothing in this repo stores one.

```bash
# once, in the browser: create the publisher at https://marketplace.visualstudio.com/manage
npx @vscode/vsce login ionshieldquad        # paste the token when asked
npx @vscode/vsce publish --no-dependencies  # from vscode/, bumps nothing, ships package.json version
```

`vsce login` keeps the token in `~/.vsce`, not in the repo. Bump `version` in `package.json` for
every later publish; the Marketplace rejects a version it has already seen.

After the listing is live, Hermes users can reach it from **Settings → Appearance → Browse VS
Code marketplace** by searching `lilythium` or the extension id
`ionshieldquad.lilythium-mainframe-access`.

## License

MIT.
