# Raspberry Pi Vision Helper Installation

## Raspberry Pi Prep

To make this work, you must have the ssh (Secure Shell) server enabled on your pi. You can do this by creating a blank file called `ssh` in the `boot` fat32 partition of the pi's microsd card. Note that this file cannot have an extention; it must be simply `ssh`.

This is tricky on Windows because explorer hides extentions by default. You can get around this by opening a command prompt with Win + R -> `cmd`, navigating to the partition by typing the drive letter and a colon: `E:`, and creating the file with `copy NUL ssh`.

On Mac or Linux, if you cannot create a file without an extention: open a terminal, navigate to the partition, and create the file with `touch ssh`.

This process may not work sometimes. If this happens, try reflashing the raspberry pi image from [the FRCVision repo](https://github.com/wpilibsuite/FRCVision-pi-gen/releases), and creating the file before the first boot. If you do this, you can back up `frc.json` and `dhcpcd.conf` to keep your camera and static ip settings, respectively.

## Repo Installation

 1. Copy entire repo into a new folder in the root of your project. We recommend `vision`. Remove the `.git` folder and the readme files.

 2. Append contents of [settings.gradle](settings.gradle) to your root folder settings.gradle. Create it if it does not exist. If not using folder `vision/`, replace all occurrences of "vision" with your folder name.

 3. Ensure that your Pi is accessable via mdns at the address frcvision.local. If it is raspberrypi.local, a non-default hostname, static IP, or if you have changed the default username or password, edit `vision/build.gradle` to account for your settings.

 4. Put your vision code inside `vision/src/main/java`. If your `public static void main` is not inside `Main.java`, or if you are using a package, edit the variable `mainClassName` inside `build.gradle` to account for your settings. The name should be a fully qualified package and class.

#### At the end, the `runCamera` file should be located in `vision/` from your root folder.
#### The following steps are only necessary if your project is a git repo.

 5. If using git, append contents of [.gitignore](.gitignore) to your root folder .gitignore. Create it if it does not exist. If not using folder `vision/`, replace all occurrences of "vision" with your folder name.
