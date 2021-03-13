# gradle jcenter plugin for android library publishing

### add this properties in 'local.properties'
```properties
bintray.user=username
bintray.apikey=api_key
```

### add this plugin in bottom of module gradle

```groovy
if (project.rootProject.file('local.properties').exists()) {
    apply from: 'https://raw.githubusercontent.com/utsmannn/gradle-jcenter/master/installv1.gradle'
    apply from: 'https://raw.githubusercontent.com/utsmannn/gradle-jcenter/master/bintrayv1.gradle'
}
```

### add ext in module gradle
This sample of geolib library, replace with what you need.
```groovy
ext {
    bintrayRepo = "utsman"
    bintrayName = "com.utsman.geolib"

    libraryName = 'location'
    artifact = 'location'

    publishedGroupId = 'com.utsman.geolib'
    libraryVersion = versionName

    libraryDescription = 'Android helper libraries for place, location and polyline utils'
    siteUrl = 'https://github.com/utsmannn/geolib'
    gitUrl = 'https://github.com/utsmannn/geolib.git'
    developerId = 'utsman'
    developerName = 'Muhammad Utsman'
    developerEmail = 'utsmannn@gmail.com'
    licenseName = 'The Apache Software License, Version 2.0'
    licenseUrl = 'https://www.apache.org/licenses/LICENSE-2.0.txt'
    allLicenses = ["Apache-2.0"]
}
```

### publish
```
./gradlew bintrayUpload
```
