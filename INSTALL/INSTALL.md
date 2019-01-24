# Raspberry Pi Vision Helper Installation

 1. Copy entire repo into a new folder in the root of your project. We recommend `vision`. Remove the `.git` folder and the readme files.

 2. Append contents of [settings.gradle](settings.gradle) to your root folder settings.gradle. Create it if it does not exist. If not using folder `vision/`, replace all occurrences of "vision" with your folder name.

 3. Ensure that your Pi is accessable via mdns at the address frcvision.local. If it is raspberrypi.local, a non-default hostname, static IP, or if you have changed the default username or password, edit `vision/build.gradle` to account for your settings.

 4. Put your vision code inside `vision/src/main/java`. If your `public static void main` is not inside `Main.java`, or if you are using a package, edit the variable `mainClassName` inside `build.gradle` to account for your settings. The name should be a fully qualified package and class.

#### At the end, the `runCamera` file should be located in `vision/` from your root folder.
#### The following steps are only necessary if your project is a git repo.

 5. If using git, append contents of [.gitignore](.gitignore) to your root folder .gitignore. Create it if it does not exist. If not using folder `vision/`, replace all occurrences of "vision" with your folder name.
