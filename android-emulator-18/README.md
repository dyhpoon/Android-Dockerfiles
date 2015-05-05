##android-emulator-18
Android and emulator armeabi-v7a (API 18)
Inspired by [ksoichiro/dockerfiles](https://github.com/ksoichiro/dockerfiles/tree/master/android-emulator)

##Contents
* Android SDK Platform API level **18**
* Android **armeabi-v7a** System Image in level **18**

##Usage
```
docker run --privileged -it \
 -v /Users/darren/docker/instagrab_android/:/workspace \
 dyhpoon/android-emulator-18 start-emulator \
 "./gradlew connectedAndroidTest"
```

It is recommended to use your host's gradle cache to speed up build time. For example:

```
docker run --privileged -it \
 -v /Path/to/your/android/project/:/workspace \
 -v /Home/.gradle/:/root/.gradle \ 
 dyhpoon/android-emulator-18 start-emulator \
 "./gradlew connectedAndroidTest"
```