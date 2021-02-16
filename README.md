Gradle with a wrapper does not work, it seems Gradle is not installed at all.

The log complains ./gradlew not found.

```
[Pipeline] { (run backend)
[Pipeline] echo
executing gradle...
[Pipeline] withGradle
[Pipeline] {
[Pipeline] sh
+ ./gradlew -v
/var/jenkins_home/workspace/my-demo-project_main@tmp/durable-315dd9f7/script.sh: 1: /var/jenkins_home/workspace/my-demo-project_main@tmp/durable-315dd9f7/script.sh: ./gradlew: not found
[Pipeline] }
[Pipeline] // withGradle
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
ERROR: script returned exit code 127
Finished: FAILURE

```


With tools, gradle can be seen being installed in log... however it still failed in the end.

```
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Tool Install)
[Pipeline] tool
Unpacking https://services.gradle.org/distributions/gradle-6.2-bin.zip to /var/jenkins_home/tools/hudson.plugins.gradle.GradleInstallation/Gradle-6.2 on Jenkins
[Pipeline] envVarsForTool
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (run frontend)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] echo
executing yarn...
[Pipeline] nodejs
[Pipeline] {
[Pipeline] sh
+ yarn install
yarn install v1.22.10
[1/4] Resolving packages...
success Already up-to-date.
Done in 0.12s.
[Pipeline] }
[Pipeline] // nodejs
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (run backend)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] echo
executing gradle...
[Pipeline] sh
+ ./gradlew -v
/var/jenkins_home/workspace/my-demo-project_main@tmp/durable-c9e8101e/script.sh: 1: /var/jenkins_home/workspace/my-demo-project_main@tmp/durable-c9e8101e/script.sh: ./gradlew: not found
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
ERROR: script returned exit code 127
Finished: FAILURE
```
