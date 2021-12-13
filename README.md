# Raspberry Pi IMSI Catcher

Single repository to store all of the necessary elements required to create a Raspberry Pi based simple IMSI catcher. I built this project to take account of the outdated guides that have not kept paces with the changes to GNUradio, gr-gsm, and the Simple_IMSI-catcher.py packages. A working main repo will be maintained here. All credit to the individual projects, joined here for ease of use.

This project is built on the PiSDR image, available on the [luigifcruz](https://github.com/luigifcruz) GitHub. The version used for this guide was the latest at the time of writing, [PiSDR Version 5.0](https://github.com/luigifcruz/pisdr-image/releases/tag/v5.0.0) released 13th Dec 2020. To download the image direct, use [this link](https://github.com/luigifcruz/pisdr-image/releases/download/v5.0.0/2020-11-13-PiSDR-vanilla.img.xz). This file is required and forms the core of this guide.

The other core elements include:

1. [GNUradio 3.8+, included in PiSDR](https://www.gnuradio.org)
2. [The gr-gsm project by ptrkrysik](https://github.com/ptrkrysik/gr-gsm)
3. [The simple_IMSI-catcher.py script by Oros42](https://github.com/Oros42/IMSI-catcher)

At the time of writing, there exist some incorrect instructions on some of Git repo guides or associated sites - updates have been made to core code while guides have not reflected the dependancies or packages required e.g. the [Osmocom](https://osmocom.org/projects/gr-gsm/wiki/Installation) guide does not take account of python3 prerequisites, instead listing python.

External sites are also listing a mixture of instructions, normally delineated by GNUradio version, 3.7 or 3.8. There was a [fork of gr-gsm hosted for GNUradio 3.8](https://github.com/velichkov/gr-gsm.git) but this is no longer required as the ptrkrysik main has now been updated.

One of the better guides can be found at [Paladion.net](https://www.paladion.net/blogs/how-to-build-an-imsi-catcher-to-intercept-gsm-traffic). Please read this for a more detailed explanation beyond the simple instructions, below.

Please follow the below process for a working simple_IMSI-catcher.py based install on any Raspberry Pi (1, 2, 3, 4), no issues with 32-bit or 64-bit as seen with some other Linux distros e.g. Ubuntu only working on Pi 4, the same with Dragon OS with its Pi64 image.

## What you will require
You will require a Raspberry Pi and the ability to flash images to the bootable media.
- A Raspberry Pi, ideally a Pi Zero 2, Pi 4, or Pi CM4.
- An SD-card, ideally a Class 10 from a reputable brand (SanDisk, Samsung, Lexar, SwissBit).
- Etcher or Rufus for copying an .ISO to the SD-card.

## SDR Hardware
You will require an SDR receiver.
- RTL-SDR from a reputable source e.g.
- HackRF One.
- BladeRF.
