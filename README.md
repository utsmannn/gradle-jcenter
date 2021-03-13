# gradle jcenter plugin for android library publishing

### add this properties in 'local.properties'
```properties
bintray.user=username
bintray.apikey=api_key
```

### add this plugin in bottom of module gradle

```gradle
if (project.rootProject.file('local.properties').exists()) {
    apply from: 'https://raw.githubusercontent.com/utsmannn/gradle-jcenter/master/installv1.gradle'
    apply from: 'https://raw.githubusercontent.com/utsmannn/gradle-jcenter/master/bintrayv1.gradle'
}
```

### publish
```
./gradlew bintrayUpload
```
