# Stage-INRS

This repository is set up to be opened from any computer without committing
machine-specific ESP-IDF or compiler paths.

## Local setup

1. Install [Visual Studio Code](https://code.visualstudio.com/).
2. Install the **Espressif IDF** VS Code extension.
3. In VS Code, run `ESP-IDF: Configure ESP-IDF extension` and select the
   ESP-IDF installation on your computer.
4. Open this repository folder in VS Code.
5. Build with the ESP-IDF extension or from a terminal where ESP-IDF is loaded:

   ```sh
   idf.py build
   ```

The repository uses `${workspaceFolder}` and VS Code settings variables for
paths. Local installation paths such as `C:\esp\...` or `/home/<user>/...`
should stay in your personal VS Code/user settings, not in the repository.

The checked-in `.vscode/c_cpp_properties.json` intentionally does not set
`compilerPath` or `compileCommands`. Those values depend on the ESP-IDF version,
target chip, and local toolchain path. After the ESP-IDF project files are
present, run `ESP-IDF: Run idf.py reconfigure task` or `idf.py reconfigure` to
generate `build/compile_commands.json` locally if you want VS Code to use compile
commands for IntelliSense.

## Notes for this upload

At the time of this setup, the repository only contains README and VS Code
configuration files. A complete ESP-IDF project usually also includes files such
as `CMakeLists.txt`, a `main/` source folder, and optionally `sdkconfig` or
`sdkconfig.defaults`. Add those project files before running `idf.py build`.