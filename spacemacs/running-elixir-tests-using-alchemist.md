When using Spacemacs with the Alchemist package installed Alchemist commands can be executed using
the Spacemacs major mode key command of leader key m, `Space-m`, but that only exposes a limited set
of commands, and test commands are not in that set. To run tests in Spacemacs the standard Alchemist
key commands, which begin with `C-c a`, needs to be used.

Run all tests: `C-c a t`
Rerun the last test: `C-c a r`
Run the test under the cursor (i.e. point en emacs lingo): `C-c a m t .`
Toggle displaying test results: `C-c M-r`

[See Alchemist reference](https://github.com/tonini/alchemist.el#testing)
