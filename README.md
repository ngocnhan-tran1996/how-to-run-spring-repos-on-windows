# How to Run Spring Docs on Windows

typing...

## Spring Security

1. `antora.yml`
   Replace every command `command: gradlew ...` to `command: <Your Disk\Your Folder>\spring-security ...`
2. Remove `docs-src` in `spring-projects\spring-security\main\docs\modules\ROOT\examples`
3. Create symbol link
   Run cmd as administrator
   `mklink /D "<Your Disk\Your Folder>\spring-security\main\docs\modules\ROOT\examples\docs-src" "<Your Disk\Your Folder>\spring-security\main\docs\src"`
   Example: `mklink /D `
4. Run `./gradlew :spring-security-docs:antora`
