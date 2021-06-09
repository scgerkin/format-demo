# Code Formatting: Clean As You Go

# First Steps
1. Checkout a repository. If there have not been any changes on the repository lately, it is likely a candidate for cleaning.
2. Add the `googleformatter-maven-plugin` to the base project `pom.xml`.
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
3. Run the formatter goal:
  ```sh
  mvn googleformatter:format
  ```
4. Remove the plugin from the project `pom.xml`.
5. Create a pull request for the updated formatting changes only and merge into the main branch of the repository. These changes do not need to be promoted but should be on any branch from which new feature development is created.
6. Create a new branch from the formatting branch for your feature development. If you are able to get a team member to approve and merge the formatting changes quickly, you can branch off the main branch instead.
7. Develop as usual and use the plugin locally in your IDE to maintain the formatting style.

# Plugin Installation Instructions
## Eclipse
