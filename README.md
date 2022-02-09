# yarn-visual-studio-repro

Demonstrates an issue running `git commit` via the Visual Studio GUI when there
is a pre-commit hook that uses Yarn 3.

Committing via shell, e.g. PowerShell, works file.

## Reproduction Steps

1. Open the folder in Visual Studio 2022.
2. Edit any file.
3. Try to commit via the Visual Studio GUI.

Expected behavior: The commit goes through.

Actual behavior: There is an error.

```text
/c/Users/sam.magura/AppData/Roaming/npm/yarn: line 5: cygpath: command not found
node:internal/modules/cjs/loader:936
  throw err;
  ^

Error: Cannot find module 'C:\program files\microsoft visual studio\2022\enterprise\common7\ide\commonextensions\microsoft\teamfoundation\team explorer\Git\node_modules\yarn\bin\yarn.js'
    at Function.Module._resolveFilename (node:internal/modules/cjs/loader:933:15)
    at Function.Module._load (node:internal/modules/cjs/loader:778:27)
    at Function.executeUserEntryPoint  as runMain
    at node:internal/main/run_main_module:17:47 {
  code: 'MODULE_NOT_FOUND',
  requireStack: []
}
husky - pre-commit hook exited with code 1 (error)
```
