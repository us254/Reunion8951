Here are the steps to build v2rayNG for Android and update it with latest Xray using GitHub Actions:

1. Copy the v2rayNG Android project files into a GitHub repository. 

2. Create a workflow YAML file `.github/workflows/build.yml` with following:

```yaml
name: Build APK

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v3

    - name: Clone Xray  
      run: |
        git clone https://github.com/XTLS/Xray-core.git
        
    - name: Build Xray AAR
      run: |
        cd Xray-core
        go mod download
        gomobile init
        gomobile bind -o xray-core.aar

    - name: Copy AAR
      run: | 
        cp Xray-core/xray-core.aar app/libs

    - name: Build Debug APK
      run: ./gradlew assembleDebug

    - name: Upload APK
      uses: actions/upload-artifact@v3
      with:
        name: app-debug.apk
        path: app/build/outputs/apk/debug/app-debug.apk
```

3. Push code to trigger workflow.

4. The workflow will build latest Xray into AAR, integrate it in app and generate debug APK artifact.

5. Download the APK artifact and install on device for testing.

Let me know if you need any clarification or have additional questions!
