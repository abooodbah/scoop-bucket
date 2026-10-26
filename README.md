# Lean apps Scoop bucket

Scoop manifests for three free, read-only viewers for Windows:

| App | What it opens | Command |
| --- | --- | --- |
| [LeanMark](https://github.com/abooodbah/leanmark) | Markdown files | `leanmark` |
| [LeanDoc](https://github.com/abooodbah/leandoc) | Word documents | `leandoc` |
| [LeanRows](https://github.com/abooodbah/leanrows) | Large CSV, TSV, JSON Lines and log files | `leanrows` |

## Install

```powershell
scoop bucket add lean https://github.com/abooodbah/scoop-bucket
scoop install lean/leanmark
scoop install lean/leandoc
scoop install lean/leanrows
```

LeanMark and LeanDoc need the Microsoft Edge WebView2 Runtime, which Windows 11
includes. On Windows 10, install it with `scoop install extras/webview2-runtime`
if it is missing.

The builds from GitHub are not code signed, so Windows may show a SmartScreen
warning the first time an app starts. The Microsoft Store versions are signed
by Microsoft:
[LeanMark](https://apps.microsoft.com/detail/9MSS4WKJ22ZV),
[LeanDoc](https://apps.microsoft.com/detail/9NSM04BJL6F6),
[LeanRows](https://apps.microsoft.com/detail/9NMV8GKJXSN0).

## Settings

Each app keeps its settings in the registry under `HKCU\Software\<App>`.
Scoop cannot carry registry settings, so they stay in place across updates and
after `scoop uninstall`.

## Updates

Each manifest has `checkver` and `autoupdate`, so a new GitHub release can be
picked up with Scoop's `checkver.ps1 -Update`.

## License

The manifests are MIT licensed, like the apps.
