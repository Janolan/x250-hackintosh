# X250 Hackintosh (macOS 10.14.x)

This is a guide to set up the Lenovo Thinkpad X250 as a 99% working hackintosh.

## Introduction

Thinkpad X250 Hackintosh configuration. This repository contains the following folders:

- `EFI`: put this in your EFI partition in `EFI` folder, including `Boot` and `CLOVER` sub-folders,
- `Kexts`: kexts to install in `/Library/Extensions` on your local drive once macOS has been installed.

It's a `99.99%` working hackintosh, including:

- *Apfs* and *HFS* disk partitions: using `ApfsDriverLoader-64.efi` and `HFSPlus-64.efi` respectively,
- **Power management**, **Temperature sensors**: Thanks to [FakeSMC](https://bitbucket.org/RehabMan/os-x-fakesmc-kozlek), which also emulates macbook pro hardware,
- **Battery status**: handled by [ACPIBatteryManager](https://bitbucket.org/RehabMan/os-x-acpi-battery-driver) kext,
- Brightness control: Thanks to [AppleBacklightFixup](https://bitbucket.org/RehabMan/applebacklightfixup) kext,
- Audio on speakers: using [AppleALC](https://github.com/acidanthera/AppleALC) kext,
- USB ports: custom made `USBPorts.kext` using [Intel FBPatcher](https://www.insanelymac.com/forum/topic/335018-hackintool-v176/),
- Graphical acceleration (QE/CI): thanks to [WhatEverGreen](https://github.com/acidanthera/WhateverGreen) kext and [Intel FBPatcher](https://www.insanelymac.com/forum/topic/335018-hackintool-v176/).
- Audio Jack connector,
- And Display Port external display.

### Prerequisites

What things you need to install the software and how to install them

```
Give examples
```

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc

