# cc-notify

Animated desktop notifications for [Claude Code](https://code.claude.com/docs/en/overview). A little Claude buddy pops up when a task finishes, fails, runs low on context, or needs your permission, and you can answer **Allow / Deny** right from the popup.

Nothing extra to install.

## Install

```
/plugin marketplace add xd3an/cc-notify
/plugin install notify@cc-notify
```

Restart Claude Code, then try `/notify test all`.

## Notifications

| When | Popup |
| --- | --- |
| Turn finishes | First line of the answer, duration, tool count, branch |
| Tool fails | The error (at most one every 10 s) |
| Permission needed | The command, with **Allow** / **Deny** buttons |
| Context fills up | At 80% and 90% |
| Session starts | Project and branch |

## Platforms

- Windows 10 / 11
- macOS (untested)
- Linux (untested)

Tried it on macOS or Linux? Issues and PRs welcome.

## Commands

```
/notify                 status
/notify test [all]      sample popup(s)
/notify mute [30m|2h]   mute for a while
/notify off | on        turn off / back on
/notify lang <code>     auto, en, zh-TW, zh-CN, ja
```

## Settings

Set these in the `/plugin` menu.

| Setting | Default | |
| --- | --- | --- |
| `language` | `auto` | Follows your system language |
| `contextWarning` | `80` | Context % that triggers a warning; `0` turns it off |
| `permissionButtons` | `true` | Allow / Deny on the Windows popup |

## Develop

```bash
claude --plugin-dir .      # load from disk, reloads on save
claude plugin test .
```

## License

[MIT](./LICENSE)
