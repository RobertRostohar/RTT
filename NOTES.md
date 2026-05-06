# SEGGER RTT Pack Notes

## RTT Configuration

- `SEGGER_RTT_Conf.h` should contain only user-specific configuration.

## Pack description (.pdsc)

- `<releases>`: not an actual release on github (no `<url>`).
- pack version 8.56.1: based on latest GitHub commit V8.56a (GitHub: latest tag is V7.54, no releases)
- single component: SEGGER:RTT
    - component version 8.56.1: based on source code comments V8.56a
    - config file version 8.56.1 (same as component version)
- [./Syscalls](./Syscalls): not included in the pack
    - Contains STDIO retargeting for GCC/IAR/ARM/SES (limited to STDIO, no file system support).
    - Better alternative is to use [CMSIS-Compiler](https://www.keil.arm.com/packs/cmsis-compiler-arm/overview/) which includes more comprehensive retargeting support. [CMSIS-Compiler](https://github.com/ARM-software/CMSIS-Compiler) repository, branch [rtt](https://github.com/ARM-software/CMSIS-Compiler/tree/rtt) already contains retargeting for SEGGER RTT.
- [./Examples](./Examples): not included in the pack
    - Contains simple examples as a single C modules demonstrating basic RTT usage.
        - Main_RTT_InputEchoApp.c: Simple application that echoes user input back to the terminal using RTT.
        - Main_RTT_MenuApp.c: Sample application to demonstrate RTT menu functionality.
        - Main_RTT_PrintfTest.c: Application to test RTT printf functionality (not a meaningful user example).
        - Main_RTT_SpeedTestApp.c: Application to test RTT speed (depends on embOS and BSP).
    - Suggestion: create a simple [CMSIS-Pack Reference Application](https://open-cmsis-pack.github.io/cmsis-toolbox/ReferenceApplications/) which demonstrates basic RTT usage.
