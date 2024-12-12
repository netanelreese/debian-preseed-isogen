# generate-debian-preseed-iso

This Bash script generates Debian ISOs with preseed for multiple environments. With this script, you can automate the process of generating custom Debian images with preconfigured settings for various environments.

In this fork, I have also added some functionality that lets you create a custom grub menu that will be embedded in the media. The default grub.cfg in this repository adds a new option to the install grub menu to select the preseed autoinstaller. It also has options to set that option as the default and sets a 30 second timeout. There are more options that can be inserted found at the [Grub2 Reference](https://www.gnu.org/software/grub/manual/grub/grub.html).

## Requirements

To use this script, you need to install the following packages:

    $ sudo apt install wget curl p7zip-full genisoimage syslinux-utils

## Usage

To use this script, follow these steps:
1. Clone this repository using Git:

       $ git clone https://github.com/bergmann-max/debain-preseed-iso-generator.git

2.  Navigate to the cloned directory:

        $ cd debain-pressed-iso-generator

3. Make a directory in `./CUSTOM/` and name it what you want your iso to be named.
        
        `$ mkdir -p ./CUSTOM/customiso`

4. Move your `preseed.cfg` and your `grub.cfg` (if you made a custom one) into the directory you created.

5. Repeat steps 3 & 4 for however many custom images you would like to make.

6. Make the script executable:

       $ chmod +x debian-preseed-iso-generator.sh

7. Run the script:

       $ ./debian-preseed-iso-generator.sh

8. After the script has finished running, you will find the generated ISO images in the directories you created. These ISOs contain the preconfigured settings specified in the <code>preseed.cfg</code> files.

That's it! Now you can use the generated ISOs to install Debian on multiple machines with the same preconfigured settings.

## More

- [Official documentation about automating the installation using preseeding](https://www.debian.org/releases/stable/amd64/apb.en.html)
- [Example preseed file](https://www.debian.org/releases/stable/example-preseed.txt)
- [Grub2 Reference](https://www.gnu.org/software/grub/manual/grub/grub.html)
