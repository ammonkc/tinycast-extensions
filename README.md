# tinycast-extensions

Personal extensions for [Tinycast](https://github.com/abue-ammar/tinycast). Each folder is an
independent Raycast style extension with its own `package.json` and `package-lock.json`. There are
no workspaces, because Tinycast fetches only the folder it installs.

| Extension | Purpose |
| --- | --- |
| `developer-utilities` | Clean node_modules, git standup, open worktree, AWS SSO login |
| `idl-docker` | Start and stop IDL Docker containers |
| `obsidian-prompts` | Obsidian implementation prompts |
| `window-edges` | Size preserving window edge movements (Apple Silicon macOS) |

## Install

In Tinycast, open Settings > Extensions > Install New > Install from GitHub and paste a link:

```
https://github.com/ammonkc/tinycast-extensions/tree/main/developer-utilities
https://github.com/ammonkc/tinycast-extensions/tree/main/idl-docker
https://github.com/ammonkc/tinycast-extensions/tree/main/obsidian-prompts
https://github.com/ammonkc/tinycast-extensions/tree/main/window-edges
```

Tinycast builds the extension on your Mac and keeps only the build. It needs Node.js 22.22.2 or
newer and a package manager (pnpm, Bun, Yarn or npm) that Tinycast can find. Custom search paths
are available in the same panel.

## Updating

Tinycast does not check GitHub installs for updates. Reinstall from the same link to update.

## Notes

`idl-docker` runs the `idl-up` and `idl-down` helpers from my
[dotfiles](https://github.com/ammonkc/dotfiles) (`packages/bin`), so they must be on the PATH it
expects.

## Development

From an extension directory:

```
npm ci
npm run lint
npm test
npm run build
```

CI runs this for every extension. `window-edges` runs on macOS because it builds a native helper.
