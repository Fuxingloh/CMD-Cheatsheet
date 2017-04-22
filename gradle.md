## Gradle

#### Properties file
put inside "user\.gradle\gradle.properties" <br />
then in build.gradle use "${artifactory_user}" to access values
```xml
artifactory_user=
artifactory_password=
artifactory_contextUrl=http://artifactory.com/artifactory
```

```bash
# Run a task for a single project/module
gradlew clean dockerBuildImage -p module
```
