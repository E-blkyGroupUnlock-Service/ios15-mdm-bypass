<h1 align="center">MDM Activation bypass iOS 15/16</h1>

Bypass MDM activation screen on checkm8 devices tested on iX 15.6 RC

---

# Prerequsites

1. A computer running macOS/linux
2. A checkm8 device (A7-A11)
3. Willing to take a risk on your idevice :)

# Usage

1. Clone and cd into this repository: `git clone https://github.com/verygenericname/SSHRD_Script --recursive && cd SSHRD_Script`
    - If you have cloned this before, run `cd SSHRD_Script && git pull` to pull new changes
2. Run `./sshrd.sh <iOS version for ramdisk>`, **without** the `<>`.
3. Place your device into DFU mode
    - A11 users, go to recovery first, then DFU.
    - checkra1n can't jailbreak iOS 15 yet, but it can help you with entering recovery and DFU
4. Run `./sshrd.sh boot` to boot the ramdisk
5. Run `./sshrd.sh ssh` to connect to SSH on your device
6. Finally, to mount the filesystems, run `mount_filesystems`  
    - /var is mounted to /mnt2 in the ssh session.
    - /private/preboot is mounted to /mnt6.
7. `cd /mnt2/containers/Shared/SystemGroup/systemgroup.com.apple.configurationprofiles/Library/ConfigurationProfiles`
8. Create new config file `nano CloudConfigurationDetails.plist`
9. Paste in contents of `CloudConfigurationDetails.plist` from this repo ([credits](https://gist.github.com/FrankSpierings/a5f6c0b8ae640bfa9909a396e1ceb03c))
10. Exit nano ^X(ctrl+x) and confirm file name and save.
11. Exit ssh ^D(ctrl+d)
12. `./sshrd.sh clean`
13. `./sshrd.sh reboot`

# Credits

[palera1n team](https://github.com/palera1n/ramdisk)
[verygenericname](https://github.com/verygenericname/SSHRD_Script)
[FrankSpierings](https://gist.github.com/FrankSpierings)