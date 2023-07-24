Here are the steps to build v2rayNG for Android with the latest Xray updates:

1. Clone the v2rayNG repository:

```bash
git clone https://github.com/2dust/v2rayNG.git
```

2. Clone the AndroidLibXrayLite repository to get the latest Xray core: 

```bash 
git clone https://github.com/2dust/AndroidLibXrayLite.git
```

3. Build the Xray core into an AAR library:

```bash
cd AndroidLibXrayLite
gomobile init
gomobile bind -o xray-core.aar
```

4. Copy the generated AAR file to the v2rayNG/app/libs folder.

5. Open the v2rayNG project in Android Studio.

6. Update build.gradle to use the new AAR file:

```groovy
implementation files('libs/xray-core.aar') 
```

7. Sync and rebuild the v2rayNG project. 

8. The app should now use the latest Xray core when building.

Let me know if you have any other questions!
