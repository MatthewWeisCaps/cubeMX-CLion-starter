# FreeRTOS CLion Template

Contains a basic BlinkingLED CLion project for the STM32F407VG MCU

## How this project was created

1. Create a new embedded intellij project
2. Open the newly created <project name>.ioc file with CubeMX and generate code using "SW4STM32" as the toolchain/IDE
3. Copy-paste CMakeLists.txt, CMakeLists_template.txt, and STM32F407VGTx_FLASH.ld from [santoslab/embedded-examples](https://github.com/santoslab/embedded-examples/blob/5de9a4d43cdfa84c3104ee193f5670c86b219ca2/stm32-examples/BuildingController_slang/building_control/src/c/ext/ext.c)
4. Remove any references to Sireum or the project's directories from CMakeLists.txt and CMakeLists_template.txt
5. Let intellij generate cmake-build-debug from CMakeLists.txt (this will create <project name>.elf)
6. Create an embedded run configuration targeting "<project name>.elf" with the board config file "board/stm32f429disc1.cfg" (not the "discovery" .cfg)
7. The project should now be runnable.
