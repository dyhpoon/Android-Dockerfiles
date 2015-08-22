##android-emulator-23
Android and emulator armeabi-v7a (API 23)
Inspired by [ksoichiro/dockerfiles](https://github.com/ksoichiro/dockerfiles/tree/master/android-emulator)

##Contents
* Android SDK Platform API level **23**
* Android **armeabi-v7a** System Image in level **23**

##Usage
```
docker run --privileged -it \
 -v /Path/to/your/android/project/:/workspace \
 dyhpoon/android-emulator-23 start-emulator \
 "./gradlew connectedAndroidTest"
```

It is recommended to use your host's gradle cache to speed up build time. For example:

```
docker run --privileged -it \
 -v /Path/to/your/android/project/:/workspace \
 -v /Home/.gradle/:/root/.gradle \
 dyhpoon/android-emulator-23 start-emulator \
 "./gradlew connectedAndroidTest"
```
