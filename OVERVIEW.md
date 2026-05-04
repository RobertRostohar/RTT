# SEGGER RTT

SEGGER Real-Time Transfer (RTT) is a high-performance communication mechanism for embedded systems that enables real-time data exchange between a target device and a host debugger without requiring additional hardware interfaces such as UART.

RTT is designed for debugging, logging, tracing, and interactive I/O, providing significantly higher throughput than UART communication or Semihosting. RTT uses a RAM-based communication mechanism where the target application writes data into memory buffers that are accessed by the debug probe. This approach enables:

- High-speed, low-latency communication with minimal intrusion into real-time execution.
- No requirement for dedicated I/O pins or peripherals as the debug port is used as communication interface.
- Bidirectional communication between host and target.

RTT operates through a control block and ring buffers located in target memory, allowing the debugger to continuously read and write data without halting the CPU.

## CMSIS-Pack

This CMSIS-Pack enables easy integration of RTT into CMSIS-based projects and toolchains and provides:

- Core RTT implementation (SEGGER_RTT.c, SEGGER_RTT.h) and configuration file.
- Optional printf retargeting support. (ToDo: how to use it)
- Reference application that exemplifies usage. (ToDo)

To use RTT in a *csolution project* add `pack: SEGGER::RTT` and `component: SEGGER:RTT`. The [RTE directory](https://open-cmsis-pack.github.io/cmsis-toolbox/build-overview/#rte-directory-structure) contains the related `SEGGER_RTT_Conf.h` for additional settings.

## Tool Support

RTT is tightly integrated with SEGGER debug probes and tools for example RTT Viewer (terminal interface), Ozone debugger, or SystemView (runtime analysis).

RTT is also supported by pyOCD and the CMSIS-Debugger VSCode extension.  Refer to the [CMSIS-Toolbox user's guide pyOCD Debugger - RTT](https://open-cmsis-pack.github.io/cmsis-toolbox/pyOCD-Debugger/#rtt) for more information.

## Links

- [Documentation](https://www.segger.com/products/debug-probes/j-link/technology/about-real-time-transfer/)
- Issues (ToDo: Segger)
- [Arm Examples](https://github.com/search?q=topic%3Artt+org%3AArm-Examples+fork%3Atrue&type=repositories) that use RTT.
