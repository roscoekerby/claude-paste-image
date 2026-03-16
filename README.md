# claude-paste-image

A Claude Code skill that lets you paste clipboard images directly into the CLI — no manual file saving needed.

## How it works

1. Copy/screenshot an image (Snipping Tool, `Win+Shift+S`, `Ctrl+PrtSc`, etc.)
2. In Claude Code, type `/paste-image`
3. Claude saves the clipboard image to a temp file and reads it automatically

## Installation

Copy `paste-image.md` to your Claude Code skills directory:

```
~/.claude/skills/paste-image.md
```

On Windows:
```
C:\Users\<you>\.claude\skills\paste-image.md
```

## Requirements

- Windows (uses `System.Windows.Forms` via PowerShell)
- Claude Code CLI

## Notes

- The temp file is saved to `%TEMP%\claude_clipboard.png` and is overwritten each use
- No permanent files are created
