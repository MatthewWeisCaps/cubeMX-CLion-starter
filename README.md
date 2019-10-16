# FreeRTOS CLion Template

Contains a basic BlinkingLED CLion project for the STM32F407VG MCU

## Why is this needed?

Typically, CLion's "Embedded Development Support" plugin should detect compatible projects automatically ([https://www.jetbrains.com/help/clion/embedded-development.html](https://www.jetbrains.com/help/clion/embedded-development.html)) in order to generate the additional project files necessary for the project to run. However, this doesn't seem to be working on newer versions of CLion. This project shows a workaround which works by manually adding CMakeLists.txt, CMakeLists_template.txt, and STM32F407VGTx_FLASH.ld to the project as premade files. Once included, a build configuration can be made and everything seems to run smoothly with this setup so far.

## How this project was created

1. Create a new embedded intellij project
2. Open the newly created <project name>.ioc file with CubeMX and generate code using "SW4STM32" as the toolchain/IDE
3. Copy-paste premade [CMakeLists.txt](https://github.com/MatthewWeisCaps/cubeMX-CLion-starter/blob/master/CMakeLists.txt), [CMakeLists_template.txt](https://github.com/MatthewWeisCaps/cubeMX-CLion-starter/blob/master/CMakeLists_template.txt), and [STM32F407VGTx_FLASH.ld](https://github.com/MatthewWeisCaps/cubeMX-CLion-starter/blob/master/STM32F407VGTx_FLASH.ld) into the project. All 3 files are included in this repo.
4. Let intellij generate cmake-build-debug from CMakeLists.txt (this will create <project name>.elf)
5. Create an embedded run configuration targeting "<project name>.elf" with the board config file "board/stm32f429disc1.cfg" (not the "discovery" .cfg). *(Go to Run -> Edit Configurations -> Add New Configuration -> OpenOCD Download & Run. Set both the Target and Executable to said ".elf" file. Set Board config file to said ".cfg" file.)*
6. The project should now be runnable.
