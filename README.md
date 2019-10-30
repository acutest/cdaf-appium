# cdaf-appium: Acutest cdaf framework component for Appium integration

This installation guide is for Android. Installation instructions are slightly different for IOS.

1. Follow steps 1 - 9 ignoring step 7 of [these](https://www.toolsqa.com/mobile-automation/appium/appium-tutorial/) instructions to setup your environment correctly.
  -  Instead of step 3 download Android studio.
  -  When installing the Android SDK in Android studio download the newest version, and in SDK Tools make sure all boxes relating to google play are ticked so you have access to the play store on your emulator.
2. In Android studio follow [these](https://developer.android.com/studio/run/managing-avds) instrustions to create an emulator. Choose one with a logo in the play store collum. Take a noe of the device's version under `target` collum. Press the green play button to start the emulator. Download `Jira Cloud` & `APK info` apps from the play store.
3. Open Appium desktop client and make sure its `Host = 0.0.0.0` and `Port = 4723` and start the server.
4. Open command prompt and `cd` to `C:\Users\P10493586\AppData\Local\Android\Sdk\platform-tools` then run command `adb devices`. If your emulator is working correctly the devices name will appear in the response. Take a note of this name.
5. Clone cdaf-appium project to your IDE and navigate to `src>test>java>com.acutest.cdaf>stepdefs>AppCapabilities`. In this class change `version` & `device name` capabilities to match your emulator's.
6. In the terminal run `mvn clean verify -Dexec.mainClass=com.acutest.cdaf.xray.XrayExport -Dexec.args="CDAFSBXC-2460" -Pxray-integration-test`. Watch the emulators screen and watch the test run.
