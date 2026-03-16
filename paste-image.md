# paste-image

Save the clipboard image to a temp file and read it.

Run this PowerShell command via the Bash tool:

```powershell
powershell -Command "
Add-Type -AssemblyName System.Windows.Forms;
\$img = [System.Windows.Forms.Clipboard]::GetImage();
if (\$img -ne \$null) {
    \$path = \"\$env:TEMP\claude_clipboard.png\";
    \$img.Save(\$path);
    Write-Output \$path
} else {
    Write-Output 'NO_IMAGE'
}
"
```

If the output is a file path, read the image at that path with the Read tool and then respond to what you see.

If the output is `NO_IMAGE`, tell the user: "No image found in clipboard. Copy an image first (e.g. with Snipping Tool or Ctrl+PrtSc), then run /paste-image."
