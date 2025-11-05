# How to Run Spring Docs on Windows

## Spring Security

Prerequisite: Clone the repository https://github.com/spring-projects/spring-security

1. Open the file `spring-security\docs\antora.yml` and replace every command that starts with `command: gradlew ...` with `command: <Your Disk>:\<Your Folder>\spring-security\gradlew ...`

   **Example:**
   ```yaml
   ext:
    collector:
      run:
        command: D:\Source\fork\spring-security\gradlew -q -PbuildSrc.skipTests=true :spring-security-docs:generateAntoraResources
   ```

2. Delete the `docs-src` directory located at `spring-security\docs\modules\ROOT\examples\docs-src`

3. Run Command Prompt as Administrator, then execute the following command: 
   ```shell
   mklink /D "<Your Disk\Your Folder>\spring-security\docs\modules\ROOT\examples\docs-src" <Your Disk\Your Folder>\spring-security\docs\src"
   ```

   **Example:** `mklink /D "D:\Source\fork\spring-security\docs\modules\ROOT\examples\docs-src" "D:\Source\fork\spring-security\docs\src"`

4. Run the following command to build the documentation: `./gradlew :spring-security-docs:antora`


## Spring AMQP

Prerequisite: Clone the repository https://github.com/spring-projects/spring-amqp

1. Open the file `spring-amqp\src\reference\antora\antora.yml` and replace every command that starts with `command: gradlew ...` with `command: <Your Disk>:\<Your Folder>\spring-amqp\gradlew ...`

   **Example:**
   ```yaml
   ext:
    collector:
      run:
        command: D:\Source\fork\spring-amqp\gradlew -q :generateAntoraResources
   ```

2. Run the following command to build the documentation: `./gradlew antora`