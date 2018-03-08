## Setting up the Android Emulator (MacOS Only)
#### TODO -> Windows version


1) Download and install [Andrioid Studio.](https://developer.android.com/studio/index.html)

2) Download Genymotion. [(Free Version)](https://www.genymotion.com/fun-zone/) Genymotion requires you to have Oracle VM VirtualBox in order for it to work. If you don't have **VirtualBox**, follow these instructions [here](https://docs.genymotion.com/Content/01_Get_Started/Installation.htm)

3) Follow these [instructions](https://docs.expo.io/versions/latest/guides/genymotion.html#genymotion) here to configure Genymotion and Android Studio. **Make sure to follow "Option 1: User Andriod Studio's tools"** and **"Step 2: Path your path in XDE"**.

	```In your home directory, open your bash_profile by typing in this command:

	$ open .bash_profile

	In your bash_profile, copy and paste these paths, enter your computer's username, and save.

	export PATH=/Users/YOUR_USER_NAME/Library/Android/sdk/platform-tools:$PATH
	export PATH=/Users/YOUR_USER_NAME/Library/Android/sdk:$PATH```

4) Run Genymotion with a Nexus 5 device.

5) In your Expo XDE, start your Expo project and choose Device -> Open on Android. 
