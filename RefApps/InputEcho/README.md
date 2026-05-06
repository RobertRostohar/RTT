# InputEcho project

The **InputEcho** project is a simple RTT example.

It is compliant to the Common Microcontroller Software Interface Standard (CMSIS).

## Operation

- At start:
    - outputs "SEGGER Real-Time-Terminal Sample" via RTT channel 0.
    - reads input from RTT channel 0 and echoes it back.

## Debug setup

### CMSIS-Toolbox with pyOCD

Add the following to the `solution:target-types:target-set:debugger` node of the `.csolution.yml` file:

```yml
  rtt:
    - channel:
        - number: 0
          mode: stdio
  telnet:
    - mode: console
```
