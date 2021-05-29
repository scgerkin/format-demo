## Maven Plugin
1. Include the `googleformatter-maven-plugin` in the `pom.xml`:
```xml
    <plugin>
      <groupId>com.theoryinpractise</groupId>
      <artifactId>googleformatter-maven-plugin</artifactId>
      <version>1.7.3</version>
      <executions>
        <execution>
          <id>reformat-sources</id>
          <configuration>
            <includeStale>false</includeStale>
            <style>GOOGLE</style>
            <formatMain>true</formatMain>
            <formatTest>true</formatTest>
            <filterModified>false</filterModified>
            <skip>false</skip>
            <fixImports>false</fixImports>
            <maxLineLength>100</maxLineLength>
          </configuration>
          <goals>
            <goal>format</goal>
          </goals>
          <phase>process-sources</phase>
        </execution>
      </executions>
    </plugin>
```
1. Run the `format` goal:
```
mvn googleformatter:format
```

## VSCode
### Pre-Requesite
If not already installed, install the [Language Support for Java extension by RedHat](https://marketplace.visualstudio.com/items?itemName=redhat.java)

### Setup
1. Download the `google-java-format` jar [here](https://github.com/google/google-java-format/releases/download/v1.10.0/google-java-format-1.10.0-all-deps.jar)
1. Install the [Google Java Format plugin](https://marketplace.visualstudio.com/items?itemName=mngrm3a.vscode-google-java-formatter)
1.  Open settings.json
    1. `ctrl+shift+P` or right-click and select `Command Palette`
    1. Enter `settings.json` and select the option to open this
        !(settings.json)[media/settingsjson.png]
1. Add the following to the JSON:
```json
"gjf.jarPath": "C:\\<FULL_PATH_TO_GOOGLE_JAVA_FORMAT_PLUGIN>.jar"
```
As an example:
![](media/vscode/settingsjson.png)

### Formatting
1. Right click the file to format and select `Format Document` or press `shift+alt+f` (default hotkey)
![](media/vscode/formatdocument.png)

1. You will get a pop-up asking you to select a formatter. Select
![](media/vscode/selectformatter1.png)
1. Select `Configure` and then select the `Google Java Format` from the command palette dropdown.
![](media/vscode/selectformatter2.png)

You'll now use the Google style for formatting.
Before:
![](media/vscode/before.png)
After:
![](media/vscode/after.png)

## Eclipse
### Setup
Directions from Google can be found [in the repository](https://github.com/google/google-java-format#eclipse) should these be unclear.
1. Download the [google-java-format Eclipse Plugin](https://github.com/google/google-java-format/releases/download/google-java-format-1.6/google-java-format-eclipse-plugin_1.6.0.jar)
1. Copy the jar file to the "Dropins" folder in Eclipse. This is located inside the install path.
For example:
```
C:\Users\scgrk\eclipse\java-2021-03\eclipse\dropins
```
1. Restart Eclipse (if already running)
1. Open `Window -> Preferences -> Java -> Code Style -> Formatter`. A new `Formatter Implementation` dropdown is available here. Select `google-java-format`.
![](media/eclipse/eclipseformatter.png)
1. Select `Apply and Close`

### Formatting
1. Right click the file to format and select `Source -> Format` or use the hotkey `ctrl+shift+F`
![](media/eclipse/format.png)
1. To enable auto-formatting on save, open `Window -> Preferences -> Java -> Editor -> Save Actions`. Check the "Perform the selected actions on save" option, and "Format source code" option. It is recommended you select for all lines, but this can be a significant change across legacy code. It is also recommended you select the "Organize imports" option as well to automatically remove any unused imports.
![](media/eclipse/format-on-save.png)

This will now format your files automatically.
Before:
![](media/eclipse/before.png)
After:
![](media/eclipse/after.png)

## IntelliJ
### Setup
1. Open the Plugin manager from `File -> Settings -> Plugins` and search for `google-java-format` and select `Install`.
![](media/intellij/plugin-install.png)
1. This requires a restart of the IDE. Select `Restart IDE`.
1. The plugin needs to be enabled. Open settings again and go to the settings for the plugin, `File -> Settings -> google java format Settings`. Click the box to enable the plugin and then save your settings with `Ok`.
![](media/intellij/enable-plugin.png)

### Formatting
1. Select the `Code` dropdown, then `Reformat Code` or use the hotkey `ctrl+alt+L`.
![](media/intellij/reformat.png)
1. To optimize imports as well, select `Reformat File` and then enable the checkbox for this.
![](media/intellij/reformat-file.png)
You can set this to work for the entire file or only what has been changed in version control. It is recommended you select for the entire file, but this can be a significant change across legacy code.
1. To enable auto-formatting on save, install the `save actions` plugin:
![](media/intellij/save-actions-plugin.png)
1. Configure the plugin by going to `File -> Plugins -> Other Settings -> Save Actions` and select the appropriate checkboxes:
![](media/intellij/configure-save-actions.png)

AS A NOTE: By default, IntelliJ automatically saves changes as you code. If the editor loses focus, this plugin will be triggered and reformat your file according to your settings. If this is overly disruptive, the solution is to only allow the plugin to be triggered on the `ctrl+shift+S` hotkey.