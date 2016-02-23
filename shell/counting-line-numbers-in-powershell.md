To count the number of lines of all files in a directory recursively use the `Measure-Object` CmdLet
with `Get-ChildItem` and `Get-Content`.

```powershell
Get-ChildItem -Recurse *.js -Exclude *.unit.js | Get-Content | Measure-Object -Line | %{$_.Lines}
```
