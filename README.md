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
2. Select `Configure` and then select the `Google Java Format` from the command palette dropdown.
![](media/vscode/selectformatter2.png)

You'll now use the Google style for formatting.
Before:
![](media/vscode/before.png)
After:
![](media/vscode/after.png)
