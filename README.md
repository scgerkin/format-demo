# VSCode

## Pre-Requesite
If not already installed, install the [Language Support for Java extension by RedHat](https://marketplace.visualstudio.com/items?itemName=redhat.java)

## Steps
1. Download the `google-java-format` jar [here](https://github.com/google/google-java-format/releases/download/v1.10.0/google-java-format-1.10.0-all-deps.jar)
1. Install the [Google Java Format plugin](https://marketplace.visualstudio.com/items?itemName=mngrm3a.vscode-google-java-formatter)
1.  Open settings.json
    1. `ctrl+shift+P` or right click and select `Command Palette`
    1. Enter `settings.json` and select the option to open this
        !(settings.json)[media/settingsjson.png]
1. Add the following to the JSON:
```json
"gjf.jarPath": "C:\\<FULL_PATH_TO_GOOGLE_JAVA_FORMAT_PLUGIN>.jar"
```
As an example:
![](media/vscode/settingsjson.png)

1. Right click the file to format and select `Format Document` or press `shift+alt+f` (default hotkey)
![](media/vscode/formatdocument.png)

1. You will get a pop-up asking you to select a formatter. Select 
![](media/vscode/selectformatter1.png)
2. Select `Configure` and then select the the `Google Java Format` from the command palette dropdown.
![](media/vscode/selectformatter2.png)

You'll now use the Google style for formatting.
Before:
![](media/vscode/before.png)
After:
![](media/vscode/after.png)
