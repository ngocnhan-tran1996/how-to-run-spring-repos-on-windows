# How to Run Spring Docs on Windows

## Spring Security

1. Open file `spring-security\docs\antora.yml` and replace every command `command: gradlew ...` to `command: <Your Disk:\Your Folder>\spring-security\gradlew ...`

   **Example:**
   ```yaml
   ext:
    collector:
      run:
        command: D:\Source\fork\spring-security\gradlew -q -PbuildSrc.skipTests=true :spring-security-docs:generateAntoraResources
   ```
2. Remove `docs-src` in `spring-security\docs\modules\ROOT\examples\docs-src`

3. Run cmd as administrator `mklink /D "<Your Disk\Your Folder>\spring-security\docs\modules\ROOT\examples\docs-src" "<Your Disk\Your Folder>\spring-security\docs\src"`

   **Example:** `mklink /D "D:\Source\fork\spring-security\docs\modules\ROOT\examples\docs-src" "D:\Source\fork\spring-security\docs\src`

4. Run `./gradlew :spring-security-docs:antora`