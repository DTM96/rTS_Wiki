**Warning: This will wipe all existing data on the USB drive.**

1. Download and run [Etcher](https://www.balena.io/etcher/)
2. Select your downloaded ISO
3. Select your target drive
4. Click "Flash" and wait for it to finish.

<details markdown="1">
<summary>Alternative steps, without using Etcher</summary>
> ### Windows
> {: .no_toc }
> 
> 1. Download and run [Rufus](https://rufus.ie/).
> 2. Select “ISO Image” and then browse for the ISO image.
> 3. Select which flash drive you want to put the installer on.
> 4. Select the target system type (GPT/MBR) depending on your motherboard's capabilities.
> 5. Click “Start” and wait for it to finish.
> 6. Eject the USB flash drive.
> 
> ### macOS
> {: .no_toc}
> 
> 1. Open the Terminal.
> 2. First, without the flash drive inserted, run `diskutil list` in the Terminal.
> 3. Plug in the flash drive and run `diskutil list` again. You can do this to identify the drive device path. The device path is in the form of `/dev/diskN`, where N is a number (example: `/dev/disk1`).
> 4. Unmount the flash drive you have identified. `diskutil unmountdisk /dev/diskN`.
> 5. Convert the ISO image. `hdiutil convert /path/to/image.iso -format UDRW -o /path/to/ubuntu.img`
> 6. Run `dd if=/path/to/image.img of=/dev/rdiskN status=progress` to create a bootable drive from the image. Using `/dev/rdiskN` instead of `/dev/diskN` usually results in faster media creation.
> 7. Wait until dd finishes. The terminal will display the next prompt when it's done.
> 8. Eject the USB flash drive: `diskutil eject /dev/diskN`.
> 
> ### Linux
> {: .no_toc }
> 
> 1. First, without the flash drive inserted, run `lsblk` in the Terminal.
> 2. Plug in the flash drive and run `lsblk` again. You can do this to identify the drive device path. The device path is usually in the form of `/dev/sdX`, where X is a letter (example: `/dev/sdb`).
> 4. Run `dd if=/path/to/image.iso of=/dev/sdX status=progress` to create a bootable drive from the ISO.
> 5. Wait until dd finishes. The terminal will display the next prompt when it's done.
</details>

You can also follow our [Ventoy guide](/docs/guides/ventoy) to make one flash drive that can boot multiple ISO files, but that is a little more difficult.
