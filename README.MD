# QP/C++ ESP32

Arduino library to use QP/C++ with the ESP32 and the Arduino SDK. 
Arduino port based on the [port](https://github.com/QuantumLeaps/qpc/tree/master/ports/esp-idf) from QP/C. Current development of the port is done here https://github.com/vChavezB/qpcpp.



## Changes from QP/C

 - Refactored macros and functions to C++
 - Task creation uses `xTaskCreatePinnedToCore` instead of `xTaskCreateStaticPinnedToCore`. 
     I made this change since I  am working with the Arduino SDK. The Arduino SDK uses a precompiled version of the ESP32 FreeRTOS, which does not include  `xTaskCreateStaticPinnedToCore` . I am not sure what is the downside of not using a preallocated region for stack in terms of the QP framework, but so far the port works fine.
- m_thread is of type `void *`, so this means that its usage in `qf_port.cpp` was lightly changed. 


## How to test

Open any of the examples and upload to an ESP32. 

### QPSY

QSPY can be activated by defining `QS_ON`in `bsp.cpp` of both examples.

```bash
qspy -c YOUR_SERIAL_PORT -b 115200
```

### QView

DPP example can be tested with [QView™](https://www.state-machine.com/qtools/qview.html) example located in `examples/dpp_bsp-esp32/qview`. There are two bat scripts (Windows) which can run the QView scripts.


Note: QSpy must be running before using QView.




